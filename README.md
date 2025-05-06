# Tech Challenge – Fase 2: Previsão de Fechamento Diário do IBOVESPA

## 📊 Descrição do Projeto

Este projeto tem como objetivo desenvolver um modelo preditivo de séries temporais para prever o fechamento diário do índice **IBOVESPA**. O desafio simula uma situação real em que fui alocado para um time de investimentos, com a missão de criar uma solução baseada em dados históricos para apoiar a tomada de decisão.

Os dados foram extraídos do site **Investing.com**, considerando o período **diário**, com o intervalo definido com base na análise dos dados.

---

## 🔍 Etapas do Projeto

### 1. Coleta e Tratamento dos Dados
- **Fonte**: [Investing.com](https://www.investing.com)
- **Período**: Diário
- **Variáveis**: Data, Abertura, Máxima, Mínima, Fechamento, Volume
- Etapas realizadas:
  - Padronização de colunas
  - Conversão de datas
  - Tratamento de valores ausentes

### 2. Análise Exploratória
- Visualizações gráficas com `Matplotlib` e `Seaborn`
- Decomposição sazonal com `seasonal_decompose`
- Teste de estacionaridade (ADF Test)
- Análise de autocorrelação (ACF/PACF)

### 3. Modelagem Preditiva
- **Técnicas utilizadas**:
  - **AutoARIMA** (via `statsforecast`)
  - **Naive**, **SeasonalNaive**, **SeasonalWindowAverage**
  - **Prophet** (Facebook)

- **Justificativa**:
  - Uso de modelos clássicos e robustos para séries temporais.
  - Avaliação de diferentes abordagens para melhor desempenho.
  - Prophet escolhido por sua capacidade de lidar com sazonalidade e tendências.

### 4. Avaliação e Resultados
- Métricas de avaliação aplicadas para aferir a performance.
- Acurácia dos modelos superiores a **70%**, atendendo o critério proposto.

---

## 🧰 Bibliotecas Utilizadas

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from statsmodels.tsa.seasonal import seasonal_decompose
from statsmodels.tsa.stattools import adfuller
from statsforecast import StatsForecast
from statsforecast.models import Naive, SeasonalNaive, SeasonalWindowAverage, AutoARIMA
from statsmodels.tsa.stattools import acf, pacf
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
from prophet import Prophet as pr
