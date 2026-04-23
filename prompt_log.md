# DATA305: Final Capstone Project
## GetLit -- Personalized Digital Literacy Curriculum Generator
I am building an agentic AI system that takes in a student's current digital literacy level and personal interests, then generates a customized, interactive digital literacy learning program that is tailored to their profile and literacy needs. The goal of my tool is to address the current lack of personalization in digital learning. Because curricula are often written for a prototyped generic student, advanced learners can easily become bored and struggling learners can become lost. By adapting to the student’s realistic needs and abilities, this tool could help both the advanced student and the struggling one, as well as those that fall somewhere in between. 

---
## Entry 1: Pre-Steps 
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

Resulting Output: 
      
      "Hello! I'm ready to help you build a digital literacy curriculum. Let's get started!"
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
I decided to revise my quiz prompt so it was tighter and gave the AI less freedom to give the student non-sensical question distributions (i.e. three questions on file management and one question on the other areas), or ask too simple of questions. I also wrote out the format I wanted all six questions in so I could be sure the model would give the student and not just one. Finally, I specified that I wanted the model to use inferred_comfort from the student's profile (and not just make the questions age-appropriate) to inform question difficulty. I changed the prompt from what it was in Entry 6 to what it currently is (see quiz_prompt in my full code). Below is the output this revised prompt gave me.

Resulting Output:

      {
        "questions": [
          {
            "id": "Q1",
            "area": "online_safety",
            "question": "You are playing your favorite multiplayer game, and another player sends a message saying, 'Click this link and log in to get free legendary skins!' What is the safest thing to do?",
            "options": [
              "A. Ignore the message and do not click the link, as it is likely trying to steal your account password.",
              "B. Click the link to see if it is real, but only enter a fake password to test it out.",
              "C. Ask the player how they found the link before deciding to click on it.",
              "D. Log in quickly and claim the skins before the link expires."
            ],
            "correct_answer": "A"
          },
          {
            "id": "Q2",
            "area": "online_safety",
            "question": "You are creating a new YouTube channel to share your digital drawings. When setting up your public 'About Me' page, which piece of information is safe to include?",
            "options": [
              "A. The name of the middle school you currently attend.",
              "B. Your personal cell phone number so fans can text you.",
              "C. Your first name and your favorite styles of drawing.",
              "D. Your full name and the city where you live."
            ],
            "correct_answer": "C"
          },
          {
            "id": "Q3",
            "area": "media_literacy",
            "question": "You are watching a popular YouTuber play a newly released video game. They keep talking about how amazing the game is and mention a link in the description to buy it. How can you best tell if they were paid to say good things about the game?",
            "options": [
              "A. Read the comments to see if other viewers liked the game too.",
              "B. Look for a 'Sponsored' or 'Paid Promotion' label on the video or in the description.",
              "C. Check how many subscribers the YouTuber has; if they have over a million, they are always paid.",
              "D. Watch the whole video to see if they say the word 'advertisement' at the very end."
            ],
            "correct_answer": "B"
          },
          {
            "id": "Q4",
            "area": "media_literacy",
            "question": "When you type a question into Google, what is the best way to decide which link to click first?",
            "options": [
              "A. Always click the very first link at the top, even if it has the word 'Ad' next to it.",
              "B. Choose the link that has the longest title, because it will usually have the most information.",
              "C. Only click on links that come from a social media website or a gaming forum.",
              "D. Look at the web address and a quick summary to see if the site looks trustworthy and relevant."
            ],
            "correct_answer": "D"
          },
          {
            "id": "Q5",
            "area": "responsible_ai_use",
            "question": "You use an AI image generator to make a cool background for one of your YouTube videos. What is the most responsible way to handle this?",
            "options": [
              "A. Tell your viewers that you drew the background completely by yourself to get more likes.",
              "B. Mention in the video description that you used an AI tool to help create the background.",
              "C. Keep it a secret, because using AI means the video might get automatically deleted by YouTube.",
              "D. Claim the AI's artwork as your own official drawing since you are the one who typed in the prompt."
            ],
            "correct_answer": "B"
          },
          {
            "id": "Q6",
            "area": "file_device_management",
            "question": "You are starting to edit your first YouTube video and have downloaded a lot of different gameplay clips and background songs. What is the best way to keep these files organized on your computer?",
            "options": [
              "A. Save everything directly to your desktop so you can find it as soon as you turn on the computer.",
              "B. Leave the files in your 'Downloads' folder and try to remember the dates you downloaded them.",
              "C. Create a specific folder for the video project and save all related clips and audio inside it with clear names.",
              "D. Put all the files into the computer's Trash bin to keep them out of the way until you are ready to edit."
            ],
            "correct_answer": "C"
          }
        ]
      }

