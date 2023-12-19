# Previsão do Índice da Bolsa de Valores Brasileira com Aprendizado Profundo e Interpretação Explicável de IA

Bem-vindo ao repositório do nosso projeto! Este projeto foi desenvolvido como parte do programa de mestrado em Ciência da Computação na Universidade Federal de Pernambuco. Neste repositório, apresentamos nosso trabalho na previsão do índice da bolsa de valores brasileira usando técnicas de Aprendizado Profundo e métodos de Inteligência Artificial Explicável (IAE) para interpretar e explicar as previsões.

## Sumário

- [Introdução](#introdução)
- [Visão Geral do Projeto](#visão-geral-do-projeto)
- [Instalação](#instalação)
- [Uso](#uso)
- [Dados](#dados)
- [Métodos](#métodos)
- [Resultados](#resultados)
- [Contribuidores](#contribuidores)

## Introdução

No cenário dos mercados financeiros, prever índices de bolsa de valores é uma tarefa desafiadora e crucial. Este projeto visa aproveitar o poder do Aprendizado Profundo e técnicas de IA Explicável para fazer previsões precisas do índice da bolsa de valores brasileira. Nosso foco não está apenas em fazer previsões, mas também em fornecer explicações transparentes e interpretáveis para essas previsões.

Os scripts se encontram em Modelos_Deep para as redes neurais Deep Learning e Modelos_Hibridos para os modelos Híbridoa Arima.

## Visão Geral do Projeto

Neste repositório, você encontrará:

- Código em Python para nossos modelos de Aprendizado Profundo e métodos de IA Explicável.
- Notebooks Jupyter ilustrando todo o processo de pré-processamento de dados, treinamento de modelos e geração de explicações.
- Fontes de dados e scripts de pré-processamento de dados.
- Documentação e tutoriais sobre como usar nosso código e replicar nossos experimentos.

## Instalação

Para começar, você precisará configurar seu ambiente e instalar as dependências necessárias. Veja como fazer isso:

```bash
import yfinance as yf
import numpy as np
import pandas as pd
from sklearn.preprocessing import MinMaxScaler
from keras.models import Sequential
from keras.layers import Dense, LSTM, GRU  # captum (biblioteca de interpretação pytorch)
import matplotlib.pyplot as plt
from sklearn.metrics import mean_squared_error

# Baixe os dados da ação (estou usando o índice Bovespa como exemplo)
dados = yf.download('^BVSP', '2007-01-01', '2023-10-17')
dados = dados[['Close']]
```

## Uso

Projetamos este projeto pensando na facilidade de uso. Você encontrará notebooks de exemplo e scripts que demonstram como treinar modelos, fazer previsões e gerar explicações.

## Dados

Nosso projeto depende de dados financeiros históricos. Utilizamos dados de fontes confiáveis, e você pode encontrar detalhes no [site do Yahoo Finance](https://finance.yahoo.com/).

Incentivamos fortemente os usuários a respeitar as licenças de dados e as restrições de uso ao trabalhar com dados financeiros.

## Métodos

Empregamos várias técnicas de Aprendizado Profundo, incluindo redes neurais com unidades recorrentes gated (GRUs), redes neurais de memória de curto e longo prazo (LSTMs) e modelos híbridos. Além disso, utilizamos métodos de IA Explicável como LIME e Importância de Features para fornecer insights sobre as previsões do modelo.

## Resultados

Nossos resultados e descobertas estão documentados no diretórios `Modelos_Deep/` e `Modelos_Hibridos/`. Apresentamos métricas de avaliação, visualizações e interpretações das previsões de nossos modelos. Esperamos que você ache nossos resultados esclarecedores e informativos.

## Contribuidores

- [Lucas Rabelo](https://github.com/marreapato)
- [Eliaquim Moreira](https://github.com/marreapato)

Agradecemos contribuições, feedback e colaboração da comunidade. Sinta-se à vontade para abrir problemas e solicitações de pull.
  

# Informações Principais

**Instituto:** CIN; **Universidade:** UFPE; **Local:** PE, Brasil

## Introdução

O mercado financeiro brasileiro tem apresentado um crescimento nos últimos anos, com diversas flutuações e desequilíbrios. Considerando a série temporal do índice Bovespa, é crucial analisar fatores como políticas governamentais, condições econômicas e eventos globais. Este projeto visa utilizar modelos LSTM e GRU para prever o índice Bovespa, incorporando técnicas de interpretabilidade, como a importância de features, análise de erros, LIME e Valores Shapley. A comparação com um baseline ingênuo fortalece a robustez da análise de séries temporais financeiras.

## Metodologia

### Modelos de Redes Neurais (LSTM e GRU)

Os modelos utilizam lags dos 6 dias anteriores como features. A arquitetura inclui camadas LSTM e GRU com 128 unidades. O treinamento ocorre por 300 épocas. A normalização MinMax é aplicada apenas nos dados de treinamento. Os modelos são avaliados em diferentes janelas de tempo de 3, 7 e 15 dias no futuro.

### Modelo ARIMA

O modelo ARIMA é escolhido automaticamente usando a função auto\_arima da biblioteca pmdarima. Ele utiliza critérios como AIC e BIC para avaliar o ajuste de diferentes combinações de hiperparâmetros.

### Modelos Híbridos

Um modelo híbrido proposto por Zhang combina ARIMA e redes neurais. O ARIMA analisa a parte linear, enquanto a rede neural modela os resíduos não lineares do ARIMA.

## Métricas de Erro e Avaliação

As métricas de erro incluem RMSE, MAE, MASE e MAPE. A seleção de modelos é baseada em RMSE e MASE, visando modelos com desempenho superior ao baseline.

## Resultados e Discussão

O modelo LSTM destaca-se como o mais eficaz, apresentando melhor desempenho em diversas métricas. Os modelos híbridos têm desempenho inferior ao LSTM e GRU. A interpretabilidade é abordada por meio de análise de lags, Shapley Values e LIME.

## Conclusão

O modelo LSTM é identificado como a melhor escolha para previsões do índice Bovespa. A interpretabilidade é considerada, fornecendo insights valiosos sobre as contribuições de diferentes lags. O uso de modelos híbridos mostra limitações em comparação com abordagens puramente baseadas em redes neurais. O trabalho contribui para a compreensão de séries temporais financeiras e aprimora a aplicação de modelos LSTM nesse contexto.

## Referências

- Velarde, G. et al. (2022). An Open Source and Reproducible Implementation of LSTM and GRU Networks for Time Series Forecasting. Eng. Proc. 2022, 18, 30.

- Zhang, G.P. (2003). Time series forecasting using a hybrid ARIMA and neural network model. Neurocomputing, 50, 159-175.

- Hyndman, R.; Athanasopoulos, G. Forecasting: Principles and Practice. 3rd ed. Melbourne, Australia: OTexts, 2021. Acessado em: 19/05/2022. Disponível em: [https://otexts.com/fpp3/](https://otexts.com/fpp3/).


Happy forecasting! 📈✨
