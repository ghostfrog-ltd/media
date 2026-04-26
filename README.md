Ghostfrog Media: Evergreen Batch Pipeline
Role: You are a Senior Python Automation Engineer and AI Systems Architect.

Context & Hardware:
I am building a 100% local, autonomous batch-processing video generation pipeline for YouTube Shorts. The focus is strictly on "Evergreen" educational content. I am running this on an Apple Mac with an M4 Pro chip and 64GB of Unified Memory.

Strict Constraints:

Zero Cloud APIs (Except Research): Do not suggest OpenAI, HeyGen, or ElevenLabs for generation. We will only use the google-genai SDK (Gemini API) at the very start to generate a list of 10-15 evergreen topics. Everything else runs locally.

Apple Silicon Optimization: All machine learning libraries must target Apple's mps backend or use the MLX framework.

Robust Error Handling (The Night-Shift Rule): This script will run unattended overnight. If the TTS or ComfyUI API fails for one script in the batch, the program MUST log the error to failed_renders.log and continue to the next item. Do not let the program halt.

The Tech Stack:

Research Agent: Gemini API (Search Grounding) to compile a JSON array of evergreen topics with high search volume.

LLM / Scripting: Ollama (running Llama-3.1-70B locally).

Audio / TTS: A high-quality local Text-to-Speech engine (e.g., Fish-Speech, Kokoro) running via Python.

Visuals / Avatar: ComfyUI running locally (LivePortrait workflow).

Orchestration & Assembly: Python 3.11+ and FFmpeg.

The Pipeline Workflow (Batch Mode):
Write an orchestration script (main.py) that executes the following loop:

Topic Generation: Hits the Gemini API to request a batch of 10 evergreen concepts within a specific niche.

The Batch Loop: Iterates through the returned JSON list. For each topic:

Script Generation: Calls the local Ollama API. Constraint: The prompt must explicitly forbid time-sensitive words ("today", "recently", "news").

Metadata Generation: Asks Ollama to generate a YouTube Title, Description, and Tags, saving them as topic_name_metadata.json.

Voice Generation: Passes the script text to the local TTS engine to output audio.wav.

Avatar Animation: Sends a JSON payload to the local ComfyUI server (127.0.0.1:8188) to trigger the LivePortrait workflow, using a static avatar_base.jpg.

Final Assembly: Uses FFmpeg to combine the generated video and audio into final_topic.mp4.

Deliverables Required:

The complete folder structure.

The requirements.txt tailored for macOS/Apple Silicon.

The complete main.py batch orchestrator script with rigorous try/except error logging.

The exact JSON payload structure needed to interface with the ComfyUI API.

Tone: Keep the response highly technical, pragmatic, and provide production-ready code.
