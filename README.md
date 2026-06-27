# Gemini Voice Chatbot

A voice-enabled AI chatbot built with Google Gemini and ElevenLabs that responds to your messages both in text and audio. Built during an Agentic AI Workshop.

The idea was to go beyond a basic text chatbot — most chatbots just return text, so I wanted to add voice output and proper conversation memory so it actually feels like a real conversation.

---

## Features

- Chat with Google Gemini 2.5 Flash — one of the latest and fastest LLMs available
- Voice responses powered by ElevenLabs text-to-speech (Rachel voice)
- Multi-turn conversation memory — the chatbot remembers what you said earlier in the same session
- Keeps last 10 exchanges in memory to avoid hitting token limits
- Clean Gradio web interface with chat history display
- Example prompts to get started quickly
- Graceful error handling — if audio generation fails, text response still works

---

## Tech Stack

- **LLM:** Google Gemini 2.5 Flash via `google-generativeai`
- **Memory:** LangChain `ConversationBufferMemory` with custom prompt template
- **Voice:** ElevenLabs `text_to_speech` API (eleven_multilingual_v2 model)
- **UI:** Gradio Blocks with chat history and audio output
- **Language:** Python

---

## How to Run

### 1. Clone the repo
```bash
git clone https://github.com/Nikhith-pok/gemini-voice-chatbot.git
cd gemini-voice-chatbot
```

### 2. Install dependencies
```bash
pip install google-generativeai elevenlabs langchain langchain-core langchain-community langchain-google-genai langchain-classic gradio requests
```

### 3. Get API keys
- **Gemini API key** — free at https://aistudio.google.com/app/apikey
- **ElevenLabs API key** — free tier at https://elevenlabs.io/

### 4. Add your keys
Open `chatbot.ipynb` and replace:
```python
GEMINI_API_KEY = "your_gemini_key_here"
ELEVENLABS_API_KEY = "your_elevenlabs_key_here"
```

### 5. Run
Open in Jupyter or Google Colab and run all cells. A Gradio link will appear at the bottom.

---

## How It Works

1. User types a message in the Gradio interface
2. The message along with conversation history is sent to Gemini 2.5 Flash
3. Gemini generates a text response
4. The text response is sent to ElevenLabs which converts it to an MP3 audio file
5. Both the text and audio are returned to the UI simultaneously
6. Conversation history is stored in memory for context in future messages

---

## What I'd Add Next

- Let users switch between different ElevenLabs voices
- Add a system prompt selector (Professional / Creative / Code Helper modes)
- Deploy on Hugging Face Spaces for a live public demo
- Add speech-to-text input so users can speak instead of type

---

Made by Nikhith Reddy — [GitHub](https://github.com/Nikhith-pok) | nikhith.naru@gmail.com
