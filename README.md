# Ltn Chat Extension 🚀

A premium Chrome extension for chatting with local AI models running in WSL. Featuring a sleek glassmorphism design, streaming responses, and markdown support.

## 🛠 Prerequisites

Before using this extension, you need to have a local LLM server running. This setup uses **WSL (Ubuntu)** and **llama.cpp**.

1. **WSL (Windows Subsystem for Linux)**
   - Open PowerShell as Administrator and run:
     ```powershell
     wsl --install
     ```
   - Restart your computer and finish the Ubuntu setup.

2. **llama.cpp**
   - Inside your WSL terminal, install dependencies:
     ```bash
     sudo apt update && sudo apt install build-essential git cmake -y
     ```
   - Clone and build `llama.cpp`:
     ```bash
     git clone https://github.com/ggerganov/llama.cpp
     cd llama.cpp
     mkdir build && cd build
     cmake ..
     cmake --build . --config Release
     ```

## 📥 Downloading the AI Model

We recommend the **Qwen 2.5 7B Instruct** model for a great balance of speed and intelligence.

1. Create a models directory in WSL:
   ```bash
   mkdir -p ~/models
   ```
2. Download the model (GGUF format):
   - Visit [Hugging Face](https://huggingface.co/Qwen/Qwen2.5-7B-Instruct-GGUF) or use `wget`:
     ```bash
     wget -O ~/models/Qwen2.5-7B-Instruct.Q4_K_M.gguf https://huggingface.co/Qwen/Qwen2.5-7B-Instruct-GGUF/resolve/main/qwen2.5-7b-instruct-q4_k_m.gguf
     ```

## 🚀 Speed Launching (Windows)

I've included a `LaunchQwen.bat` file in this folder. Double-click it to:
- Automatically open WSL.
- Navigate to your `llama.cpp` folder.
- Start the OpenAI-compatible server on port `8080`.

*Note: If your file paths are different, right-click `LaunchQwen.bat` and click "Edit" to update your paths.*

## 🧩 Installing the Chrome Extension

1. Open **Chrome** and go to `chrome://extensions/`.
2. Toggle **Developer mode** (top right corner).
3. Click **Load unpacked**.
4. Select this project folder (`LtnWEBAssist`).
5. Click the **Puzzle Piece** icon in Chrome and pin **Ltn Chat Extension**.

## ✨ Features

- **Local & Private**: No data leaves your machine.
- **Markdown Support**: Beautifully rendered code blocks, lists, and headers.
- **Streaming**: See the AI type its response in real-time.
- **Quick Actions**: Copy answers or regenerate responses with one click.
- **Concise Mode**: Optimized for quick, short answers.

## ⚙️ Customization

- **Change Prompt**: Edit `sidepanel.js` and look for the `role: 'system'` message to change how the AI behaves.
- **Server Port**: If you change the port in `llama.cpp`, update the URLs in `sidepanel.js` and `manifest.json`.
