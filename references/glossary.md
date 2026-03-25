# Glossary

Terms are defined according to ISO/IEC 27000 and ISO/IEC 22989 (AI concepts) where applicable. Novel terms introduced by AAISAF are marked with *.

---

## A

**AAISAF** *
Australian AI Security Assessment Framework. An open-source, evidence-based AI security assessment methodology with technique-level taxonomy and Australian regulatory mapping.

**AISS** *
AI Impact Severity Score. AAISAF's severity scoring system combining CVSS base score with five AI-specific impact metrics. Scale: 0.0–10.0.

**Agent (AI)**
An AI system that can take autonomous actions, use tools, execute code, or interact with external systems beyond generating text responses.

**APP**
Australian Privacy Principle. The 13 principles in Schedule 1 of the Privacy Act 1988 governing how entities handle personal information.

**ATLAS**
Adversarial Threat Landscape for Artificial-Intelligence Systems. MITRE's knowledge base of adversary tactics and techniques targeting AI/ML systems.

## C

**Cascade Potential** *
AISS metric measuring whether exploitation in one AI component can propagate to connected components or systems. Scale: 0–10.

**CVSS**
Common Vulnerability Scoring System. Industry-standard vulnerability severity rating (v3.1 or v4.0).

## D

**Deep Assessment** *
AAISAF assessment type involving full technique-level active adversarial testing over 5–10 days.

**DTMF**
Dual-Tone Multi-Frequency. Signalling tones used in telephony systems, relevant to voice AI exploitation (TA06).

## E

**Embedding**
A numerical vector representation of text, used in RAG systems for semantic search.

**Essential Eight**
Australian Signals Directorate (ASD) baseline mitigation strategies for cyber security incidents. Mandatory for Australian federal government entities.

## G

**Guardrail**
A safety or security control applied to an AI system to prevent harmful outputs or actions. May be implemented at the prompt, output filter, or application layer.

## I

**Indirect Prompt Injection**
An attack where malicious instructions are placed in data sources (documents, web pages, databases) that the AI system retrieves and processes, causing the AI to follow the attacker's instructions.

## J

**Jailbreaking**
Techniques that manipulate an AI system into bypassing its safety guidelines or content policies.

## K

**Knowledge Base**
A structured or unstructured data repository used by RAG systems for information retrieval.

## L

**LLM**
Large Language Model. A neural network trained on large text datasets capable of generating human-like text.

## M

**MCP**
Model Context Protocol. An open standard (released by Anthropic, November 2024) for connecting AI systems to external tools and data sources.

**MCP Server**
A service that exposes tools, resources, and prompts to AI systems via the Model Context Protocol.

**Multi-Agent System**
An AI architecture where multiple AI agents collaborate, delegate tasks, or compete, often sharing information and tool access.

## N

**NDB**
Notifiable Data Breach. The Australian scheme (Part IIIC, Privacy Act 1988) requiring entities to notify the OAIC and affected individuals of eligible data breaches.

**NIST AI RMF**
National Institute of Standards and Technology AI Risk Management Framework. A voluntary framework for managing risks in AI system design, development, and deployment.

## O

**OWASP LLM Top 10**
The Open Worldwide Application Security Project's list of the top 10 most critical vulnerabilities in LLM applications (2025 edition).

## P

**Persistence** *
AISS metric measuring how long the effects of exploitation persist, from ephemeral (single response) to permanent (irreversible modification).

**Prompt Injection**
An attack where crafted input causes an AI system to deviate from its intended instructions, either directly (via user input) or indirectly (via retrieved data).

## Q

**Quick Self-Assessment** *
AAISAF assessment type using checklist-based evaluation over approximately 30 minutes.

## R

**RAG**
Retrieval-Augmented Generation. An architecture that augments LLM responses with information retrieved from external knowledge sources.

**Rug Pull Attack** *
An MCP attack where a tool's description or behaviour is modified after the user has approved it, exploiting the gap between approval-time and execution-time behaviour.

## S

**SOCI Act**
Security of Critical Infrastructure Act 2018 (Australia). Imposes security obligations on entities responsible for critical infrastructure assets.

**Standard Assessment** *
AAISAF assessment type covering all applicable tactics over 1–2 days.

**System Prompt**
The initial instruction set provided to an LLM that defines its behaviour, personality, and constraints. Also called "system message."

## T

**Tactic** *
In AAISAF's taxonomy, a category of adversary objective (e.g., "Prompt Manipulation"). Equivalent to MITRE ATT&CK tactic concept.

**Technique** *
In AAISAF's taxonomy, a specific method to achieve a tactic's objective (e.g., "Direct Prompt Injection"). Equivalent to MITRE ATT&CK technique concept.

**Tool Poisoning** *
An MCP attack where a malicious tool description contains hidden instructions that manipulate the AI system's behaviour.

**Tool Shadowing** *
An MCP attack where a malicious tool's description references other legitimate tools by name, intercepting or modifying their behaviour.

## V

**VAISS/AI6**
Voluntary AI Safety Standard. Australia's 10 voluntary AI safety guardrails published September 2024 under the AI6 initiative.

**Vector Database**
A database optimised for storing and querying vector embeddings, used in RAG systems.

**Voice AI**
AI systems that interact via speech, including speech-to-text (STT), text-to-speech (TTS), and end-to-end voice conversation systems.

**Vishing**
Voice phishing. Social engineering attacks conducted via telephone, relevant to voice AI exploitation where AI agents may be used as vishing tools or targets.
