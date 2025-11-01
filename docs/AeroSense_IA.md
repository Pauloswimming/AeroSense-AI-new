# 📡 Guia de Integração do Flight Radar

## Visão Geral
Este documento explica como integrar os dados do FlightRadar24 com o sistema de Otimização de Horários de Voo do **AeroSense AI**, atendendo aos requisitos do Hackathon Honeywell.

## 🎯 Alinhamento com o Problema Proposto

### Requisitos do Desafio
1. **Analisar rotas de voo** usando dados do Flight Radar/FlightAware para aeroportos movimentados (Mumbai, Delhi).  
2. **Apoiar decisões de agendamento** com insights baseados em dados.  
3. **Usar uma semana de voos** no Aeroporto de Mumbai a partir do FlightRadar24.  
4. **Lidar com informações de horário** para o mesmo período.

### Implementação da Solução

#### 1. Fontes de Dados
- **Principal**: `Flight_Data.xlsx` (dados de amostra mencionados no enunciado).  
- **Integração FlightRadar24**: Dados em tempo real para Mumbai (BOM) e Delhi (DEL).  
- **Dados Gerados**: Dados sintéticos aprimorados seguindo padrões de tráfego reais de Mumbai/Delhi.

#### 2. Funcionalidades-Chave que Atendem ao Problema

##### 🕐 Encontrar Melhor Horário para Decolagem/Pouso
```
Consulta: "Find best takeoff times with minimal delays"
Análise: Compara horários programados x reais para identificar slots ideais.
```
##### 🚫 Encontrar Horários Mais Movimentados a Evitar
```
Consulta: "Show busiest time slots to avoid"
Análise: Identifica períodos de pico com alta probabilidade de atraso.
```
##### ⚙️ Ajustar Horário de Qualquer Voo
```
Consulta: "Optimize morning schedule for reduced delays"
Análise: Fornece recomendações específicas com análise de impacto de atraso.
```
##### 🔗 Isolar Voos com Maior Impacto em Cascata
```
Consulta: "Find flights causing most cascade delays"
Análise: Usa análise de rede para identificar voos críticos para estabilidade do cronograma.
```
## 📊 Requisitos de Formato dos Dados

### Estrutura Esperada do Arquivo Flight_Data.xlsx
```
Flight_ID | Airline | Aircraft_ID | Scheduled_Time | Actual_Time | Origin | Destination | Delay_Minutes | Runway | Capacity
AI101 | AI | VT-AIR | 2024-01-01 06:00 | 2024-01-01 06:15 | BOM | DEL | 15 | 09R/27L | 180
```
### Padronização Automática dos Dados
O sistema reconhece automaticamente variações de nomes de colunas:
- `flight_id`, `flight_number` → `Flight_ID`  
- `scheduled_time`, `scheduled` → `Scheduled_Time`  
- `delay_minutes`, `delay` → `Delay_Minutes`  
- `runway` → `Runway`  
- `aircraft_capacity`, `capacity` → `Capacity`  

## 🚀 Instruções de Uso

### 1. Opções de Carregamento de Dados

#### Opção A: Usar o Arquivo Flight_Data.xlsx
1. Coloque `Flight_Data.xlsx` na pasta raiz do projeto.  
2. Inicie o dashboard: `streamlit run app/main.py`  
3. O sistema carregará automaticamente os dados do Excel.

#### Opção B: Fazer Upload de Exportação do FlightRadar24
1. Exporte os dados do FlightRadar24 para o Aeroporto de Mumbai.  
2. Use “Upload Flight Data (CSV/Excel)” na barra lateral.  
3. O sistema padroniza o formato automaticamente.

#### Opção C: Gerar Dados Sintéticos
1. Use “Generate New Data” → “Mumbai/Delhi Congested Airports”.  
2. O sistema cria dados realistas seguindo padrões de tráfego reais.

### 2. Análise com Linguagem Natural

