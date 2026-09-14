# n8n-whatsapp-ai-agent
Multimodal WhatsApp AI agent built with n8n that processes text, voice messages, and images and automatically sends AI-generated responses.
# Multimodal WhatsApp AI Agent

An AI-powered WhatsApp automation built with **n8n** and **Google Gemini** that can receive and respond to **text messages, voice notes, and images**.

The workflow automatically detects the incoming message type, converts audio or image content into text when required, sends the extracted text to Gemini for understanding, and then sends an AI-generated response back to the user on WhatsApp.

## Features

- Automatically triggers when a WhatsApp message is received
- Supports normal text messages
- Supports WhatsApp voice notes / audio messages
- Supports image messages
- Converts audio content into text before AI processing
- Extracts or interprets image content and converts it into text
- Sends the processed text to Google Gemini
- Generates contextual AI responses
- Automatically replies to the user through WhatsApp
- Built completely as an automated n8n workflow

## How It Works

```text
Incoming WhatsApp Message
          |
          v
   WhatsApp Trigger
          |
          v
 Detect Message Type
    /      |      \
   /       |       \
Text     Audio     Image
 |          |         |
 |          v         v
 |     Convert to   Convert /
 |        Text      Analyze
 |          |         |
 \__________|_________/
            |
            v
      Text Processing
            |
            v
       Google Gemini
            |
            v
 Generate AI Response
            |
            v
    Send WhatsApp Reply
```

## Message Processing

### Text Messages

When a normal text message is received, the workflow directly sends the message content to **Google Gemini**.

Gemini analyzes the message and generates a relevant response.

The response is then automatically sent back to the user through WhatsApp.

### Voice / Audio Messages

When a user sends a voice note or audio message:

1. The workflow detects that the incoming message is audio.
2. The audio is retrieved and processed.
3. The spoken content is converted into text.
4. The generated text is sent to Google Gemini.
5. Gemini understands the user's request and generates a response.
6. The response is automatically sent back through WhatsApp.

### Image Messages

When a user sends an image:

1. The workflow detects the image message.
2. The image is retrieved and processed.
3. The content of the image is interpreted and converted into text.
4. The extracted information is sent to Google Gemini.
5. Gemini generates a contextual response based on the image content.
6. The response is automatically sent back to the WhatsApp user.

## Technologies Used

- **n8n** — Workflow automation and orchestration
- **Google Gemini** — AI understanding and response generation
- **WhatsApp Cloud API** — Receiving and sending WhatsApp messages
- **Meta Developer Platform** — WhatsApp application and webhook configuration
- **Webhooks** — Real-time incoming message handling
- **Audio-to-Text Processing** — Converts voice messages into text
- **Image-to-Text / Vision Processing** — Converts image content into text for AI processing
- **REST APIs** — Communication between external services

## Workflow Architecture

The workflow follows a branching architecture where the incoming WhatsApp message is first classified by message type.

```text
WhatsApp
   |
   v
n8n Trigger
   |
   v
Message Type Detection
   |
   +-------------------+-------------------+
   |                   |                   |
   v                   v                   v
 Text                Audio               Image
   |                   |                   |
   |             Audio -> Text       Image -> Text
   |                   |                   |
   +-------------------+-------------------+
                       |
                       v
                  Gemini AI
                       |
                       v
                Generate Response
                       |
                       v
                WhatsApp Reply
```

## Use Cases

This type of automation can be extended for:

- AI customer support assistants
- WhatsApp business assistants
- Frequently asked question automation
- Lead qualification
- Appointment assistance
- Product information bots
- AI sales assistants
- Internal business support systems
- Multimodal customer-service workflows

## Project Structure

```text
n8n-whatsapp-ai-agent/
|
├── README.md
|
├── workflow/
|   └── whatsapp-ai-agent-workflow.json
|
└── screenshots/
    ├── workflow-overview.png
    ├── text-message-demo.png
    ├── audio-message-demo.png
    └── image-message-demo.png
```

## Importing the Workflow

To use the workflow:

1. Download the workflow JSON file from the `workflow` folder.
2. Open your n8n instance.
3. Select **Import from File**.
4. Import `whatsapp-ai-agent-workflow.json`.
5. Configure your own WhatsApp credentials.
6. Configure your own Google Gemini credentials.
7. Update the required webhook and API settings.
8. Activate the workflow.
9. Send a test message to the connected WhatsApp number.

## Required Configuration

You will need your own:

- n8n instance
- Meta Developer account
- WhatsApp Cloud API configuration
- WhatsApp access credentials
- Google Gemini API credentials
- Webhook configuration

## Security Notice

All credentials, API keys, access tokens, phone numbers, and sensitive configuration should be removed before publishing the workflow publicly.

The workflow shared in this repository is intended for portfolio and educational purposes.

Users importing the workflow must configure their own credentials and service connections.

## Demo

A video demonstration of the workflow shows the agent responding to:

- Text messages
- Voice / audio messages
- Image messages

**Demo video:** Add your YouTube demo link here.

## What This Project Demonstrates

This project demonstrates practical experience with:

- n8n workflow development
- AI automation
- Multimodal AI workflows
- WhatsApp API integration
- Webhook configuration
- Message-type routing
- Audio processing
- Image processing
- Google Gemini integration
- API-based automation
- End-to-end automated response systems

## Author
Hasaan Hanif

AI Automation & n8n Developer
