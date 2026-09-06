# n8n AI Request Routing Assistant

## Overview

The n8n AI Request Routing Assistant is a simple workflow automation project that captures user requests through a form, uses AI to classify and prioritize each request, recommends the right owner or team, logs the request in Google Sheets, and sends an automated Gmail confirmation to the requester.

The project demonstrates how n8n can be used to build a practical internal tool for request intake, routing, structured record keeping, and user communication.

## Live Demo

A production version of the request form is available here:

[Open the AI Request Routing Form] https://adobeaess.app.n8n.cloud/form/3108ee3d-7d7b-4fa1-a439-22efe6fc55bf

Note: This is a demo workflow. Please submit only test or demo requests.

## Problem

Small teams often receive requests through scattered channels such as email, chat, forms, and spreadsheets. Without a clear routing process, requests can be delayed, assigned to the wrong person, duplicated, or forgotten.

This creates problems such as:

- Slow response time
- Manual request triage
- Inconsistent prioritization
- Poor visibility into open requests
- Repeated follow-ups
- Lack of a single source of truth

## Solution

This workflow automates the request routing process.

When a user submits a request, the workflow:

1. Captures the request through an n8n form
2. Sends the request details to an AI model for classification
3. Assigns a category and priority level
4. Recommends the right owner or team
5. Generates a suggested next action
6. Logs the structured result in Google Sheets
7. Sends an automated confirmation email to the requester

## Workflow Architecture

```text
Form Submission
      ↓
AI Classification
      ↓
JavaScript Output Parsing
      ↓
Google Sheets Logging
      ↓
Gmail Confirmation

Tools Used
n8n
OpenAI / n8n AI Gateway
Google Sheets
Gmail
JavaScript
Workflow automation
AI-assisted classification
Workflow Steps
1. Form Submission

The workflow starts with an n8n form that collects request details from the user.

The form captures:

Name
Email
Company / Team
Request Type
Request Description
Urgency
Preferred Response Time
2. AI Classification

The submitted request is sent to an AI model. The AI reviews the request and returns a structured classification.

The AI output includes:

Request category
Priority level
Recommended owner or team
Suggested next action
Plain-language response for the requester
3. JavaScript Output Parsing

A JavaScript Code node parses the AI response and converts it into clean structured fields that can be used by the next workflow steps.

This helps ensure the workflow does not rely on messy free-text AI output.

4. Google Sheets Logging

The structured request is logged in Google Sheets.

The sheet acts as a lightweight tracking system and single source of truth for submitted requests.

Logged fields include:

Timestamp
Name
Email
Company
Request Type
Description
Urgency
Preferred Response Time
AI Category
Priority
Recommended Owner
Next Action
Plain Language Response
Status
5. Gmail Confirmation

After the request is logged, the workflow sends an automated confirmation email to the requester.

The email includes:

Request category
Priority
Recommended owner/team
Next action
Plain-language summary
Sample Request
Our team manually compiles weekly performance reports from different Google Sheets and email updates. The process takes too much time, the numbers sometimes do not match, and managers often ask for the same report repeatedly. We need a better way to route the request, log it, and automate the reporting workflow.
Example AI Output
{
  "ai_category": "Report Request",
  "priority": "High",
  "recommended_owner": "Data/Analytics",
  "next_action": "Review the reporting process and consolidate the weekly performance data into a structured automated workflow.",
  "plain_language_response": "Your report request has been received and routed to the data team for review."
}
Business Value

This workflow helps teams reduce manual request triage and improve operational visibility.

It supports:

Faster request routing
Clearer ownership
Better prioritization
Structured request tracking
Reduced manual follow-up
More consistent requester communication
A lightweight single source of truth for submitted requests
Screenshots
Workflow Canvas

Request Form

Google Sheets Log

Gmail Confirmation

AI Output

Repository Structure
n8n-ai-request-routing-assistant/
│
├── README.md
├── workflow/
│   └── ai-request-routing-assistant.json
│
├── screenshots/
│   ├── workflow-canvas.png
│   ├── request-form.png
│   ├── google-sheet-log.png
│   ├── gmail-confirmation.png
│   └── ai-output.png
│
└── docs/
    └── project-notes.md
