# ai-multilingual-video-pipeline

🎬 AI Multilingual Video Pipeline

> An open-source, local-first pipeline that turns one English video into multiple language versions — with voice cloning, lip sync, and automated rendering. Built for YouTube creators, indie filmmakers, and brand content teams.

---

📌 Overview

This project is **Service 2** of an AI Creative Production Agency — an automated multilingual video localization pipeline built entirely on open-source tools with zero monthly subscription cost.

**One video in → 4 localized videos out.**

📹 English Video → 🎙️ Transcription → 🌐 Translation → 🎤 Voice Cloning → 👄 Lip Sync → 🎬 Final Render → 📦 Spanish · Hindi · Arabic · Japanese

---

## ✨ Features

- 🆓 **100% open source** — runs entirely on your machine, no API keys needed
- 🌍 **23+ languages** supported including Hindi, Arabic, Japanese, Spanish, Tamil, Telugu
- 🎤 **Zero-shot voice cloning** — clones the original speaker's voice in any language
- 👄 **Lip sync rendering** — re-animates mouth movements to match new audio
- ⚡ **Automated pipeline** — drop a video in a folder, get localized versions out
- 🔄 **Modular design** — swap any tool (e.g. replace Coqui with ElevenLabs) in minutes
- 🤖 **n8n automation** — folder-watcher triggers the pipeline automatically

---

## 🛠️ Tech Stack

| Step | Tool | Purpose |
|------|------|---------|
| Transcription | [OpenAI Whisper]Speech-to-text in 99 languages
| Translation | [LibreTranslate]Free self-hosted text translation
| Voice Cloning | [Coqui XTTS v2]Multilingual TTS + zero-shot voice clone
| Lip Sync | [Wav2Lip]GAN-based video lip sync
| Video Render[FFmpeg]
| Automation | [n8n]| Workflow orchestration

---

## 📁 Folder Structure

The pipeline uses a step-by-step folder system. Each step processes files from its input folder and moves them to the next:

- **1_upload** — Drop your original video here
- **2_transcribe** — Whisper transcript output
- **3_translate** — Translated transcripts in 4 languages
- **4_voice** — Cloned voice audio files
- **5_lipsync** — Lip-synced video files
- **6_output** — Final deliverable videos ready to send to clients

---

## 🚀 Getting Started

### Prerequisites

- Windows 10/11 (64-bit)
- Python 3.11
- FFmpeg
- Git
- Node.js LTS

### Tools to install

- **Whisper** — OpenAI's open-source speech recognition model
- **LibreTranslate** — Self-hosted translation server (no API key needed)
- **Coqui TTS** — Open-source voice cloning using XTTS v2 model
- **Wav2Lip** — Lip sync model (download wav2lip_gan.pth model weights separately)
- **n8n** — Open-source workflow automation

---

## ▶️ How It Works

**Step 1 — Transcription**
Drop a video into the upload folder. Whisper automatically detects the language and transcribes every word spoken with timestamps.

**Step 2 — Translation**
The transcript is sent to LibreTranslate running locally. It produces translated text files in Spanish, Hindi, Arabic, and Japanese simultaneously.

**Step 3 — Voice Cloning**
Coqui XTTS v2 extracts a 15-second voice sample from the original video, then generates speech in each target language using the cloned voice.

**Step 4 — Lip Sync**
Wav2Lip takes the original video and the new cloned audio, and re-renders the speaker's lip movements to match perfectly.

**Step 5 — Final Render**
FFmpeg merges the lip-synced video with the normalised audio, burns in subtitles, and exports a YouTube-ready H.264 MP4 file for each language.

**Automation**
n8n watches the upload folder every minute. The moment a new video appears, it triggers the full pipeline automatically. No manual steps required.

---

## 🔄 Swapping Tools

The pipeline is fully modular — each step is independent. Any tool can be upgraded without touching the rest of the pipeline.

| Current tool | Upgrade option | Benefit |
|---|---|---|
| Coqui TTS | ElevenLabs API ($5/mo) | Higher quality voice cloning |
| LibreTranslate | DeepL API ($5.49/mo) | Better translation accuracy |
| Wav2Lip | HeyGen API (pay per use) | Professional lip sync quality |

---

## 💰 Cost

| Setup | Monthly cost |
|---|---|
| Full open source (this repo) | **$0** |
| + ElevenLabs Starter (better voice) | $5/mo |
| + DeepL Pro (better translation) | $5.49/mo |
| + HeyGen API (better lip sync) | Pay per use |

---

## 📋 System Requirements

- RAM: 8GB minimum (16GB recommended for voice cloning)
- Storage: ~10GB for all AI model files
- OS: Windows 10/11 (macOS/Linux support coming)
- GPU: Optional but recommended for faster Wav2Lip processing

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

## 👤 Author

**Manoj Kumar** — AI Creative Production Agency, Bengaluru, India
