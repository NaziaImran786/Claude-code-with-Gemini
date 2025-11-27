# 🚀 Free Claude Code Setup With Google Gemini

A complete and beginner-friendly guide to install, configure, and run **Claude Code + Gemini API Router** on Windows.

---

## ✅ Step 1 — Generate FREE Google Gemini API Key

1. Visit **Google AI Studio** → https://aistudio.google.com  
2. Click **“Get API Key”**  
3. Click **“Create API Key”**  
4. Enter a name for your key  
5. Create the key  
6. Copy and save it  
7. Move on to Step 2  

---

## ✅ Step 2 — Install Claude Code + Router

Open **PowerShell as Administrator** and check Node version:

```sh
node -v
```

If version is **20+**, continue.  
Otherwise download → https://nodejs.org

Install:

```sh
npm install -g @anthropic-ai/claude-code @musistudio/claude-code-router
```

---

## ✅ Step 3 — Create Required Folders

```sh
mkdir $HOME/.claude-code-router
mkdir $HOME/.claude
```

---

## ✅ Step 4 — Create config.json

⚠ PowerShell does **not support EOF**, so use Notepad.

Open config file:

```sh
notepad $HOME/.claude-code-router/config.json
```

Paste this (replace **$GOOGLE_API_KEY** with your real API key):

```json
{
  "LOG": true,
  "LOG_LEVEL": "info",
  "HOST": "127.0.0.1",
  "PORT": 3456,
  "API_TIMEOUT_MS": 600000,
  "Providers": [
    {
      "name": "gemini",
      "api_base_url": "https://generativelanguage.googleapis.com/v1beta/models/",
      "api_key": "$GOOGLE_API_KEY",
      "models": [
        "gemini-2.5-flash",
        "gemini-2.0-flash"
      ],
      "transformer": {
        "use": ["gemini"]
      }
    }
  ],
  "Router": {
    "default": "gemini,gemini-2.5-flash",
    "background": "gemini,gemini-2.5-flash",
    "think": "gemini,gemini-2.5-flash",
    "longContext": "gemini,gemini-2.5-flash",
    "longContextThreshold": 60000
  }
}
```

Save and close.

---

## ✅ Step 5 — Set Gemini API Key as Environment Variable

```sh
[System.Environment]::SetEnvironmentVariable('GOOGLE_API_KEY', 'YOUR_API_KEY_HERE', 'User')
```

Example:

```sh
[System.Environment]::SetEnvironmentVariable('GOOGLE_API_KEY', 'AIzaSy........', 'User')
```

Restart PowerShell → verify:

```sh
echo $env:GOOGLE_API_KEY
```

---

## ✅ Step 6 — Verify Installation

```sh
claude --version
ccr version
echo $env:GOOGLE_API_KEY
```

✔ If all commands respond → setup successful.

---

## ✅ Step 7 — Daily Workflow

### **Window 1 — Start Router Server**

```sh
ccr start
```

Expected output:

```
⚠ API key is not set. HOST is forced to 127.0.0.1.
Loaded JSON config from: C:\Users\Admin\.claude-code-router\config.json
```

✔ This is normal.

---

### **Window 2 — Start Claude Code**

Go to your project folder:

```sh
cd your-project-folder
```

Start AI coding:

```sh
ccr code
```

---

## ✅ Step 8 — Test the AI

Type:

```
hi
```

If it replies → 🎉 **Setup completed successfully!**

Best of luck for your **Hackathon!** 🏆

---

## 💝 Made by **Nazia Imran**

<p align="center">
  <a href="https://github.com/syedjalees" target="_blank">
    <img src="https://img.shields.io/badge/Made%20by-Nazia%20Imran-blue?style=for-the-badge&logo=github" />
  </a>
</p>
