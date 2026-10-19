# Meeting AI Agent - Project Knowledge Base

## Project Goal
Build a fully local, privacy-focused AI meeting assistant capable of listening to meetings, understanding discussions, and generating structured summaries without requiring cloud services or permanent transcript retention.

## Vision
- Capture meeting audio from Teams, Zoom, Google Meet and similar platforms.
- Capture local microphone audio.
- Transcribe conversations continuously.
- Maintain meeting context.
- Identify discussion topics, decisions, action items, risks and unanswered questions.
- Generate structured meeting summaries.
- Preserve privacy by running entirely on local hardware.

## Core Architecture
Teams / Zoom / Meet
→ Audio Capture Layer
→ Faster-Whisper
→ Context Memory
→ Phi-4
→ Summary Generator
→ Markdown / Word / Teams Export

## Technology Decisions
Audio Capture:
- Primary: WASAPI Loopback
- Fallback: VB-Cable / VoiceMeeter

Speech-to-Text:
- Faster-Whisper

Local LLM:
- Primary: Phi-4
- Alternatives: Qwen, Llama

Orchestration:
- Semantic Kernel

Storage:
- SQLite

## Development Environment
Repository: meeting-ai-agent
IDE: VS Code
Source Control: Git + GitHub

## Branch Strategy
main
↓
develop
↓
feature/*

Feature branches:
- feature/audio-capture
- feature/whisper
- feature/phi4
- feature/ui
- feature/diarization
- feature/teams-integration

## Milestones
Milestone 1: Audio Capture Validation
Success: Record meeting audio to WAV.

Milestone 2: Microphone Capture
Success: Record microphone audio separately.

Milestone 3: Faster-Whisper Integration
Success: WAV → Transcript.

Milestone 4: Phi-4 Summaries
Success: Transcript → Executive Summary, Decisions, Actions, Risks, Open Questions.

## Repository Structure
meeting-ai-agent/
├── docs/
├── src/
├── tests/
├── scripts/
├── data/
└── README.md

Current architecture folders:
- audio_capture
- speech_to_text
- diarization
- llm
- summarization
- memory
- storage
- ui
