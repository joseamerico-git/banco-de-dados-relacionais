# Bancodde Dados Relacionais
Santander BootCamp: 
Instrutora: Pâmela Apolinário Borges

# Resumo de Estudos pessoais. By José Américo.

```
    # Criando um database
    CREATE DATABASE NOMEDB;
    USE NOMEDB;

```

# Introdução 

É uma coleção organizada de dados

Tipos: 
- Relacionais/SQL
- Não Relacionais / NoSQL (Not onlySQL)
- Orientado a Objetos
- Hierárquico

Um banco de dados por sí só não é auto-controlado, temos então um SGBD (Sistema Gerenciador de Banco de Dados) que possui um conjunto de ferramentas e recursos para que um Banco de Dados seja administrados.

# Funcionalidades básicas do banco relacional.

CRUD

-Create 
-Read
-Update
-Delete

Um database possui Tupla | Tuple
Linhas
Registros
Chaves estrangeiras
Chaves primárias

Tabelas são composta por linhas e colunas, onde o conjunto delas torna-se um registro.

# SQL é uma linguagem de consulta estruturada

# Banco de Dados Relacionais

# CaracterÍsticas do BD Relacional

- Relacionamento entre tabelas
- Linguagem de Consulta Estruturada
- Integridade referêncial -> Não permite deletar registros em que há um outro relacionamento
- Normalização de dados
- Segurança
- Flexibilidade e extensibilidade -> pode ser alterada 
- Suporte a Transações 

# ACID(Atomicidade, Consistência, Isolamento e Durabilidade)
ex: transações bancárias não permite duas que duas transações aconteçam em mesmo tempo evitando assim confusões de valores. 


# Conceitos básicos SQL.
SQL é um padrão de consultas em banco de dados.

DQL -> Linguagem de consulta de dados (Q) QUERY
    -> SELECT
DML -> Linguagem de Manipulaçõa de dados (M) MANIPULATION
    -> INSERT, UPDATE e DELETE
DDL -> Linguagem de Definição de dados (DDL) DATA DEFINITION
    -> CREATE, ALTER, DROP
DCL -> Linguagem de Controle de Dados (DC) DATA CONTROLS (PERMISSÕES DE ACESSO E CONTROLE)
    -> GRANT, REVOKE
DTL -> Linguagem de Transação de Dados (DT) DATA TRANSACTIONS
    -> BEGIN, COMMIT, ROLLBACK    

# Sintáxe básica de nomenclatura

- Os nomes devem começar com uma letra ou um caractere de sublinhado (_)
- Os nomes podem conter letras, números e caracteres de sublinhado
- Sensibilidade a maiúsculas ou minúsculas vai depender do tipo de banco de dados a ser utilizado.

