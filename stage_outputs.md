# Stage Outputs

- In Part I, I have included the outputs I received when I used the tool to generate a curriculum for my digitial literacy needs. 
- In Part II, I have included the outputs from the evaluation pipeline, when I ran Jordan, Sarah, and Marcus through it.

# Part I
## Stage #1 (My conversation with the AI)

    === GetLit: Digital Literacy Coach ===
    
    Coach: Hey there! I'm so glad we get to chat today. I'm your digital literacy coach—think of me as a guide to help you get the most out of the tech you use every day, minus all the boring lectures. 
    
    To start us off and get to know you a bit, what's your name and what grade are you in?
    
    You: Grace
    Coach: Nice to meet you, Grace! What grade are you in this year?
    
    You: I'm a junior in college
    Coach: A junior in college! That is a super exciting (and usually pretty busy!) time. 
    
    When you're not buried in coursework or running to class, what do you like to do for fun? Any hobbies or interests you're really into right now?
    
    You: I really like hiking and cooking
    Coach: Hiking and cooking sound like the perfect combo to decompress from classes! There's nothing quite like a good homemade meal after a long day on the trails. 
    
    Since we're going to be talking about tech, I'd love to know a bit about your relationship with it. When you run into a tech problem—like your laptop freezing up or an app acting weird—what is your usual go-to move?
    
    You: I do a hard reset
    Coach: The classic "turn it off and back on again" method! Honestly, it's a classic for a reason—it fixes things 90% of the time. 
    
    Thinking about your daily routine as a college student, is there something specific you wish you could do better with technology? Maybe a skill you want to learn, or just a way to make managing your coursework a little easier?
    
    You: I want to get better at coding
    
    --- Profile complete ---
    {
      "name": "Grace",
      "grade": "Junior in college",
      "interests": [
        "hiking",
        "cooking"
      ],
      "self_reported_comfort": "Does a hard reset when facing tech problems",
      "inferred_comfort": "Comfortable with basic troubleshooting",
      "goals": "Get better at coding"
    }

## Stage #2 (Questions AI generated for me)

      {
        "questions": [
          {
            "id": "Q1",
            "area": "online_safety",
            "question": "Grace finds an online store selling high-end hiking gear at a massive 80% discount, but the URL looks slightly unfamiliar. What is the most reliable way to verify the site is safe before entering her payment information?",
            "options": [
              "A. Test the site by entering fake credit card details first to see if it processes an error.",
              "B. Check if the URL starts with HTTPS and search for independent reviews of the specific domain name.",
              "C. Look for a padlock icon anywhere on the webpage and ensure they accept major credit cards.",
              "D. Rely on her browser's built-in ad blocker to automatically block the site if it is malicious."
            ],
            "correct_answer": "B"
          },
          {
            "id": "Q2",
            "area": "online_safety",
            "question": "While studying at a coffee shop on their public Wi-Fi, Grace tries to log into her college portal but gets a browser warning that her connection is 'not private.' What is the safest immediate action?",
            "options": [
              "A. Ignore the warning if the website URL begins with HTTPS, as the connection is already encrypted.",
              "B. Open the site in a private or incognito browsing window so her data cannot be intercepted by others.",
              "C. Disconnect from the Wi-Fi or turn on a trusted VPN before entering any passwords or personal data.",
              "D. Clear her browser's cache and cookies to force the public network to issue a new security certificate."
            ],
            "correct_answer": "C"
          },
          {
            "id": "Q3",
            "area": "media_literacy",
            "question": "Grace watches a viral video showing a 'hack' for cooking pasta in half the time using a specific brand of thin plastic wrap in the microwave. How should she evaluate if this method is actually safe to try?",
            "options": [
              "A. Read the top comments on the video to see if other users have successfully tried the hack without issues.",
              "B. Check if the video creator has a blue verified checkmark on their profile to confirm they are a legitimate chef.",
              "C. Look at the view count and like-to-dislike ratio to determine if the video is broadly trusted by the community.",
              "D. Search for verified articles from food safety organizations or culinary experts addressing this specific method."
            ],
            "correct_answer": "D"
          },
          {
            "id": "Q4",
            "area": "media_literacy",
            "question": "A news article with a sensational headline about a massive new college loan forgiveness program is being widely shared on social media. Before forwarding it to her classmates, what is the best way for Grace to verify its credibility?",
            "options": [
              "A. Use lateral reading by opening new tabs to see what established, reputable news outlets are reporting on the same topic.",
              "B. Read the 'About Us' page on the website to ensure the organization states that they are unbiased and independent.",
              "C. Check the date of the article to make sure it was published within the last 24 hours.",
              "D. Look closely at the website's design to see if it uses professional formatting and high-quality images."
            ],
            "correct_answer": "A"
          },
          {
            "id": "Q5",
            "area": "responsible_ai_use",
            "question": "Grace is using a generative AI chatbot to help her understand a difficult coding concept for a software engineering assignment. What is the most responsible way to use the AI's output?",
            "options": [
              "A. Treat the AI's code as a learning guide, review the logic to ensure she understands it, and write her own final code.",
              "B. Copy and paste the AI's code directly into her assignment, as AI-generated code is publicly available and does not require citation.",
              "C. Ask the AI to write the code in a slightly less efficient way so her professor will not suspect she used an AI tool.",
              "D. Prompt the AI to provide only the final code without explanations, so she doesn't get confused by unnecessary technical jargon."
            ],
            "correct_answer": "A"
          },
          {
            "id": "Q6",
            "area": "file_device_management",
            "question": "Grace's laptop is running extremely slowly when she tries to compile her code, and she notices her hard drive storage is almost completely full. What is the most effective first step to improve her computer's performance?",
            "options": [
              "A. Download and run a third-party registry cleaner tool to optimize the computer's background processes.",
              "B. Identify and uninstall large, unused applications, and move large media files to an external drive or cloud storage.",
              "C. Perform a hard reset on the laptop by holding down the power button for ten seconds to clear the motherboard's memory.",
              "D. Defragment her solid-state drive (SSD) to physically push all of her coding files closer together on the disk."
            ],
            "correct_answer": "B"
          }
        ]
      }

