# Product Ideation: Resume + Mock Interview Platform

Note that this is just a rudimentary idea of what is planned and can change with suggestions, improvements and solving bottlenecks

---

## One-liner
An AI platform that analyzes a resume against a target role, suggests fixes with templates, then runs a job-specific mock interview (TTS questions, STT answers, AI assessment) built from the same resume/JD context.

## Core Wedge
Most tools do resume feedback OR mock interviews, not both tied together. The interview questions should be generated *from* the resume's weak points + the target JD, not generic — that's the differentiator.

## Features (v1 scope)

### 1. Resume Analyzer
- Upload resume, paste target role/JD
- Score (1–10) against the role
- Feedback on content, phrasing, relevance, formatting
- Suggest pre-filled templates to fix weak sections

### 2. JD → Question Generator
- User pastes job role or full JD
- System generates a tailored question set (behavioral + role-specific)
- Pulls weak areas flagged in resume analysis to probe those directly

### 3. Mock Interview Loop
- TTS asks questions aloud
- STT captures spoken answers
- AI assesses answers against a defined rubric (not just "LLM vibes")
- Rubric candidates: structure (STAR), specificity, relevance to JD, filler-word/confidence signals from audio

### 4. Feedback Report
- Per-question scoring + overall summary
- Ties back to resume gaps ("you said X in your resume but struggled to elaborate when asked")

## Suggested Build Order
1. Resume analyzer + templates (fastest — most overlap with prior experience)
2. JD → question generator (text-only first, validate question quality)
3. Add STT/TTS once scoring logic is solid
4. Tie resume gaps → interview questions (the real differentiator)

## Open Questions
- Niche: general job seekers vs. specific (new grads? SWE-only? case interviews?)
- Assessment rubric: define explicitly before building, not as an afterthought
- Cost control: STT/TTS cost scales with usage — cheaper fallback model needed at scale
- Free vs. paid tier split (templates free, mock interviews gated?)

## Tech Stack Notes (based on existing skills)
- Backend: FastAPI
- LLM orchestration: LangChain / LangGraph
- Validation: Pydantic (strict schemas for question gen + assessment output)
- STT/TTS: reuse pipeline learnings from prior speech-to-text optimization work
- Frontend: React.js + Vite
- DB: MongoDB or PostgreSQL (resume data, session history)

## Risks to Watch
- Category is crowded — don't ship "just another resume grader"
- Assessment quality makes or breaks trust — generic feedback kills retention
- Audio-in-the-loop cost scaling needs budgeting from day one
