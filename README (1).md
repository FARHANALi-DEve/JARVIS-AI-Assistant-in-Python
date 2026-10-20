<div align="center">

# J.A.R.V.I.S.
### A voice-first Python desktop assistant with a cinematic interface.

**PYTHON · SPEECH RECOGNITION · DESKTOP AUTOMATION · GEMINI · CUSTOMTKINTER**

[GitHub repository](https://github.com/FARHANALi-DEve/JARVIS-AI-Assistant-in-Python) · [Developer](https://github.com/FARHANALi-DEve)

</div>

---

## Meet JARVIS

JARVIS brings together voice commands, spoken responses, a typed fallback, familiar Windows utilities, and optional Gemini-powered questions. Its sci-fi HUD includes animated interface elements, command feedback and system information; a terminal-only interface is available as a fallback.

**The AI feature requires your own Gemini API key and an internet connection.** Local commands can run without an AI key.

## What you can do

- **Talk or type:** microphone speech input, text-to-speech and typed commands.
- **Desktop shortcuts:** open Windows apps, folders, websites and system tools.
- **Automation:** selected keyboard, mouse, volume, clipboard and screenshot actions.
- **Productivity:** saved local notes, daily task file, time/date, calculator and disk status.
- **AI questions:** ask Gemini in natural language when configured.
- **Flexible display:** CustomTkinter sci-fi HUD, terminal mode and UI preview.

JARVIS does **not** provide unrestricted command execution, delete arbitrary files or shut down the PC automatically.

## Install on Windows

The application is in a **nested folder** within this repository:

```text
JARVIS-AI-Assistant-in-Python/
└── jarvis/
    └── JARVIS-AI-Assistant-in-Python/
        ├── voice_assistant.py
        ├── jarvis_sci_fi_ui.py
        ├── requirements.txt
        └── daily_tasks.txt
```

Open PowerShell in the **inner** `jarvis/JARVIS-AI-Assistant-in-Python` folder, then run:

```powershell
py -3 -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe voice_assistant.py
```

For the no-window terminal experience:

```powershell
.\.venv\Scripts\python.exe voice_assistant.py --terminal
```

> Windows microphone support depends on your audio setup and supported Python package builds. If the HUD cannot load, JARVIS can fall back to terminal mode.

## Optional Gemini setup

Create your key through Google AI Studio. Place it in an **untracked `.env` file** beside `voice_assistant.py`:

```dotenv
GEMINI_API_KEY=your_private_api_key
```

Then start JARVIS and enter `ask explain how decorators work`. Model availability, quotas and billing depend on your Gemini account; no model is guaranteed to remain available forever. To diagnose configuration problems:

```powershell
.\.venv\Scripts\python.exe gemini_probe.py
```

Never put the key in source code, a screenshot, or a Git commit.

## Try these commands

```text
help
what time is it
system status
remember Finish the portfolio README
read notes
open github
open calculator
search Python asyncio tutorial
weather in Lahore
calculate 12 * (4 + 2)
ask What is cloud computing?
```

For continuous microphone listening or a self-check:

```powershell
python voice_assistant.py --continuous
python voice_assistant.py --self-test
python test_ui_smoke.py
```

The daily brief is loaded from `daily_tasks.txt`. `JARVIS_DAILY_TASKS_FILE` and `JARVIS_MUSIC_DIR` can override the default paths.

## Technology and files

| Component | Library / location |
| :--- | :--- |
| Speech input | `SpeechRecognition`, `PyAudioWPatch` |
| Speech output | `pyttsx3` |
| Desktop UI | `customtkinter`, `jarvis_sci_fi_ui.py` |
| AI responses | `google-genai`, environment-based key |
| Automation | `pyautogui` |
| App entry | `voice_assistant.py` |
| Local tests | `test_ui_smoke.py`, `--self-test` |

### Responsible use

Desktop automation can interact with the active window. Review voice commands before running JARVIS around private documents or sensitive apps. `jarvis_notes.json` and any task files contain local user data; keep them off public repositories.

---

<div align="center"><sub>Engineered by <a href="https://github.com/FARHANALi-DEve">Farhan Ali</a> · Python × AI × Human-Computer Interaction</sub></div>