## Stage #2 (My completion of the quiz)
  
      === Quiz Time! ===
      
      Answer each question by typing A, B, C, or D.
      
      Q1: Grace finds an online store selling high-end hiking gear at a massive 80% discount, but the URL looks slightly unfamiliar. What is the most reliable way to verify the site is safe before entering her payment information?
        A. Test the site by entering fake credit card details first to see if it processes an error.
        B. Check if the URL starts with HTTPS and search for independent reviews of the specific domain name.
        C. Look for a padlock icon anywhere on the webpage and ensure they accept major credit cards.
        D. Rely on her browser's built-in ad blocker to automatically block the site if it is malicious.
      Your answer: B
      
      Q2: While studying at a coffee shop on their public Wi-Fi, Grace tries to log into her college portal but gets a browser warning that her connection is 'not private.' What is the safest immediate action?
        A. Ignore the warning if the website URL begins with HTTPS, as the connection is already encrypted.
        B. Open the site in a private or incognito browsing window so her data cannot be intercepted by others.
        C. Disconnect from the Wi-Fi or turn on a trusted VPN before entering any passwords or personal data.
        D. Clear her browser's cache and cookies to force the public network to issue a new security certificate.
      Your answer: C
      
      Q3: Grace watches a viral video showing a 'hack' for cooking pasta in half the time using a specific brand of thin plastic wrap in the microwave. How should she evaluate if this method is actually safe to try?
        A. Read the top comments on the video to see if other users have successfully tried the hack without issues.
        B. Check if the video creator has a blue verified checkmark on their profile to confirm they are a legitimate chef.
        C. Look at the view count and like-to-dislike ratio to determine if the video is broadly trusted by the community.
        D. Search for verified articles from food safety organizations or culinary experts addressing this specific method.
      Your answer: D
      
      Q4: A news article with a sensational headline about a massive new college loan forgiveness program is being widely shared on social media. Before forwarding it to her classmates, what is the best way for Grace to verify its credibility?
        A. Use lateral reading by opening new tabs to see what established, reputable news outlets are reporting on the same topic.
        B. Read the 'About Us' page on the website to ensure the organization states that they are unbiased and independent.
        C. Check the date of the article to make sure it was published within the last 24 hours.
        D. Look closely at the website's design to see if it uses professional formatting and high-quality images.
      Your answer: A
      
      Q5: Grace is using a generative AI chatbot to help her understand a difficult coding concept for a software engineering assignment. What is the most responsible way to use the AI's output?
        A. Treat the AI's code as a learning guide, review the logic to ensure she understands it, and write her own final code.
        B. Copy and paste the AI's code directly into her assignment, as AI-generated code is publicly available and does not require citation.
        C. Ask the AI to write the code in a slightly less efficient way so her professor will not suspect she used an AI tool.
        D. Prompt the AI to provide only the final code without explanations, so she doesn't get confused by unnecessary technical jargon.
      Your answer: A
      
      Q6: Grace's laptop is running extremely slowly when she tries to compile her code, and she notices her hard drive storage is almost completely full. What is the most effective first step to improve her computer's performance?
        A. Download and run a third-party registry cleaner tool to optimize the computer's background processes.
        B. Identify and uninstall large, unused applications, and move large media files to an external drive or cloud storage.
        C. Perform a hard reset on the laptop by holding down the power button for ten seconds to clear the motherboard's memory.
        D. Defragment her solid-state drive (SSD) to physically push all of her coding files closer together on the disk.
      Your answer: B
      
      Quiz complete!

## Stage #2 (Scoring of my quiz answers and building of skill matrix)

      {
        "online_safety": {
          "score": 2,
          "note": "strong \u2014 got everything right here"
        },
        "media_literacy": {
          "score": 2,
          "note": "strong \u2014 got everything right here"
        },
        "responsible_ai_use": {
          "score": 1,
          "note": "strong \u2014 got everything right here"
        },
        "file_device_management": {
          "score": 1,
          "note": "strong \u2014 got everything right here"
        }
      }
      
      Overall level: advanced
      
      Summary: Grace, your digital literacy quiz results are excellent – you've shown a strong understanding in every area, from online safety to managing your devices and using AI responsibly. This solid foundation means you're perfectly positioned to dive into your goal of getting better at coding, and exploring introductory programming concepts would be a fantastic next step.

