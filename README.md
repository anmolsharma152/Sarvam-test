# Sarvam AI Testbed & Experimentation Bench

A dedicated sandbox and component testbench for exploring, validating, and benchmarking [Sarvam AI](https://docs.sarvam.ai) models and APIs (LLMs, Speech-to-Text, Text-to-Speech, Translation, and Document AI).

## Architectural Role

This repository acts as the isolated **Hardware Lab / Component Testbench**:
- **Scope**: Direct SDK experiments, isolated endpoint benchmarks, audio format validation, and feature verification.
- **Decoupled**: Serves as the validation bed for vendor-specific parameters before consuming them via clean provider interfaces (`BaseSTT`, `BaseTTS`, `BaseLLM`) in upstream production systems.

## Capabilities Covered

- **LLMs & Reasoning**: `sarvam-105b` (128K context MoE) and `sarvam-105b-conversations` (32K context).
- **Speech-to-Text (STT)**: `saaras:v4` (5 modes: `transcribe`, `translate`, `verbatim`, `translit`, `codemix`).
- **Text-to-Speech (TTS)**: `bulbul:v3` (30+ authentic Indian voices, expressiveness & pace controls).
- **Translation & Transliteration**: `mayura:v1` (conversational Hinglish) and `sarvam-translate:v1` (22 scheduled Indian languages).
- **Document Intelligence**: Sarvam Vision Doc AI (OCR & structured schema extraction).

## Quickstart

### 1. Prerequisites & Environment Setup

```bash
# Clone the repository
git clone https://github.com/anmolsharma152/Sarvam-test.git
cd Sarvam-test

# Create virtual environment and install dependencies
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### 2. Configure API Credentials

Obtain an API key from [Sarvam AI Dashboard](https://dashboard.sarvam.ai) or [Indus Developer Portal](https://indus.sarvam.ai/developer).

```bash
cp .env.example .env
# Edit .env and paste your key
SARVAM_API_KEY=sk_...
```

### 3. Run the Initial Verification Script

```bash
python main.py
```

Expected output:
```text
I am an AI assistant created by Sarvam, here to help you with information and tasks.
```

## License

MIT
