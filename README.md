# AI Learning Platform Chatbot (n8n + Gemini)

This project is an AI-powered chatbot built using **n8n** .\
The chatbot helps users get information about courses and frequently
asked questions (FAQ) from a Google Sheets database.

If the chatbot cannot find an answer, it stores the user's question and
mobile number in a Google Sheet so the team can contact them later.

------------------------------------------------------------------------

## Features

-   AI-powered chatbot using Google Gemini
-   Supports **multiple languages**
    -   English
    -   Hindi
    -   Gujarati
-   Retrieves **course information** from Google Sheets
-   Answers **FAQ questions** automatically
-   Stores **unanswered questions** for follow-up
-   Simple conversation **memory support**

------------------------------------------------------------------------

## Workflow Overview

The workflow includes the following nodes:

1.  **Chat Trigger**
    -   Receives chat messages from the chatbot interface.
2.  **AI Agent**
    -   Processes the user question and decides which tool to use.
3.  **Google Gemini Chat Model**
    -   Generates intelligent responses.
4.  **Simple Memory**
    -   Maintains conversation context.
5.  **Google Sheets Integration**
    -   Get Course Info
    -   Get FAQ
    -   Append unanswered queries

------------------------------------------------------------------------

## Google Sheets Structure

### Sheet 1: Course

Example columns: - Course Name - Description - Duration - Fees

### Sheet 2: FAQ

-   Question
-   Answer

### Sheet 3: Unanswered Queries

-   Customer Question
-   Mobile Number

------------------------------------------------------------------------

## How It Works

1.  User sends a message through the chatbot.
2.  The AI Agent analyzes the question.
3.  If the question matches:
    -   **Course Data → returns course details**
    -   **FAQ Data → returns the FAQ answer**
4.  If the question is not found:
    -   The chatbot asks for the user's mobile number.
    -   The query is stored in **Google Sheets**.

------------------------------------------------------------------------

## Tech Stack

-   **n8n** -- workflow automation
-   **Google Gemini API** -- AI responses
-   **Google Sheets API** -- data storage

------------------------------------------------------------------------

## Setup Instructions

### 1. Install n8n

Run n8n using Docker:

docker run -it --name n8n -p 5678:5678 docker.n8n.io/n8nio/n8n

------------------------------------------------------------------------

### 2. Import Workflow

1.  Open n8n
2.  Click **Import Workflow**
3.  Upload the `workflow.json` file

------------------------------------------------------------------------

### 3. Connect Credentials

Add the following credentials:

-   Google Gemini API
-   Google Sheets OAuth

------------------------------------------------------------------------

### 4. Configure Google Sheets

Create a Google Sheet with three sheets:

-   Course
-   FAQ
-   Unanswered Queries

Update the sheet IDs in the workflow if needed.

------------------------------------------------------------------------

## Example Use Cases

User Questions:

-   What courses do you offer?
-   What is the duration of the Python course?
-   Do you provide certificates?

If the system cannot answer:

The chatbot will ask for the user's mobile number and store the query
for manual follow-up.

------------------------------------------------------------------------
