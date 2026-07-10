# CareerPilot AI — Multi-Agent Career Assistant

CareerPilot AI is an end-to-end **Agentic AI career assistant** that helps candidates analyze their resume against a job description, identify skill gaps, optimize their resume, generate interview preparation questions, create a cover letter, build a preparation roadmap, and export a complete career report.

This project combines:

- Retrieval-Augmented Generation
- Embeddings
- FAISS vector search
- LangGraph workflow orchestration
- CrewAI multi-agent collaboration
- Ollama local LLM
- OpenAI API support
- Hugging Face API support
- LLM provider switching
- Agent trace logging
- Career memory tracking
- PDF report generation
- Streamlit UI

---

## Table of Contents

- [Project Overview](#project-overview)
- [Problem Statement](#problem-statement)
- [Project Goals](#project-goals)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [System Architecture](#system-architecture)
- [RAG Architecture](#rag-architecture)
- [LangGraph Workflow](#langgraph-workflow)
- [CrewAI Integration](#crewai-integration)
- [LLM Provider Switcher](#llm-provider-switcher)
- [Project Folder Structure](#project-folder-structure)
- [Installation](#installation)
- [Environment Setup](#environment-setup)
- [Ollama Setup](#ollama-setup)
- [How to Run](#how-to-run)
- [Generated Outputs](#generated-outputs)
- [Version History](#version-history)
- [Interview Explanation](#interview-explanation)
- [Resume Bullet Points](#resume-bullet-points)
- [What I Learned](#what-i-learned)
- [Future Improvements](#future-improvements)
- [GitHub Upload Notes](#github-upload-notes)
- [Author](#author)

---

## Project Overview

CareerPilot AI is a multi-agent career preparation platform designed for candidates applying to AI, Machine Learning, Data Science, and Generative AI roles.

The system takes three main inputs:

1. Resume PDF
2. Job description text
3. Target role

Then it produces a complete career preparation report containing:

- Resume analysis
- Job description analysis
- Skill match score
- Matched skills
- Missing skills
- Skill gap explanation
- Resume optimization suggestions
- Interview preparation questions
- 7-day preparation roadmap
- Customized cover letter
- CrewAI-style career recommendation
- Evaluator feedback
- Final action plan
- PDF report
- Agent trace logs
- Career memory

---

## Problem Statement

Job seekers often struggle to understand how well their resume matches a specific job description.

Common problems include:

- Not knowing which skills are missing
- Not knowing how to improve the resume
- Not knowing what interview questions to prepare
- Not knowing how to explain projects clearly
- Not knowing how to honestly explain missing skills
- Not having a structured preparation roadmap
- Not having personalized cover letters

CareerPilot AI solves this by using multiple AI agents that work together to analyze the resume, job description, skill gaps, and interview preparation needs.

---

## Project Goals

The main goal of this project is to build a practical Agentic AI system that demonstrates:

- Multi-agent AI workflows
- RAG-based context retrieval
- Resume and JD analysis
- Skill gap detection
- Resume optimization
- Interview preparation
- CrewAI-based agent collaboration
- LangGraph-based workflow orchestration
- Local and cloud LLM integration
- API fallback handling
- PDF report generation
- Career memory tracking
- Agent observability

---

## Key Features

### 1. Resume Analyzer Agent

The Resume Analyzer Agent reads the resume PDF and extracts:

- Candidate summary
- Technical skills
- Project highlights
- Strengths
- Weak areas
- Best points for interview preparation

---

### 2. Job Description Analyzer Agent

The JD Analyzer Agent analyzes the job description and extracts:

- Required skills
- Responsibilities
- Tools and technologies
- AI/ML expectations
- GenAI/RAG/LLM requirements
- Interview focus areas

---

### 3. Skill Gap Agent

The Skill Gap Agent compares the resume with the job description.

It generates:

- Match score
- Matched skills
- Missing skills
- Skill gap explanation
- Honest interview explanation for missing skills

---

### 4. Resume Optimizer Agent

The Resume Optimizer Agent suggests:

- ATS-friendly resume improvements
- Better professional summary
- Skills section improvements
- JD keywords to add honestly
- Project bullet rewrites
- AI/ML project positioning
- What not to overclaim

---

### 5. Interview Coach Agent

The Interview Coach Agent generates:

- Technical interview questions
- HR interview questions
- Project explanation questions
- RAG-related questions
- Agentic AI questions
- LLM-related questions
- Suggested answer strategy

---

### 6. Career Roadmap Agent

The Career Roadmap Agent creates a short-term preparation plan.

It helps the candidate know:

- What to revise first
- What projects to explain
- What concepts to prepare
- What skills to improve
- How to prepare before the interview

---

### 7. Cover Letter Agent

The Cover Letter Agent generates a customized cover letter based on:

- Resume strengths
- JD requirements
- Matched skills
- Target role
- Candidate projects

---

### 8. Evaluator Agent

The Evaluator Agent reviews the final report and adds:

- Report quality feedback
- Missing improvement areas
- Final interview strategy
- Strongest talking points
- Honest explanation for weak areas

---

### 9. Career Crew Agent

The Career Crew Agent adds a CrewAI-style role-based collaboration layer.

It includes roles such as:

- Resume Expert
- JD Strategist
- Skill Gap Coach
- Interview Strategist
- Career Manager

Each role has:

- Role
- Goal
- Backstory
- Task
- Expected output

---

### 10. Real CrewAI Integration

The project includes actual CrewAI integration using:

- CrewAI Agent
- CrewAI Task
- CrewAI Crew
- Sequential process

This is implemented separately from the main LangGraph workflow so both frameworks can be compared safely.

---

### 11. LLM Provider Switcher

The project supports multiple LLM providers:

- Ollama local LLM
- OpenAI API
- Hugging Face API
- Fallback mode

The active provider is controlled from the `.env` file.

---

### 12. Agent Trace Logs

Every workflow step is logged with:

- Node name
- Agent name
- Task
- Tools used
- Status
- Duration
- Output summary
- Timestamp

This makes the system easier to debug and explain.

---

### 13. Career Memory

The memory system stores previous runs and tracks:

- Target role
- Match score
- Matched skills
- Missing skills
- Report path
- Trace path
- Progress compared to previous runs

---

### 14. PDF Report Export

The final career report is exported as:

- Markdown report
- PDF report

---

### 15. Streamlit UI

The Streamlit app provides a simple interface to:

- Upload resume PDF
- Paste job description
- Enter target role
- Run CareerPilot AI
- View final report
- View agent trace
- View memory and progress
- Download reports

---

## Tech Stack

| Category | Tools / Libraries |
|---|---|
| Programming Language | Python |
| UI | Streamlit |
| Workflow Orchestration | LangGraph |
| Multi-Agent Framework | CrewAI |
| RAG | Custom RAG Pipeline |
| Vector Database | FAISS |
| Embeddings | Sentence Transformers |
| Local LLM | Ollama |
| Cloud LLM APIs | OpenAI, Hugging Face |
| PDF Reading | PyMuPDF |
| PDF Generation | ReportLab |
| Configuration | python-dotenv |
| Data Processing | Pandas, NumPy |
| ML Utilities | Scikit-learn |
| API Calls | requests, OpenAI SDK |

---

## System Architecture

```text
User Input
│
├── Resume PDF
├── Job Description
└── Target Role
        │
        ▼
Data Processing Layer
│
├── PDF Text Extraction
├── JD Text Loading
└── Text Cleaning
        │
        ▼
RAG Layer
│
├── Text Chunking
├── Embedding Generation
├── FAISS Vector Store
└── Context Retrieval
        │
        ▼
LangGraph Workflow Layer
│
├── Resume Analyzer Agent
├── JD Analyzer Agent
├── Skill Gap Agent
├── Resume Optimizer Agent
├── Interview Coach Agent
├── Career Roadmap Agent
├── Cover Letter Agent
├── Career Crew Agent
└── Evaluator Agent
        │
        ▼
Output Layer
│
├── Markdown Report
├── PDF Report
├── Agent Trace Logs
├── Career Memory
└── CrewAI Report
```

---

## RAG Architecture

RAG means **Retrieval-Augmented Generation**.

In this project, RAG is used to give each agent relevant context from the resume and job description.

Instead of sending the full resume or full JD to every agent, the system retrieves only the most relevant chunks.

```text
Resume / JD Text
        │
        ▼
Text Splitter
        │
        ▼
Text Chunks
        │
        ▼
Embedding Model
        │
        ▼
Vector Embeddings
        │
        ▼
FAISS Vector Store
        │
        ▼
Similarity Search
        │
        ▼
Relevant Context
        │
        ▼
Agent Prompt
        │
        ▼
LLM Response
```

### RAG Tools Used

| File | Purpose |
|---|---|
| `tools/text_splitter.py` | Splits resume and JD text into chunks |
| `tools/embedding_tool.py` | Converts text chunks into embeddings |
| `tools/vector_store.py` | Stores embeddings and performs similarity search |
| `tools/rag_tool.py` | Retrieves relevant context for agents |

---

## LangGraph Workflow

LangGraph is used as the main workflow orchestration system.

It controls the order of execution using:

- State
- Nodes
- Edges

### Workflow Flow

```text
START
  ↓
load_jd
  ↓
resume_analysis
  ↓
jd_analysis
  ↓
skill_gap
  ↓
resume_optimizer
  ↓
interview_coach
  ↓
roadmap
  ↓
cover_letter
  ↓
career_crew
  ↓
final_report
  ↓
evaluator
  ↓
save_report
  ↓
END
```

### Why LangGraph?

LangGraph is useful because it provides:

- Clear workflow control
- Shared state management
- Node-based execution
- Easy debugging
- Agent orchestration
- Step-by-step traceability

---

## CrewAI Integration

CareerPilot AI includes two CrewAI-related systems.

---

### 1. CrewAI-Style Manual Layer

This layer manually implements CrewAI-style design concepts.

Each agent profile contains:

- Role
- Goal
- Backstory
- Task
- Expected output

Example roles:

```text
Resume Expert
JD Strategist
Skill Gap Coach
Interview Strategist
Career Manager
```

This helped demonstrate the core idea of role-based multi-agent collaboration.

---

### 2. Actual CrewAI Runner

The project also includes a real CrewAI implementation using:

```text
Agent
Task
Crew
Process.sequential
```

The actual CrewAI runner is separate from the main LangGraph workflow.

This allows comparison between:

| LangGraph | CrewAI |
|---|---|
| State-based workflow | Role-based collaboration |
| Nodes and edges | Agents and tasks |
| Precise control | Natural agent teamwork |
| Better for workflows | Better for role-based crews |

---

## LLM Provider Switcher

The project includes an LLM router that can switch between different LLM providers.

```text
ask_llm(prompt)
      │
      ▼
LLM Provider Router
      │
      ├── Ollama
      ├── OpenAI
      ├── Hugging Face
      └── Fallback
```

The provider is selected from `.env`.

```env
LLM_PROVIDER=ollama
```

Supported values:

```text
ollama
openai
huggingface
fallback
```

---

### Ollama Provider

Used for local LLM execution.

Example:

```env
LLM_PROVIDER=ollama
OLLAMA_BASE_URL=http://localhost:11434
OLLAMA_MODEL=qwen2.5:1.5b
```

---

### OpenAI Provider

Used for OpenAI API calls.

Example:

```env
LLM_PROVIDER=openai
OPENAI_API_KEY=your_openai_api_key
OPENAI_MODEL=gpt-4o-mini
```

---

### Hugging Face Provider

Used for Hugging Face API calls.

Example:

```env
LLM_PROVIDER=huggingface
HUGGINGFACE_API_KEY=your_huggingface_api_key
HUGGINGFACE_MODEL=Qwen/Qwen2.5-7B-Instruct
```

---

### Fallback Provider

If the selected LLM provider fails, the fallback system returns a safe rule-based response.

This prevents the project from crashing.

---

## Project Folder Structure

```text
CareerPilot-AI/
│
├── agents/
│   ├── resume_agent.py
│   ├── jd_agent.py
│   ├── skill_gap_agent.py
│   ├── resume_optimizer_agent.py
│   ├── interview_agent.py
│   ├── roadmap_agent.py
│   ├── cover_letter_agent.py
│   ├── evaluator_agent.py
│   └── manager_agent.py
│
├── crews/
│   ├── __init__.py
│   ├── agent_profiles.py
│   ├── career_crew.py
│   └── real_crewai_runner.py
│
├── workflows/
│   ├── __init__.py
│   ├── career_state.py
│   └── career_graph.py
│
├── tools/
│   ├── pdf_reader.py
│   ├── skill_matcher.py
│   ├── report_writer.py
│   ├── text_splitter.py
│   ├── embedding_tool.py
│   ├── vector_store.py
│   ├── rag_tool.py
│   ├── trace_writer.py
│   └── pdf_report_generator.py
│
├── memory/
│   ├── __init__.py
│   ├── memory_store.py
│   └── progress_tracker.py
│
├── data/
│   └── .gitkeep
│
├── outputs/
│
├── app.py
├── app_langgraph.py
├── app_streamlit.py
├── app_crewai.py
├── config.py
├── llm_client.py
├── test_llm_provider.py
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
```

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/CareerPilot-AI.git
cd CareerPilot-AI
```

---

### 2. Create Virtual Environment

For Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

For macOS/Linux:

```bash
python -m venv venv
source venv/bin/activate
```

---

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Requirements

```txt
pymupdf
requests
numpy
pandas
scikit-learn
sentence-transformers
faiss-cpu
streamlit
plotly
langgraph
crewai
reportlab
python-dotenv
openai
```

---

## Environment Setup

Create a `.env` file in the project root.

Use `.env.example` as reference.

### `.env.example`

```env
# CareerPilot AI Environment Example
# Copy this file and rename it to .env
# Do not upload your real .env file to GitHub.

# Supported values:
# ollama
# openai
# huggingface
# fallback

LLM_PROVIDER=ollama

# Ollama local LLM config
OLLAMA_BASE_URL=http://localhost:11434
OLLAMA_MODEL=qwen2.5:1.5b

# OpenAI API config
OPENAI_API_KEY=
OPENAI_MODEL=gpt-4o-mini

# Hugging Face API config
HUGGINGFACE_API_KEY=
HUGGINGFACE_MODEL=Qwen/Qwen2.5-7B-Instruct
```

Do not upload your real `.env` file to GitHub.

---

## Ollama Setup

Install Ollama from the official website.

Pull the local model:

```bash
ollama pull qwen2.5:1.5b
```

Start Ollama:

```bash
ollama serve
```

If it says the port is already in use, Ollama may already be running.

---

## How to Run

### 1. Test LLM Provider

```bash
python test_llm_provider.py
```

Expected output:

```text
Current LLM Provider: ollama
[LLM Router] Provider: ollama
LLM Response:
...
```

---

### 2. Run LangGraph Workflow

```bash
python app_langgraph.py --resume data/resume.pdf --jd data/job_description.txt --role "AI/ML Intern"
```

---

### 3. Run Streamlit App

```bash
streamlit run app_streamlit.py
```

---

### 4. Run CrewAI Version

```bash
python app_crewai.py --resume data/resume.pdf --jd data/job_description.txt --role "AI/ML Intern"
```

---

## Generated Outputs

Generated files are saved inside the `outputs/` folder.

```text
outputs/career_report.md
outputs/career_report.pdf
outputs/agent_trace.json
outputs/agent_trace.md
outputs/career_memory.json
outputs/crewai_career_report.md
```

The `outputs/` folder should not be uploaded to GitHub because it may contain private resume or job data.

---

## Example Use Case

A candidate applying for an AI/ML Internship can use CareerPilot AI like this:

1. Upload resume PDF
2. Paste the job description
3. Enter target role as `AI/ML Intern`
4. Run the system
5. Review the generated report
6. Check skill gap score
7. Improve resume using suggestions
8. Prepare interview questions
9. Download PDF report

---

## Version History

### Version 1 — CLI Multi-Agent Career Assistant

Initial command-line version.

Features:

- Resume Analyzer Agent
- JD Analyzer Agent
- Skill Gap Agent
- Interview Coach Agent
- Roadmap Agent
- Manager Agent
- Markdown report generation

Output:

```text
outputs/career_report.md
```

---

### Version 2 — RAG + Embeddings + FAISS

Added retrieval-augmented generation.

Features:

- Text chunking
- Embeddings
- FAISS vector store
- Resume RAG index
- JD RAG index
- Context retrieval

Tools added:

```text
tools/text_splitter.py
tools/embedding_tool.py
tools/vector_store.py
tools/rag_tool.py
```

---

### Version 3 — Streamlit UI

Added web interface.

Features:

- Resume PDF upload
- Job description input
- Target role input
- Report display
- Markdown download

File added:

```text
app_streamlit.py
```

---

### Version 4 — LangGraph Workflow

Added graph-based workflow orchestration.

Features:

- LangGraph state
- LangGraph nodes
- LangGraph edges
- Structured workflow execution

Workflow:

```text
START → load_jd → resume_analysis → jd_analysis → skill_gap → interview_coach → roadmap → final_report → END
```

---

### Version 5 — Evaluator Agent + Reflection

Added evaluator agent.

Features:

- Final report review
- Quality feedback
- Interview strategy
- Reflection section
- Improved final report

---

### Version 6 — Agent Trace + Tool Usage Logs

Added observability.

Features:

- Agent trace logs
- Node duration tracking
- Tool usage tracking
- Status tracking
- JSON trace
- Markdown trace

Outputs:

```text
outputs/agent_trace.json
outputs/agent_trace.md
```

---

### Version 7 — Memory + Progress Tracker

Added career memory.

Features:

- Save career runs
- Track previous match scores
- Compare latest and previous runs
- Store matched and missing skills
- Progress summary

Output:

```text
outputs/career_memory.json
```

---

### Version 8 — PDF Report Export

Added PDF generation.

Features:

- Markdown to PDF conversion
- Professional report format
- Page numbers
- Downloadable PDF report

Output:

```text
outputs/career_report.pdf
```

---

### Version 9 — Cover Letter Agent

Added customized cover letter generation.

Features:

- Cover letter generation
- Resume/JD-based personalization
- Interview-friendly wording
- Streamlit cover letter section

---

### Version 10 — Resume Optimizer Agent

Added resume optimization system.

Features:

- ATS keyword suggestions
- Resume summary improvement
- Project bullet rewrites
- Honest skill positioning
- Resume improvement checklist

---

### Version 11 — CrewAI-Style Role-Based Agent Layer

Added manual CrewAI-style agent design.

Features:

- Agent role
- Agent goal
- Agent backstory
- Agent task
- Expected output
- Career Crew Agent

Agents added:

- Resume Expert
- JD Strategist
- Skill Gap Coach
- Interview Strategist
- Career Manager

---

### Version 12 — Actual CrewAI Integration

Added real CrewAI integration.

Features:

- CrewAI Agent
- CrewAI Task
- CrewAI Crew
- Sequential process
- Ollama LLM configuration for CrewAI
- Separate CrewAI runner

File added:

```text
app_crewai.py
```

---

### Version 13 — LLM Provider Switcher

Added multi-provider LLM support.

Features:

- Ollama provider
- OpenAI provider
- Hugging Face provider
- Fallback provider
- `.env` configuration
- Provider test script

File added:

```text
test_llm_provider.py
```

---

### Version 14 — GitHub Documentation

Added portfolio-ready documentation.

Features:

- Complete README
- Architecture explanation
- Setup steps
- Version history
- Interview explanation
- GitHub upload notes

---

## Interview Explanation

### Short Explanation

CareerPilot AI is a multi-agent career assistant that helps candidates prepare for job applications. It analyzes a resume and job description, identifies skill gaps, suggests resume improvements, generates interview questions, creates a roadmap, generates a cover letter, and exports a final career report.

The system uses RAG, embeddings, FAISS, LangGraph, CrewAI, Ollama, OpenAI API support, Hugging Face API support, memory tracking, trace logs, and PDF generation.

---

### One-Minute Explanation

I built CareerPilot AI as a Multi-Agent Career Assistant for AI/ML job preparation. The system takes a resume, a job description, and a target role as input. It then uses multiple specialized agents to analyze the resume, understand the job description, calculate a skill match score, identify missing skills, suggest resume improvements, generate interview preparation questions, create a roadmap, and generate a customized cover letter.

I used RAG by extracting resume and JD text, splitting them into chunks, creating embeddings, storing them in FAISS, and retrieving relevant context for each agent. I used LangGraph to orchestrate the workflow using nodes, edges, and shared state. I also integrated CrewAI separately to understand role-based collaboration using agents, tasks, crews, and sequential execution.

The project supports multiple LLM providers, including Ollama, OpenAI, Hugging Face, and fallback mode. It also generates trace logs, stores career progress memory, and exports the final report as Markdown and PDF.

---

### RAG Explanation for Interview

RAG means Retrieval-Augmented Generation.

In this project, I used RAG to make the agents more context-aware.

The system extracts text from the resume and job description, splits the text into chunks, converts those chunks into embeddings, stores them in FAISS, and retrieves the most relevant chunks for each agent.

This helps the agents generate better responses because they receive only the most relevant context instead of the entire document.

---

### LangGraph Explanation for Interview

I used LangGraph to build the main workflow.

LangGraph helps structure the application as a graph of nodes and edges. Each node performs one task, such as resume analysis, JD analysis, skill gap analysis, or report generation.

The shared state stores data and passes it from one node to another.

LangGraph is useful because it gives precise control over the workflow.

---

### CrewAI Explanation for Interview

I integrated CrewAI separately to understand role-based multi-agent collaboration.

In CrewAI, I created agents such as Resume Expert, JD Strategist, Interview Coach, and Career Manager.

Each agent has a role, goal, backstory, and task. The crew runs tasks sequentially and creates a final career recommendation.

---

### Difference Between LangGraph and CrewAI

LangGraph and CrewAI are useful for different purposes.

LangGraph is better for state-based workflow orchestration. It gives more control over nodes, edges, and shared state.

CrewAI is better for role-based agent collaboration. It allows agents to be defined with roles, goals, backstories, and tasks.

In this project, I used both to understand the difference practically.

---

### LLM Provider Switcher Explanation

I added an LLM provider switcher so the system can use different LLM backends.

Supported providers are:

- Ollama
- OpenAI
- Hugging Face
- Fallback

The provider is selected using the `.env` file.

This makes the project flexible because I can run it locally with Ollama or use cloud APIs when needed.

---

### Fallback Handling Explanation

If an LLM provider fails, the system does not crash. It uses fallback responses.

For example, if Hugging Face API fails because of model availability, token issues, or network problems, the fallback system returns a basic useful response.

This makes the application more robust.

---

### Memory System Explanation

The memory system stores previous career analysis runs.

It tracks:

- Previous target role
- Previous match score
- Matched skills
- Missing skills
- Report path
- Trace path

This allows the project to compare the current run with previous runs and show progress.

---

### Agent Trace Explanation

The agent trace system records what each agent did.

It logs:

- Node name
- Agent name
- Task
- Tools used
- Execution time
- Output summary
- Status

This makes the system more explainable and easier to debug.

---

## Challenges Faced

Some challenges faced during development:

1. Managing multiple agents in a clean workflow
2. Passing state correctly between LangGraph nodes
3. Fixing LangGraph parallel update errors
4. Handling local LLM and cloud API differences
5. Integrating CrewAI without breaking the existing workflow
6. Creating fallback handling for failed APIs
7. Generating clean PDF reports
8. Maintaining memory and trace logs
9. Handling Hugging Face API model compatibility
10. Keeping the system modular and easy to extend

---

## What I Learned

Through this project, I learned:

- How to build a RAG pipeline
- How embeddings work
- How FAISS vector search works
- How to orchestrate agents with LangGraph
- How to create CrewAI agents and tasks
- How to use Ollama local LLMs
- How to integrate OpenAI API
- How to integrate Hugging Face API
- How to handle API failures safely
- How to build a Streamlit interface
- How to generate PDF reports
- How to store memory across runs
- How to create agent trace logs
- How to explain an AI system clearly

---

## Best Interview Answer

If asked to explain the project, I would say:

I built CareerPilot AI as a multi-agent career assistant that helps candidates prepare for AI/ML roles. It takes a resume, job description, and target role as input. It uses RAG to retrieve relevant context from the resume and JD, then multiple agents analyze the resume, job description, skill gaps, resume improvements, interview preparation, roadmap, and cover letter.

I used LangGraph for workflow orchestration because it provides state, nodes, and edges. I also integrated CrewAI separately to learn role-based multi-agent collaboration. I added an LLM provider switcher that supports Ollama, OpenAI, Hugging Face, and fallback mode.

The project helped me understand RAG, embeddings, FAISS, LangGraph, CrewAI, local LLMs, cloud API integration, prompt engineering, memory, observability, and end-to-end AI application development.

---

## Resume Bullet Points

You can add these to your resume:

- Built CareerPilot AI, a multi-agent career assistant using Python, LangGraph, CrewAI, RAG, FAISS, Streamlit, Ollama, OpenAI API, and Hugging Face API.
- Implemented resume analysis, job description analysis, skill gap detection, resume optimization, interview preparation, roadmap generation, cover letter generation, memory tracking, and PDF export.
- Designed an LLM provider switcher supporting Ollama, OpenAI, Hugging Face, and fallback mode for robust AI response generation.
- Integrated agent trace logging to improve workflow observability, debugging, and explainability.
- Built a RAG pipeline using text chunking, sentence embeddings, FAISS vector search, and context retrieval for agent-based reasoning.

---

## Future Improvements

Planned future improvements:

- Add authentication
- Deploy Streamlit app
- Add database support
- Add live job scraping
- Add LinkedIn profile analyzer
- Add recruiter email generator
- Add interview answer evaluator
- Add Docker support
- Add cloud deployment
- Add voice-based interview preparation
- Add resume scoring dashboard
- Add job application tracker

---

## GitHub Upload Notes

Do not upload:

```text
.env
venv/
outputs/
API keys
Private resume PDFs
Private job descriptions
```

Upload:

```text
agents/
crews/
workflows/
tools/
memory/
data/.gitkeep
app.py
app_langgraph.py
app_streamlit.py
app_crewai.py
config.py
llm_client.py
requirements.txt
test_llm_provider.py
README.md
.env.example
.gitignore
```

---

## Recommended `.gitignore`

```gitignore
# Python cache
__pycache__/
*.py[cod]
*.pyo
*.pyd

# Virtual environments
venv/
env/
.venv/
ENV/

# Environment variables
.env
*.env

# Outputs and generated reports
outputs/
*.pdf
*.docx

# Uploaded private data
data/*.pdf
data/*.docx
data/*.txt
data/*.csv
data/*.json

# Keep data folder structure
!data/.gitkeep

# Logs
*.log
logs/

# OS files
.DS_Store
Thumbs.db

# IDE files
.vscode/
.idea/

# Jupyter
.ipynb_checkpoints/

# Streamlit secrets
.streamlit/secrets.toml

# Model/cache files
.cache/
models/
*.pt
*.pth
*.bin
*.onnx

# Hugging Face / sentence-transformers cache
huggingface/
sentence_transformers/
```

---

## Author

**Jerry James**

AI/ML and Data Science enthusiast building hands-on projects in Machine Learning, Computer Vision, Generative AI, RAG, and Agentic AI.

---

## Project Status

Current version:

```text
Version 14 — GitHub Documentation Ready
```

This project is ready for GitHub upload and interview explanation.
