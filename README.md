# SentinelAI
An AI-powered Intrusion Detection System for Startups  

## Project Overview  
SentinelAI is an autonomous, AI-powered Intrusion Detection System (IDS) designed specifically for small startups that lack the budget and expertise for a dedicated security team. It autonomously detects, triages, and escalates network threats to give startups an affordable, accessible layer of protection without needing a full security team.

## Problem Statement  
Many startups lack the budget and expertise for a dedicated security team, leaving them exposed. When an attack hits, they often mishandle the situation due to lack of experience or resources, risking further or even worse vulnerabilities and attacks. Even when they respond, inexperienced handling can inadvertently create new vulnerabilities, opening the door to future attacks. SentinelAI changes that by implementing a detective network traffic security system in a way that's affordable and accessible.  

## Architecture
SentinelAI uses a 4-agent Plan-Act-Reflect architecture:

- **Scanner (temp 0.1)** — reads incoming network log entries and flags anomalies or suspicious patterns  
- **Triage (temp 0.0)** — classifies flagged entries as a real threat or false positive  
- **Response (temp 0.0)** — for confirmed known-pattern threats, logs the action and applies a predefined safe response  
- **Escalation** — for anything critical or unresolved after 5 iterations, flags for human review rather than acting autonomously

## Tech Stack
- **Language:** Python 3.11
- **AI Model:** Google Gemini (via Gemini API)
- **Dataset:** UNSW-NB15 — a publicly available network traffic dataset with labeled attack categories (Normal, DoS, Exploits, etc.)
- **Agent Framework:** Agentic loop architecture (Scanner → Triage → Response → Escalation)
- **Development Platform:** Google Antigravity