## Stage #3 (Sorting learning areas by priority)

      Lesson priority order:
        1. responsible_ai_use (score: 1) — strong — got everything right here
        2. file_device_management (score: 1) — strong — got everything right here
        3. online_safety (score: 2) — strong — got everything right here
        4. media_literacy (score: 2) — strong — got everything right here

## Stage #3 (Generating lessons for each skill)

      ✓ Generated lesson for: responsible_ai_use
      ✓ Generated lesson for: file_device_management
      ✓ Generated lesson for: online_safety
      ✓ Generated lesson for: media_literacy
      
      Total lessons generated: 4

## Stage #3 (Storing curriculum as JSON)

      {
        "student_name": "Grace",
        "overall_level": "advanced",
        "priority_order": [
          "responsible_ai_use",
          "file_device_management",
          "online_safety",
          "media_literacy"
        ],
        "lessons": [
          {
            "title": "AI Code Auditing: Safe Trail Mapping",
            "area": "responsible_ai_use",
            "learning_objective": "Students will be able to audit AI-generated code for security vulnerabilities and hallucinated functions, demonstrating responsible use of AI tools in software development.",
            "summary": "This lesson bridges Grace's goal of improving at coding with responsible AI use. She will act as a code reviewer for an AI assistant, auditing an AI-generated Python script designed for mapping hiking trails to identify and fix security flaws and hallucinations.",
            "interest_hook": "Whether you're prepping for a multi-day hike or trying out a complex new recipe, you wouldn't blindly trust a random stranger's instructions without double-checking the map or the ingredients. The same goes for coding with AI. Since you want to get better at programming, we're going to explore how to use AI coding assistants responsibly\u2014because sometimes, AI will confidently invent 'ingredients' or suggest a 'trail' that leads straight to a security vulnerability.",
            "activity": "You will be provided with an AI-generated Python script that is supposed to calculate elevation changes for local hiking trails using a mock API. Your task is to perform a strict 'AI Audit' on the code. First, find and remove the hallucinated library the AI imported ('trail_calc_utils' - which does not exist). Second, identify the major security risk where the AI used the unsafe 'eval()' function to parse the trail data. Third, rewrite those specific lines using Python's standard, secure 'json' library and basic math operators. Submit your corrected, working script.",
            "estimated_duration": "45 minutes"
          },
          {
            "title": "Command Line Chef & Trailblazer: Automating File Organization",
            "area": "file_device_management",
            "learning_objective": "Students will be able to navigate the command line interface and write a basic shell script to automate file management tasks.",
            "summary": "This lesson bridges Grace's mastery of basic file management with her goal of learning to code. By introducing the command line interface (CLI) and basic scripting, she will learn how programmers manage and automate device operations, building troubleshooting confidence beyond a 'hard reset'.",
            "interest_hook": "When you're prepping a complex recipe or packing for a multi-day hike, organization is everything\u2014you wouldn't throw your hiking boots in the fridge! Right now, your computer's Downloads folder might look like an unpacked backpack. Since you want to get better at coding, let's skip the manual drag-and-drop. Today, you are going to write a mini-program that automatically sorts your trail maps and recipe files in milliseconds.",
            "activity": "Step 1: Open your computer's Terminal (Mac/Linux) or PowerShell (Windows). Step 2: Type 'cd Desktop' to navigate to your desktop, then 'mkdir sorting_project' to create a new folder. Move into it by typing 'cd sorting_project'. Step 3: Let's create some dummy files! Type 'touch chili_recipe.txt pancake_recipe.txt yosemite_trail.jpg'. Step 4: Open a basic text editor and write a short script to sort these. Write: 'mkdir Recipes Hikes' on line 1, 'mv *recipe* Recipes/' on line 2, and 'mv *trail* Hikes/' on line 3. Save this text file as 'sorter.sh' in your project folder. Step 5: Go back to your Terminal and execute your code by typing 'bash sorter.sh'. Open the folder on your desktop to watch how your code instantly organized your files into the correct directories!",
            "estimated_duration": "30-45 minutes"
          },
          {
            "title": "Securing the Trail: Protecting API Keys in Your Code",
            "area": "online_safety",
            "learning_objective": "Students will be able to securely store and access sensitive credentials in a coding project using environment variables and .gitignore files to prevent unauthorized access.",
            "summary": "To support your goal of getting better at coding, we are taking online safety to the developer level. You will learn how to secure sensitive data like API keys using a .env file, ensuring you never accidentally leak credentials when sharing your code.",
            "interest_hook": "Imagine you are building a custom Python app to pull real-time weather and GPS data for your next big hiking trip. If you leave your mapping API key hardcoded in your script and upload it to GitHub, malicious bots can hijack your key in seconds, racking up massive charges or locking you out of the data you need. Let's make sure your code is as secure and weather-proof as your hiking gear.",
            "activity": "Step 1: Create a new folder and make a Python file called 'trail_mapper.py'. Inside, simulate a hardcoded secret by typing `API_KEY = 'super_secret_trail_key_99'` followed by `print('Connecting with:', API_KEY)`. Step 2: Set up professional security by creating a new file named '.env'. Move your key there by typing `API_KEY=super_secret_trail_key_99` and delete the hardcoded string from your Python file. Step 3: Create a '.gitignore' file and add '.env' to it\u2014this tells version control to never upload your secrets. Step 4: Back in 'trail_mapper.py', import the 'os' and 'dotenv' modules. Use `load_dotenv()` and update your variable to `API_KEY = os.getenv('API_KEY')`. Step 5: Run 'trail_mapper.py' in your terminal. If it prints the key, you have successfully implemented a professional security standard used by software engineers to keep apps safe from hackers.",
            "estimated_duration": "30 minutes"
          },
          {
            "title": "Python for Photo Forensics: Verifying Trail Locations",
            "area": "media_literacy",
            "learning_objective": "Students will be able to write a basic Python script to extract and analyze EXIF metadata from digital images to verify the authenticity and context of online media.",
            "summary": "By combining her goal to learn coding with her interest in hiking, Grace will write a Python script to extract hidden EXIF metadata from a landscape photo, learning how digital investigators fact-check online images.",
            "interest_hook": "You know those stunning photos of 'secret' hiking trails you see online? Sometimes people fake a remote hike when they are actually just right off a busy highway. Since you want to get better at coding, let's play digital detective. We are going to use a little bit of Python to extract the hidden metadata from a hiking photo to find out exactly where and when it was actually taken.",
            "activity": "1. Open Google Colab (a browser-based Python environment, so no local setup or 'hard resets' are required if you get stuck). 2. Upload the provided 'mystery_trail.jpg' file to the workspace. 3. Write a short Python script using the 'Pillow' (PIL) library to open the image and extract its 'getexif()' data. 4. Filter the raw data to isolate the GPSInfo tag. 5. Write a small function to convert the raw GPS degrees, minutes, and seconds into standard decimal coordinates. 6. Plug those exact coordinates into Google Maps to reveal the true location of the hike, verifying if the image's online claim matches reality.",
            "estimated_duration": "45 minutes"
          }
        ]
      }

