# 🌍 UK Industry Analytics - TripleZone Framework

## 🚀 Project Mission
This project implements a professional AI-driven analytical framework to evaluate industrial sector readiness and strategic alignment. Using a local Large Language Model (**DeepSeek-R1**), the system processes specialised industrial policy documents and research data to generate actionable business scores.

---

## 🏗️ TripleZone Architecture
The repository follows a Medallion-inspired structure to ensure high standards of data governance:

* **01_Zona_A_Public_Rigor**: Contains specialised industrial research, policy papers, and sector studies. All sources are curated and renamed for maximum traceability and professional audit standards.
* **02_Zona_B_Business_Impact**: The "Gold Layer" featuring AI-synthesised intelligence and scoring, optimised for executive Power BI dashboards.
* **03_Zona_C_Future_of_Work**: Houses global reference frameworks and World Bank API specifications for international benchmarking.

---

## 🧠 Technology & Scalability
* **Orchestration**: `ai_global_master.py` - The central engine managing data logic and AI integration.
* **AI Engine**: DeepSeek-R1 (via Ollama) – chosen for its high-level reasoning and 100% local data privacy.
* **Future-Proofing**: The architecture includes the **World Bank Data360 OpenAPI** specification. This allows the framework to scale from current static qualitative analysis to live, multi-indicator global economic data feeds.

---

## 📊 Quick Start Guide
1. **Environment**: Ensure **Ollama** is active with the `deepseek-r1:8b` model.
2. **Execute**: Run `python scripts/ai_global_master.py` to process the industrial data pipeline.
3. **Visualise**: Load the Power BI report and refresh the connection to `02_Zona_B_Business_Impact`.

---

## 📝 Development Evolution (Changelog)
* **Refactoring**: Consolidated legacy code into a unified, high-performance Master Engine.
* **Data Curation**: Transitioned from general training datasets to high-value industrial policy documents.
* **Standardisation**: Migrated the project to the TripleZone Framework for professional-grade data lineage.
