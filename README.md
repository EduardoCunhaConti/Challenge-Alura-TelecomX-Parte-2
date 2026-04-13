# TelecomX - Previsão de Churn de Clientes

## Visão Geral do Projeto

Este projeto tem como objetivo **prever a evasão de clientes (churn)** da empresa TelecomX utilizando técnicas de **Machine Learning**.

A análise busca identificar **quais fatores influenciam o cancelamento de serviços**, permitindo que a empresa desenvolva **estratégias de retenção de clientes** baseadas em dados.

O modelo utiliza variáveis relacionadas ao perfil do cliente, tipo de contrato, serviços contratados e valores pagos para **estimar a probabilidade de churn**.

---

# Objetivo da Análise

O objetivo principal do projeto é:

- **Construir modelos de Machine Learning capazes de prever o churn de clientes**
- **Identificar os fatores mais relevantes que influenciam a evasão**
- **Gerar insights estratégicos para retenção de clientes**

Com isso, a empresa pode **antecipar cancelamentos e agir preventivamente** para reduzir perdas de receita.

---

# Estrutura do Projeto

A organização do projeto segue uma estrutura simples para facilitar a navegação e reprodução da análise.

```
TelecomX-Churn-Analysis
│
├── dados_tratados.csv
│
├── Challenge Alura_TelecomX_Parte_2.ipynb
│
└── README.md

```

### Descrição dos Arquivos

**dados_tratados.csv**  
Contém os dados tratados utilizados na modelagem.

**Challenge Alura_TelecomX_Parte_2.ipynb**  
Contém o notebook principal com toda a análise, preparação de dados, treinamento dos modelos e avaliação.

**README.md**  
Documentação geral do projeto.

---

# Preparação dos Dados

A preparação dos dados foi uma etapa fundamental para garantir o bom desempenho dos modelos.

## Classificação das Variáveis

As variáveis foram divididas em dois grupos:

### Variáveis Numéricas
Exemplos:

- `tenure`
- `MonthlyCharges`
- `TotalCharges`

### Variáveis Categóricas
Exemplos:

- `Contract`
- `InternetService`
- `PaymentMethod`
- `Partner`
- `Dependents`

Essa separação foi necessária para aplicar **transformações adequadas a cada tipo de variável**.

---

## Codificação de Variáveis Categóricas

As variáveis categóricas foram transformadas utilizando:

**OneHotEncoder**

Essa técnica cria colunas binárias para cada categoria possível, permitindo que os modelos de Machine Learning interpretem corretamente essas variáveis.

Exemplo:

```
Contract
Monthly
One year
Two year
```

Se transforma em:

```
Contract_Monthly
Contract_OneYear
Contract_TwoYear
```

---

## Normalização dos Dados

As variáveis numéricas foram normalizadas utilizando:

```
StandardScaler
```

Essa técnica padroniza os dados para média 0 e desvio padrão 1, o que melhora o desempenho de modelos como:

- Regressão Logística
- KNN
- SVM

---

## Separação em Treino e Teste

Os dados foram divididos em dois conjuntos:

- **Treino:** 80%
- **Teste:** 20%

Utilizando:

```python
train_test_split()
```

O conjunto de treino é utilizado para **treinar os modelos**, enquanto o conjunto de teste serve para **avaliar a capacidade de generalização**.

---

# 🤖 Modelagem e Escolha dos Modelos

Foram utilizados diferentes algoritmos de classificação para prever o churn:

- Regressão Logística
- K-Nearest Neighbors (KNN)
- Random Forest
- Support Vector Machine (SVM)

### Justificativa das Escolhas

**Regressão Logística**

- Modelo interpretável
- Permite analisar coeficientes das variáveis

**KNN**

- Baseado em similaridade entre clientes
- Útil para capturar padrões locais nos dados

**Random Forest**

- Modelo robusto
- Reduz risco de overfitting
- Permite análise de importância das variáveis

**SVM**

- Bom desempenho em problemas de classificação
- Capaz de criar fronteiras complexas entre classes

---

# Análise Exploratória de Dados (EDA)

Durante a EDA foram gerados diversos gráficos para entender melhor os dados.

## Distribuição de Churn

Gráfico mostrando a proporção de clientes que cancelaram e os que permaneceram.

Insights:

- A maioria dos clientes **não cancelou**, indicando um dataset desbalanceado.

---

## Relação entre Tempo de Contrato e Churn

Clientes com **menor tempo de permanência** apresentam maior taxa de evasão.

Insight importante:

Clientes novos possuem **maior risco de cancelamento**.

---

## Valor Mensal vs Churn

Clientes com **MonthlyCharges mais altos** apresentam maior probabilidade de churn.

Possível causa:

- Percepção de custo-benefício menor
- Ofertas mais competitivas da concorrência

---

## Importância das Variáveis (Random Forest)

O modelo Random Forest permitiu identificar as variáveis mais relevantes.

Principais fatores identificados:

- **Tipo de contrato**
- **Tempo de permanência (tenure)**
- **Valor mensal**
- **Serviços adicionais contratados**

---

# Principais Insights

A análise revelou alguns fatores críticos para churn:

1️⃣ Clientes com **contrato mensal** cancelam mais frequentemente.

2️⃣ Clientes com **baixo tempo de permanência** possuem maior risco de evasão.

3️⃣ **Valores mensais altos** aumentam a probabilidade de churn.

4️⃣ Clientes sem **serviços adicionais** demonstram menor fidelização.

Esses fatores podem orientar **estratégias de retenção**.

---

# Como Executar o Projeto

## 1️⃣ Clonar o Repositório

```bash
git clone https://github.com/seu-usuario/telecomx-churn-analysis.git
```

---

## 2️⃣ Executar o Notebook

Abra o Jupyter Notebook:

```bash
jupyter notebook
```

Em seguida, abra:

```
notebooks/Alura_TelecomX_Parte_2.ipynb
```

Execute as células sequencialmente.

---

## 4️⃣ Carregar os Dados

Os dados tratados estão no arquivo:

```
telecom_churn_tratado.csv
```

Caso necessário, ajuste o caminho no notebook:

---

# 👨‍💻 Autor

Projeto desenvolvido por Eduardo Conti para análise de **evasão de clientes utilizando Machine Learning**.
