
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
