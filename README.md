
# 🤖 Kahoot Hackathon Challenge

Welcome to the Kahoot Hackathon! 🎉  
In this fun and fast-paced challenge, you'll use automation, OCR, and AI to **play Kahoot quizzes** — then **improve the bot** to dominate upcoming rounds.

This repo provides a working base version. Your job is to **hack, extend, and win!**

---

## 🧠 Project Overview

- Automates joining a Kahoot quiz.
- Takes screenshots of questions and answers.
- Uses OCR + an LLM to choose and click the correct answer.
- Built using Playwright, OpenCV, Tesseract OCR, and a local Ollama-hosted LLM.

---

## 📁 Project Structure

| Notebook | Purpose |
|----------|---------|
| `00_setup_environment.ipynb` | Installs all required dependencies (Playwright, Tesseract, Python libs, etc.) |
| `01_kahoot_bot_playground.ipynb` | Main automation logic for playing Kahoot using screenshots + LLM |

---

## 🖥️ System Prerequisites (Pre-configured for you)

You’ve been provided with:
- Ubuntu VM (already logged in)
- Docker installed ✅
- [Ollama](https://ollama.com) installed ✅
- This repo cloned into your home directory ✅

---

## 🚀 How to Start

### 🔌 Step 1: Launch JupyterLab in Docker

```bash
docker run -d --name jupyterlab --gpus all --network host \
-v /home/demouser/Documents/workspace/kahoot_hackathon:/home/jovyan/work \
-e JUPYTER_TOKEN='password' \
--user root -e GRANT_SUDO=yes \
jupyter/tensorflow-notebook start-notebook.sh \
--ServerApp.allow_password_change=False
```

> Replace the volume path if your project is in a different directory.

---

### 🌐 Step 2: Open JupyterLab

1. Open Firefox browser.
2. Go to: [http://127.0.0.1:8888](http://127.0.0.1:8888)
3. Enter password: **`password`**

---

### 🧪 Step 3: Test Your Ollama Setup

Inside a terminal:

```bash
ollama list
```

You should see a list of available models. Make sure at least one is downloaded (e.g., `qwen2.5vl:7b-fp16`).

Pull additional models using:
```bash
ollama pull 
```
⚠️ Note: Make sure the available GPU has enough memory to load the selected model. Overloading the GPU may crash or freeze the system.

---

## 💡 What to Do Next?

1. Open `00_setup_environment.ipynb` and run all cells to set up the environment.
2. Open `01_kahoot_bot_playground.ipynb`, join a Kahoot game, and test the bot.
3. Start improving:
   - Use better models or prompting.
   - Improve OCR accuracy.
   - Add decision-making logic.
   - Speed up performance.
   - Detect image questions in the screenshot.
   - Your imagination is the limit!

---

## 🏆 Goal

Make your version the **fastest and most accurate Kahoot player** of the hackathon.

Happy hacking! 🚀
