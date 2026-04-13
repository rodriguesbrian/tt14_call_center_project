# TT14 - Call Center Project

Um conjunto de análises de dados focadas em **eficiência operacional de call centers**, **testes A/B de e-commerce**, e **estudo sobre plataforma de livros digital** usando Python, Jupyter Notebooks, SQL e análise estatística.

## 📋 Sumário

- [Visão Geral](#visão-geral)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Datasets](#datasets)
- [Análises Incluídas](#análises-incluídas)
- [Requisitos](#requisitos)
- [Como Usar](#como-usar)
- [Tecnologias](#tecnologias)
- [Visualizações](#visualizações)

## 🎯 Visão Geral

Este projeto combina três análises principais de dados:

### 1. **Análise de Teste A/B (A/B Test Analysis)**
Análise completa de um teste A/B de um sistema de recomendação em uma plataforma de e-commerce internacional. O teste compara o comportamento de usuários em dois grupos (controle e variação) ao longo do funil de compras.

**Período do teste:** 07/12/2020 a 01/01/2021  
**Público:** 15% de novos usuários da região UE (6.000 participantes esperados)

### 2. **Eficiência do Call Center**
Identificação e análise de operadores ineficientes em um serviço de telefonia virtual usando métricas de desempenho como chamadas perdidas, tempo de espera e volume de chamadas.

### 3. **Queries SQL**
Investigação sobre o acervo de plataformas de livros digitais e comportamentos de usuários.   
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

## 📊 Datasets

### Datasets de Teste A/B

| Arquivo | Descrição |
|---------|-----------|
| `ab_project_marketing_events_us.csv` | Calendário de eventos de marketing para 2020 (campanha, datas, regiões) |
| `final_ab_new_users_upd_us.csv` | Novos usuários cadastrados entre 07-21/12/2020 (ID, região, dispositivo) |
| `final_ab_events_upd_us.csv` | Eventos dos usuários no período 07/12/2020 a 01/01/2021 (conversões, visualizações) |
| `final_ab_participants_upd_us.csv` | Participantes do teste A/B com grupo de controle (A) e variação (B) |

### Datasets de Call Center

| Arquivo | Descrição |
|---------|-----------|
| `telecom_dataset_new.csv` | Dados de chamadas (direção, duração, perdidas, operador, etc.) |
| `telecom_clients.csv` | Informações dos clientes (ID, plano tarifário, data de registro) |
| `final_results_telecom.csv` | Resultados consolidados da análise de call center |

## 📈 Análises Incluídas

### 1️⃣ Análise de Teste A/B (`ab_test_analysis.ipynb`)

**Objetivo:** Validar se o novo sistema de recomendação melhorou significativamente as conversões.

**Métricas Analisadas:**
- Visualizações de página de produto (product_page)
- Adições ao carrinho (product_cart)
- Compras realizadas (purchase)
- Taxa de conversão em cada etapa do funil
- Tamanho do efeito (lift) esperado: +10% em cada etapa

**Métodos Estatísticos:**
- Testes de hipótese (t-teste, chi-square)
- Análise de funil de conversão
- Avaliação de significância estatística

### 2️⃣ Eficiência do Call Center (`call_center_efficiency.ipynb`)

**Objetivo:** Identificar operadores ineficientes com base em critérios de desempenho.

**Critérios de Ineficiência:**
- Muitas chamadas perdidas (internas ou externas)
- Tempo de espera prolongado em chamadas entrantes
- Volume baixo de chamadas ativas (para operadores de saída)

**Análises:**
- Métricas de desempenho por operador
- Segmentação de operadores
- Identificação de gaps de performance
- Recomendações de melhoria

### 3️⃣ Análise de Plataforma de Livros - Queries SQL (`sql_queries.ipynb`)

**Contexto:** Análise de dados de uma plataforma de livros desenvolvida durante a pandemia de COVID-19 para atender à crescente demanda de serviços de leitura digital. A plataforma compila informações sobre livros, autores, editoras e avaliações de usuários.

**Objetivo:** Gerar proposições de valor para o desenvolvimento de novo produto utilizando análise de dados de mercado competidor.

**Estrutura do Banco de Dados:**

| Tabela | Descrição | Campos Principais |
|--------|-----------|------------------|
| `books` | Livros disponíveis | `book_id`, `author_id`, `title`, `num_pages`, `publication_date`, `publisher_id` |
| `authors` | Informações de autores | `author_id`, `author` |
| `publishers` | Informações de editoras | `publisher_id`, `publisher` |
| `ratings` | Classificações de usuários | `rating_id`, `book_id`, `username`, `rating` |
| `reviews` | Revisões e comentários | `review_id`, `book_id`, `username`, `text` |

**Análises SQL Incluídas:**
- Exploração e compreensão da estrutura de dados
- Análise de padrões de leitura e preferências de usuários
- Identificação de livros e autores mais populares
- Agregações de classificações e avaliações
- Consolidação de métricas para proposição de produto
- Limpeza, validação e transformação de dados

## 🔧 Requisitos

- Python 3.8+
- Jupyter Notebook ou JupyterLab
- Bibliotecas listadas em `requirements.txt`

## 📥 Como Usar

### 1. Clonar o repositório

```bash
git clone https://github.com/seu-usuario/tt14_call_center_project.git
cd tt14_call_center_project
```

### 2. Criar ambiente virtual (opcional, mas recomendado)

```bash
python -m venv venv
source venv/bin/activate  # No Windows: venv\Scripts\activate
```

### 3. Instalar dependências

```bash
pip install -r requirements.txt
```

### 4. Executar Jupyter Notebook

```bash
jupyter notebook
```

### 5. Abrir e executar os notebooks

Navegue para a pasta `notebooks/` e abra:
- `ab_test_analysis.ipynb` - para análise A/B
- `call_center_efficiency.ipynb` - para eficiência do call center
- `sql_queries.ipynb` - para queries SQL

## 🛠 Tecnologias

| Tecnologia | Propósito |
|-----------|----------|
| **Python 3** | Linguagem principal |
| **Pandas** | Manipulação e análise de dados |
| **NumPy** | Computação numérica |
| **SciPy** | Cálculos estatísticos avançados |
| **Statsmodels** | Modelagem e testes estatísticos |
| **Matplotlib & Seaborn** | Visualizações |
| **SQLAlchemy** | ORM e conexão com bancos de dados |
| **psycopg2** | Driver PostgreSQL |
| **Jupyter** | Ambiente interativo de análise |

## 📊 Visualizações

As análises incluem dashboards e visualizações no Tableau Public:

🔗 **[Dashboard de Eficiência do Call Center](https://public.tableau.com/app/profile/brian.rodrigues5391/viz/TT14-CallCenterIneficiency/CallCenterIneficiency)**

## 📝 Notas Importantes

- Os dados contêm informações de períodos específicos (dezembro 2020-janeiro 2021)
- As análises utilizadas foram validadas com testes estatísticos rigorosos
- Todos os arquivos CSV devem ser mantidos na pasta `datasets/`
- Recomenda-se usar a versão mais recente das dependências do `requirements.txt`

## 👨‍💻 Autor

Brian Rodrigues

## 📄 Licença

Este projeto é fornecido como está para fins educacionais e comerciais autorizados.

---
