# Clara Agent Automation Pipeline

## Overview

This project demonstrates a zero-cost automation pipeline that converts demo call transcripts and onboarding updates into structured Clara AI voice agent configurations.

The system produces:

- Structured Account Memo JSON
- Retell Agent Draft Specification
- Versioned updates (v1 → v2)
- Change logs showing onboarding updates

## Architecture

Demo Call Transcript  
↓  
Extraction Pipeline  
↓  
Account Memo v1  
↓  
Agent Prompt Generator  
↓  
Retell Agent Spec v1  

Onboarding Update  
↓  
Account Memo Patch  
↓  
Account Memo v2  
↓  
Agent Spec v2  
↓  
Change Log

## Repository Structure

data/  
&nbsp;&nbsp;&nbsp;&nbsp;demo_calls/  
&nbsp;&nbsp;&nbsp;&nbsp;onboarding_calls/

outputs/  
&nbsp;&nbsp;&nbsp;&nbsp;accounts/  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;bens-electric/  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v1/  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v2/  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;changes.md  

scripts/  
workflows/

## Running the Pipeline

1. Place transcripts inside

data/demo_calls  
data/onboarding_calls  

2. Run the extraction script

python scripts/extract_demo.py

3. The pipeline generates:

- account memo JSON
- agent configuration
- onboarding update version

## Retell Setup

If Retell API access is unavailable on free tier:

1. Create an agent in Retell dashboard
2. Copy the generated system prompt
3. Configure transfer numbers manually

## Limitations

- Rule-based extraction
- No automated transcription
- Mock orchestration workflow

## Future Improvements

- Whisper transcription
- LLM-based extraction
- Fully automated n8n pipeline
