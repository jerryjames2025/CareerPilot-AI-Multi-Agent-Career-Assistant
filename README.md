# CareerPilot AI — Multi-Agent Career Assistant

CareerPilot AI is an AI-powered multi-agent career assistant designed to help candidates analyze resumes, compare them with job descriptions, identify skill gaps, generate interview preparation plans, optimize resumes, create cover letters, and produce career roadmaps.

The project combines **RAG**, **embeddings**, **FAISS vector search**, **LangGraph workflows**, **CrewAI agents**, **local LLMs with Ollama**, **OpenAI API support**, **Hugging Face API support**, **memory tracking**, **agent trace logs**, and **PDF report generation**.

---

## Project Goal

The goal of this project is to build a practical Agentic AI system that helps job seekers prepare for AI/ML, Data Science, and Generative AI roles.

CareerPilot AI takes:

- Candidate resume
- Job description
- Target role

and generates:

- Resume analysis
- Job description analysis
- Skill gap analysis
- Resume optimization suggestions
- Interview preparation questions
- Career roadmap
- Customized cover letter
- CrewAI-style career recommendation
- Evaluator reflection
- Final career report
- PDF report
- Agent trace logs
- Career progress memory

---

## Key Features

### Resume Analysis Agent

Extracts and analyzes resume content from PDF files.

### Job Description Analysis Agent

Analyzes job descriptions and identifies important technical skills, responsibilities, and expectations.

### Skill Gap Agent

Compares resume skills with JD requirements and calculates a match score.

### Resume Optimizer Agent

Suggests ATS-friendly resume improvements, project bullet rewrites, and role-specific resume keywords.

### Interview Coach Agent

Generates interview questions and project explanation strategies.

### Career Roadmap Agent

Creates a short-term preparation roadmap for the target role.

### Cover Letter Agent

Generates a customized cover letter based on the resume and job description.

### Evaluator Agent

Reviews the generated report and adds final feedback, improvement suggestions, and interview strategy.

### Career Crew Agent

Adds a CrewAI-style role-based collaboration layer with agents such as Resume Expert, JD Strategist, Skill Gap Coach, Interview Strategist, and Career Manager.

### Real CrewAI Integration

Includes an actual CrewAI runner using CrewAI Agents, Tasks, Crew, and sequential process.

### LLM Provider Switcher

Supports multiple LLM providers:

- Ollama local LLM
- OpenAI API
- Hugging Face API
- Fallback mode

### RAG Pipeline

Uses:

- Text chunking
- Embeddings
- FAISS vector store
- Retrieval-augmented generation

### Memory and Progress Tracking

Stores previous career analysis runs and compares the latest performance with older runs.

### Agent Trace Logs

Tracks every workflow step, agent name, task, tools used, duration, status, and output summary.

### PDF Export

Generates a downloadable PDF career report.

### Streamlit UI

Provides an interactive web interface for uploading resumes, pasting job descriptions, viewing reports, and downloading outputs.

---

## Tech Stack

| Category | Tools Used |
|---|---|
| Programming Language | Python |
| UI | Streamlit |
| Workflow Orchestration | LangGraph |
| Multi-Agent Framework | CrewAI |
| RAG | Custom RAG pipeline |
| Vector Database | FAISS |
| Embeddings | Sentence Transformers |
| Local LLM | Ollama |
| Cloud LLM APIs | OpenAI, Hugging Face |
| PDF Reading | PyMuPDF |
| Report Export | ReportLab |
| Configuration | python-dotenv |
| Data Processing | Pandas, NumPy |
| ML Utilities | Scikit-learn |

---

## Project Architecture

```text
Resume PDF + Job Description
        |
        v
Text Extraction
        |
        v
Text Chunking
        |
        v
Embeddings
        |
        v
FAISS Vector Store
        |
        v
RAG Retrieval
        |
        v
LangGraph Multi-Agent Workflow
        |
        |-- Resume Analyzer Agent
        |-- JD Analyzer Agent
        |-- Skill Gap Agent
        |-- Resume Optimizer Agent
        |-- Interview Coach Agent
        |-- Career Roadmap Agent
        |-- Cover Letter Agent
        |-- Career Crew Agent
        |-- Evaluator Agent
        |
        v
Final Career Report
        |
        |-- Markdown Report
        |-- PDF Report
        |-- Agent Trace Logs
        |-- Career Memory



---

# `docs/PROJECT_ARCHITECTURE.md`

```markdown
# CareerPilot AI — Project Architecture

This document explains the architecture of CareerPilot AI, a multi-agent career assistant powered by RAG, LangGraph, CrewAI, and multiple LLM providers.

---

## 1. System Overview

CareerPilot AI takes a candidate resume, a job description, and a target role as input.

The system generates a complete career preparation report containing resume analysis, JD analysis, skill gap analysis, resume optimization, interview questions, roadmap, cover letter, evaluator feedback, and final action plan.

---

## 2. High-Level Architecture

```text
User Input
  |
  |-- Resume PDF
  |-- Job Description Text
  |-- Target Role
  |
  v
Data Processing Layer
  |
  |-- PDF text extraction
  |-- JD loading
  |-- Text cleaning
  |
  v
RAG Layer
  |
  |-- Text chunking
  |-- Embedding generation
  |-- FAISS vector indexing
  |-- Context retrieval
  |
  v
Agent Layer
  |
  |-- Resume Analyzer Agent
  |-- JD Analyzer Agent
  |-- Skill Gap Agent
  |-- Resume Optimizer Agent
  |-- Interview Coach Agent
  |-- Roadmap Agent
  |-- Cover Letter Agent
  |-- Career Crew Agent
  |-- Evaluator Agent
  |
  v
Workflow Layer
  |
  |-- LangGraph state
  |-- LangGraph nodes
  |-- LangGraph edges
  |
  v
Output Layer
  |
  |-- Markdown report
  |-- PDF report
  |-- Agent trace logs
  |-- Career memory
