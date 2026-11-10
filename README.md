# AI-Powered GTM Marketing Agent

## Project Overview

This project is an AI-powered Go-To-Market (GTM) Marketing Agent developed using n8n. It automates marketing research, content creation, quality review, revision, and human approval using multiple AI agents.

The workflow was tested using AI Study Buddy, a fictional AI-powered study assistant for college students.

## Technologies Used

- n8n — Workflow automation
- OpenAI — AI agents and content generation
- Pinecone — Vector database
- RAG — Retrieval-Augmented Generation
- Gmail — Human approval notifications

## Workflow Architecture

1. **Chat Trigger:** Receives the user's marketing request.
2. **GTM Research & Planning Agent:** Retrieves relevant product information using Pinecone and RAG.
3. **GTM Content Creator Agent:** Generates LinkedIn posts, promotional emails, blogs, and advertisements.
4. **GTM Content Review Agent:** Checks the generated content for accuracy, tone, and completeness.
5. **IF Node:** Routes content based on the initial review result.
6. **GTM Content Revision Agent:** Improves content that fails the initial review.
7. **GTM Final Review Agent:** Evaluates the revised content.
8. **Gmail and Wait Nodes:** Send approval notifications and collect human decisions.
9. **Human Approval IF Nodes:** Route content based on Approve or Reject decisions.

## Testing and Results

The workflow was tested for content generation, AI review, revision, Gmail notifications, and human approval routing.

Successful tests included:
- AI Final Review returning PASS.
- Original content approval routing.
- Revised content approval routing.
- Revised content rejection routing.
- Original rejection condition verified in a separate test workflow.

## Key Learnings

This project helped me understand multi-agent systems, RAG, prompt engineering, conditional routing, debugging, and human-in-the-loop automation.

## Limitations

The workflow prepares and reviews marketing content but does not automatically publish content to social media platforms.

## Setup Instructions

1. Import the workflow JSON into n8n.
2. Configure your own OpenAI, Pinecone, and Gmail credentials.
3. Prepare and connect a Pinecone knowledge base.
4. Verify the AI agent prompts and workflow settings.
5. Configure the Gmail recipient and approval process.
6. Test the workflow using the chat trigger.

**Security:** Do not upload API keys, private credentials, or live approval URLs.
