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
I iterated the profile prompt slightly to make it more conversational and natural than the initial version, which was slightly more rigid and place enough of a focus on actually getting to know the student. I ideally want my learning tool to feel like a human tutor but have the improved efficiency and accesibility of a digital assistant. Some of the biggest changes I made were adding descriptive adjectives that tell the AI how it should interact with/approach the student -- i.e. "friendly", "relaxed", "warm", "encouraging". I also specified that it's okay for the AI to make remarks or ask follow-ups before continuing, to increase the natural feel of the conversation. This was what I revised my 

