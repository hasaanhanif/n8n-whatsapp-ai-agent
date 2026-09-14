# n8n WhatsApp AI Agent

This project is a **multimodal WhatsApp AI automation built with n8n and Google Gemini**.

The workflow can receive and respond to:

- Text messages
- Voice / audio messages
- Images

For audio and image inputs, the workflow first processes the content and converts the relevant information into text. That text is then sent to **Google Gemini**, which generates the final response. The response is automatically sent back to the user through WhatsApp.

## Workflow

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
 |      Convert     Convert /
 |      to Text     Analyze
 |          |         |
 +----------+---------+
            |
            v
       Google Gemini
            |
            v
   Generate AI Response
            |
            v
    WhatsApp Reply
```

## Features

- Automatic WhatsApp message trigger
- Text message processing
- Voice / audio message processing
- Image processing
- Audio-to-text conversion
- Image-to-text / image understanding
- Google Gemini integration
- Automatic AI-generated replies
- Multimodal message handling in a single workflow

## Technologies Used

- n8n
- Google Gemini
- WhatsApp Cloud API
- Meta Developer Platform
- Webhooks
- REST APIs
- Audio processing
- Image processing

## Demo Video

Watch the complete workflow demonstration here:

[Watch on YouTube](https://youtu.be/k5n_JpD5UZI)

## Files

This folder contains:

```text
README.md
whatsapp-ai-agent-workflow.json
```

The JSON file can be imported directly into n8n.

## How to Import

1. Download the JSON workflow file.
2. Open your n8n instance.
3. Create a new workflow.
4. Select **Import from File**.
5. Import the JSON file.
6. Configure your own WhatsApp and Google Gemini credentials.
7. Update any required webhook settings.
8. Activate the workflow.


