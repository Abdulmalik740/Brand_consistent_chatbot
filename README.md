# Apex Stride — Adaptive AI Chatbot

An AI-powered customer support chatbot for Apex Stride that adapts its tone and responses based on context. All brand settings, tone rules, and product config live in `brand_config.yaml`.

---

## Requirements

- Python 3.9+
- An OpenAI API key

Install dependencies:

```bash
pip install openai flask pyyaml python-dotenv
```

---

## Setup

**1. Clone the repo**
```bash
git clone https://github.com/Abdulmalik740/Brand_consistent_chatbot.git
cd Brand_consistent_chatbot
```

**2. Add your OpenAI key**

Create a `.env` file in the project root:
```
OPENAI_API_KEY=sk-your-key-here
```

**3. (Optional) Point to a custom config**

By default the app reads `brand_config.yaml` from the project root. To use a different file:
```bash
export BRAND_CONFIG_PATH=/path/to/your_config.yaml
```

---

## Running the App

**Web interface (recommended)**
```bash
python web_interface_universal.py
```
Then open [http://localhost:5000](http://localhost:5000)

**Command-line demo**
```bash
python universal_adaptive_framework.py
```
Runs the demo scenarios from `brand_config.yaml` and prints responses with performance stats.

---

## Project Files

| File | What it does |
|---|---|
| `brand_config.yaml` | All config — brand voice, products, tone rules, LLM settings |
| `universal_adaptive_framework.py` | Main pipeline — ties all modules together |
| `web_interface_universal.py` | Flask web UI |
| `context_understanding_engine.py` | Detects emotion, intent, urgency from user messages |
| `tone_adaptation_engine.py` | Picks the right tone profile for each situation |
| `brand_consistency_guard.py` | Validates responses against brand rules before sending |
| `conversation_state_manager.py` | Tracks session state, user profile, risk signals |
| `config_loader.py` | Loads and caches `brand_config.yaml` |
| `performance_tracker.py` | Tracks latency, tokens, and cost per step |

---

## Changing the Brand

Edit `brand_config.yaml` — no Python changes needed. Key sections to update:

- `brand` — name, tagline, personality
- `voice_guidelines` — what to do and not do
- `products` — your product catalog
- `tone_profiles` — tone variants and when to use them
- `special_rules` — support flows (refund, replacement, etc.)
- `llm` — which models to use and at what temperature

---

## Environment Variables

| Variable | Required | Default | Description |
|---|---|---|---|
| `OPENAI_API_KEY` | Yes | — | Your OpenAI API key |
| `BRAND_CONFIG_PATH` | No | `./brand_config.yaml` | Path to config file |
