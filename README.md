# Project-Rossmann-Sales-Forecast

![nick-morrison-FHnnjk1Yj7Y-unsplash](https://user-images.githubusercontent.com/94136773/151415576-1b2ee7ae-07e5-4051-9114-4f71c6504cde.jpg)
Projeto de Previsão de Vendas.

## 1. Contexto

A Rossmann é uma grande Rede de Farmácias, com operação na Europa. A diversos fatores que influênciam as vendas, porém não há uma metodologia padrão utlizada para todas as lojas, a previsão de vendas é baseadas de forma individual com base de circunstâncias únicas ocasionando resultados com imprecisão e variados.  

Os dados utilizados foram disponibilizados pela Rossmann através do site Kaggle, contendo dados de vendas até o ano de 2016.(https://www.kaggle.com/c/rossmann-store-sales/data)

O contexto é fictício, e foi utilizado para descrever um problema real enfrentado por grandes Varejistas, que é padronizar a previsão de vendas em sua rede de lojas. 

## 2. Problema de Negócio

### 2.1 Problema 

Durante uma reunião mensal, foi requisitado pelo CFO da empresa uma previsão de Vendas das Próximas 6 semanas de cada Loja. Pois será necessário ter dados mais precisos para definição do Budget para a Reformas das lojas. 

### 2.2 Causas do Problema

Predição de vendas usada atualmente apresenta muitas divergências, pois é baseado em Experiências Passadas, feita manualmente de forma individual por cada loja. A visualização das vendas é limitada ao computador

### 2.3 Solução 

Será desenvolvido uma solução com uso de Machine Learning para realizar a previsão de Vendas de todas as lojas, assim padronizando a metodologia de previsão de  e buscando aumentar a assertividade das mesmas. 
A visualização das predições poderão ser feitas pelo Smartphone. 


## 3. Descrição das Variáveis.

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



	
	
	
 	
		
	
	
	
	
	
	
