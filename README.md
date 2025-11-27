🚀 Free Claude Code Setup With Google Gemini

A complete & beginner-friendly guide to install, configure, and run Claude Code + Gemini API Router on Windows.

✅ Step 1 — Generate FREE Google Gemini API Key

Go to Google AI Studio → https://aistudio.google.com

Click on “Get API Key”

Click “Create API Key”

Name your Key & Project

Create the key

Save it for configuration

Move to Step 2

✅ Step 2 — Install Claude Code + Routing Modules

Open PowerShell as Administrator, then check your Node version:

node -v


If version is 20 or above, continue.
If not, download the latest Node: https://nodejs.org

Install Claude Code + Router:

npm install -g @anthropic-ai/claude-code @musistudio/claude-code-router

✅ Step 3 — Create Required Folders
mkdir $HOME/.claude-code-router
mkdir $HOME/.claude

✅ Step 4 — Create config.json

⚠ Windows PowerShell does not support EOF blocks, so use Notepad.

Open config file:

notepad $HOME/.claude-code-router/config.json


Paste this JSON (replace $GOOGLE_API_KEY with your real key):

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


Save & close.

✅ Step 5 — Set Your Gemini API Key as Environment Variable
[System.Environment]::SetEnvironmentVariable('GOOGLE_API_KEY', 'YOUR_API_KEY_HERE', 'User')


Example:

[System.Environment]::SetEnvironmentVariable('GOOGLE_API_KEY', 'AIzaSy.............', 'User')


Restart PowerShell → verify:

echo $env:GOOGLE_API_KEY

✅ Step 6 — Verify Installation
claude --version
ccr version
echo $env:GOOGLE_API_KEY


If all commands respond correctly → ✔ Setup is good.

✅ Step 7 — Daily Workflow (How to Use)
Window 1 — Start Router Server
ccr start


If you see:

⚠ API key is not set. HOST is forced to 127.0.0.1.
Loaded JSON config from: C:\Users\Admin\.claude-code-router\config.json


This is normal. Keep this window open.

Window 2 — Start Claude Code

Go to your project folder:

cd your-project-folder


Start the coding environment:

ccr code

✅ Step 8 — Test the AI

Type:

hi


If it replies → 🎉 Setup Successful!

Best of luck for your Hackathon! 🏆

Made with 💝 by Nazia Imran
<p align="center"> <a href="https://github.com/syedjalees" target="_blank"> <img src="https://img.shields.io/badge/Made%20by-Nazia%20Imran-blue?style=for-the-badge&logo=github" /> </a> </p>