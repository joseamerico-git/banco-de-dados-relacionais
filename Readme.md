# Bancodde Dados Relacionais
Santander BootCamp: 
Instrutora: Pâmela Apolinário Borges

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

[Interessante](https://www.quickdatabasediagrams.com/)