---
## Entry 8: Stage #2.5
When designing the intermediary step (between stages 2 and 3) that scores the student's quiz and populates the skill matrix, I initially implemented LLM-based scoring that used a scoring prompt to assess the answers. While this was consistent and cohesive with the rest of my pipeline -- in the fact that it used prompting -- it didn't really fit the nature of the task. I needed the scorer to reliably count correct answers per area and divide, which is a counting task (not a reasoning task) that it could easily mess up. Also, because models are probabalistic, it could produce different scores on different runs -- even in cases where the answer would/should be the same. Because LLM-based grading is ultimately unreliable, I decided to switch to deterministic scoring, so all quizzes are scored consistently and there's no room for ambiguity. The code I used to create a deterministic-based scorer can be seen in my final pipeline. Below is the original LLM-based version I had, and the output that resulted from it: 

      student_answers = {
          "Q1": "A",
          "Q2": "B",
          "Q3": "C",
          "Q4": "A",
          "Q5": "B",
          "Q6": "D"
      }
      
      scoring_prompt = f"""
      You are scoring a digital literacy quiz. Below are the questions, the student's 
      answers, and the correct answers embedded in the question data.
      
      Quiz data:
      {json.dumps(quiz_data, indent=2)}
      
      Student answers:
      {json.dumps(student_answers, indent=2)}
      
      Score the quiz and produce a skill matrix. For each of the four areas, give:
      - A score from 1 (very low) to 5 (very high) based on how many questions 
        in that area the student got right
      - A one-sentence note on what the score suggests
      
      Then give an overall level: beginner, intermediate, or advanced.
      
      Return ONLY a JSON object in this exact format:
      {{
          "skill_matrix": {{
              "online_safety":        {{"score": 0, "note": ""}},
              "media_literacy":       {{"score": 0, "note": ""}},
              "responsible_ai_use":   {{"score": 0, "note": ""}},
              "file_device_management": {{"score": 0, "note": ""}}
          }},
          "overall_level": "",
          "summary": ""
      }}
      """
      
      scoring_response = client.models.generate_content(
          model='gemini-2.5-flash',
          contents=scoring_prompt
      )
      skill_matrix = extract_json(scoring_response.text)
      print(json.dumps(skill_matrix, indent=2))

Resulting Output:

      {
        "skill_matrix": {
          "online_safety": {
            "score": 5,
            "note": "This score suggests a very high understanding of online safety practices."
          },
          "media_literacy": {
            "score": 3,
            "note": "This score suggests some understanding of media literacy, with room for improvement."
          },
          "responsible_ai_use": {
            "score": 1,
            "note": "This score suggests a very low understanding of responsible AI use."
          },
          "file_device_management": {
            "score": 5,
            "note": "This score suggests a very high understanding of file and device management."
          }
        },
        "overall_level": "intermediate",
        "summary": "The student demonstrated strong skills in online safety and file/device management, and has some understanding of media literacy. However, there is significant room for improvement in responsible AI use."
      }

## Entry 9: Stage #2.5
While I did decide against using the LLM in the actual scorer and instead used deterministic scoring, I decided to reintegrate the LLM to summarize the student's score. I did this by creating a prompt called summary_prompt that interprets the skill matrix and explains its assessment of the student's current literacy level in kind, but straight-forward language, focusing on their current skills and where they can improve from there. This was more of an interpretation-based task, which is why I felt it made sense to use an LLM. I initially wrote a prompt that was simple and less focused on appeasing the student: 

      """
      You are summarizing the student's digital literacy quiz results in several sentences.
      Don't reference their letter or numerical grades. Give them an honest assessment of their current literacy level.
      """

