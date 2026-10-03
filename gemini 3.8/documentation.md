# Gemini 3.8 Live API Documentation Summary

Based on the official Google documentation for Gemini 3.8 released in September 2026, here is an overview of the new Gemini 3.8 Live API features, resources, and implementation details for your project.

## Overview
The **Gemini 3.8 Live API** is part of the Gemini Enterprise Agent Platform. It focuses on real-time, bidirectional multimodal streaming, allowing for fluid voice and video interactions with the model.

### Key Features
1. **Multimodal Streaming**: Supports native, real-time streaming of audio and video inputs over WebSocket connections.
2. **Extended Thinking**: Includes advanced reasoning capabilities that allow the model to narrate its thought process in the background without interrupting the live voice interaction.
3. **Asynchronous Tool Calling (MCP)**: Supports real-time function calling during a live session, allowing the model to trigger external tools (perfect for your Xiaozhi server architecture).
4. **Live Avatar**: Built-in support for generating real-time avatar synthesis during live sessions.

### Key Models
*   `gemini-3.8-flash`: Fast, intelligent model designed for complex multi-step reasoning.
*   `gemini-3.8-live` and `gemini-3.8-live-extended`: Tailored specifically for natural voice interactions.

## How to Get Started

### 1. Developer Documentation & API References
- **Developer Guide**: Comprehensive details are available in the [Developer's Guide to Gemini 3.8 Live](https://cloud.google.com/vertex-ai/docs) on Google Cloud.
- **Google AI Studio**: You can test the Multimodal Live API without code directly in [Google AI Studio](https://aistudio.google.com/).
- **SDK**: Start by installing the updated SDK:
  ```bash
  pip install -U google-genai
  ```
- **Node.js (for this repo)**: You will continue to use `@google/genai` (as seen in your `package.json`), but you'll need to point the model initialization to `gemini-3.8-live`.

### 2. Implementation in Your Relay Server
Since your server (`app.js` and `providers/`) already implements a WebSocket bridge using the `gemini-2.5-flash-native-audio-preview` or similar, migrating to 3.8 Live generally involves:
1. Updating the model name in your `.env` (e.g., `GEMINI_MODEL=gemini-3.8-live`).
2. Ensuring your `@google/genai` SDK is updated to the latest version supporting 3.8.
3. Reviewing the updated WebSocket session lifecycle documented in the Google Gen AI SDK for any new initialization parameters.

---
*Note: If you need to implement the new "Extended Thinking" or "Live Avatar" specific endpoints, refer to the [Gemini Live API Reference](https://ai.google.dev/) for precise payload schemas.*
