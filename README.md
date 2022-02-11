## Desafio SQL

## Descrição do Projeto
<p>Projeto desenvolvido para o desafio da Gama Academy onde a proposta foi fazer a nossa primeira estrutura de banco de dados em SQL.</p>

### REQUISITOS MÍNIMOS PARA ENTREGA:

# E-commerce

<p>Criação de um banco de dados em MySql conforme o esquema abaixo.</p>

<img src="./imgReadme/esquema.png"/>

<p>O conjunto de instruções SQL que implementam este modelo está a seguir:
<h1>Criando tabela cliente</h1>
   
           CREATE TABLE cliente(

            id INTEGER NOT NULL AUTO_INCREMENT PRIMARY KEY, 

            nome VARCHAR(100) NOT NULL, 

            email VARCHAR(70) NOT NULL UNIQUE, 

            senha VARCHAR(20) NOT NULL, 

            cpf VARCHAR(15) NOT NULL UNIQUE

            );
   

<h1>Criando tabela  departamento</h1>



    CREATE TABLE departamento(

      codigo INTEGER NOT NULL AUTO_INCREMENT PRIMARY KEY, 

      nome   VARCHAR(50) NOT NULL, 

      descricao TEXT

      );


<h1>Criando tabela endereco</h1>
            
      CREATE TABLE endereco(

         num_seq    INTEGER NOT NULL AUTO_INCREMENT PRIMARY KEY, 

         tipo       VARCHAR(5) NOT NULL, 

         logradouro VARCHAR(45) NOT NULL, 

      numero     INTEGER, 

      complemento VARCHAR(20), 

      bairro     VARCHAR(30), 

      cidade     VARCHAR(50),

      estado     VARCHAR(2), 

      cep        VARCHAR(10), 

      cliente_id INTEGER NOT NULL,

      CONSTRAINT endereco_cliente FOREIGN KEY 

      (cliente_id) REFERENCES cliente(id)

      );
</p>
<h1>Criando tabela pedido</h1>

      CREATE TABLE pedido(

         numero INTEGER NOT NULL AUTO_INCREMENT PRIMARY KEY, 

         status VARCHAR(1) NOT NULL, 

         data_pedido DATE, 

         valor_bruto DOUBLE, 

         desconto    DOUBLE, 

         valor_final   DOUBLE, 

         cliente_id INTEGER NOT NULL,

         CONSTRAINT cliente_pedido FOREIGN KEY 

            (cliente_id) REFERENCES cliente(id)

         );

<h1>Criando tabela produto</h1>

      CREATE TABLE produto(

         codigo INTEGER NOT NULL AUTO_INCREMENT PRIMARY KEY, 

         nome VARCHAR(45) NOT NULL, 

         descricao TEXT, 

         preco DOUBLE, 

         estoque INTEGER, 

         link_foto VARCHAR(255), 

         departamento_codigo INTEGER NOT NULL,

         CONSTRAINT produto_depto FOREIGN KEY 

         (departamento_codigo) REFERENCES departamento(codigo)

        );


 <h1>Criando tabela item_pedido</h1>


        CREATE TABLE item_pedido(

         num_sequencial INTEGER NOT NULL AUTO_INCREMENT PRIMARY KEY, 

         quantidade INTEGER, 

         valor_unitario DOUBLE, 

         valor_total DOUBLE, 

         produto_codigo INTEGER NOT NULL, 

         pedido_numero INTEGER NOT NULL,

         CONSTRAINT item_produto FOREIGN KEY 

         (produto_codigo) REFERENCES produto(codigo),

         CONSTRAINT item_pedido FOREIGN KEY 

         (pedido_numero) REFERENCES pedido(numero)
      );

# Com base nestas informações, realize os seguintes exercícios, gerando instruções SQL para responder às questões.

<ol>
    <li>Este exercício é livre para você inserir dados nas tabelas. Adicione vários dados em todas as tabelas. Crie vários clientes, com vários endereços. Insira muitos produtos em vários departamentos. Crie pedidos em várias datas com meses diferentes (serão necessários para os próximos exercícios).</li>
    <li>Quantos clientes estão cadastrados na sua base?</li>
    <li>Qual o produto mais caro?</li>
    <li>Qual o produto mais barato?</li>
    <li>Mostre todos os produtos com seus respectivos departamentos.</li>
    <li>Quantos produtos há em cada departamento? Exiba o nome do departamento e a quantidade de produtos que há em cada um. (pense em SUM e GROUP BY)</li>
    <li>Mostre os dados dos pedidos, incluindo nomes dos clientes e nomes dos produtos que foram vendidos.</li>
    <li>Mostre quantos pedidos foram feitos por mês no ano de 2022 (caso você tenha registros neste ano, senão escolha um ano que você tenha cadastrado - Novamente pense em COUNT e GROUP BY).</li>
    <li>Mostre quanto foi faturado por mês (leve em conta o valor total de cada pedido - novamente pense em GROUP BY e SUM).</li>
    <li>Mostre o valor total do estoque por departamento.</li>
</ol>




### Autor
[<img src="https://avatars.githubusercontent.com/u/66260886?v=4" width=115 > <br> <sub> Gisele Correia </sub>](https://github.com/GiseleCorreia) |
| :---: |  

Feito por Gisele Correia 👋🏽 Entre em contato!

[![Linkedin Badge](https://img.shields.io/badge/-Gisele-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/maria-gisele-correia-53180483/)](https://www.linkedin.com/in/maria-gisele-correia-53180483/) [![Gmail Badge](https://img.shields.io/badge/-mariagisele12@gmail.com-c14438?style=flat-square&logo=Gmail&logoColor=white&link=mailto:mariagisele12@gmail.com)](mailto:mariagisele12@gmail.com)
