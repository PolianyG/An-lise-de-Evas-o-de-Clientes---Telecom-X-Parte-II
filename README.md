# Análise Preditiva de Evasão de Clientes (Churn) para Telecom X
---

Este projeto foi desenvolvido como parte de um desafio de ciência de dados e tem como objetivo principal analisar a evasão de clientes (churn) em uma empresa de telecomunicações fictícia, a "Telecom X". O estudo abrange desde a preparação e limpeza dos dados até a construção de modelos de machine learning para prever a probabilidade de um cliente cancelar seu contrato, culminando em um relatório com insights e recomendações estratégicas para a retenção de clientes.

## 🎯 Objetivos

* **Preparar os Dados:** Realizar a limpeza, transformação e codificação dos dados para prepará-los para a modelagem.
* **Analisar Fatores de Churn:** Identificar as principais variáveis que influenciam a decisão de um cliente em evadir.
* **Construir Modelos Preditivos:** Desenvolver e treinar modelos de classificação (Regressão Logística e Random Forest) para prever o churn.
* **Avaliar a Performance:** Medir a eficácia dos modelos utilizando métricas como acurácia, precisão, recall e F1-Score.
* **Gerar Recomendações:** Propor ações estratégicas baseadas nos insights da análise para reduzir a taxa de evasão de clientes.

## 📌 Etapas do Projeto

O projeto foi estruturado seguindo as principais etapas de um pipeline de ciência de dados:

1.  **Preparação e Limpeza dos Dados:**
    * Remoção de colunas irrelevantes (`customerID`).
    * Tratamento de valores categóricos, como a unificação de `"No internet service"` para `"No"`, simplificando a análise.
    * Aplicação de **One-Hot Encoding** para converter variáveis categóricas em um formato numérico adequado para os modelos.
    * Verificação e remoção de valores nulos para garantir a qualidade do dataset.

2.  **Balanceamento de Classes:**
    * O dataset original apresentava um desbalanceamento entre as classes de clientes (evadidos vs. não evadidos).
    * Foi aplicada a técnica **SMOTE (Synthetic Minority Over-sampling Technique)** para criar um conjunto de dados de treino balanceado, melhorando a capacidade do modelo de aprender com a classe minoritária (clientes que evadiram).

3.  **Análise Exploratória e Visualização:**
    * Criação de um **heatmap de correlação** para identificar as variáveis mais correlacionadas com a variável alvo (`Churn_Yes`).
    * Geração de **boxplots e stripplots** para visualizar a distribuição de variáveis importantes, como o total gasto (`account.Charges.Total`) e o tempo de contrato (`customer.tenure`), em relação ao status de evasão.

4.  **Modelagem Preditiva:**
    * Os dados foram divididos em conjuntos de treino (70%) e teste (30%).
    * Os dados de treino foram normalizados com `StandardScaler` para otimizar a performance da Regressão Logística.
    * Foram treinados dois modelos de classificação:
        * **Regressão Logística:** Um modelo linear robusto e de fácil interpretação.
        * **Random Forest:** Um modelo de ensemble que combina múltiplas árvores de decisão para maior precisão e robustez.

5.  **Avaliação e Análise de Importância:**
    * Os modelos foram avaliados no conjunto de teste com base em métricas de classificação.
    * A **análise dos coeficientes** da Regressão Logística e a **importância das variáveis** do Random Forest foram utilizadas para extrair os principais fatores preditivos do churn.

## ⚙️ Ferramentas e Bibliotecas Utilizadas

* **Linguagem:** Python 3
* **Bibliotecas Principais:**
    * `pandas`
    * `scikit-learn`
    * `imblearn`
    * `matplotlib` & `seaborn`

## 🚀 Como Executar o Projeto

Este projeto foi desenvolvido para ser executado no ambiente do Google Colab.

1.  **Download dos Arquivos:**
    * Faça o download do notebook: `Challenge_Telecom_X_análise_de_evasão_de_clientes_part2.ipynb`
    * Faça o download da base de dados: `tabela tratada.csv`

2.  **Ambiente Google Colab:**
    * Acesse o [Google Colab](https://colab.research.google.com/).
    * Faça o upload do arquivo `.ipynb` para o seu ambiente.
    * Na aba de arquivos (ícone de pasta à esquerda), faça o upload do arquivo `tabela tratada.csv`. O arquivo será carregado no diretório `/content/`.

3.  **Execução:**
    * Com os dois arquivos no ambiente, execute as células do notebook em ordem sequencial para reproduzir a análise.

## 📊 Resultados e Conclusões

Ambos os modelos apresentaram bom desempenho, com destaque para o **Random Forest**, que alcançou uma **acurácia de 85,4%** e um **recall de 86,3%**, mostrando-se muito eficaz em identificar os clientes com maior propensão a evadir.

**Principais Fatores que Influenciam o Churn:**
* **Fatores Financeiros:** O **gasto total (`account.Charges.Total`)** e o **tempo de contrato (`customer.tenure`)** foram os preditores mais fortes. Clientes mais antigos e com maior gasto acumulado tendem a ser mais leais.
* **Método de Pagamento:** Clientes que utilizam **cheque eletrônico** (`account.PaymentMethod_Electronic check`) possuem uma probabilidade significativamente maior de evadir.
* **Tipo de Serviço:** O serviço de **internet de fibra óptica** está fortemente associado ao churn, sugerindo possíveis problemas de qualidade, preço ou suporte neste serviço.


---
**Desafio do programa Oracle Next Education (ONE), por Poliany Guimarães.**
