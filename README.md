# 🤖 AI Resume Screening System

An intelligent resume screening system that evaluates candidates using AI-powered analysis with LangChain and LangSmith tracing.

## 📖 Overview

This project automates resume screening through a 4-step AI pipeline:
1. **Extract** skills and experience from resumes
2. **Match** candidates against job requirements  
3. **Score** candidates using a 100-point rubric
4. **Explain** decisions with detailed reasoning

## ✨ Features

- ✅ Automated skill extraction from resumes
- ✅ Objective scoring (0-100 points)
- ✅ Explainable AI with evidence-based reasoning
- ✅ LangSmith tracing for debugging
- ✅ Anti-hallucination safeguards
- ✅ FREE Google Gemini API

## 🎯 Results

| Candidate | Experience | Score | Decision |
|-----------|------------|-------|----------|
| Dr. Sarah Chen | 7+ years, PhD | 100/100 | ✅ Strongly Recommend |
| Michael Rodriguez | 3 years, MS | 55/100 | 🟡 Consider |
| Jessica Thompson | 0 years, BS | 10/100 | ❌ Do Not Recommend |


## 📊 Pipeline Architecture

The system processes resumes through a sequential 4-step chain built with LangChain LCEL:

```text
       Resume Text
            ↓
    ┌───────────────┐
    │    Extract    │ ──→ Skills, Experience, Education
    └───────────────┘
            ↓
    ┌───────────────┐
    │     Match     │ ──→ Matched Skills, Gaps, Match %
    └───────────────┘
            ↓
    ┌───────────────┐
    │     Score     │ ──→ Score Breakdown (0-100)
    └───────────────┘
            ↓
    ┌───────────────┐
    │    Explain    │ ──→ Strengths, Gaps, Recommendation
    └───────────────┘
            ↓
 LangSmith Tracing (All steps logged for observability)
```

## 🛠️ Technologies Used

The system is built using a modern AI stack focused on modularity and observability:

* **Python 3.9+**: The core programming language for the pipeline.
* **LangChain**: The primary framework used for LLM orchestration and data flow.
* **Google Gemini**: Utilized as the reasoning engine via the **FREE** LLM API.
* **LangSmith**: Employed for full-stack tracing, debugging, and pipeline monitoring.
* **LCEL (LangChain Expression Language)**: Used to create declarative, modular chains for seamless data transitions between steps.



## 🔍 Scoring Rubric

The system evaluates candidates against a total of **100 points** across five key categories to ensure an objective and consistent screening process.

| Category | Max Points | Criteria |
| :--- | :---: | :--- |
| **Technical Skills** | 30 | Match quality and proficiency in required technical skills. |
| **Experience** | 25 | Total years of professional experience and industry relevance. |
| **Education & Certs** | 15 | Highest degree level attained and relevant professional certifications. |
| **Tools & Tech** | 15 | Hands-on proficiency with required software, platforms, and tools. |
| **Additional Value** | 15 | Leadership experience, published research, and preferred qualifications. |
| **TOTAL** | **100** | |



## 📈 Sample Output

The following report demonstrates the system's evaluation of a top-tier candidate, showcasing the structured scoring and evidence-based strengths analysis.

```text
======================================================================
SCREENING REPORT: Dr. Sarah Chen
======================================================================

👤 Candidate: Dr. Sarah Chen
📊 Score: 100/100
🏷️  Tier: Strong Fit

📊 SCORE BREAKDOWN:
Technical Skills.............. 30/30
Experience.................... 25/25
Education & Certs............. 15/15
Tools & Tech.................. 15/15
Additional Value.............. 15/15
TOTAL......................... 100/100

✅ KEY STRENGTHS:
• Deep Technical Expertise Across ML Stack
• Extensive Cloud and MLOps Experience
• Proven Leadership and Mentorship Capabilities

🎯 RECOMMENDATION: Strongly Recommend
Confidence: High
