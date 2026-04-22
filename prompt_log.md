# DATA305: Final Capstone Project
GetLit -- Personalized Digital Literacy Curriculum Generator
I am building an agentic AI system that takes in a student's current digital literacy level and personal interests, then generates a customized, interactive digital literacy learning program that is tailored to their profile and literacy needs. The goal of my tool is to address the current lack of personalization in digital learning. Because curricula are often written for a prototyped generic student, advanced learners can easily become bored and struggling learners can become lost. By adapting to the student’s realistic needs and abilities, this tool could help both the advanced student and the struggling one, as well as those that fall somewhere in between. 

---
## Entry 1: Pre-steps 
Before writing any prompts, I sketched out the three data structures the pipeline will use to pass information between stages: a student profile (Stage 1 output), a skill matrix (Stage 2 output), and a lesson object (Stage 3 output). I wanted to know what shape each prompt must produce, so that writing the actual prompts will be easier later down the line and the outputs will be consistent. I made "interest_hook" its own separate field in the lesson object instead of folding it into the summary so that the Stage 4 evaluator can score personalization on its own and doesn't have to infer it from the lesson description.

---
## Entry 2: Stage #1 
The first prompt I wrote was the profile prompt which is the first thing the system will use to gain an initial understanding of the student and their needs, interests, etc. It will do this by asking them questions about themselves (i.e. name, age, grade, interests, etc.) and then use this information to build a profile that the rest of the system can use. This is my first iteration of the profile prompt:

      """
      You are a digital literacy coach. Your must learn about a student 
      so you can build them a learning program.
      
      Ask the student the following questions:
      1. What is your name and how old are you?
      2. What grade are you in?
      3. What are your top 2-3 interests or hobbies?
      4. How comfortable are you with technology? (beginner, intermediate, or advanced)
      
      Once you have all five answers, return ONLY a JSON object in this exact format:
      {
          "name": "",
          "age": 0,
          "grade": "",
          "interests": [],
          "self_reported_comfort": "",
      }
      """      
      Resulting Output: "Hello! I'm ready to help you build a digital literacy curriculum. Let's get started!"
---
## Entry 3: Stage #1
I iterated the profile prompt slightly to make it more conversational and natural than the initial version, which was slightly more rigid and place enough of a focus on actually getting to know the student. I ideally want my learning tool to feel like a human tutor but have the improved efficiency and accesibility of a digital assistant. Some of the biggest changes I made were adding descriptive adjectives that tell the AI how it should interact with/approach the student -- i.e. "friendly", "relaxed", "warm", "encouraging". I also specified that it's okay for the AI to make remarks or ask follow-ups before continuing, to increase the natural feel of the conversation. The revised prompt (profile_prompt) can be seen in my final code. Below is the output this revised prompt gave me: 

Resulting Output: 
      "Hey there! So glad you're here. I'm excited to just chat a bit and get to know you better. Think of me as your friendly guide in the digital world, and we're just having a relaxed first chat.

      To kick things off, what's your name, and what grade are you in?"
---
## Entry 4: Stage #1
Because I made these changes to the profile prompt, I had to go back to the set-up code and edit it accordingly. I changed student_profile, skill_matrix, and lesson from this: 
      
      student_profile = {
          "name": "",
          "age": 0,
          "grade": "",
          "interests": [],
          "self_reported_comfort": "",  # "beginner", "intermediate", "advanced"
          "goals": ""
      }
      
      skill_matrix = {
          "online_safety": 0,        # score 1-5
          "media_literacy": 0,       # score 1-5
          "responsible_ai_use": 0,   # score 1-5
          "file_and_device_management": 0  # score 1-5
      }
      
      lesson = {
          "title": "",
          "learning_objective": "",
          "summary": "",
          "interest_hook": "",  # personalized to student's interests
          "activity": "",
          "estimated_duration": ""
      }

      To what it currently is (see full code). 
---
## Entry 5: Stage #1
While I was still in the editing stages of my pipeline, I used a placeholder chunk of code to simulate the output the model would ideally produce for a hypothetical student that was using the curriculum generator. I placed it directly below my '# STAGE 1: Getting to know the student chunk'. This is what the placeholder code looked like:

      # STAGE 1: Simulated output (placeholder until conversation loop is built)
      # Replace this with extract_json(response.text) once Stage 1 produces a full profile

      student_profile = {
          "name": "Jordan",
          "grade": "7th",
          "interests": ["gaming", "drawing", "YouTube"],
          "self_reported_comfort": "I usually just Google it or ask my older sister",
          "inferred_comfort": "beginner",
          "goals": "learn how to make and edit my own YouTube videos"
      }
      
      print(json.dumps(student_profile, indent=2))
