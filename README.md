# Análise Exploratória Utilizando o SQLite

## Objetivo:
Este projeto tem como objetivo realizar uma análise exploratória simples, respondendo cinco perguntas utilizando apenas SQLite + dBeaver. 
Neste projeto, busquei aprimorar minhas habilidades em manipulação de dados e consulta em bancos de dados relacionais. A análise inclui a aplicação de técnicas como:
Funções de Agregação, Manipulação de Data, Condicionais com CASE WHEN, CTEs e JOINs entre Tabelas.

O dataset escolhido foi o [Marketplace Transactional Dataset](https://www.kaggle.com/datasets/petewojtczak/raw-transactional-data) que fornece dados transacionais, consistindo em cinco tabelas inter-relacionadas:

1. Explorando as tabelas pela primeira vez no banco de dados uso o comando LIMIT para evitar o carregamento excessivo dos dados;<br>
![pergunta1](imgs/img1%20-%20conhecendodataset.png)

2. Para responder qual a categoria de produto mais 'comum' do marketplace utilizo o comando COUNT para contar a ocorrência de cada product_category_name. Em seguida, faço agrupamento dos resultados por categoria e ordeno pela contagem em ordem decrescente. Aplico limit para aparecer apenas a categoria mais frequente.<br>
![pergunta1](imgs/img2%20-%20ask1.png)
![pergunta1](imgs/img2%20-%20ask1r.png)

3. Para identificar o estado dos vendedores que possui os três produtos mais caros faço um inner join entre as tabelas order_items e sellers, utilizando o seller_id.
Ordeno os preços encontrados na tabela order_items em ordem decrescente e exibo o estado dos vendedores encontrado na tabela sellers. Aplico LIMIT 3 para trazer os três maiores preços<br>
![pergunta1](imgs/img3%20-%20ask2.png)
![pergunta1](imgs/img3%20-%20ask2r.png)

Etapa 4<br>
![pergunta1](imgs/img4%20-%20ask3.png)
![pergunta1](imgs/img4%20-%20ask3r.png)

Etapa 5<br>
![pergunta1](imgs/img5%20-%20ask4.png)
![pergunta1](imgs/img5%20-%20ask4r.png)

Etapa 6<br>
![pergunta1](imgs/img6%20-%20ask5.png)
![pergunta1](imgs/img6%20-%20ask5r.png)


