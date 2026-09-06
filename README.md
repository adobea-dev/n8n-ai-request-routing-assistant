# n8n-ai-request-routing-assistant
AI-powered request routing workflow built with n8n, OpenAI, Google Sheets, Gmail, and JavaScript.

# n8n AI Request Routing Assistant

## Overview

This project is an AI-powered request routing workflow built in n8n. It captures user requests through a form, classifies each request using an AI model, recommends the right owner/team, logs the structured result in Google Sheets, and sends an automated Gmail confirmation to the requester.

The project demonstrates practical workflow automation, AI-assisted request routing, structured data capture, and internal tool building.

## Problem

Small teams often receive requests through scattered channels such as email, forms, chat, and spreadsheets. These requests may be manually reviewed, categorized, assigned, and tracked, which can lead to delays, missed follow-ups, inconsistent routing, and poor visibility.

## Solution

The workflow automates the request intake and routing process by:

1. Collecting request details through an n8n form
2. Using an AI model to classify the request
3. Assigning a priority level
4. Recommending the responsible owner/team
5. Generating a clear next action
6. Logging the request in Google Sheets
7. Sending an automated confirmation email through Gmail

## Workflow Architecture

Form Submission → OpenAI Classification → JavaScript Parsing → Google Sheets Logging → Gmail Confirmation

## Tools Used

- n8n
- OpenAI / n8n AI Gateway
- Google Sheets
- Gmail
- JavaScript
- Workflow automation
- AI-assisted classification

## Key Features

- Request intake form
- AI-based request classification
- Priority assignment
- Recommended owner/team
- Suggested next action
- Structured logging in Google Sheets
- Automated email confirmation
- Simple internal tool workflow

## Sample Use Case

A team member submits a report request saying:

> “We manually compile weekly performance reports from different sheets and send updates to managers. It takes too much time and sometimes the numbers do not match.”

The workflow classifies the request as a report request, assigns high priority, routes it to the Data/Analytics owner, logs the request, and sends a confirmation email.

## Example Output

```json
{
  "ai_category": "Report Request",
  "priority": "High",
  "recommended_owner": "Data/Analytics",
  "next_action": "Review the report compilation process and propose an automation solution.",
  "plain_language_response": "We'll look into automating your report compilation process to save time and ensure accuracy."
}
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
