
## API REST Laravel 

# O que foi usado nessa aplicação:

 - Homestead;
 - Postman para realizar os teste;

# Como Usar

 - Para testar aconselho usar o Postman e enviar os campos abaixo:

## Para Cadastrar Cliente:

	Enviar um Post com os campos (endpoint:/customer):
 - name = string;
 - cpf = numérico; (deve ser um cpf válido para teste sugiro usar algum
   gerador de cpf);

 - birthdate = no formato Y/M/D (exemplo: 2018-04-15);

## Para Cadastrar um Produto:

	Enviar um Post com os campos (endpoint:/product):

 - code = numérico;

 - name = string;

 - price = valor;

## Para Cadastrar um Pedido

	Enviar um Post com os campos (endpoint:/order):

		

 - customer_id = deverá ser enviado (poderá ser resgato na consulta do
   cliente);

## Para Cadastrar um ItemPedido

	Enviar um Post com os campos (endpoint:/orderProduct):

 - order_id = poderá ser resgatado no get de pedidos;
 - product_id = poderá ser resgatado no get dos produtos;
 - quantity = numérico acima de 0;
 - discount = deverá ser percentual, caso não enviar esse campo o mesmo será 0;

# Filtros e Buscas

## Buscar no endpoint /customer:

	 	

 - cpf = passar por get o campo(cpf) com numero exato;
 - name = passar por get o campo(name) com nome a ser pesquisado (pode ser apenas o primeiro nome ou uma letra) ;

	

 - data de nascimento = passar por get o campo(birthdate) e a data 
   no formato  Y/M/D (exemplo: 2018-04-15);


## Buscar no endpoint /product:


 - code = passar por get o campo(code) e o numero exato;
 - name = passar por get o campo(name) e o nome ;

## Buscar no endpoint /order:

 - Cliente = passar por get no campo(customer_id) o id do cliente, o mesmo
   poderá ser regatado em qualquer busca no endpoint 		   customer ou ao
   solicitar o get sem parametro;

	

 - Codigo do pedido = passar por get no campo(code) o codigo do pedido, o mesmo    poderá ser resgatado ao concluir o pedido ou 		   qualquer das
   buscas mencionadas;

	

 - Emissão = passar por get no campo (emission) a data da emissão
   do pedido no formato  Y/M/D, poderá ser pesquisada por ano também ou mês ;

 - Total do pedido = Passar por get no campo (total_order) o valor total
   exato do pedido;
 - Produtos = passar por get no campo (product_id) o id do produto, o mesmo   poderá ser resgatado em qualquer busca no 				  endpoint product ou
   solicitar o get sem parâmetro;

## Banco de Dados
Alterar o arquivo .ENV.EXAMPLE para .ENV.
No arquivo .ENV deverá alterar DB_DATABASE="*seubandodados*"  para o nome do seu banco de dados.  
Apos executar o migrate com o seed no comando abaixo:

    php artisan migrate --seed