---
## Entry 6: Stage #2
My second prompt is the quiz prompt which will build a brief quiz specifically tailored to each student's needs, age, and background. I chose four areas of digital literacy that I wanted the AI to assess the student's knowledge on. These included online safety, media literacy, responsible AI use, and file management. The student's profile is used at the input for this stage, and a skill matrix that that scores them in the four areas is the output. This was is the first version of my prompt:

      """
      You are a digital literacy assessment tool. Based on the student profile below,
      generate 6 multiple choice questions to assess their actual digital literacy level.
      
      Student profile:
      {json.dumps(student_profile, indent=2)}
      
      Rules:
      - Make questions age-appropriate for this specific student
      - Cover all four areas: online safety, media literacy, responsible AI use,
        and file/device management (at least 1 question per area)
      - Where possible, connect question scenarios to the student's interests
      
      Return ONLY a JSON object in this exact format, with no extra text:
      {{
          "questions": [
              {{
                  "id": "Q1",
                  "area": "",
                  "question": "",
                  "options": ["A. ", "B. ", "C. ", "D. "],
                  "correct_answer": ""
              }}
          ]
      }}
      """
      
Resulting Output:

      {
        "questions": [
          {
            "id": "Q1",
            "area": "online safety",
            "question": "While playing your favorite online multiplayer game, another player sends you a chat message offering free in-game currency if you just give them your username and password. What is the safest thing to do?",
            "options": [
              "A. Give them your password but change it right after you get the currency.",
              "B. Ignore the message, block the user, and never share your password.",
              "C. Give them a fake password to see what happens.",
              "D. Ask your older sister if it seems like a good deal before sharing."
            ],
            "correct_answer": "B. Ignore the message, block the user, and never share your password."
          },
          {
            "id": "Q2",
            "area": "media literacy",
            "question": "You are watching YouTube tutorials to learn about video editing, and you see a recommended video with a thumbnail that says 'SECRET TRICK: Get 1 Million Subscribers Overnight!' How should you treat this video?",
            "options": [
              "A. Believe it completely because the video has a lot of views.",
              "B. Try the trick immediately so you can grow your new channel.",
              "C. Understand it is likely 'clickbait' designed to get views, rather than a guaranteed fact.",
              "D. Share it with all your friends so they can get famous too."
            ],
            "correct_answer": "C. Understand it is likely 'clickbait' designed to get views, rather than a guaranteed fact."
          },
          {
            "id": "Q3",
            "area": "responsible AI use",
            "question": "You want to create a cool profile picture for your new YouTube channel. You decide to use an AI image generator to help. What is the most responsible way to use this tool?",
            "options": [
              "A. Generate an image and tell your viewers you drew it all by yourself.",
              "B. Type in a prompt, download the image, and claim full legal copyright over the artwork.",
              "C. Ask the AI to exactly copy a specific digital artist's drawing so you can use it without paying them.",
              "D. Use the AI to brainstorm ideas and color palettes, then use your drawing skills to create your own unique logo."
            ],
            "correct_answer": "D. Use the AI to brainstorm ideas and color palettes, then use your drawing skills to create your own unique logo."
          },
          {
            "id": "Q4",
            "area": "file/device management",
            "question": "You are starting to record your gaming sessions to edit into YouTube videos, but your computer screen keeps popping up with a 'Storage Space Running Out' warning. What is the best way to manage your files?",
            "options": [
              "A. Delete random folders in your operating system to make room for your videos.",
              "B. Keep all your raw video clips on your desktop so they are easy to find.",
              "C. Move your older, finished videos to an external hard drive or cloud storage to free up space.",
              "D. Search Google for a website where you can 'download more computer storage'."
            ],
            "correct_answer": "C. Move your older, finished videos to an external hard drive or cloud storage to free up space."
          },
          {
            "id": "Q5",
            "area": "file/device management",
            "question": "You have game clips, background music, and digital drawings saved all over your computer. When you open your video editor, it is taking you a long time to find the files you need. What should you do?",
            "options": [
              "A. Create a main folder for your YouTube channel with subfolders like 'Video Clips', 'Audio', and 'Images'.",
              "B. Just use the search bar every time you need a file, even if it takes longer.",
              "C. Rename every single file to 'YouTubeVideo' so they all match.",
              "D. Ask your sister to search through your computer and find the files for you every time you edit."
            ],
            "correct_answer": "A. Create a main folder for your YouTube channel with subfolders like 'Video Clips', 'Audio', and 'Images'."
          },
          {
            "id": "Q6",
            "area": "online safety",
            "question": "You run into a technical problem while trying to record your game, so you 'Google it' to find a fix. The first search result is an unknown blog telling you to download a special '.exe' program to fix the glitch. What should you do?",
            "options": [
              "A. Download and run the file immediately since it was the first Google search result.",
              "B. Check the official game website or trusted forums first instead of downloading unknown files.",
              "C. Send the link to your older sister and ask her to download it on her computer first to test it.",
              "D. Turn off your computer's antivirus software so the file can download faster."
            ],
            "correct_answer": "B. Check the official game website or trusted forums first instead of downloading unknown files."
          }
        ]
      }

---
## Entry 7: Stage #2
I decided to revise my quiz prompt so it was tighter and gave the AI less freedom to give the student non-sensical question distributions (i.e. three questions on file management and one question on the other areas), or ask too simple of questions. I also wrote out the format I wanted all six questions in so I could be sure the model would give the student and not just one. Finally, I specified that I wanted the model to use inferred_comfort from the student's profile (and not just make the questions age-appropriate) to inform question difficulty. I changed the prompt from what it was in Entry 6 to what it currently is (see full code).