## Stage #3 (Converting JSON into readable printout)

      ================================================================
        DIGITAL LITERACY PLAN — GRACE
        Overall Level: Advanced
      ================================================================
      
        Grace, your digital literacy quiz results are excellent – you've shown a strong understanding in every area, from online safety to managing your devices and using AI responsibly. This solid foundation means you're perfectly positioned to dive into your goal of getting better at coding, and exploring introductory programming concepts would be a fantastic next step.
      
        LESSON 1 OF 4  ·  Responsible AI Use
        AI Code Auditing: Safe Trail Mapping
        45 minutes
      
        Goal
        Students will be able to audit AI-generated code for security vulnerabilities and hallucinated functions, demonstrating responsible use of AI tools in software development.
      
        Overview
        This lesson bridges Grace's goal of improving at coding with responsible AI use. She will act as a code reviewer for an AI assistant, auditing an AI-generated Python script designed for mapping hiking trails to identify and fix security flaws and hallucinations.
      
        Opening Hook
        Whether you're prepping for a multi-day hike or trying out a complex new recipe, you wouldn't blindly trust a random stranger's instructions without double-checking the map or the ingredients. The same goes for coding with AI. Since you want to get better at programming, we're going to explore how to use AI coding assistants responsibly—because sometimes, AI will confidently invent 'ingredients' or suggest a 'trail' that leads straight to a security vulnerability.
      
        Activity
        You will be provided with an AI-generated Python script that is supposed to calculate elevation changes for local hiking trails using a mock API. Your task is to perform a strict 'AI Audit' on the code. First, find and remove the hallucinated library the AI imported ('trail_calc_utils' - which does not exist). Second, identify the major security risk where the AI used the unsafe 'eval()' function to parse the trail data. Third, rewrite those specific lines using Python's standard, secure 'json' library and basic math operators. Submit your corrected, working script.
      
      ────────────────────────────────────────────────────────────────
      
        LESSON 2 OF 4  ·  File & Device Management
        Command Line Chef & Trailblazer: Automating File Organization
        30-45 minutes
      
        Goal
        Students will be able to navigate the command line interface and write a basic shell script to automate file management tasks.
      
        Overview
        This lesson bridges Grace's mastery of basic file management with her goal of learning to code. By introducing the command line interface (CLI) and basic scripting, she will learn how programmers manage and automate device operations, building troubleshooting confidence beyond a 'hard reset'.
      
        Opening Hook
        When you're prepping a complex recipe or packing for a multi-day hike, organization is everything—you wouldn't throw your hiking boots in the fridge! Right now, your computer's Downloads folder might look like an unpacked backpack. Since you want to get better at coding, let's skip the manual drag-and-drop. Today, you are going to write a mini-program that automatically sorts your trail maps and recipe files in milliseconds.
      
        Activity
        Step 1: Open your computer's Terminal (Mac/Linux) or PowerShell (Windows). Step 2: Type 'cd Desktop' to navigate to your desktop, then 'mkdir sorting_project' to create a new folder. Move into it by typing 'cd sorting_project'. Step 3: Let's create some dummy files! Type 'touch chili_recipe.txt pancake_recipe.txt yosemite_trail.jpg'. Step 4: Open a basic text editor and write a short script to sort these. Write: 'mkdir Recipes Hikes' on line 1, 'mv *recipe* Recipes/' on line 2, and 'mv *trail* Hikes/' on line 3. Save this text file as 'sorter.sh' in your project folder. Step 5: Go back to your Terminal and execute your code by typing 'bash sorter.sh'. Open the folder on your desktop to watch how your code instantly organized your files into the correct directories!
      
      ────────────────────────────────────────────────────────────────
      
        LESSON 3 OF 4  ·  Online Safety
        Securing the Trail: Protecting API Keys in Your Code
        30 minutes
      
        Goal
        Students will be able to securely store and access sensitive credentials in a coding project using environment variables and .gitignore files to prevent unauthorized access.
      
        Overview
        To support your goal of getting better at coding, we are taking online safety to the developer level. You will learn how to secure sensitive data like API keys using a .env file, ensuring you never accidentally leak credentials when sharing your code.
      
        Opening Hook
        Imagine you are building a custom Python app to pull real-time weather and GPS data for your next big hiking trip. If you leave your mapping API key hardcoded in your script and upload it to GitHub, malicious bots can hijack your key in seconds, racking up massive charges or locking you out of the data you need. Let's make sure your code is as secure and weather-proof as your hiking gear.
      
        Activity
        Step 1: Create a new folder and make a Python file called 'trail_mapper.py'. Inside, simulate a hardcoded secret by typing `API_KEY = 'super_secret_trail_key_99'` followed by `print('Connecting with:', API_KEY)`. Step 2: Set up professional security by creating a new file named '.env'. Move your key there by typing `API_KEY=super_secret_trail_key_99` and delete the hardcoded string from your Python file. Step 3: Create a '.gitignore' file and add '.env' to it—this tells version control to never upload your secrets. Step 4: Back in 'trail_mapper.py', import the 'os' and 'dotenv' modules. Use `load_dotenv()` and update your variable to `API_KEY = os.getenv('API_KEY')`. Step 5: Run 'trail_mapper.py' in your terminal. If it prints the key, you have successfully implemented a professional security standard used by software engineers to keep apps safe from hackers.
      
      ────────────────────────────────────────────────────────────────
      
        LESSON 4 OF 4  ·  Media Literacy
        Python for Photo Forensics: Verifying Trail Locations
        45 minutes
      
        Goal
        Students will be able to write a basic Python script to extract and analyze EXIF metadata from digital images to verify the authenticity and context of online media.
      
        Overview
        By combining her goal to learn coding with her interest in hiking, Grace will write a Python script to extract hidden EXIF metadata from a landscape photo, learning how digital investigators fact-check online images.
      
        Opening Hook
        You know those stunning photos of 'secret' hiking trails you see online? Sometimes people fake a remote hike when they are actually just right off a busy highway. Since you want to get better at coding, let's play digital detective. We are going to use a little bit of Python to extract the hidden metadata from a hiking photo to find out exactly where and when it was actually taken.
      
        Activity
        1. Open Google Colab (a browser-based Python environment, so no local setup or 'hard resets' are required if you get stuck). 2. Upload the provided 'mystery_trail.jpg' file to the workspace. 3. Write a short Python script using the 'Pillow' (PIL) library to open the image and extract its 'getexif()' data. 4. Filter the raw data to isolate the GPSInfo tag. 5. Write a small function to convert the raw GPS degrees, minutes, and seconds into standard decimal coordinates. 6. Plug those exact coordinates into Google Maps to reveal the true location of the hike, verifying if the image's online claim matches reality.
  
      ================================================================

