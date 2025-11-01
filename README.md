✈️ AeroSense AI — README (versão melhorada & ousada)

Visão rápida: AeroSense AI é um dashboard de operações aéreas impulsionado por IA — otimiza horários de voo, prevê atrasos e reduz impactos em cascata em aeroportos congestionados. Este README foi reescrito para ficar direto, moderno e com paths corrigidos para o fluxo de uso mostrado na sua captura (ambiente flight-env, pasta AeroSense AI no Desktop, execução em app/).

🎯 O que é

AeroSense AI é uma aplicação Streamlit que reúne ML, otimização e NLP para dar ao time operacional uma visão proativa das janelas de operação, previsão de atrasos e recomendações de remanejamento de slots.

🚀 Funcionalidades principais

Transformação de dados automática (CSV/XLSX → formato canônico)

Predição de atrasos com modelos ML treináveis

Otimização de horários para minimizar congestionamento e atrasos em cascata

Análise de impacto em cascata (quais voos afetam mais outros voos)

Utilização de pistas (runway planning / capacity)

Interface NLP para consultas operacionais (pergunte em linguagem natural)

Dashboard interativo construído com Streamlit

🧰 Requisitos

Python 3.10+

Conda (recomendado)

4 GB RAM mínimo (8 GB recomendado para datasets grandes)

Windows / macOS / Linux

📁 Estrutura do projeto (atualizada)
AeroSense AI/
├── app/
│   ├── main.py                 # Main Streamlit application
│   └── main_updated.py         # Updated version with enhancements
├── src/
│   ├── data_processor.py       # Data processing and transformation
│   ├── optimizer.py            # Schedule optimization algorithms
│   ├── predictor.py            # ML models for delay prediction
│   ├── anomaly_detector.py     # Anomaly detection in flight patterns
│   ├── peak_time_analyzer.py   # Peak time analysis
│   ├── cascade_delay_predictor.py  # Cascade delay analysis
│   ├── nlp_query_processor.py  # Natural language query processing
│   └── advanced_optimizer.py   # Advanced optimization algorithms
├── data/
│   ├── flight_schedule_data.csv    # Sample flight data
│   ├── optimized_schedule.csv      # Optimized schedule output
│   └── Flight_Data.xlsx            # Sample Excel data
├── notebooks/
│   └── flight_analysis.ipynb       # Jupyter notebook for analysis
├── docs/
│   ├── flight_radar_integration.md
│   └── openai_setup.md
├── requirements.txt                 # Python dependencies
├── .env.example                     # Environment variables template
└── README.md                        # Este arquivo

⚡ Inicialização rápida (modo recomendado — Conda / Windows)

Use o Anaconda Prompt (ou terminal no Windows) e siga estes passos exatos — refletem o que aparece na sua imagem:

# 1) (Opcional) clonar o repositório
git clone <URL-do-seu-repo> "AeroSense AI"
cd "AeroSense AI"

# 2) criar e ativar o ambiente (igual ao da sua imagem)
conda create --name flight-env python=3.10 -y
conda activate flight-env

# 3) instalar dependências (execute no diretório raiz do projeto)
pip install -r requirements.txt

# 4) navegar até a pasta da app e iniciar o Streamlit (como na sua captura)
cd "AeroSense AI"         # se já estiver aqui, pule
cd app
streamlit run main.py

Exemplo do terminal (mesma sequência da sua imagem)
(base) C:\Users\SONY VAIO>conda activate flight-env
(flight-env) C:\Users\SONY VAIO>cd Desktop/"AeroSense AI"
(flight-env) C:\Users\SONY VAIO\Desktop\AeroSense AI>cd app
(flight-env) C:\Users\SONY VAIO\Desktop\AeroSense AI\app>streamlit run main.py

🔑 Variáveis de ambiente

Crie um arquivo .env na raiz (AeroSense AI/.env) com as chaves necessárias. Exemplo:

GEMINI_API_KEY=seu_gemini_api_key_aqui
OPENAI_API_KEY=seu_openai_api_key_aqui   # opcional
OUTROS_SEGREDOS=valor


(use .env.example como referência)

✅ Dicas rápidas e troubleshooting (se algo falhar)

Streamlit não encontrado → certifique-se de ter instalado streamlit no flight-env:
pip install streamlit

Erro de versão do Python → confirme python --version dentro do env flight-env.

Se o app não abrir no browser → abra manualmente http://localhost:8501.

Dependências conflitantes → recrie o ambiente: conda remove -n flight-env --all e refaça os passos.

Se estiver usando macOS/Linux, troque cd Desktop/"AeroSense AI" por cd ~/Desktop/AeroSense\ AI ou o caminho onde clonou o repo.

🧪 Executando em Linux / macOS (atalho)
git clone <URL-do-repo> "AeroSense AI" && cd "AeroSense AI"
conda create -n flight-env python=3.10 -y && conda activate flight-env
pip install -r requirements.txt
cd app && streamlit run main.py

📚 Como usar o dashboard

Upload Data — carregue CSV/XLSX pela barra lateral.

Optimization & AI — rode o pipeline de pré-processamento e otimização.

Query (NLP) — pergunte ao sistema em linguagem natural (ex.: “quais são os horários de pico amanhã?”).

Visualize — painéis interativos mostrarão janelas críticas, previsões e recomendações.