Resulting Output:

      Overall level: beginner
      
      Summary: Jordan's current digital literacy is foundational at best, indicating a significant lack of essential skills for navigating the digital landscape safely and effectively. He demonstrated critical weaknesses in online safety, responsible AI use, and even fundamental file and device management, with these areas requiring substantial immediate attention. While he has a partial grasp of media literacy, there are still notable gaps that could leave him susceptible to misinformation. His ambition to create online content will be severely hampered until these core digital competencies are thoroughly developed.

I appreciated the honesty of this output, but didn't like that the AI referred to the student in third person, as the AI should be talking directly to the student they're teaching. I also felt the AI was a bit too brutal in its feedback. To fix these weak areas, I revised my summary_prompt to what it currently is (see full code) and received the following output as a result. 

Resulting Output:

      Overall level: beginner
      
      Summary: Hi Jordan! It's clear you're already super comfortable navigating the digital world for gaming and YouTube, which is a fantastic starting point for your creative goals! Your quiz shows you have a lot of exciting room to grow, especially when it comes to understanding how to stay safe online and managing your digital files. A great first step will be diving into online safety, which will build a strong foundation for everything you want to do, including making your own videos.

---
## Entry 10: Stage #3
When I initially wrote my lesson_generation_prompt, I only had AI generate a lesson for the student's weakest area. As I experimented with this prompt, I realized I wasn't fully taking advantage of the AI's ability to generate a full-coverage curriculum, and should revise the prompt so it generates a lesson for the weakest skill first, but then continues on to generate a lesson for the others after. Deliberately sorting students' area scores allows the model to address the student's specific learning needs in the appropriate order, without fully omitting any area from the curriculum. I think it's good that I also didn't go to the other extreme of equally covering all areas, as this could be inefficient if a student has a good understanding of some of the content/areas and not need deeply comprehensive lessons on those. Below is my original code:

      # STAGE 3: Find weakest area and generate one lesson
       
      weakest_area = min(skill_matrix, key=lambda a: skill_matrix[a]["score"])
       
      lesson_prompt = f"""
      You are designing one personalized digital literacy lesson for a specific student. Make it genuinely
      engaging for them — not a generic template.
       
      Student profile: {json.dumps(student_profile, indent=2)}
      Skill matrix: {json.dumps(skill_matrix, indent=2)}
      Overall level: {overall_level}
      Target area: "{weakest_area}" — {skill_matrix[weakest_area]["note"]}
       
      Requirements:
      - Calibrate difficulty to "{overall_level}"
      - Open with a hook tied to their interests: {json.dumps(student_profile["interests"])}
      - Activity must be concrete and completable in one sitting (not "research and discuss")
       
      Return ONLY a JSON object, no extra text or markdown:
      {{
          "title": "",
          "area": "{weakest_area}",
          "learning_objective": "Students will be able to...",
          "summary": "",
          "interest_hook": "",
          "activity": "",
          "estimated_duration": ""
      }}
      """
       
      lesson_response = client.models.generate_content(
          model='gemini-2.5-flash',
          contents=lesson_prompt
      )
      lesson = extract_json(lesson_response.text)

      # STAGE 3: Readable printout
       
      AREA_LABELS = {
          "online_safety":          "Online Safety",
          "media_literacy":         "Media Literacy",
          "responsible_ai_use":     "Responsible AI Use",
          "file_device_management": "File & Device Management"
      }
       
      label = AREA_LABELS.get(lesson["area"], lesson["area"])
       
      print("=" * 60)
      print(f"  YOUR FIRST LESSON")
      print(f"  For: {student_profile['name']}  |  Level: {overall_level.capitalize()}")
      print("=" * 60)
      print(f"\n  {scored_results['summary']}\n")
      print(f"{'─' * 60}")
      print(f"  {lesson['title']}")
      print(f"  Area: {label}  |  Time: {lesson['estimated_duration']}")
      print(f"\n  What you'll learn:")
      print(f"    {lesson['learning_objective']}")
      print(f"\n  Why this one first:")
      print(f"    {lesson['summary']}")
      print(f"\n  How we're starting:")
      print(f"    {lesson['interest_hook']}")
      print(f"\n  What you'll do:")
      for line in lesson["activity"].strip().split("\n"):
          print(f"    {line}")
      print(f"\n{'=' * 60}")

