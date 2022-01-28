# Project-Rossmann-Sales-Forecast 



![nick-morrison-FHnnjk1Yj7Y-unsplash](https://user-images.githubusercontent.com/94136773/151415576-1b2ee7ae-07e5-4051-9114-4f71c6504cde.jpg)


## Contexto

#### Projeto de Previsão de Vendas de uma Rede de Farmácias.

A Rossmann é uma grande Rede de Farmácias, com operação na Europa. A diversos fatores que influênciam as vendas, porém não há uma metodologia padrão utlizada para todas as lojas, a previsão de vendas é baseadas de forma individual com base de circunstâncias únicas ocasionando resultados com imprecisão e variados.  

Os dados utilizados foram disponibilizados pela Rossmann através do site Kaggle, contendo dados de vendas até o ano de 2016.

O contexto é fictício, e foi utilizado para descrever um problema real enfrentado por grandes Varejistas, que é padronizar a previsão de vendas em sua rede de lojas. 

## 1. Questão de Negócio

### 1.1. Problema 

Durante uma reunião mensal, foi requisitado pelo CFO da empresa uma previsão de Vendas das Próximas 6 semanas de cada Loja. Pois será necessário ter dados mais precisos para definição do Budget para a Reformas das lojas. 

### 1.2. Causas do Problema

Predição de vendas usada atualmente apresenta muitas divergências, pois é baseado em Experiências Passadas, feita manualmente de forma individual por cada loja. A visualização das vendas é limitada ao computador

### 1.3. Solução 

Será desenvolvido uma solução com uso de Machine Learning para realizar a previsão de Vendas de todas as lojas, assim padronizando a metodologia de previsão de  e buscando aumentar a assertividade das mesmas. 
A visualização das predições poderão ser feitas pelo Smartphone. 


## 2. Descrição das Variáveis.

Variáveis  do daset original:

| Variável |  Descrição  |
| ------------------- | ------------------- |
|  store |  Id único para cada loja |
|  day_of_weed |  dia da semana da data de registro |
|  day |  data do registro |
|  sales |  faturamento da loja na data do registro |
|  customers |  quantidade de clientes na loja no data do registro |
|  open |  loja aberta( 0= fechada, 1 =  aberta ) |
|  state_holiday |  feriado nacional( a= public, b = easter, c = christmas, 0 = dia comum |
|  school_holiday |  indica se a loja  foi afetada pelo fechamento de escolas públicas |
|  store_type |  modelo da loja( a, b, c, d) |
|  assortment |  nivel de varidades dos produtos( a = basic, b = extra, c = extended ) |
|  competition_distance |  distancia em metros do competidor mais próximo |
|  competition_open_since_month |  mês de abertura do competidor mais próximo |
|  competition_open_since_year |  no de abertura do competidor mais próximo |
|  promo |  promoção ativa no dia do registro |
|  promo2 |  promoção contínua e consecutiva(0 = não participou, 1 = paricipou) |
|  promo2_since_week |  semana onde a loja entrou em promo2 |
|  promo2_since_year |  ano em que a loja entrou em promo2 |
|  promo_interval |  meses de início anual que a promo2 foi iniciada(ex:.feb, may, aug) |


Variáveis derivadas no Feature Selection:

| Variável |  Descrição  |
| ------------------- | ------------------- |
|  competition_since |  data inícial da existência de conpetidores |
|  dcompetition_time_month |  número de mêses desde que houve a existência de competidores |
|  promo2_since |  data inicial de atividade da promo2 |
|  promo2_time_week |  número de semanas de atividade da promo2 |



## 3. Planejamento da Solução:

### 3.1. O que será entregue:

- Bot desenvolvido no aplicativo Telegram, ao qual será possível ao inserir o código da loja retorna em tempo real a previsão de venda para as próximas  6 semanas. Estas consultas poderão ser realizadas via celular, ou qualquer dispositivo que consiga acessar o Telegram.

### 3.2. Ferramentas Usadas:

- Python 3.8;
- Jupyter Notebook;
- Panda Enviroment;
- Git e Github;
- Heroku;
- Flask e python API's

### 3.3. Processo :

- Coleta de Dados: Através de download dos dados disponibilizados do site Kaggle(https://www.kaggle.com/c/rossmann-store-sales/data)
- Limpeza dos Dados: Organizar e Renomear colunas, descrever os tipos, dimensão, checar dados faltantes e Realizar Descrição estatística, criar hipóteses de negócio criando novas variáveis para exploração destas adiante.
- Exploração dos dados: Fazer análise gráfica das variáveis, validar as hipóteses levantadas.
- Modelagem dos dados: Será feita a transformação das variáveis fazendo ajuste de escala e fazendo as transformações necessárias para podermos usar o algoritmos de Machine Learning da melhor forma. Usaremos o Boruta junto com a analise das hipóteses para escolher as variáveis para o modelo final.
- Algoritmo de Machine Learning: Sera feita a avaliação de alguns algortmos de Machine Learning, usando o método Cross Validation para definir qual algoritmo usaremos. Definido o Algoritmo, usaremos a técnica de Random Search para definirmos os melhores parâmetros apara o nosso modelo.
- Avaliação do Algoritmo: Interpretar o erro e o intervalo das predições das vendas encontrados, caso já gere valor para empresa, colocá-lo para produção
- Modelo em Produção: Colocar o  modelo no Heroku para hospedá-lo e ficar sempre disponível para acesso, onde usaremos um bot do telegram para realizar consultos. 

Este processo passo a passo esta detalhado no Notebook localizado no repositório do github: https://github.com/LucasAsilveira/Project-Rossmann-Sales-Forecast/blob/main/Project_Rossmann_FinalV0.0.ipynb

## 4. Principais Insights dos Dados:

1. Lojas com maior sortimentos deveriam vender mais.( FALSO )¶
- Insight Gerado:  Vimos que um maior número de sortimentos não geraram mais lucros, assim a equipe de estratégias pode fazer uma reavaliação da quantidade de sortimentos nestas lojas. 

2. Lojas com competidores mais próximos deveriam vender menos.¶( FALSO ) 
- Insight Gerado: A proximidade dos competidores não tiveram um impacto negativo nas vendas, assim quando forem abrir novas filiais não é a principal aspecto a se preocupar. 

3. Lojas deveriam vender mais depois do dia 10 de cada mês.( VERDADEIRO )
- Insigth Gerado: É percebido um aumento do acumulado nas vendas após dia 10, mesmo levando em consideração que o acumulado possuí mais dias no mês após o dia 10, não há uma queda de vendas significativa, o que faz com que os 10 primeiros dias não sejam tão relevantes com a equipe de vendas sugeria. Podendo usar isto para promoções durante o mês. 

## 5. Resultados financeiros para o negócio:



## AINDA EDITANDO....

5. Resultados financeiros para o negócio:
- Quanto a empresa espera lucrar com a sua
solução ?
6. Conclusão:
- Seu objetivo inicial foi alcançado? Sim ? Não ?
Porque ?
7. Conclusão:
- Seu objetivo inicial foi alcançado? Sim ? Não ?
Porque ?

	
	
	
 	
		
	
	
	
	
	
	
