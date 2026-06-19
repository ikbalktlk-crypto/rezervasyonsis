# AI-Powered Autonomous Hotel Reservation Agent

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-UI-FF4B4B.svg)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o--mini-412991.svg)
![SQLite](https://img.shields.io/badge/Database-SQLite-003B57.svg)

## Executive Summary
This project is a fully autonomous AI agent designed to revolutionize traditional hotel booking systems. Unlike standard conversational chatbots, this system leverages **OpenAI's Tool Calling architecture** to actively perform tasks, query relational databases in real-time, enforce strict security guardrails, and execute backend logic (such as cryptographic PNR generation and SMTP email dispatching) without human intervention. 

Designed with a mathematical approach to state management and algorithmic routing, it demonstrates how Large Language Models (LLMs) can be safely integrated into deterministic production environments.

## Key Features

* **Agentic Loop Architecture:** The core system runs on a dynamic `while` loop that allows the LLM to trigger multiple sequential tools in a single turn to solve complex user requests autonomously.
* **Real-Time Database Operations:** Connects directly to a SQLite database (`otel_yonetim.db`) containing synthetic room data, enabling real-time queries for availability, double-booking prevention (via `LEFT JOIN` logic), and reservation tracking.
* **Strict Security & Guardrails (Separation of Concerns):** * The LLM is strictly prohibited from asking for credit card details in the chat context. 
  * Payment processes are isolated into a secure, dynamic Streamlit UI Modal (`@st.dialog`), ensuring sensitive data never enters the LLM's prompt history.
* **Automated Post-Action Triggers:** Successful payments autonomously trigger deterministic Python backend functions to generate secure PNR codes and send HTML-formatted confirmation emails via SMTP.

## Tool Calling Implementation
The model is equipped with a restricted, highly specific set of JSON schema tools to interact with the environment:

1. `bos_oda_bul`: Queries the SQLite database for available rooms based on dates and category, filtering out overlapping reservations.
2. `odeme_ekranini_goster`: Acts as a security bridge, halting the LLM's conversational flow to trigger the external secure payment UI.
3. `rezervasyon_sorgula`: Enables users to check their existing reservations via Name or PNR code.
4. `rezervasyon_iptal`: Safely deletes a database record, requiring a strict two-factor match (Name + PNR).

*(Note: Critical functions like `guvenli_mail_gonder` and `rezervasyon_kodu_uret` are intentionally kept out of the LLM's toolset to adhere to the Principle of Least Privilege and prevent prompt injection.)*

## 🛠️ Technology Stack
* **LLM & Orchestration:** OpenAI API (`gpt-4o-mini`)
* **Frontend UI:** Streamlit (with Custom CSS for a Figma-like dark theme experience)
* **Backend & Data Manipulation:** Python, Pandas
* **Database:** SQLite
* **Networking (Colab Deployment):** Cloudflare Tunnels

## How to Run Locally

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/AI-Hotel-Reservation-Agent.git](https://github.com/YOUR_USERNAME/AI-Hotel-Reservation-Agent.git)
   cd AI-Hotel-Reservation-Agent

