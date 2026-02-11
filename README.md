I want to build an industry-style Loan Approval System step-by-step.
Important Rules:
•	Development assistant: Claude Haiku 4.5 (GitHub Copilot)
•	AI model for logic: Google Gemini 2.5 Flash
•	Orchestration: Langflow
•	Backend: FastAPI
•	Frontend: React (two apps)
•	Web search: Serper API (LinkedIn grounding)
•	Storage: JSON files only
•	Input: User uploads a loan application PDF
________________________________________
How I Want You to Work
Do NOT generate everything at once.
Instead:
•	Generate the project one module at a time
•	Wait for my confirmation after each step
•	Move to next step only when I say:
👉 “continue to next step”
________________________________________
PROJECT STRUCTURE TO FOLLOW
loan-approval-project/

│── langflow/
│   └── flow.json

│── backend-tools/
│   ├── credit.py
│   ├── eligibility.py
│   ├── collateral.py
│   ├── employment.py
│   ├── serper_tool.py

│── backend-api/
│   ├── main.py
│   ├── routes.py
│   ├── models.py
│   ├── services.py
│   ├── utils.py

│── data/
│   ├── applicants.json
│   ├── evidences.json
│   ├── decisions.json
│   ├── critiques.json

│── frontend-user/
│   └── React App

│── frontend-admin/
│   └── React Dashboard

│── .env
________________________________________
START IMPLEMENTATION SEQUENCE
Follow this exact order:
________________________________________
STEP 1 – Project Initialization
Generate:
•	Python virtual environment setup
•	requirements.txt
•	basic README
•	folder structure
After generating this, stop and wait.
________________________________________
STEP 2 – FastAPI Skeleton
Create:
•	main.py
•	routes.py
•	models.py
•	services.py
•	utils.py
Include these endpoints:
POST /upload-loan-application
GET /applications
GET /application/{id}
GET /evidences/{id}
GET /decision/{id}
Use JSON files in /data as storage.
Then stop.
________________________________________
STEP 3 – Utility Layer
Implement in utils.py:
•	read_json()
•	write_json()
•	append_json()
•	generate_application_id()
•	pdf_text_extractor()
Then stop.
________________________________________
STEP 4 – Deterministic Business Logic Tools
Generate one file at a time:
1.	credit.py
2.	eligibility.py
3.	collateral.py
4.	employment.py
Each tool must accept applicant data and return structured JSON evidence.
Stop after each file and wait for my “continue”.
________________________________________
STEP 5 – Serper API Tool
Generate serper_tool.py that:
•	Reads SERPER_API_KEY from .env
•	Performs LinkedIn search
•	Returns structured verification result
No real API calls in demo mode, but keep function structure ready.
Then stop.
________________________________________
STEP 6 – Services Layer
Implement services.py to:
•	Call all deterministic tools
•	Call Serper tool
•	Aggregate evidences
•	Communicate with Langflow
•	Store outputs in JSON
Then stop.
________________________________________
STEP 7 – Langflow Flow
Generate:
langflow/flow.json
Containing:
•	Planner Agent
•	Deterministic tool nodes
•	LinkedIn verification node
•	Evidence critique agent
•	Decision maker agent
•	Decision critique agent
Using Gemini 2.5 Flash as LLM.
Then stop.
________________________________________
STEP 8 – Frontend User (React)
Generate:
•	React app for PDF upload
•	API integration with FastAPI
•	Basic UI and status page
Then stop.
________________________________________
STEP 9 – Frontend Admin (React)
Generate:
•	Dashboard listing applications
•	Evidence viewer
•	Decision viewer
•	Critique viewer
Then stop.
________________________________________
STEP 10 – Integration
Generate:
•	End-to-end integration
•	README with run instructions
•	sample .env template
•	test JSON data
________________________________________
Coding Guidelines
•	Write clean, modular, typed Python code
•	Use proper error handling
•	Follow REST best practices
•	React code should be component-based
•	Use environment variables
•	Make everything runnable locally
