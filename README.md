# ÉquiProgress AI — Internship @ Cavalons

> **10-week engineering internship** at [Cavalons](https://www.cavalons.fr), a French equestrian tech startup, focused on designing and integrating an AI-powered coaching chatbot for the **ÉquiProgress** application.

---

## Overview

| Field            | Value                                      |
|------------------|--------------------------------------------|
| Student          | Manil Doudou                               |
| School           | CESI — Y3 Computer Science Engineering     |
| Company          | Cavalons (Paris, Île-de-France, France)                   |
| Period           | January 12, 2026 – March 8, 2026                |
| Company Tutor    | Ms. Camille Despesse (CEO)                |
| Academic Tutor   | Mr. Wassim Masri                           |

## Mission

**Cavalons** is a startup that connects horse owners and riders through a peer-to-peer platform (demi-pension, horse sitting, experience sharing). During my internship, the company was building **ÉquiProgress** — an AI coaching assistant for equestrian training.

My primary mission was to **design, build, and integrate the core AI chatbot** for ÉquiProgress, covering:

- Conversational flow design on **Botpress**
- Integration with the **Google Gemini 1.5 Pro API**
- Equestrian **knowledge base curation** (RAG architecture)
- **Data analysis** of equestrian datasets (Cavalons, Ekwo, Appaloo)
- **Supabase** backend schema design (13 interconnected tables)
- Embedding the chatbot into the **Figma mock-up** prototype
- Strategic **research on AI Agents** and AI-powered training generators

---

## Repository Structure

```
equiprogress-internship/
│
├── docs/
│   ├── reports/
│   │   ├── Discovery_Report_Manil_Doudou.pdf        # Mid-internship report (week 4)
│   │   └── Final_Report_Internship_Manil_Doudou.pdf # Full 10-week final report
│   └── analyses/
│       ├── Comparatif_Appaloo_EKWO.pdf              # Comparative dataset analysis
│       ├── Analyse_des_données_Cavalons.docx         # Cavalons dataset deep-dive
│       ├── Analyse_des_données_Ekwo.docx             # Ekwo dataset deep-dive
│       └── Liste_des_base_de_données.docx            # Database inventory
│
├── data-analysis/
│   ├── notebooks/
│   │   ├── cavalons_data_analysis.ipynb             # EDA on Cavalons horse dataset
│   │   └── analyse_ekwo_db.ipynb                    # EDA on Ekwo training database
│   └── datasets/
│       ├── chevaux_equiprogress.xlsx                # Horse profiles dataset
│       ├── Excel_donnees_ekwo_final_uniforme.xlsx   # Standardized Ekwo data
│       └── Excel_Chatbot_Cavalons.xlsx              # Chatbot knowledge base (Excel)
│
├── chatbot/
│   └── action-plan/
│       └── Plan_action_Chatbot_Cavalons.docx        # Full chatbot development plan
│
├── research/
│   └── presentations/
│       └── Mission1_Agents_IA_Powerpoint.pptx      # Study of AI Agents (Mission 1)
│
├── requirements.txt                                  # Python dependencies
├── .gitignore
└── README.md
```

---

## Tech Stack

| Layer | Technology |
|---|---|
| **Conversational AI** | [Botpress](https://botpress.com) — NLU, dialogue flows, KB |
| **Language Model** | Google Gemini 1.5 Pro API |
| **Backend / Database** | Supabase (PostgreSQL, Auth, Edge Functions) |
| **Frontend** | React Native + Figma mock-up |
| **Data Analysis** | Python — pandas, matplotlib |
| **Project Management** | Trello, Google Meet, WhatsApp |

---

## Data Analysis

The first phase of the internship involved exploratory analysis of three equestrian datasets to extract training patterns, identify recovery protocols after veterinary interventions, and benchmark existing market data.

### Datasets analysed

| Dataset | Source | Records | Description |
|---|---|---|---|
| Cavalons | Internal | ~1,000+ | Horse profiles, age/height distributions |
| Appaloo Exercices | External | 470 | Equestrian exercises (15 fields) |
| Ekwo Entraînements | External | 77 | Training sessions (6 fields) |

### Key findings

- **Appaloo** offers 6× more exercises with richer metadata (15 fields vs 6), strong in Obstacle (131) and Cavalettis (95)
- **Ekwo** is more beginner-friendly (55% beginner/easy vs 28% for Appaloo), stronger in Dressage (31) and CSO (16)
- The two databases are **complementary** and were recommended for harmonization
- Recovery pattern analysis after veterinary interventions (injections, osteopathy) produced **evidence-based convalescence guidelines** embedded into the chatbot's logic

→ See [`data-analysis/notebooks/`](./data-analysis/notebooks/) for the full Python analysis.

---

## Chatbot Architecture

The ÉquiProgress AI coach was built with a layered architecture designed for safety, personalization, and pedagogical soundness.

```
User Input
    │
    ▼
[Botpress NLU]  ──── intent classification + entity extraction
    │
    ▼
[Context Gathering Flow]  ──── horse name, energy, duration, objective
    │
    ▼
[Supabase API Call]  ──── user profile, last 5 sessions, health events
    │
    ▼
[Gemini 1.5 Pro API]  ──── system prompt + context + knowledge base (RAG)
    │
    ▼
[Safety Filter]  ──── risk-tiered response guardrails
    │
    ▼
Structured Response: warm-up → main exercise → alternatives → calendar prompt
```

### Safety & Ethics

The chatbot implements a **risk-tiered response system**:
- **Low-risk** (fun flatwork exercise): high AI autonomy, creative suggestions
- **Medium-risk** (horse seems stiff): conservative suggestions, vet reminder
- **High-risk** (horse is sick/lame): guardrail flow, no strenuous exercise, mandatory professional consultation

The chatbot is strictly scoped to equestrian topics and will never attempt to diagnose injuries.

---

## Strategic Research 

Two research presentations were delivered to Cavalons leadership:

### Mission 1 — Study of AI Agents
- Typologies of AI agents (reactive, deliberative, hybrid, LLM-based)
- Modern agent architectures: memory, RAG, tool use, planning
- Comparative analysis of tools: LangChain, LlamaIndex, CrewAI, Botpress, N8N, Vertex AI
- Comparative analysis of LLMs: GPT-4o, Gemini 1.5 Pro, Claude 3.5, Mistral
- Case studies: Petriage, Happieanimals

### Mission 2 — Feasibility of an AI-Powered Training Generator
- Model selection for text + image generation
- Exercise source strategy (legal, quality-controlled)
- Personalisation via RAG + vector databases (pgvector)
- Proposed 3-phase technical architecture: rule-based → hybrid RAG → multimodal

→ See [`research/presentations/`](./research/presentations/)

---

## Reports

| Document | Description |
|---|---|
| [Discovery Report](./docs/reports/Discovery_Report_Manil_Doudou.pdf) | Analysis of Cavalons' structure, culture, and early technical contributions (Week 4) |
| [Final Internship Report](./docs/reports/Final_Report_Internship_Manil_Doudou.pdf) | Comprehensive 10-week report covering all 4 phases of the internship |

---

## Getting Started (Data Analysis Notebooks)

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/equiprogress-internship.git
cd equiprogress-internship

# Install Python dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook data-analysis/notebooks/
```

---

## Key Takeaways

1. **AI Safety is non-negotiable** — building a domain-specific guardrail system was as important as the chatbot itself
2. **RAG over fine-tuning** — for a small startup, grounding the LLM in a curated knowledge base is faster, cheaper, and safer
3. **Integration is the hard part** — connecting Botpress → Supabase → Gemini required deep knowledge of three separate systems
4. **Domain knowledge matters** — understanding equestrian training principles was essential to build a credible product

---

