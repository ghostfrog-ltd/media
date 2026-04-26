# ghostfrog-media

System Architecture & Code Generation Request: Local AI Avatar Pipeline

Role: You are a Senior Python Automation Engineer and AI Systems Architect.

Context & Hardware:
I am building a 100% local, autonomous video generation pipeline for YouTube Shorts featuring a digital talking avatar. I am running this on an Apple Mac with an M4 Pro chip and 64GB of Unified Memory.

Strict Constraints:

Zero Cloud APIs: Do not suggest OpenAI, HeyGen, ElevenLabs, or any paid cloud services. Everything must run locally.

Apple Silicon Optimization: All machine learning libraries must target Apple's mps (Metal Performance Shaders) or use the MLX framework.

No Web-UI Mimicry: No Selenium or Playwright browser automation for the generation phase. We are using pure Python and local APIs.

The Tech Stack:

LLM / Scripting: Ollama (running Llama-3.1-70B locally).

Audio / TTS: A high-quality local Text-to-Speech engine (e.g., Fish-Speech, XTTSv2, or Kokoro) running via Python.

Visuals / Avatar: ComfyUI running locally. We will use a static generated character image (created via Flux) and animate it using LivePortrait inside ComfyUI.

Orchestration & Assembly: Python 3.11+ and FFmpeg.

The Pipeline Workflow:
Write an orchestration script (main.py) that executes the following chain:

Script Generation: Calls the local Ollama API to generate a 60-second video script based on a given topic. It must return plain spoken text without stage directions.

Voice Generation: Passes the text to the local TTS engine to output an audio.wav file.

Avatar Animation: Sends an API payload to the local ComfyUI server (running on 127.0.0.1:8188). The payload must trigger a LivePortrait workflow, passing the audio.wav and a static avatar_base.jpg to generate the talking head video.

Final Assembly: Uses FFmpeg (via the subprocess module) to combine the final video and audio, outputting final_short.mp4.

Deliverables Required:

The complete folder structure for this project.

The requirements.txt specifically tailored for macOS/Apple Silicon.

The complete main.py orchestration script.

The JSON API payload structure needed to trigger the ComfyUI LivePortrait workflow.

Tone: Keep the response highly technical, pragmatic, and provide production-ready code. Do not suggest SaaS alternatives.
