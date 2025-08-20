# Análise Exploratória de Dados de Óbitos por Doenças Crônicas (DCNT) no Brasil

Este projeto realiza uma análise exploratória de dados sobre os óbitos por Doenças Crônicas Não Transmissíveis (DCNT) no Brasil, utilizando dados públicos do Ministério da Saúde. A análise completa está documentada no notebook `Atividade1_CiênciaDeDados.ipynb`.

## Descrição do Dataset

- **Nome:** Óbitos por Doenças Crônicas Não Transmissíveis (DCNT) – Brasil
- **Fonte:** Sistema de Informação sobre Mortalidade (SIM) – Ministério da Saúde
- **Período:** 2020 a 2024
- **Link de Acesso:** [Dados Abertos Gov BR](https://dados.gov.br/dados/conjuntos-dados/doencas_croninas2)

O dataset consolida informações sobre mortalidade por quatro principais grupos de DCNT, conforme a Classificação Internacional de Doenças (CID-10):
- **Neoplasias (tumores malignos):** C00–C97
- **Diabetes Mellitus:** E10–E14
- **Doenças Cardiovasculares:** I00–I99
- **Doenças Respiratórias Crônicas:** J30–J98

## Etapas da Análise

O processo de análise foi dividido nas seguintes etapas:

### 1. Carregamento e Consolidação dos Dados
- Os arquivos CSV anuais (2020 a 2024) foram carregados e combinados em um único DataFrame utilizando a biblioteca `pandas`.
- O DataFrame resultante possui **397.575 registros e 13 colunas**.

### 2. Limpeza e Tratamento
- **Conversão de Tipos:** A coluna `nu_idade` foi convertida para o formato numérico para permitir cálculos estatísticos.
- **Tratamento de Datas:** A coluna `dt_obito` foi convertida para o formato `datetime`, e uma nova coluna `Ano` foi extraída para análises temporais.
- **Criação de Variável:** Foi criada a coluna `Grupo_DCNT` para categorizar os óbitos nos quatro grupos principais de doenças, facilitando a análise agregada.

### 3. Análise Estatística Descritiva
- Foram calculadas as principais métricas estatísticas para a idade (`nu_idade`), incluindo:
  - Média, Mediana e Moda
  - Desvio Padrão e Variância
  - Quartis (Q1, Q3) e Intervalo Interquartil (IQR)
- Foi realizada a contagem de valores ausentes por coluna para avaliar a qualidade dos dados.

### 4. Visualização de Dados
Foram gerados diversos gráficos com as bibliotecas `matplotlib` e `seaborn` para explorar visualmente os dados:

- **Histograma da Distribuição de Idades:** Para visualizar a frequência de óbitos por faixa etária.
- **Gráfico de Barras por Grupo de DCNT:** Para comparar o número de óbitos entre os diferentes grupos de doenças.
- **Gráfico de Dispersão (Stripplot):** Para analisar a distribuição da idade dos óbitos dentro de cada grupo de DCNT.
- **Gráfico de Barras por Ano e Tipo de Doença:** Para observar a tendência temporal dos óbitos por DCNT ao longo dos anos.