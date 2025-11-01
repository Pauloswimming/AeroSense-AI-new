# ✈️ **AeroSense AI** — Flight Intelligence Dashboard
![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![Streamlit](https://img.shields.io/badge/Streamlit-1.x-FF4B4B?logo=streamlit&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)
![Conda](https://img.shields.io/badge/Conda-Env-blue?logo=anaconda)
![Status](https://img.shields.io/badge/Status-Active-success?style=flat-square)

Visão rápida:
O AeroSense AI é um dashboard de operações aéreas impulsionado por Inteligência Artificial, projetado para otimizar horários de voo, prever atrasos e reduzir impactos em cascata em aeroportos congestionados.
Combina Machine Learning, NLP e otimização avançada em uma interface Streamlit moderna e interativa.

---

### 🧭 Visão Geral
**AeroSense AI** é um dashboard de operações aéreas impulsionado por **Inteligência Artificial**, projetado para **otimizar horários de voo**, **prever atrasos** e **reduzir impactos em cascata** em aeroportos congestionados.  
Combina **Machine Learning, NLP e algoritmos de otimização** em uma interface **Streamlit** moderna, visual e interativa.

---

## 🎯 O que é
O **AeroSense AI** ajuda times operacionais e analistas a tomarem decisões proativas e baseadas em dados, através de:

- 📊 Análises preditivas de atrasos e gargalos.  
- ⚙️ Reprogramação automática de voos com base em restrições reais.  
- ✈️ Simulação de impacto entre conexões e slots.

---

## 🚀 Funcionalidades Principais
- ✅ Transformação automática de dados (CSV/XLSX → formato padronizado)  
- ✅ Predição de atrasos com modelos de Machine Learning  
- ✅ Otimização de horários de voo para reduzir congestionamentos  
- ✅ Análise de impacto em cascata (efeito dominó entre voos)  
- ✅ Planejamento de pista e uso eficiente da infraestrutura  
- ✅ Interface NLP para consultas em linguagem natural  
- ✅ Dashboard interativo e intuitivo, feito com Streamlit

---

## 🧰 Requisitos
- 🐍 **Python:** 3.10 ou superior  
- 🧩 **Conda:** recomendado  
- 💻 **RAM:** mínimo 4 GB (8 GB recomendado)  
- 🪟 **Compatível com:** Windows / macOS / Linux

---

## 📁 Estrutura do Projeto (atualizada)
```bash
📦 AeroSense-AI
├── 📂 app/
│   ├── main.py — Entrada do Streamlit
│   └── main_updated.py — Versão com melhorias
├── 📂 src/
│   ├── data_processor.py — Processamento e transformação de dados
│   ├── optimizer.py — Algoritmos de otimização de horários
│   ├── predictor.py — Modelos de ML para previsão de atrasos
│   ├── anomaly_detector.py — Detecção de anomalias em padrões de voo
│   ├── peak_time_analyzer.py — Análise de horários de pico
│   ├── cascade_delay_predictor.py — Análise de atrasos em cascata
│   ├── nlp_query_processor.py — Processamento de linguagem natural
│   └── advanced_optimizer.py — Algoritmos avançados de otimização
├── 📂 data/
│   ├── flight_schedule_data.csv — Dados de voo (amostra)
│   ├── optimized_schedule.csv — Saída otimizada
│   └── Flight_Data.xlsx — Dados em Excel
├── 📂 notebooks/
│   └── flight_analysis.ipynb — Análises exploratórias
├── 📂 docs/
│   ├── flight_radar_integration.md
│   └── openai_setup.md
├── requirements.txt — Dependências
├── .env.example — Template de variáveis de ambiente
└── README.md — Este arquivo ✈️
```
⚡ Inicialização Rápida (via Conda / Windows)

Use o Anaconda Prompt e siga os passos abaixo:

1️⃣ Clonar o repositório
```bash
git clone https://github.com/Pauloswimming/AeroSense-AI.git
cd "AeroSense AI"
```

2️⃣ Criar e ativar o ambiente Conda
```
conda create --name flight-env python=3.10 -y
conda activate flight-env
```

3️⃣ Instalar dependências
```
pip install -r requirements.txt
```

4️⃣ Executar o app Streamlit
```bash
cd app
streamlit run main.py
```

Exemplo no terminal:
```bash
(base) C:\Users\SONY VAIO>conda activate flight-env
(flight-env) C:\Users\SONY VAIO>cd Desktop\AeroSense AI
(flight-env) C:\Users\SONY VAIO\Desktop\AeroSense AI>cd app
(flight-env) C:\Users\SONY VAIO\Desktop\AeroSense AI\app>streamlit run main.py
```
🔑 Variáveis de Ambiente

Crie um arquivo .env na raiz do projeto e adicione suas chaves (não comite esse arquivo):
```
GEMINI_API_KEY=seu_gemini_api_key_aqui
OPENAI_API_KEY=seu_openai_api_key_aqui  # opcional
OUTROS_SEGREDOS=valor
```

Use .env.example como referência.

🧩 Dicas e Soluções Rápidas

⚠️ Erro “streamlit not found” → pip install streamlit no ambiente flight-env.

🧠 Versão incorreta do Python → python --version.

🌐 App não abriu automaticamente → acesse http://localhost:8501.

🔄 Ambiente corrompido → recrie com:
```
conda remove -n flight-env --all
conda create -n flight-env python=3.10
```
🧪 Execução em Linux / macOS (atalho único)
```
git clone https://github.com/Pauloswimming/AeroSense-AI.git && cd "AeroSense AI" &&
conda create -n flight-env python=3.10 -y && conda activate flight-env &&
pip install -r requirements.txt && cd app && streamlit run main.py
```
📊 Como Usar o Dashboard

📂 Upload Data — carregue CSV/XLSX pela barra lateral.

⚙️ Optimization & AI — rode o pipeline de otimização e previsão.

💬 Query (NLP) — pergunte ao sistema: “Quais são os horários de pico amanhã?”

📈 Visualize — painéis interativos mostram previsões, gargalos e recomendações.

🌟 Contribuições

Pull Requests são bem-vindos!
Fluxo sugerido:

Fork → 2. git checkout -b feature-nome → 3. Commit & Push → 4. Abra PR.

🧑‍💻 Autor

👨‍💻 Paulo Henrique Rodrigues Nogueira