[Referência dos conceitos](https://www.sqltutorial.org/)

# MER 
- Modelo de entidades e relacionamentos
Modelo conceitual para representar a estrutura conceitual de cada entidade

# DER

- Diagrama de entidades e relacionamentos
Representação gráfica do modelo representados por símbolos que demonstram os relacionamentos e a estrutura de um bd.

# Entidades 

As entidades são nomeadas com substantivos concretos ou abstratos que representam de forma clara sua função dentro do domínio.

Ex: usuarios, destinos, reservas etc...

# Atributos 

Os atributos são características ou propriedades das entidades. Que descrevem as informações específicas sobre uma entidade.


Ex: 

Entidade usuario tem atributos --> nome, email, senha...

Abaixo um link para poder criar alguns diagramas.
@@ Guia anónima ------>> 123
[Creately](https://creately.com/pt/home/)

# Criamos um diagrama vazio

Criamos três entidades Usuario, Destinos e Reservas

Usuarios com id, nome, dataNascimento etc...

# Existem duas maneiras de representar os atributos em diagramas a conotação utilizaraemos então a conotação tradicional elipse, porém o diagrama fica um pouco poluido visualmente

# Relacionamentos 

1..1 (um para um) --> uma instância de uma entidade pode estar relacionado no máximo a uma instância de uma outra entidade 

1..n ou 1..* (um para muitos) uma instância de entidade pode estar relacionada a uma ou muitas instâncias de uma outra entidade

n..n ou *..* (muitos para muitos) muitas instâncias de uma entidade podem estar relacionadas a muitas instâncias de uma outra entidade.

No exemplo de usuário e reserva temos que:

A cardinalidade de usuarios para reservas é 1..n, porém a cardinalidade de reservas para usuários é 1..1.

             Um [usuário] 1..1 ______<realiza>______0..n [reservas]

             Nenhuma ou mais [reservas]0..n______<vicula>______ 1..1 [destino]

[Interessante](https://www.quickdatabasediagrams.com/) Denenhando projetos on-line.

Configuração do cloudclusters
Criar um usuário
adm
permission --super
senha padrão --> Mariadb


As tabelas servem para organizar os dados
As colunas representam atributos de acordo com o tipo de dado que é definido no momento da criação (DDL).
Os registros são as informações aramazenadas nas linhas dessa tabela.

# COMANDOS DDL

CREATE TABLE {{NOMETABELA}} 
    (
        {{COLUNA}} {{TIPO}} COMMENT
        {{'COMENTARIO'}}


    );

# TIPOS PODEM VARIAR DEPENDENDO DO SGBD

INTEGER | DECIMAL | NUMERIC | CHARACTER | VARCHAR | DATA | BOOLEAN | TEXT
OPÇÕES RESTRIÇÕES DE VALORES 
NOT NULL| UNIQUE | DEFAULT
PRIMARY KEY | FOREIGN KEY | AUTO_INCREMENT

[PhpMyAdmin](https://phpmyadmin-c013.cloudclusters.net/index.php)

SCRIPTS
```

CREATE TABLE usuarioas (
    id INT,
    nome VARCHAR(255) NOT NULL COMMENT 'Nome do usuário',
    email VARCHAR(100) UNIQUE NOT NULL COMMENT 'Email do usuário',
    data_nascimento DATE NOT NULL COMMENT 'Data de nascimento do usuário',
    endereco VARCHAR(255) NOT NULL COMMENT 'Endereço do usuário'

);

CREATE TABLE viagens.destinos (
    id INT,
    nome VARCHAR(255) NOT NULL UNIQUE COMMENT 'Nome do destino',
    descricao VARCHAR(255) NOT NULL COMMENT 'Descricao do destino'
        
);

CREATE TABLE viagens.reservas (
 id INT COMMENT 'Identificador único da reserva',
 id_usuario INT COMMENT 'Referência ao ID usuário que faz a reserva',
 id_destino INT COMMENT 'Referência ao ID destino na reserva',
 data DATE  COMMENT 'Data da reserva',
 status VARCHAR(255) DEFAULT 'pendente' COMMENT 'Status da reserva (confirmada, pendente, cancelada, etc...)'


);

```
# DML(S)

# INSERT

```
insert into USUARIOS (id,nome,email,data_nascimento,endereco) 
values (1,'JOÃO PEDRO','jp@gmail.com','2019-11-25','XV DE NOVEMBRO, 5000 ASSIS/SP');

insert into USUARIOS (id,nome,email,data_nascimento,endereco) 
values (2,'JUNIHO','jr@gmail.com','2000-11-25','XV DE NOVEMBRO, 5000 ASSIS/SP');

insert into USUARIOS (id,nome,email,data_nascimento,endereco) 
values (3,'SEBASTIÃO','sb@gmail.com','1998-11-25','XV DE NOVEMBRO, 5000 ASSIS/SP');

insert into destinos (id,nome, descricao) 
values 
(1,"Praia do Tenôrio de Ubatuba","Maravilhosa praia para suas férias");

insert into destinos (id,nome, descricao) 
values 
(3,"Praia Asturias","Maravilhosa praia para suas férias"),
(4,"Praia deserta","Maravilhosa praia para suas férias");


insert into reservas (id,id_destino,id_usuario,status,data) values (1,1,1,'pendente','2023-09-28');

insert into reservas (id,id_destino,id_usuario,status,data) values (2,1,2,'concluido','2023-09-28');

insert into reservas (id,id_destino,id_usuario,status,data) values (3,2,2,'concluido','2023-09-28');

insert into reservas (id,id_destino,id_usuario,status,data) values (4,2,3,'concluido','2023-09-28');

```

# SELECT 

Observação com o Like pegamos também padrões exemplo sem precisar clausula where select *from reservas where status like 'concluido';
```
    # SELECT *FROM USUARIOS;
    # SELECT *FROM USUARIOS ORDER BY nome;
    # SELECT *FROM USUARIOS WHERE id = 1;
    # SELECT *FROM USUARIOS WHERE data_nascimento between '2019-11-25' and '2023-09-28';

```

# UPDATE

```
    UPDATE USUARIOS SET NOME = 'SEBASTIAO DA SILVA' WHERE USUARIOS.ID = 3;
    UPDATE USUARIOS SET NOME = 'SEBASTIAO DA SILVA', email ='sbsilva@gmail.com' WHERE USUARIOS.ID = 3;


```

# DELETE 

```
    DELETE FROM USUARIOS WHERE ID =2;
```

A clausula where funciona com um filtro para a consulta seguida das (condições)

# ALTERANDO AS TABELAS PARA CORRIGIR A FALTA DE RELACIONAMENTOS
# COMANDOS DDL

```
    # Alterando nome da tabela
    ALTER TABLE usuarioas_nova RENAME usuarios; 

```

# RECRIANDO UMA TABELA PARA MIGRAR DADOS DE UMA TABELA A SER ALTERADA.

```
CREATE TABLE usuarioas_nova (
    id INT,
    nome VARCHAR(255) NOT NULL COMMENT 'Nome do usuário',
    email VARCHAR(100) UNIQUE NOT NULL COMMENT 'Email do usuário',
    data_nascimento DATE NOT NULL COMMENT 'Data de nascimento do usuário',
    endereco VARCHAR(255) NOT NULL COMMENT 'Endereço do usuário'

);

# Migrando os dados de uma table utilizando um DUMP, porem vamos fazer de outra # forma.

# Migrando os dados

INSERT INTO usuarios_nova (id,nome,email,endereco,data_nascimento)
SELECT id,nome,email,endereco,data_nascimento from usuarios;


drop table usuarios;





```

# EXLUINDO TABELAS

```
  DROP TABLE NOMETABELA  

```




