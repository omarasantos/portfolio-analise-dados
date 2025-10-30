# Projeto de Bootcamp: Previsão de desempenho de estudantes
# Equipe: Dato

## 1. 🎯 Objetivo

O objetivo deste projeto é utilizar técnicas de Machine Learning para prever a nota final de um estudante (“exam_score“) com base em seus hábitos de estudo e informações demográficas. A análise busca identificar quais fatores mais influenciam o desempenho acadêmico e comparar diferentes modelos preditivos para encontrar o mais acurado.

## 2. Análise exploratória e pré-processamento

Para preparar os dados para a modelagem, seguimos uma rigorosa etapa de análise e pré-processamento:

* **Dicionário de Dados:** O dataset é composto por 14 features, incluindo variáveis quantitativas (horas de estudo, idade, frequência de exercícios) e qualitativas (gênero, nível de educação dos pais, qualidade da internet).
* **Estratégias de Pré-processamento:**
    * **Tratamento de Valores Faltantes:** Imputação com a **média** para variáveis contínuas, **mediana** para discretas e **moda** para qualitativas.
    * **Normalização:** Aplicação do `MinMaxScaler` em todas as features quantitativas para padronizar a escala dos dados.
    * **Codificação Categórica:** Utilização do `OrdinalEncoder` para variáveis ordinais e `OneHotEncoder` para as nominais, transformando-as em formato numérico.

## 3. Análise comparativa e metodologia

Para determinar o modelo mais eficaz, adotamos uma metodologia robusta de otimização e validação.

* **Algoritmos Testados:**
    * Regressão Linear (LRG)
    * K-Nearest Neighbors (KNN)
    * Decision Tree Regressor (DTR)
    * Support Vector Regressor (SVR)

* **Otimização de hiperparâmetros:** Utilizamos o `RandomizedSearchCV` com validação cruzada (k-fold = 5) para encontrar a melhor combinação de hiperparâmetros para cada algoritmo, otimizando sua performance.

* **Validação Final:** Para garantir a estabilidade e a capacidade de generalização dos resultados, aplicamos a técnica `ShuffleSplit` (Validação Cruzada de Monte-Carlo) com 30 repetições.

Após a análise comparativa, o modelo de **Regressão Linear (LRG) se destacou como o mais eficaz**. Ele obteve o melhor equilíbrio entre precisão e eficiência, com os seguintes resultados:

* **Coeficiente de determinação (R²): 0.894**
* **Erro absoluto mdio (MAE): 4.32**

## 5. Tecnologias utilizadas

* **Linguagem:** Python
* **Bibliotecas Principais:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn
* **Ambiente de Desenvolvimento:** Google Colab
