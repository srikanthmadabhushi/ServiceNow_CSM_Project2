# ServiceNow_CSM_Project2
ServiceNow CSM | Agentic AI Smart Escalation Flow (Yokohama PDI)
# ServiceNow CSM | Agentic AI Smart Escalation Flow (Yokohama PDI)

## Overview
This project simulates an **Agentic AI** that reads a Customer Case, detects urgency/tone, and **automatically escalates** or routes it to the right queue—logging clear AI reasoning.

## Flow Logic
1. **Trigger:** Customer Case created or updated
2. **If (AI Escalation Decision):**
   - Short description contains: `urgent`, `critical`, `angry`, `not happy`
   - OR **Priority** is **1 – Critical**
   - OR **Sentiment** is **Negative**
3. **Then (True):**
   - **Assignment group** = Escalation Team
   - **Priority** = 1 – Critical
   - **AI Escalation Notes** = “AI detected critical tone/negative sentiment; escalated automatically.”
4. **Else (False):**
   - **Assignment group** = Customer Support
   - **AI Escalation Notes** = “AI detected normal tone/priority; sent to standard queue.”

## Highlights
- No-code **Flow Designer** (Yokohama PDI)
- Demonstrates **agentic reasoning** (read → decide → act → explain)
- Works with the same custom **Customer Case** table used in Project 1

## Diagram
![Flow](Diagrams/Flow Diagram.png)

## Test Scenarios
| Short Description | Sentiment | Priority | Expected |
|---|---|---|---|
| “Customer angry about billing issue” | Negative | 3 | **Escalated** |
| “Need urgent help, not working” | Neutral | 2 | **Escalated** |
| “General account query” | Neutral | 3 | **Standard queue** |
