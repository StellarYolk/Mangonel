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

### 4. Question generator  --> yerra-srikar, HasNetwork

### 5. answer input (text for now) + feedback report  --> yerra-srikar, HasNetwork
