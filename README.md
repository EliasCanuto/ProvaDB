# Resolução da Prova Prática Banco de Dados

## 1ª Questão

```sql
select * from tb_aluno
insert into tb_aluno(codigo_aluno, nome_aluno, ano_nasc, email, sexo)
values ('4', 'Pedro César', '1995-06-04', 'pedro@provaSQL.com.br', 'M')
select * from tb_matricula
insert into tb_matricula(codigo_curso, codigo_aluno)
values ('4', '4')
```
## Resultado 

![q1 2Db](https://user-images.githubusercontent.com/114403979/206186429-af1a1a67-b402-4d8d-9c29-eb38b7826505.png)
<br/>
![q1DB](https://user-images.githubusercontent.com/114403979/206186442-0047b5c9-f95d-4b70-99e5-2033b8503a11.png)


## 2ª Questão

```sql
select tb_aluno.nome_aluno, tb_curso.nome_curso
from tb_aluno
inner join tb_matricula
on tb_aluno.codigo_aluno = tb_matricula.codigo_aluno
inner join tb_curso
on tb_curso.codigo_curso = tb_matricula.codigo_curso
```
## Resultado 

![q2DB](https://user-images.githubusercontent.com/114403979/206186499-aa04cc46-34ac-4e64-b51f-1843522f754f.png)


## 3ª Questão
```sql
select email
from tb_aluno where 2022 - ano_nasc >= 18
```
## Resultado 

![q3DB](https://user-images.githubusercontent.com/114403979/206186533-a190cc9f-05e8-4611-a4ea-f29c2c64f3d8.png)


## 4ª Questão

```sql
select count(codigo_aluno)
from tb_aluno
```
## Resultado 

![q4DB](https://user-images.githubusercontent.com/114403979/206186568-aa8d2e99-5bd3-437c-a59c-e5c1cbec1640.png)


## 5ª Questão

```sql
select tb_curso.nome_curso,
codigo_curso + codigo_aluno as numero_alunos
from tb_curso
inner join tb_aluno
on tb_aluno.codigo_aluno = tb_curso.codigo_curso
```
## Resultado 


![q5DB](https://user-images.githubusercontent.com/114403979/206186607-70f17862-97dd-4c9e-8318-ca044ccb31a5.png)

## 6ª Questão

```sql
select nome_aluno
from tb_aluno where 2022 - ano_nasc >= 18
```
## Resultado 

![02](https://user-images.githubusercontent.com/105735037/206178292-be49f604-890b-494c-9a4b-07f093e433c1.PNG)

## 7ª Questão

```sql
select nome_aluno, sexo
from tb_aluno where sexo = 'F'
```
## Resultado 

![q7DB](https://user-images.githubusercontent.com/114403979/206186706-6570fca1-5caa-41d0-8a2f-c71fc50761dd.png)


## 8ª Questão

```sql
select tb_aluno.nome_aluno as mulheres_em_medicina
from tb_aluno
inner join tb_matricula
on tb_matricula.codigo_aluno = tb_aluno.codigo_aluno
and tb_matricula.codigo_curso = 1
and tb_aluno.sexo = 'F'
```
## Resultado 

![q8DB](https://user-images.githubusercontent.com/114403979/206186751-fd47532f-a7c7-4ba0-ac4a-5aa069914f5b.png)


## 9ª Questão

```sql
select nome_curso
from tb_curo order by nome_curso asc
```
## Resultado 

![q9DB](https://user-images.githubusercontent.com/114403979/206186768-c63918de-50f1-41da-a721-61b891b4f73e.png)

## 10ª Questão

```sql
select tb_aluno.nome_aluno,ano_nasc,sexo, tb_curso.nome_curso
from tb_aluno
inner join tb_curso
on tb_aluno.cod_aluno = tb_curso.cod_curso
where sexo = 'M' and 2022 - ano_nasc >= 18
```
## Resultado 


# Questões teoricas

## Questão 1

Resumidamente, é uma linguagem de programação para lidar com banco de dados relacional (baseado em tabelas). Foi criado para que vários desenvolvedores pudessem acessar e modificar dados de uma empresa. É o acrônimo para Structured Query Language, para acesso e manipulação de dados, principalmente para banco de dados relacionados.

## questão 2

O SQL desenvolvido no início dos anos 70 nos laboratórios da IBM, dentro do prjeto "System R", que tinha objetivo demostrar a viabilidade da implementação do modelo relacional proposto por E.F Codd, nome sequel, acrônimo para "Structured English Query Language". A linguagem é um grande padrão de banco de dados, ela é mais usada por sua simplicidade e facilidade de uso. É uma linguagem declarativa em oposição a outras linguagens procedurais. SQL tenha sido originalmente criado pela IBM, essa expansão de mercado levou a necessidade de ser criado e adaptado um padrão para a linguagem, fieita pela a American National Standards Institute (ANSI). Em 1992 o SQL foi feita uma atualização chamada SQL-92 com sua nova versão, e depois lançado novamento outra versão nos anos de 1999 e 2003 com SQL3 e SQL:1999, usando expressões regulares de emparelhamento e queries recursivas e gatilhos para o inglês "triggers". Depois foi feita introduzida o SQL:2003 características com XML com sequências padronizadas e colunas com valores e colunas-identidade.O padronizado pela a ansi e ISO, possui muitas variações e extenções produzidas pelos diferentes fabricantes de sistemas gerenciadores de bases de dados. Com suas aproximações é permitido para código interagir com o banco de dados. Como por exemplo Java, Perl, C usando funções com PostgreSQL e Oracle incluindo Java.

## questão 3

Sintaxe e semântica específicas da definição de dados SQL e linguagens de manipulação de dados. Ele também fornece estrutura de dados e operações básicas para projetar, avaliar, manter, controlar e proteger bancos de dados SQL. Portabilidade de definição de banco de dados. Os aplicativos podem ser movidos de uma máquina para outra. Os profissionais de SI compartilham uma linguagem comum e reduzem os custos de treinamento. Os profissionais podem se tornar proficientes em seu uso e aumentar a produtividade. Ele fornece longevidade.Ele fornece dependência reduzida de um único fornecedor.
## questão 4

SELECT: Cláusula obrigatória em uma consulta SQL, responsável por listar todas as colunas que serão projetadas na consulta;

FROM: Nesta Cláusula informamos a fonte das informações, podendo ser apenas uma ou várias. Também é obrigatória e juntamente com a cláusula SELECT formam a base de qualquer consulta SQL;

WHERE: Cláusula não obrigatória(opcionais) que restringe os dados obtidos através de operações que testam se cada registro satisfaz a condição ou não;

GROUP BY: Responsável por agrupar os dados com base nos campos informados, estes poderão ser projetados na cláusula SELECT, mas somente poderá constar nesta, os campos listados no GROUP BY ou os campos em funções aritméticas internas do banco.

HAVING: Somente pode ser utilizado quando aplicada a cláusula GROUP BY, visando restringir os dados recuperados através de testes dos campos das funções aritméticas;

ORDER BY: Cláusula muito utilizada tem a função de ordenar a consulta com base em determinados campos ou funções escolhidos pelo usuário, capaz de ordenar campos numéricos e strings;
##  questão 5

A SQL é uma linguagem simples e direta que permite essas manipulações dos dados, algo tão importante para a criação dos mais diversos softwares e sistemas web. Para entender um pouco sobre isso que acabei de falar, precisa ter saber sobre os subgrupos do SQL.
São eles :
DML - Data Manipulation Language

São comandos que alteram informações no banco de dado:

SELECT => utilizado para realizar consultas
INSERT => insere uma nova informação na tabela
DELETE => exclui informações da tabela
UPDATE => muda as variáveis de dados já inseridos 
DDL - Data Definition Language

Esses comandos modificam as próprias tabelas :

CREATE => permite a criação de objetos, como tabelas e novas visualizações
ALTER => adiciona algo a um objeto já existente
DROP => apaga algum objeto 
DCL - Data Control Language

É a parte responsável pelas permissões do banco de dados, restringindo, bloqueando ou permitindo os acessos e as modificações realizadas por um usuário :

GRANT => permite que o usuário acesse e/ou modifique as informações do banco de dados
REVOKE  => proíbe ou impede que o usuário acesse e/ou modifique o banco de dados
DTL - Linguagem de Transição de Dados

É a parte responsável por salvar as alterações feitas pelos usuários :

COMMIT => autoriza que as alterações sejam salvas
ROLLBACK => restaura o banco de dados ao ponto do último COMMIT 
