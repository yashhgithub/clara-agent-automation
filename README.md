# Clara Agent Automation Pipeline

## Overview

This repository implements a zero-cost automation pipeline that converts
demo call transcripts and onboarding updates into structured Clara AI
voice agent configurations.

The system generates:

- Structured Account Memo JSON
- Retell Agent Draft Specification
- Versioned updates (v1 → v2)
- Change logs for onboarding modifications

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

Onboarding Call  
↓  
Patch Update  
↓  
Account Memo v2  
↓  
Agent Spec v2  
↓  
Change Log

## Repository Structure