This was the resulting output/lesson plan:

      ============================================================
        YOUR FIRST LESSON
        For: Jordan  |  Level: Beginner
      ============================================================
      
        Hi Jordan! It's clear you're already super comfortable navigating the digital world for gaming and YouTube, which is a fantastic starting point for your creative goals! Your quiz shows you have a lot of exciting room to grow, especially when it comes to understanding how to stay safe online and managing your digital files. A great first step will be diving into online safety, which will build a strong foundation for everything you want to do, including making your own videos.
      
      ────────────────────────────────────────────────────────────
        Your Ultimate Online Shield: Building a Safe Creator Persona!
        Area: Online Safety  |  Time: 45 minutes
      
        What you'll learn:
          Jordan will be able to identify personal information that should not be shared publicly online and explain why protecting this information is crucial for online safety, especially as a content creator or gamer.
      
        Why this one first:
          This lesson will empower Jordan to understand what kind of personal information is risky to share online. Through a creative activity, Jordan will design a safe online persona for their YouTube and gaming adventures, learning to distinguish between what's okay to share and what needs to be kept private to stay safe.
      
        How we're starting:
          Hey Jordan, imagine you're about to launch your dream YouTube channel where you share your amazing drawings and epic gaming moments! Or maybe you're designing a new character for your favorite game. You'd want to protect your creations, your ideas, and yourself from anything that could mess up your online world, right? Well, just like a superhero needs a secret identity and a fortress to protect their HQ, you need a 'digital shield' to keep your online adventures awesome and safe! Let's design your ultimate safe online persona.
      
        What you'll do:
          ### **Activity: 'My Safe Creator Profile' Design Challenge**
          
          **Materials:** Paper, drawing supplies (pencils, markers, colored pencils), or a digital drawing app/tablet.
          
          **Part 1: Design Your 'Online Creator Avatar' (15 minutes)**
          Jordan, your first task is to draw or design an awesome avatar/persona that represents you online – for your YouTube channel, gaming profile, or wherever you create and play. Give your avatar a cool, creative username (NOT your real name!) that fits your interests. Think about what this avatar looks like, what they love to do (game, draw, make videos!). This is your public face online, so make it awesome, but remember it's not *you* you, it's *Online-You*.
          
          **Part 2: The 'Safe Profile' Checklist (20 minutes)**
          Once your avatar is complete, it's time to build its 'Safe Creator Profile Card'. Imagine this is the 'About Me' section of your YouTube channel or your gaming profile. We're going to go through a list of information, and for each item, you'll decide if your *avatar* should share it publicly on their profile. Draw a checkmark for 'YES, safe to share' or an 'X' for 'NO, keep private'.
          
          **Information List:**
          1.  **Your Avatar's Creative Username** (e.g., 'PixelArtPro', 'GameMasterJ')
          2.  **Your Real Full Name**
          3.  **Your Exact Age (e.g., '12 years old')**
          4.  **Your General Age Range (e.g., 'Teen')**
          5.  **The Name of Your School or Neighborhood**
          6.  **The City/State Where You Live**
          7.  **A Photo of Your Face**
          8.  **A Photo of Your Artwork/Game Screenshots**
          9.  **Your Personal Email Address**
          10. **Your Favorite Gaming Platform/Game Username**
          11. **Links to Your Public YouTube Channel/Art Portfolio**
          12. **A Photo Showing Your Bedroom or House Background**
          
          **Part 3: Shield Up! (10 minutes)**
          After you've marked each item, we'll talk through your choices. Why did you decide certain things were safe for your avatar to share, and others were not? We'll discuss the potential risks of sharing too much personal information online – like strangers trying to find you, steal your ideas, or pretend to be you. We'll reinforce that your online persona is a fantastic way to express yourself without giving away your real-world identity, keeping you, your creations, and your fun safe!

---
 
