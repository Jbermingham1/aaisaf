# TA06 — Voice AI Exploitation

## Overview

**Voice AI systems** — including AI-powered phone agents, interactive voice response (IVR) replacements, voice assistants, and real-time voice cloning platforms — represent a rapidly expanding attack surface that no existing security framework covers. By 2026, AI voice agents handle millions of inbound and outbound calls daily across healthcare, finance, customer service, and sales. These systems combine speech-to-text (STT), large language models (LLMs), and text-to-speech (TTS) into a pipeline where each component introduces distinct vulnerabilities.

Voice AI exploitation is uniquely dangerous because it operates on a channel humans inherently trust — the human voice. Unlike text-based attacks that users can review before acting, voice interactions happen in real-time, creating pressure to respond without verification. The combination of synthetic voice generation, adversarial audio, and telephony signal manipulation creates attack vectors that bridge the gap between traditional phreaking, social engineering, and AI prompt injection.

**No existing security framework systematically catalogues voice AI attack techniques.** OWASP LLM covers text-based prompt injection but not speech-specific vectors. MITRE ATLAS includes some adversarial ML techniques but does not address telephony integration, voice cloning in active calls, or conversation flow manipulation. AAISAF is the first framework to provide comprehensive coverage of voice AI exploitation techniques.

## Why This Matters

- **$243,000 stolen** in the first documented AI voice deepfake fraud (2019 WSJ-reported CEO impersonation via synthetic voice)
- **Real-time voice cloning** now achievable with 3 seconds of reference audio (Microsoft VALL-E, 2023; open-source RVC/so-vits-svc widely available)
- **AI voice agents deployed at scale** across industries — Retell AI, Vapi, Bland AI, and others process millions of calls with minimal human oversight
- **STT adversarial examples** demonstrated by Carlini & Wagner can produce arbitrary transcriptions from benign-sounding audio
- **Traditional vishing** already accounts for $39.5B in annual losses (FTC, 2024) — AI voice agents multiply both attack and defence surface
- **No authentication standard** exists for verifying voice identity against synthetic speech in real-time calls

## Applicable System Types

- **Type E**: Voice-Enabled AI System (primary) — any system that accepts speech input, generates speech output, or both
- **Type G**: Composite systems with voice AI components — multi-modal systems where voice is one interface among several

## Techniques

| ID | Technique | Severity | AISS |
|----|-----------|----------|------|
| [TA06.001](../techniques/TA06/TA06.001-voice-prompt-injection.md) | Voice Prompt Injection via Speech | High | 7.0 |
| [TA06.002](../techniques/TA06/TA06.002-synthetic-voice-spoofing.md) | Synthetic Voice Spoofing / Deepfake | Critical | 8.5 |
| [TA06.003](../techniques/TA06/TA06.003-conversation-flow-bypass.md) | Conversation Flow Bypass | Medium | 5.5 |
| [TA06.004](../techniques/TA06/TA06.004-audio-adversarial-examples.md) | Audio Adversarial Examples | High | 7.2 |
| [TA06.005](../techniques/TA06/TA06.005-credential-harvesting.md) | Credential Harvesting via Voice Agent | Critical | 8.3 |
| [TA06.006](../techniques/TA06/TA06.006-dtmf-signal-injection.md) | DTMF and Telephony Signal Injection | High | 6.8 |
| [TA06.007](../techniques/TA06/TA06.007-voice-agent-vishing.md) | Voice Agent Vishing / AI-Assisted Social Engineering | Critical | 8.7 |
| [TA06.008](../techniques/TA06/TA06.008-stt-pipeline-exploitation.md) | Speech-to-Text Pipeline Exploitation | Medium | 5.8 |
| [TA06.009](../techniques/TA06/TA06.009-realtime-voice-cloning.md) | Real-Time Voice Cloning in Active Call | Critical | 9.0 |

## Attack Tree

```
Voice AI Attack Surface
├── Input Layer (Speech → Text)
│   ├── TA06.001 Voice Prompt Injection (spoken injection payloads)
│   ├── TA06.004 Audio Adversarial Examples (crafted audio → wrong transcription)
│   └── TA06.008 STT Pipeline Exploitation (language/accent/homophone attacks)
├── Logic Layer (Conversation Management)
│   ├── TA06.003 Conversation Flow Bypass (skip auth, reach unintended branches)
│   └── TA06.005 Credential Harvesting (manipulate agent into collecting secrets)
├── Output Layer (Identity & Voice)
│   ├── TA06.002 Synthetic Voice Spoofing (impersonate real people)
│   └── TA06.009 Real-Time Voice Cloning (voice MITM in active calls)
├── Telephony Layer (Signal & Infrastructure)
│   └── TA06.006 DTMF Signal Injection (telephony signal manipulation)
└── Weaponisation Layer (Scaling Attacks)
    └── TA06.007 Voice Agent Vishing (AI-powered social engineering at scale)
```

## Key References

- Carlini, N. & Wagner, D. (2018). "Audio Adversarial Examples: Targeted Attacks on Speech-to-Text." IEEE S&P Workshop.
- Müller, N. et al. (2019). "Speech Is Silver: Targeted Adversarial Examples Against ASR Systems." DLS Workshop.
- Wall Street Journal. (2019). "Fraudsters Used AI to Mimic CEO's Voice in Unusual Cybercrime Case."
- Microsoft Research. (2023). "VALL-E: Neural Codec Language Models are Zero-Shot Text to Speech Synthesizers."
- Federal Trade Commission. (2024). Consumer Sentinel Network Data Book — Fraud Loss Statistics.
- NIST. (2024). "Adversarial Machine Learning: A Taxonomy and Terminology of Attacks and Mitigations." NIST AI 100-2e2023.
- Retell AI, Vapi, Bland AI. (2024-2025). Production voice AI agent platforms — deployment scale documentation.