#### Tipos Principais de Consultas
```python
# Análise de Melhores Horários
"What's the best time to schedule flights?"
"Find optimal landing slots by hour"
"Which hours have lowest average delays?"

# Horários de Pico a Evitar
"Show busiest time slots to avoid"
"Which hours have maximum congestion?"
"Peak delay periods during the day"

# Otimização de Agenda
"Optimize morning schedule for reduced delays"
"Reschedule flights to minimize cascade effects"
"Adjust schedule for runway efficiency"

# Análise de Impacto em Cascata
"Find flights causing most cascade delays"
"Show critical flights for schedule stability"
"Analyze delay propagation patterns"
```
3. Análises Avançadas
Análise de Horários de Pico
Identificação de congestionamento via clustering

Classificação em 4 níveis: Super Pico, Pico, Moderado, Baixo

Recomendações de redistribuição para redução de 15–20% nos atrasos.

Predição de Atrasos em Cascata
Modelagem de rede de conexões para propagação de atrasos.

Tipos múltiplos de conexão: aeronave, tripulação, pista, passageiros.

Identificação de voos críticos via análise de centralidade.

Otimização de Pista
Alocação dinâmica de slots com base em prioridade.

Conformidade com separação de turbulência de esteira.

Melhoria de 10–15% na eficiência operacional.

🔧 Integração com FlightRadar24
Coleta de Dados
```
# Exemplo conceitual de coleta de dados do FlightRadar24
import requests

def fetch_mumbai_flights(date_range):
    """Busca voos do FlightRadar24 para o Aeroporto de Mumbai"""
    endpoint = "https://api.flightradar24.com/common/v1/airport.json"
    params = {
        'code': 'BOM',
        'plugin[]': ['schedule', 'runways', 'airlines'],
        'plugin-setting[schedule][mode]': 'arrivals',
        'plugin-setting[schedule][timestamp]': timestamp
    }
    return standardized_data
```
Atualizações em Tempo Real
python
```
def update_flight_data():
    """Atualiza dados de voo a partir do FlightRadar24"""
    # Busca novos dados
    # Atualiza previsões
    # Recalcula recomendações de otimização
```
📈 Resultados Esperados
Melhorias de Desempenho
Redução de 15–20% nos atrasos totais.

Melhoria de 10–15% na eficiência de pista.

Aprimoramento na tomada de decisão para controladores de tráfego aéreo.

Prevenção proativa de atrasos em cascata.

Capacidades de Apoio à Decisão
Recomendações de slots ideais.

Estratégias de evitação de congestionamento.

Análise de impacto de ajustes de cronograma.

Identificação de voos críticos.

🛠️ Arquitetura Técnica
Pipeline de Dados
graphql
```
FlightRadar24 → Padronização de Dados → Motor de Análise → Interface NLP → Dashboard Streamlit
```
Módulos Principais
Gerador de Dados: padrões realistas de tráfego Mumbai/Delhi.

Analisador de Picos: identificação de congestionamentos via clustering.

Preditor de Cascata: modelagem de propagação de atrasos.

Otimizador de Pista: alocação dinâmica de slots.

Processador NLP: interface de consultas em linguagem natural.

Detector de Anomalias: IA para identificar padrões fora do normal.

Componentes de IA/ML
Isolation Forest + DBSCAN para detecção de anomalias (90%+ precisão).

K-means + DBSCAN para análise de horários de pico.

NetworkX para análise de propagação em rede.

OR-Tools para otimização de cronogramas.

📱 Funcionalidades do Dashboard
5 Abas Principais
📊 Visão Geral — métricas e KPIs em tempo real.

🚀 Otimização & IA — ferramentas de otimização de horários.

🔬 Análises Avançadas — módulos detalhados de estudo.

💬 Consultas em Linguagem Natural — perguntas operacionais.

🤖 Insights de IA — previsões e recomendações inteligentes.

Conformidade com o Desafio
✅ Interface em linguagem natural para consultas.

✅ Integração com dados do FlightRadar24.

✅ Análise específica para Mumbai/Delhi.

✅ Comparação entre horário planejado e real.

✅ Identificação e prevenção de atrasos em cascata.

🔮 Melhorias Futuras
Integração em Tempo Real
API ao vivo do FlightRadar24.

Previsões de atraso em tempo real.

Ajustes dinâmicos de horários.

Inteligência Artificial Avançada
Modelos de deep learning para predição de atrasos.

NLP com modelos transformer.

Otimizações automáticas baseadas em IA.

Cobertura Expandida
Análise multi-aeroporto.

Coordenação de voos internacionais.

Integração com dados meteorológicos.
