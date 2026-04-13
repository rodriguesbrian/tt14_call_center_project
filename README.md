# TT14 – Data Analysis Project

## 📌 Overview

Projeto de análise de dados focado em três frentes principais:

- **Eficiência operacional em Call Centers**
- **Validação de hipóteses via A/B Testing**
- **Exploração de dados com SQL para geração de insights de produto**

O objetivo central foi transformar dados brutos em **decisões acionáveis**, diferenciando problemas individuais de falhas estruturais.

---

## 🎯 Principais Resultados

- Identificação de operadores com **desempenho estatisticamente inferior**
- Detecção de **padrões de ineficiência ao nível de empresa**
- Aplicação de testes estatísticos para evitar decisões baseadas em ruído
- Desenvolvimento de dashboard para **priorização operacional**

---

## 📁 Estrutura do Projeto

```
tt14_call_center_project/
├── README.md                              # Este arquivo
├── requirements.txt                       # Dependências do Python
├── datasets/                              # Dados brutos
│   ├── ab_project_marketing_events_us.csv
│   ├── final_ab_events_upd_us.csv
│   ├── final_ab_new_users_upd_us.csv
│   ├── final_ab_participants_upd_us.csv
│   ├── final_results_telecom.csv
│   ├── telecom_clients.csv
│   └── telecom_dataset_new.csv
├── notebooks/                             # Jupyter Notebooks com análises
│   ├── ab_test_analysis.ipynb
│   ├── call_center_efficiency.ipynb
│   └── sql_queries.ipynb
└── reports/                               # Relatórios e visualizações
    └── link_tableau_public.txt
```


---

## 📞 Case 1: Call Center Efficiency

### 🎯 Objetivo
Identificar operadores e empresas com baixo desempenho operacional e priorizar ações corretivas.

---

### ⚙️ Metodologia

#### KPIs definidos

**1. Missed Rate**
- Percentual de chamadas inbound perdidas  
- Comparação operador vs equipe  
- Teste estatístico: Two-proportion Z-test  
- Critérios:
  - p-value < 0.05  
  - diferença relativa ≥ 25%  

---

**2. Waiting Time**
- Mediana do tempo de espera  
- Teste estatístico: Mann-Whitney U  
- Critérios:
  - diferença estatisticamente significativa  
  - diferença absoluta relevante  
  - operador acima do Q3 da equipe  

---

**3. Outbound Productivity**
- Mediana semanal de chamadas outbound  
- Teste estatístico: Mann-Whitney U  
- Critérios:
  - ≥30% abaixo da equipe  
  - diferença absoluta mínima  

---

### 📈 Insights

- Apenas uma pequena fração dos operadores apresentou falhas, mas com **alto impacto operacional**
- Identificação de operadores com:
  - alta taxa de chamadas perdidas  
  - tempos de espera elevados  
  - baixa produtividade outbound  

- Evidência de **problemas estruturais em algumas empresas**
  - múltiplos operadores com padrões semelhantes  
  - indica falha de gestão, não apenas desempenho individual  

- Um operador apresentou falha em múltiplos KPIs → **prioridade crítica**

---

### 💡 Implicação de Negócio

Nem todo desvio estatístico é relevante.  
A priorização deve considerar:

- volume de chamadas  
- magnitude da diferença  
- recorrência dentro da empresa  

---

## 🧪 Case 2: A/B Testing

### 🎯 Objetivo
Validar se um novo sistema de recomendação melhora conversões.

---

### ⚙️ Metodologia

- Análise de funil (login → product → purchase)  
- Testes de proporção  
- Avaliação de significância estatística  

---

### 📈 Resultado

- Diferenças entre grupos foram avaliadas estatisticamente  
- O teste permitiu distinguir entre:
  - variações reais de comportamento  
  - flutuações aleatórias  

---

## 🧮 Case 3: SQL Analysis

### 🎯 Objetivo
Explorar dados de uma plataforma de livros para identificar oportunidades de produto.

---

### 📈 Principais análises

- Identificação de livros e autores mais relevantes  
- Padrões de avaliação e comportamento de usuários  
- Consolidação de métricas para suporte a decisões de produto  

---

## 📊 Dashboard

🔗 Tableau Public:  
https://public.tableau.com/app/profile/brian.rodrigues5391/viz/TT14-CallCenterIneficiency/CallCenterIneficiency

Inclui:
- ranking de operadores problemáticos  
- heatmap de falhas por KPI  
- % de operadores ineficientes por empresa  

---

## 🛠 Tecnologias

| Tecnologia | Uso |
|-----------|-----|
| Python | Análise de dados |
| Pandas | Manipulação de dados |
| NumPy | Computação numérica |
| SciPy | Testes estatísticos |
| Statsmodels | Modelagem estatística |
| Matplotlib / Seaborn | Visualização |
| SQL | Consulta e exploração de dados |
| Tableau | Dashboard interativo |

---

## ⚠️ Limitações

- Análise baseada em janela temporal específica  
- Dependência de volume mínimo por operador  
- Ausência de análise temporal (tendência ao longo do tempo)  

---

## 🚀 Próximos Passos

- Construção de pipeline automatizado (ETL → análise → output)  
- Inclusão de análise temporal de desempenho  
- Tradução dos resultados em impacto financeiro  

---

## 👨‍💻 Autor

Brian Rodrigues