# Análise Exploratória Utilizando o SQLite

## Objetivo:
Este projeto tem como objetivo realizar uma análise exploratória simples, respondendo seis perguntas utilizando apenas SQLite + dBeaver. 
A ideia é explicar o que fiz em cada código para conseguir responder a pergunta. Neste projeto, busquei aprimorar minhas habilidades em manipulação de dados e consulta em bancos de dados relacionais. A análise inclui a aplicação de técnicas como: Funções de Agregação, Manipulação de Data, Condicionais com CASE WHEN, CTEs e JOINs entre Tabelas.

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

4. Para responder sobre a distribuição de contatos com clientes, utilizo a função strftime para extrair apenas ano e mês da coluna timestamp fazendo a conversão para o formato AAAA-MM. Conto os contatos únicos utilizando COUNT(DISTINCT, faço agrupamento pelo campo year_month que foi gerado na função strftrime para calcular a contagem de contatos por mês, por fim, ordeno os resultados em ordem crescente.<br>
![pergunta1](imgs/img4%20-%20ask3.png)
![pergunta1](imgs/img4%20-%20ask3r.png)

5. Na receita total gerada por cada produto, utilizei uma CTE para calcular o preço médio por categoria de produto, a consulta interna faz um SELECT do nome da categoria de produto (product_category_name) da tabela products e calcula a média dos preços da tabela order_items relacionada através de um INNER JOIN usando o product_id comum às duas tabelas. Por fim, utilizo ROUND para arredondar o valor da média dos preços.
Após definir a CTE, a consulta final seleciona o product_category_name e o preco_medio da CTE media_preco, ordenando os resultados em ordem alfabética (ORDER BY product_category_name).<br>
![pergunta1](imgs/img5%20-%20ask4.png)
![pergunta1](imgs/img5%20-%20ask4r.png)

6. Para responder sobre a relação entre o peso dos produtos e suas avaliações utilizei uma CTE e fiz um INNER JOIN entre três tabelas, products, order_items e order_reviews por product_id, order_id. Usei CASE para categorizar as faixas de peso entre menor que 1000g, entre 1000g e 10000g, entre 10000g e 20000g e maior que 20000g. Também fiz o cálculo das médias das avaliações e arredondei com ROUND. Agrupei pela faixa peso e ordenei com CASE para ficar organizado.<br>
![pergunta1](imgs/img6%20-%20ask5.png)
![pergunta1](imgs/img6%20-%20ask5r.png)


