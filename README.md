# Rossman Sales Prediction
Meu primeiro projeto completo de Data Science. Foi utilizada a metodologia CRISP-DM no desenvolvimento do projeto. 

## 1. Sobre o Projeto
### 1.1. Problema de Negócio
A Rossmann é uma rede de farmácias. Seu CEO deseja obter previsões de faturamento por loja para as próximas 06 semanas, a fim de decidir em quais lojas ele deve investir (em estoque, melhorias, etc).

### 1.2. Data Overview
São 03 datasets: de lojas, de treino e de teste do modelo de Machine Learning. 

Todos os dados foram extraídos do [Kaggle](https://www.kaggle.com/c/rossmann-store-sales) ![kaggle](https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=Kaggle&logoColor=white)

### 1.3. Premissas
n/a.

### 1.4. Solução

**1.4.1. Análise Descritiva:** análise de cada coluna da base de dados, obtendo uma tabela com um resumo estatístico da base de dados.

**1.4.2. Geração de Hipóteses (feature engineering):** elaborei um mapa de hipóteses sobre quais variáveis poderiam afetar a variável-resposta, a saber, o faturamento por loja. Foram geradas 20 hipóteses. Em seguida, o dataset foi tratado para obter as colunas necessárias ao posterior teste de hipóteses.

**1.4.3. Filtragem dos Dados:** eliminação de linhas/colunas desnecessárias ao teste de hipóteses, como lojas fechadas ou com vendas zeradas.

**1.4.4. EDA - Análise Exploratória dos Dados:** foram elaboradas análises **univariada, bivariada e multivariada** das variáveis que poderiam afetar a variável-resposta. Em seguida, verifiquei se as hipóteses geradas anteriormente eram verdadeiras ou falsas. Estas análises permitiram identificar algumas variáveis relevantes para o posterior treinamento do modelo de Machine Learning.

**1.4.5. Preparação dos Dados:** normalização, rescaling e transformação (encoding e transformação) das variáveis. A normalização não foi efetuada pois não foram encontradas variáveis numéricas com distribuição normal.

**1.4.6. Seleção de Atributos (feature selection):** divisão do dataset em treino e teste. Utilização do **algoritmo Boruta** como seletor de variáveis. Foi identificado um problema grave nesta etapa: o elevado consumo de memória e processamento do Boruta, motivo pelo qual precisei executá-lo no ambiente **Google Colab**.

**1.4.7. Modelos de Machine Learning:** utilização de vários modelos de ML para previsão das vendas das lojas, seguida do **Cross Validation** de cada um, comparando os valores de MAPE, MAE e RMSE. Modelos utilizados:
- modelo de média
- modelo de regressão linear
- modelo de regressão linear - Lasso
- modelo Random Forest
- **modelo XGBoost - modelo escolhido em função do desempenho versus custo de aplicação do modelo**

**1.4.8. Hyperparameters Fine Tuning:** utilização de **Random Search** para fazer o fine tuning dos parâmetros adotados pelo modelo XGboost.

**1.4.9. Performance:** cálculo da performance do modelo (taxa de erros) e geração de cenários **worst case e best case** para o faturamento total da rede Rossmann com base nas previsões do modelo.

**1.4.10. Deployment:** publicação do modelo em ambiente de cloud (Heroku), acessível através de **bot do Telegram** via requisições de API.

## 2. Tecnologias Utilizadas
- Python 3.10
- Visual Studio Code 1.63
- Jupyter Notebook
- Heroku Cloud
- Flask 2.0.2
- Telegram

## 3. Utilização
As previsões por cada loja podem ser acessadas através do bot do Telegram criado no projeto. Basta adicionar o @rossmansales_bot aos seus contatos e enviar o número da loja como mensagem. 

## 4. Status do Projeto
O projeto está **concluído**. Foi adotada a metodologia de gerenciamento de projetos **CRISP-DM** para obtenção, em curto período de tempo, de uma solução razoável. O modelo adotado faz previsões satisfatórias de cada loja da rede para as próximas 06 semanas, acessíveis pelo smartphone através de um bot do Telegram. 

## 5. Lições Aprendidas
- A Análise Exploratória fornece insights relevantes para o negócio, muitos dos quais contrariando as hipóteses lançadas. Além disso, esta etapa permite estimar algumas variáveis relevantes que serão selecionadas na etapa de feature selection.
- A escolha do modelo de Machine Learning deve levar em conta não apenas a taxa de acertos do modelo, mas também o seu custo operacional (memória, processamento). 

## 6. Melhorias Sugeridas
- Criação de modelos específicos para as lojas onde o modelo aqui adotado teve performance insatisfatória.
- Análise detalhada dessas lojas.
- Adição de funcionalidades ao bot do Telegram, por exemplo: exibição de gráficos.

## 7. Agradecimentos
Este projeto é um exercício do curso *DS em Produção*, ministrado na [Comunidade DS](https://www.linkedin.com/company/comunidade-ds/).

## 8. Contato
Projeto criado por Joao Marcos Visotaky Junior

Data Scientist em formação

[Portfolio de Projetos](https://joaomj.github.io/portfolio_projetos/)
