# n8n-ai-chat-data-analysis-workflow
Overview

This workflow allows a user to upload a dataset through chat, processes the data, sends it to an AI agent for analysis, and returns both insights and auto-generated charts in the final response.

It runs on-demand, triggered manually through the chat interface rather than on a schedule.

Workflow Steps

- Chat Trigger – Starts the workflow when a user sends a message or uploads a file.

- Check for File – Detects whether a dataset was attached.

- Clean & Process Data (Code Node) – Converts the uploaded file into structured JSON for analysis.

- Pass Through (Code Node) – Sends original chat text to the AI along with the processed data.

- AI Agent (Groq Model + Memory) – Performs the data analysis and generates insights.

- HTTP Request – Generate Charts – Sends summarized data to a chart-generation API.

- Add Charts to Response (Code Node) – Combines AI findings + chart URLs into a single chat reply.

- Chat Response – Returns the final analyzed output back to the user.

Import Instructions

- In n8n, open Workflows → Import from File

- Upload the .json file

- Add your Groq API key + Chart API key

- Activate and open chat panel to test

Requirements

- n8n instance (self-hosted or cloud)

- Groq API key (or compatible LLM provider)

- Chart API endpoint (e.g., quickchart.io)
