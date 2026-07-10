
---

# `docs/INTERVIEW_EXPLANATION.md`

```markdown
# CareerPilot AI — Interview Explanation

This document contains a clear explanation of CareerPilot AI for interviews.

---

## 1. Short Project Explanation

CareerPilot AI is a multi-agent career assistant that helps candidates prepare for job applications. It analyzes a resume and job description, identifies skill gaps, generates resume improvement suggestions, creates interview questions, builds a career roadmap, generates a cover letter, and produces a final career report.

The system uses RAG, embeddings, FAISS, LangGraph, CrewAI, Ollama, OpenAI API support, Hugging Face API support, memory, trace logs, and PDF report generation.

---

## 2. One-Minute Explanation

I built CareerPilot AI as a Multi-Agent Career Assistant for AI/ML job preparation. The system takes a resume, a job description, and a target role as input. It then uses multiple specialized agents to analyze the resume, understand the job description, calculate a skill match score, identify missing skills, suggest resume improvements, generate interview preparation questions, create a roadmap, and generate a customized cover letter.

I used RAG by extracting resume and JD text, splitting them into chunks, creating embeddings, storing them in FAISS, and retrieving relevant context for each agent. I used LangGraph to orchestrate the workflow using nodes, edges, and shared state. I also integrated CrewAI separately to understand role-based collaboration using agents, tasks, crews, and sequential execution.

The project supports multiple LLM providers, including Ollama, OpenAI, Hugging Face, and fallback mode. It also generates trace logs, stores career progress memory, and exports the final report as Markdown and PDF.

---

## 3. Problem Statement

Job seekers often struggle to understand how well their resume matches a job description. They may not know which skills are missing, how to improve their resume, what interview questions to prepare, or how to explain their projects.

CareerPilot AI solves this by automating the career preparation process using multiple AI agents.

---

## 4. Why I Built This Project

I built this project to learn and demonstrate:

- Generative AI application development
- RAG pipelines
- Embeddings and vector databases
- Multi-agent workflows
- LangGraph orchestration
- CrewAI integration
- Local and cloud LLM usage
- API integrations
- Prompt engineering
- Practical AI product design

---

## 5. Main Agents

### Resume Analyzer Agent

Analyzes the candidate resume and extracts skills, projects, strengths, and improvement areas.

### JD Analyzer Agent

Analyzes the job description and identifies required skills, responsibilities, and role expectations.

### Skill Gap Agent

Compares resume skills with JD skills and calculates the match score.

### Resume Optimizer Agent

Suggests ATS-friendly resume improvements and project bullet rewrites.

### Interview Coach Agent

Generates interview questions and preparation points.

### Career Roadmap Agent

Creates a short-term roadmap to prepare for the target role.

### Cover Letter Agent

Generates a customized cover letter.

### Career Crew Agent

Adds CrewAI-style role-based collaboration.

### Evaluator Agent

Reviews the final report and adds reflection, feedback, and final strategy.

---

## 6. RAG Explanation

RAG means Retrieval-Augmented Generation.

In this project, I used RAG to make the agents more context-aware.

The process is:

```text
Resume/JD Text
  ↓
Text Chunks
  ↓
Embeddings
  ↓
FAISS Vector Store
  ↓
Relevant Context Retrieval
  ↓
Agent Response
