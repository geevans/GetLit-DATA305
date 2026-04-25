# Stage Outputs

- In Part I, I have included the outputs I received when I used the tool to generate a curriculum for my digitial literacy needs. 
- In Part II, I have included the outputs from the evaluation pipeline, when I ran Jordan, Sarah, and Marcus through it.

## Part I: Stage #1 Output (My conversation with the AI)

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

## Part I: Stage #2 Output (Questions AI generated for me)

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

## Part I: Stage #2 Output (My completion of the quiz)
  
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

## Part I: Stage #2 Output (Scoring of my quiz answers and building of skill matrix)

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

## Part I: Stage #3 Output (Sorting learning areas by priority)

  Lesson priority order:
    1. responsible_ai_use (score: 1) — strong — got everything right here
    2. file_device_management (score: 1) — strong — got everything right here
    3. online_safety (score: 2) — strong — got everything right here
    4. media_literacy (score: 2) — strong — got everything right here

## Part I: Stage #3 Output (Generating lessons for each skill)

  ✓ Generated lesson for: responsible_ai_use
  ✓ Generated lesson for: file_device_management
  ✓ Generated lesson for: online_safety
  ✓ Generated lesson for: media_literacy
  
  Total lessons generated: 4

## Part I: Stage #3 Output (Storing curriculum as JSON)

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

## Part I: Stage #3 Output (Converting JSON into readable printout)

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
