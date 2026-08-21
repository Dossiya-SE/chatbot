# Streamlit Chatbot — API Integration Learning Artifact

This repository is a small **Streamlit + OpenAI API integration exercise**.

It is based on the Streamlit conversational-app template/tutorial pattern and is maintained here as a learning artifact. It is **not** presented as an original foundation model, production conversational-AI platform, RAG system, autonomous agent, or evaluated safety-critical assistant.

## What the code actually implements

[`streamlit_app.py`](streamlit_app.py) currently:

- creates a Streamlit chat interface;
- asks the user to supply an API key through a password input;
- creates an OpenAI client;
- stores conversation turns in `st.session_state`;
- sends the accumulated message history to the chat-completions API;
- streams the assistant response back to the UI;
- stores the streamed response in session state.

The code is therefore evidence of a basic API/UI integration pattern, not evidence of model training or advanced AI architecture.

## Current architecture

```text
browser
→ Streamlit UI
→ user-supplied API key
→ OpenAI API client
→ chat-completions request
→ streamed response
→ Streamlit session state
```

## Provenance

The source itself links to Streamlit's conversational-app tutorial. This repository should be read as a **template-derived learning implementation**.

That provenance matters: adapting a tutorial correctly is useful engineering practice, but it is different from claiming original algorithmic authorship.

## Current model configuration

The committed code is hard-coded to:

```python
model="gpt-3.5-turbo"
```

API/model availability changes over time. The repository does not claim that this historical configuration is the recommended or currently available production configuration.

Before running the project, verify current API documentation and update the model/configuration as required.

## Local execution

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
streamlit run streamlit_app.py
```

On Windows, activate the environment with the appropriate `.venv\Scripts\activate` command.

## Security boundary

The application asks the user for an API key through a password field. That UI choice does **not** by itself make the application production-secure.

A production design should address, as applicable:

- secret storage and rotation;
- server/client trust boundaries;
- logging and accidental key exposure;
- rate limiting and abuse controls;
- authentication / authorization;
- request validation;
- cost controls;
- data-retention and privacy requirements;
- model/content-safety requirements;
- dependency updates and vulnerability management.

No API key should be committed to Git.

## Evaluation boundary

This repository does not currently include an evaluation harness for:

- factuality;
- hallucination rate;
- instruction following;
- latency;
- cost;
- safety;
- robustness;
- adversarial prompts;
- domain-specific accuracy.

Therefore the existence of a working chat interface must not be interpreted as evidence that the assistant is reliable for a particular domain.

## What this repository demonstrates

The public source supports evidence of basic experience with:

- Streamlit application structure;
- API-client initialization;
- conversational state handling;
- streaming model output;
- simple secret-input UX;
- reading and adapting official/tutorial code patterns.

## What it does not demonstrate

It does not establish:

- model training or fine-tuning;
- retrieval-augmented generation;
- vector databases;
- agent planning/tool execution;
- production security;
- production observability;
- systematic model evaluation;
- original LLM architecture research.

## Maturity

**Status:** learning artifact / template adaptation.

For current evidence-bearing research/software work, see:

- [Mathematical Research Portfolio](https://github.com/Dossiya-SE/dossiya-se.github.io)
- [Africa Energy Dignity](https://github.com/Dossiya-SE/africa-energy-dignity)
- [Financial Engineering Models](https://github.com/Dossiya-SE/dossiyadakou-mac-project)

---

**Repository rule:** integration evidence is reported as integration evidence; it is not inflated into a claim of original AI-model development.
