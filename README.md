# cemaden-climate-data-pipeline

📌 Data Pipeline de Monitoramento e Impactos Climáticos (CEMADEN 2025)

🎯 Objetivo do Projeto
Criar um pipeline ETL (Extração, Transformação e Carga) automático para processar e integrar dados sobre extremos climáticos e desastres no Brasil, gerando um Data Warehouse analítico e um Dashboard interativo de Alertas e Impactos.

🛠️ Stack Tecnológica & Ferramentas
* Linguagem / Scripting: Python 3.10+ (Pandas, Requests, SQLAlchemy, GeoPandas) 
* Orquestração: Apache Airflow ou scripts automatizados via Cron/Task Scheduler
* Armazenamento / Banco de Dados: PostgreSQL com extensão PostGIS (para dados geoespaciais)
* Modelagem & Transformação: Scripts SQL modularizados
* Visualização / BI: Metabase, Power BI 
* Containerização: Docker e Docker Compose (para subir o ambiente sem complicações)


📐 Metodologia de Desenvolvimento
Adotaremos a arquitetura Medallion (Bronze, Silver, Gold), amplamente utilizada na engenharia de dados moderna:
```text
[ Fontes de Dados ] 
            │
            ▼
┌─────────────────────────┐
│   Camada BRONZE (Raw)   │ ──> Dados brutos armazenados como extraídos
└─────────────────────────┘
            │
            ▼ (Limpeza, Deduplicação e Tipagem)
┌─────────────────────────┐
│  Camada SILVER (Trusted)│ ──> Tabelas padronizadas e relacionáveis
└─────────────────────────┘
            │
            ▼ (Modelagem dimensional DWH / Agregações)
┌─────────────────────────┐
│   Camada GOLD (Refined) │ ──> Tabelas agregadas e visões para o Dashboard
└─────────────────────────┘
            │
            ▼
[ Dashboard Analítico (BI) ]







