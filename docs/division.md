## Division of work

### 1. Parser only  --> HasNetwork
- Look into [Docling](https://github.com/docling-project/docling) and get how to use the OCR for pdf parsing
- Convert the pdf to markdown format 
- use a LLM (preferably groq but feel free to choose any other provider) for cleaning & to convert the markdown into json with the help of a pydantic schema for structured output 

### 2. resume builder  --> Vatsal-Khatri, pranjalkapure
- Build the frontend part for accepting resume
- keep 2 options :
    1. upload ur own resume (pdf format only)
    2. build ur own resume
- The 2nd option
    - consist of a questionnaire format form which will ask the user for relevant details like Name, DOB, contact info (phone number, email), experience, skills, etc.
    - Use JS (and React.js if u guys already know JS) for making the form and send the data to backend in JSON format

### 3. Analyzer  --> yerra-srikar
- Take JD from user and use it to analyze the given resume
- For the resume data use the parsed JSON data 
- Grade the resume between 0-10 (float point, 2 decimal places) as per experience level, relevancy of skills, validity of projects, etc. (U can add ur own areas of judging too)
- Generate a report which consists:
    1. General summary and feedback 
    2. Explain the good elements of the resume
    3. Explain the bad or missing aspects of the resume and suggest improvements for the same
- See if u can use pydantic schema for the above 

### 4. Question generator  --> yerra-srikar, HasNetwork
- Generate 10 questions from the resume + JD and give to the user
- It should have 3 easy, 4 medium and 3 hard level questions 

### 5. answer input (text for now) + feedback report  --> yerra-srikar, HasNetwork
- Take the input from the user for each question as the answer for that question and submit it to the LLM for checking
- The LLM should match the given answers to the ideal answers and give appropriate feedback for the same
- Generate a report for the same and give it to the user