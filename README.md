## AI Hiring Manager

## Problem Statement 
The challenges HR teams face when manually reviewing a large volume of resumes, including time consumption, human error, and the risk of missing good candidates.

## Solution Overview 
The proposed solution involves a system where users upload CVs to a website, which are then sent to n8n via a webhook. 
An AI agent within n8n reads, analyzes the resume, and saves the final decision (selected/rejected) and feedback into a Google Sheet.

## System Architecture 
User Upload CV: Candidates upload their CVs through a custom-built website.  
n8n Processing: The CV is sent to n8n, which uses an AI model to process the information.  
Google Sheet Storage: The final decision and candidate information are stored in a Google Sheet.

<img width="1366" height="590" alt="Screenshot 2026-02-27 072234" src="https://github.com/user-attachments/assets/626dae4c-0160-495a-b1b5-949f0ed28fa3" />


## Building the Workflow in n8n
Webhook Node: set up a webhook in n8n to receive CVs from the front-end website.
Google AI Studio for Front-end Development: -
Extracting Data from PDF: An "Extract From File" node is used to pull textual information from the uploaded PDF resumes.
AI Agent Node: An AI Agent node is configured to analyze the extracted resume data.
System Message (Prompt Engineering): A detailed system message is provided to the AI agent, outlining
strict professional criteria for selection and rejection, as well as the desired output format.
Google Sheet Integration: A "Google Sheet" node is used to append the analyzed candidate data (decision, name, contact details, experience, final opinion) to a Google Sheet.

<img width="1366" height="607" alt="Screenshot 2026-02-27 093034" src="https://github.com/user-attachments/assets/821f04ed-e0f1-41c3-846e-22001a4047e2" />


Testing and Deployment: Upload your resume. AI Model will analyze based on system prompt and send results to google sheets whether you are selected or rejected.