# Part II
## Step #1 (Creating the personas)

        Personas loaded: ['Jordan', 'Sarah', 'Marcus']

## Step #2 (Combining Stages #2-3 into a function to run personas through)

        (No output created in this step.)

## Step #3 (Running the three personas through the pipeline)

        Running pipeline for Jordan...
          Done. Overall level: beginner, priority order: ['online_safety', 'responsible_ai_use', 'media_literacy', 'file_device_management']
        
        Running pipeline for Sarah...
          Done. Overall level: advanced, priority order: ['responsible_ai_use', 'file_device_management', 'online_safety', 'media_literacy']
        
        Running pipeline for Marcus...
          Done. Overall level: beginner, priority order: ['online_safety', 'responsible_ai_use', 'media_literacy', 'file_device_management']
        
        All personas complete.

## Step #3 (Reviewing pipeline outputs)

        ============================================================
          PERSONA: JORDAN
          inferred_comfort: beginner
          overall_level:    beginner
          priority_order:   ['online_safety', 'responsible_ai_use', 'media_literacy', 'file_device_management']
        
          QUIZ QUESTIONS:
            [online_safety] You are playing your favorite online multiplayer game, and a new teammate asks for your real name and the name of your school so you can 'be better friends.' What is the safest thing to do?
              A. Tell them your real name but not your school.
              B. Give a fake school name but your real first name.
              C. Ignore the question or say you don't share personal info online. <-- correct
              D. Tell them the information because you are on the same team.
            [online_safety] You are reading the comments on a YouTube video about drawing setups. A comment says, 'Click here to get a free drawing tablet!' and includes a link. What should you do?
              A. Click the link to see if the offer is real.
              B. Do not click the link, because it could be a scam or a virus. <-- correct
              C. Reply to the comment asking if anyone else got the free tablet.
              D. Click the link but close it quickly if it looks suspicious.
            [media_literacy] You are watching a video where a popular artist says, 'This is the best drawing software ever!' but you notice the word 'Sponsored' at the bottom of the screen. What does 'Sponsored' mean?
              A. The artist made the software themselves.
              B. The company that makes the software paid the artist to talk about it. <-- correct
              C. The artist is giving away the software for free to their subscribers.
              D. YouTube forced the artist to make a video about this software.
            [media_literacy] You see a headline online that says, 'Aliens land in New York City!' but no other news websites are talking about it. How can you tell if the story is true?
              A. Check to see if trusted, well-known news sites are also reporting the story. <-- correct
              B. Assume it is true because someone posted it on the internet.
              C. Share the story with your friends to see what they think.
              D. Look at the comments to see if people believe it.
            [responsible_ai_use] You have to write an essay for school about your favorite YouTuber. You find an AI chatbot that can write the whole essay for you in seconds. What is the most responsible way to use the AI?
              A. Copy and paste the AI's essay and turn it in as your own work.
              B. Ask the AI to write the essay, but change a few words so the teacher doesn't know.
              C. Use the AI to brainstorm ideas or help make an outline, but write the essay yourself. <-- correct
              D. Tell the AI to write the essay and just put the AI's name at the top of the paper.
            [file_device_management] You just recorded three different video clips for your new YouTube channel, and they are saved on your computer as 'Video1', 'Video2', and 'Video3'. What is the best way to keep these files organized so you can easily edit them later?
              A. Rename the files to describe what happens in them and put them in a specific 'YouTube Videos' folder. <-- correct
              B. Leave the names as they are and keep them scattered on your computer's desktop.
              C. Delete the original files as soon as you put them into your video editing software.
              D. Put all your computer files into one giant folder so you only have to look in one place.
        
          SKILL MATRIX:
            online_safety: 0 — needs work — missed most questions in this area
            media_literacy: 1 — partial — some gaps worth addressing
            responsible_ai_use: 0 — needs work — missed most questions in this area
            file_device_management: 1 — strong — got everything right here
        
          LESSON HOOKS:
            [online_safety] Keeping Your Channel Safe: Privacy for Future YouTubers
              Hook: You are getting ready to launch your own YouTube gaming and drawing channel! But before you hit 'Upload' on your first video, you need to make sure hackers can't mess with your account or figure out where you live.
              Activity preview: The Streamer Shield Activity: Jordan will review a mock 'About Me' page for a fake gaming YouTuber and highlight red fla...
            [responsible_ai_use] Teaming Up with AI for Your YouTube Videos
              Hook: Have you ever seen your favorite YouTubers use AI to come up with crazy video challenges or help draw thumbnails? AI can be an awesome co-op partner for your channel, but you have to know its cheat codes and its glitches.
              Activity preview: The AI Brainstorm Challenge: Under supervision, Jordan will ask a free, safe AI chatbot to generate 5 ideas for a new ga...
            [media_literacy] Spotting the Fakes: Clickbait, Scams, and Real Gaming News
              Hook: Imagine you click on a video titled 'FREE ROBUX/V-BUCKS TRICK 2024 (NOT CLICKBAIT)' and suddenly your computer is acting weird. As a future YouTuber, how do you spot fake videos and make sure the content you share with your audience is real?
              Activity preview: Clickbait Detective: Jordan will examine 5 different YouTube video thumbnails and titles provided by the teacher. They w...
            [file_device_management] Setting Up Your Creator Studio Workspace
              Hook: You already know your way around your files, which is awesome! But making YouTube videos means juggling huge gameplay clips, audio tracks, and your digital drawings. Let's organize your computer like a pro video editor so you never lose a masterpiece.
              Activity preview: The YouTube Folder Hierarchy: Jordan will create a master 'YouTube Creator Studio' folder on their desktop. Inside it, t...
        
        ============================================================
          PERSONA: SARAH
          inferred_comfort: advanced
          overall_level:    advanced
          priority_order:   ['responsible_ai_use', 'file_device_management', 'online_safety', 'media_literacy']
        
          QUIZ QUESTIONS:
            [online_safety] While pushing the source code for your new podcast website to a public GitHub repository, you realize you accidentally included the private API key for your audio hosting platform. What is the most secure immediate action to take?
              A. Quickly commit a new change that deletes the API key from the file and push the update to GitHub.
              B. Change your GitHub account password and enable two-factor authentication.
              C. Revoke the API key on the audio hosting platform's developer dashboard and generate a new one. <-- correct
              D. Make the GitHub repository private so no one else can see the commit history.
            [online_safety] As a student journalist, you receive an urgent email from a supposed whistleblower with an encrypted zip file attachment. The email uses industry-specific terminology and references a recent article you wrote. What is the primary cybersecurity risk here, and how should you handle it?
              A. The encrypted zip file might bypass your antivirus; you should forward it to a standard webmail account to scan it first.
              B. This is a potential spear-phishing attack; you should verify the sender's identity through an independent, trusted communication channel before opening the file. <-- correct
              C. The sender is using a man-in-the-middle attack; you should reply asking them to send the file via a cloud storage link instead.
              D. This is a standard ransomware attempt; you should download the file to a USB drive and open it on your primary computer while disconnected from Wi-Fi.
            [media_literacy] When researching a breaking news story for your school paper, you find a viral article citing a highly realistic, but unverified, video of a political figure. Which advanced media literacy technique is best for determining if the content is an AI-generated deepfake?
              A. Run the article's text through a plagiarism checker to see if the author has copied the narrative from another news outlet.
              B. Read the comments section of the viral article to see if a consensus of readers believes the video has been AI-generated.
              C. Check if the website hosting the article has an SSL certificate (HTTPS) and a professional-looking domain name.
              D. Perform a lateral reading exercise by checking independent fact-checking organizations and looking for digital artifacts in the video. <-- correct
            [media_literacy] You notice a sudden influx of highly polarized, sensationalized news blogs on your social media feed. Knowing how algorithmic curation and programmatic AI content farms operate, what is the most likely reason these articles are being recommended to you?
              A. The platform's algorithm optimizes for high-engagement metrics, and AI content farms exploit this by rapidly generating sensationalized content to trigger emotional responses. <-- correct
              B. The AI content farms have hacked the platform's servers to force their articles into the feeds of users interested in journalism.
              C. Your web browser's cache has been corrupted by a tracking cookie, causing it to exclusively display AI-generated news sites.
              D. The platform's algorithm is prioritizing articles that have been cryptographically verified for accuracy by independent AI moderation tools.
            [responsible_ai_use] You are writing a script to automate data collection for a journalism piece, and you use a Large Language Model (LLM) to summarize a complex dataset. What is the most significant ethical and practical risk of publishing this AI-generated summary directly?
              A. The LLM will automatically copyright the summary, preventing your school newspaper from legally publishing the article under its own name.
              B. The AI will embed hidden HTML tracking codes into the text, violating the privacy of the readers visiting your website.
              C. The LLM may hallucinate plausible-sounding but factually incorrect data points, compromising your journalistic integrity if not manually verified. <-- correct
              D. The LLM will permanently alter the original dataset in your local directory to match the summary it generated.
            [file_device_management] You are managing gigabytes of raw, unedited lossless audio files for your podcast, along with the source code for your website. Which file management strategy provides the most robust protection against both hardware failure and accidental file overwriting?
              A. Store all files solely on a high-capacity external Solid State Drive (SSD) and rely on the operating system's default auto-save feature while editing.
              B. Implement a 3-2-1 backup strategy for the audio files (three copies, two different media types, one offsite/cloud) and use a version control system like Git for the website code. <-- correct
              C. Compress the audio and code files together into a single ZIP archive every day and email the archive to yourself as a backup.
              D. Sync your active working directory exclusively to a cloud storage service, ensuring local copies are deleted automatically to save hard drive space.
        
          SKILL MATRIX:
            online_safety: 2 — strong — got everything right here
            media_literacy: 2 — strong — got everything right here
            responsible_ai_use: 1 — strong — got everything right here
            file_device_management: 1 — strong — got everything right here
        
          LESSON HOOKS:
            [responsible_ai_use] Algorithmic By-lines: Decoding AI in Journalism
              Hook: As a journalist and web builder, you've probably noticed an influx of articles that sound just a little bit 'off.' Let's use your analytical skills to spot the ghosts in the machine and establish the ground rules for AI in modern publishing.
              Activity preview: Read three provided 500-word news briefs: one human-written, one 100% AI-generated, and one AI-generated but human-edite...
            [file_device_management] Version Control for Creators: Git for Audio and Code
              Hook: Have you ever accidentally overwritten a perfect podcast edit or broken your website's CSS and couldn't undo it? Let's apply software engineering file management (Git and advanced directory structuring) to your podcasting and coding workflows.
              Activity preview: Create a mock 'Podcast Project Directory' on your computer. Initialize a Git repository inside it. Write a '.gitignore' ...
            [online_safety] Securing the Scoop: Cryptography for Journalists
              Hook: Investigative journalists often communicate with whistleblowers who need to remain anonymous. If someone wanted to send you a sensitive audio file for your podcast, how would you ensure no one else could intercept it?
              Activity preview: Use a free tool like Mailvelope, Kleopatra, or GPG in your terminal to generate your own PGP public/private key pair. En...
            [media_literacy] Trusting Your Ears: Detecting Deepfake Audio
              Hook: Since you already edit your own audio, you know what a natural human voice looks like on a timeline. But AI voices are getting terrifyingly good. Let's open up your audio editor and learn how to catch an AI deepfake by looking at the frequencies the human ear might miss.
              Activity preview: Download two provided audio files (one real human voice, one AI clone). Open them in your preferred audio editor (Audaci...
        
        ============================================================
          PERSONA: MARCUS
          inferred_comfort: beginner
          overall_level:    beginner
          priority_order:   ['online_safety', 'responsible_ai_use', 'media_literacy', 'file_device_management']
        
          QUIZ QUESTIONS:
            [online_safety] You get a direct message on TikTok from someone claiming to be a scout for a famous basketball team. They say they want to send you free gear and ask for your home address. What is the safest thing to do?
              A. Show the message to a trusted adult before replying or clicking anything. <-- correct
              B. Give them a fake address just to see what happens.
              C. Reply and ask them to prove they are a real scout before sending your address.
              D. Send them your address because you don't want to miss out on free gear.
            [online_safety] You are creating an account for a new online game. Which of the following is the most secure password to use?
              A. Your first name and the year you were born, like 'Marcus2010'.
              B. The word 'password' followed by the number 1, like 'password1'.
              C. A mix of letters, numbers, and symbols like 'B@sk3tb@ll99!'. <-- correct
              D. The same password you use for your school email account.
            [media_literacy] You see a viral TikTok video showing a famous basketball player making 20 full-court shots in a row without missing. How can you best check if this video is real or fake?
              A. Read the comments on the TikTok video to see if other users think it is real.
              B. Search for the story on reliable sports news websites to see if they reported it. <-- correct
              C. Assume it is real because the video has millions of views and likes.
              D. Watch the video a few more times to see if you can spot any editing mistakes.
            [media_literacy] You are reading an article online and see a link at the bottom that says 'Sponsored' next to a shocking news headline. What does 'Sponsored' mean?
              A. The article has been fact-checked and proven to be 100% true.
              B. The website recommends this article because it is highly educational.
              C. A famous person wrote the article and wants you to read it.
              D. An advertiser paid to put that link there to get you to click on it. <-- correct
            [responsible_ai_use] You use an AI tool to write a complete set of lyrics for a new music track you are producing. What is the most responsible way to share this song online?
              A. Give credit to the AI tool for writing the lyrics in the song's description. <-- correct
              B. Tell everyone you wrote the lyrics completely by yourself.
              C. Keep it a secret so people think you are a genius songwriter.
              D. Sell the lyrics to another musician and say they are originally yours.
            [file_device_management] You have spent hours making a new beat on your computer. What is the best way to make sure you don't lose your music file if your computer crashes?
              A. Keep the music program open on your computer at all times.
              B. Save a copy of the file to a cloud drive or an external hard drive. <-- correct
              C. Change the name of the file so the computer knows it is important.
              D. Email the file to yourself and then delete it from your computer.
        
          SKILL MATRIX:
            online_safety: 0 — needs work — missed most questions in this area
            media_literacy: 1 — partial — some gaps worth addressing
            responsible_ai_use: 0 — needs work — missed most questions in this area
            file_device_management: 1 — strong — got everything right here
        
          LESSON HOOKS:
            [online_safety] Don't Get Faked Out: Protecting Your Privacy on TikTok
              Hook: Have you ever seen a TikTok promising a free pair of exclusive basketball sneakers or a free plugin for your music software if you just 'click the link in bio'? Let's look at why those are almost always traps designed to steal your information.
              Activity preview: The Privacy Audit: Open your TikTok account (or use a provided simulated interface). Go through a 5-step checklist to ad...
            [responsible_ai_use] AI Beats and Bytes: Using AI in Music Fairly
              Hook: You've probably heard those viral AI covers on TikTok where it sounds exactly like a famous artist singing another artist's song. But who actually owns that track? Let's dive into how AI makes music and what that means for creators like you.
              Activity preview: The AI Producer Challenge: Listen to two short audio clips and read two short text paragraphs. Guess which ones are AI-g...
            [media_literacy] The Crossover: Spotting Fake News on Your Feed
              Hook: A blockbuster NBA trade rumor blows up on TikTok, complete with an image of the player in his new jersey. Before you send it to your friends, how do you know if it's a real breaking news bomb or just a fan using Photoshop?
              Activity preview: Fact-Check the Feed: Take a provided 'viral' social media post about a fake NBA rule change. Practice 'lateral reading' ...
            [file_device_management] Master the Mix: Organizing Your Digital Studio
              Hook: Imagine you just spent three hours making the perfect beat, but your computer crashes. When you restart, you can't find the file because it was saved as 'Untitled_Project_4'. Let's build a pro-level system for your music files so you never lose a track.
              Activity preview: Folder Hierarchy Blueprint: Create a main folder on your desktop called 'Music_Production'. Inside, create subfolders fo...

## Step #4 (Filling results into the scorecard)

        Scorecard ready to fill in. Run the summary cell after scoring.

## Step #4 (Printing the scorecard)

        Criterion                         Jordan     Sarah    Marcus
        ------------------------------------------------------------
        quiz_difficulty_match               PASS      PASS      PASS
        interest_integration_quiz           PASS      PASS      PASS
        lesson_hook_specificity             PASS      PASS      PASS
        lesson_difficulty_match             PASS      PASS      PASS
        priority_order_logic                PASS      PART      PASS
        
        NOTES:
        
          Jordan:
        
          Sarah:
            quiz_difficulty_match: This isn't a fail, but Sarah got everything right, which might mean the quiz wasn't hard enough to find her weak spots, or that she's genuinely strong across all areas. It's hard to tell with simulated answers.
            priority_order_logic: Sarah scored 'strong' in all four areas, so there wasn't really a weakest area to put first. The pipeline picked responsible_ai_use first, but the scores were all the same so it didn't really matter which one went first. Priority ordering works correctly when there's score variance it isn't really meaningful here.
        
          Marcus:
            priority_order_logic: Marcus and Jordan ended up with the exact same priority order, which looks a little suspicious. It's because the fixed random seed (random.seed(42)) gives both beginner personas the same answer pattern, not because the pipeline actually reasoned about Marcus specifically.
        
