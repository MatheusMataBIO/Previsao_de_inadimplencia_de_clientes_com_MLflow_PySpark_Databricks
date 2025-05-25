# Previsão de Inadimplência de clients

### Objetivo 

Este projeto tem como objetivo prever a inadimplência de clientes no mês seguinte utilizando algoritmos de machine learning implementados com PySpark e MLflow no ambiente Databricks.

### 📚 Sobre o Projeto

Trata-se de uma abordagem prática de um problema de classificação binária, usando como base um dataset de clientes com informações financeiras e comportamentais. O modelo principal é um Gradient Boosted Trees Classifier com ponderação de classes para lidar com desbalanceamento.

### 📁 Estrutura do Projeto

**default os credit card clients**: Dataset utilizado no projeto

**Script PySpark 1 (2).ipynb:** Notebook principal contendo todo o pipeline de machine learning.

**README.md:** Arquivo explicativo com orientações sobre o projeto.

**Diretório MLflow:** Armazena experimentos, métricas e modelos registrados.

### Pipeline de Machine Learning

**Carregamento e preparação dos dados**

Features como: limite de crédito, idade, histórico de pagamentos e valores de faturas.

Conversão para vetor de features com VectorAssembler.

**Tratamento de desbalanceamento**

Cálculo de pesos com classWeightCol com base nas proporções das classes (inadimplente e adimplente).

**Treinamento do modelo**

GBTClassifier com 100 iterações (maxIter=100) e weightCol.

**Avaliação**

Métricas: F1-score, Precisão, Recall e AUC.

Ajuste do threshold com base na melhor F1-score.

**MLflow Tracking**

Log do modelo treinado.

Registro do experimento no MLflow.

Salvamento dos parâmetros, métricas e artefatos.

### 🔍 Dataset

O dataset depois do processamento possui as seguintes colunas:

**Informações de cliente:**

client id, gender, education level, marital status, age, credit limit

**Histórico de pagamento:**

payment status [apr-sep]

Valores financeiros:

bill amount [apr-sep]

payment amount [apr-sep]

**Target:**

default next month (0 = adimplente, 1 = inadimplente)

### 💾 Como Executar

**⚙️ Pré-requisitos**

Conta gratuita no Databricks Community Edition

Cluster configurado com versão 14.0 LTS ou superior

MLflow já instalado e funcional no Databricks

**▶️ Passos**

Importe o notebook Script PySpark 1 (2).ipynb para o Databricks.

Execute célula por célula.

O modelo será treinado, avaliado e registrado no MLflow.

O melhor threshold será aplicado para melhorar a performance.

### 📈 Resultados

O modelo foi avaliado com:

Melhor threshold: ajustado via F1-score

F1-score (ajustado): X.XXXX

Precisão: X.XXXX

Recall: X.XXXX

ROC-AUC: X.XXXX

OBS: Substitua as métricas reais acima após executar.

### ☁️ Sobre o Deploy

O modelo treinado foi salvo no MLflow Tracking Server do Databricks. É possível:

Carregar o modelo com mlflow.spark.load_model()

Realizar previsões com novos dados no mesmo formato vetorizado

Avaliar ou versionar o modelo via MLflow UI

