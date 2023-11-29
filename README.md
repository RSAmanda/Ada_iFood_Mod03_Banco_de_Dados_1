# Banco de Dados 1
- Professor Matheus Andrade

## Aula 1
### O que é banco de dado?

 Um banco de dados é um sistema organizado de informações que pode ser acessado, gerenciado e atualizado de maneira conveniente. Em termos simples, um banco de dados é um armário gigante que armazena informações sobre tudo, desde os nomes de clientes até informações de produtos, registros financeiros e muito mais.

### Utilidade de um banco de dados
Um banco de dados é como um grande armário de arquivos, mas em vez de papel, ele armazena informações digitais. Ele é projetado para armazenar e gerenciar grandes quantidades de dados de maneira organizada e eficiente. Assim como um armário de arquivos é útil para manter documentos organizados e fáceis de encontrar, um banco de dados é útil para armazenar e acessar informações de maneira rápida e eficiente.

 Com um banco de dados, você pode armazenar todas essas informações em uma única fonte confiável e organizada. Você pode facilmente acessar e atualizar informações sobre seus produtos, clientes e pedidos em tempo real, em vez de ter que procurar em vários arquivos ou documentos. Você pode gerar relatórios e análises para ajudar a entender melhor seu negócio e tomar decisões informadas com base nos dados.

### PostgreSQL

O PostgreSQL é conhecido por sua confiabilidade, escalabilidade e desempenho. Ele foi projetado para suportar cargas de trabalho pesadas e é altamente personalizável, permitindo que os usuários ajustem o sistema de acordo com suas necessidades específicas. Além disso, ele é altamente compatível com padrões do setor e oferece suporte a muitos recursos avançados, como transações ACID, índices em texto completo, integridade referencial e muito mais. Ele é uma das ferramentas de banco de dados mais populares do mercado, oferecendo recursos avançados de segurança, confiabilidade e escalabilidade.

### Tipos de banco de dados:
#### 1 - Banco de dados relacionais

Os bancos de dados relacionais são baseados em uma estrutura de tabelas inter-relacionadas. Os dados são organizados em tabelas, cada uma com uma coluna para um tipo específico de dado e cada linha contendo uma entrada individual. As tabelas são inter-relacionadas por meio de chaves primárias e estrangeiras, que são usadas para vincular os dados em diferentes tabelas. O SQL (Structured Query Language) é a linguagem de programação mais comumente usada para manipular bancos de dados relacionais.

#### 2 - Banco de dados não-relacionais

Os bancos de dados não relacionais são projetados para armazenar dados sem a estrutura rígida de tabelas e esquemas relacionais. Eles são mais flexíveis em termos de como os dados são organizados e podem ser mais escaláveis e tolerantes a falhas do que os bancos de dados relacionais. Eles também podem ser usados para armazenar tipos de dados mais complexos, como documentos, gráficos e dados de séries temporais. Exemplos de bancos de dados não relacionais incluem bancos de dados de documentos, bancos de dados de grafos e bancos de dados de séries temporais.

### Instalação PostgreSQL

A maneira mais fácil de instalar o PostgreSQL no Windows é através do instalador disponível no site oficial.

[O link para download](https://www.postgresql.org/download/windows/).

Basta baixar o arquivo de instalação correspondente à versão desejada, executá-lo e seguir as instruções na tela. É importante lembrar que durante a instalação é possível selecionar os componentes que deseja instalar, como a ferramenta gráfica **pgAdmin**. Além disso, também é possível escolher o local de instalação e a senha do usuário admin. Após a instalação, o PostgreSQL estará pronto para uso.

Para mais informações sobre a instalação do PostgreSQL no Windows, consulte a [documentação oficial](https://www.postgresql.org/docs/current/tutorial-install.html).

### DDL e DML

DDL significa *Data Definition Language*, que é uma linguagem utilizada para definir a estrutura e as características dos dados em um banco de dados. DDL é usado para criar, modificar e excluir objetos no banco de dados, como tabelas, índices, views e outros objetos.

[Documentação](https://www.postgresql.org/docs/current/ddl.html).

Já o DML significa *Data Manipulation Language*, que é uma linguagem usada para manipular os dados dentro de um banco de dados. DML é usado para inserir, atualizar, excluir e recuperar dados em um banco de dados. Isso significa que o DML é usado para fazer operações de leitura e escrita nos dados armazenados em um banco de dados.

[Documentação](https://www.postgresql.org/docs/current/dml.html).

### Databases

#### Criando um banco de dados com o comando createdb:

Para criar um banco de dados usando o createdb, basta executar o seguinte comando no terminal:
```
createdb <nome_do_banco_de_dados>
```

Substitua ``<nome_do_banco_de_dados>`` pelo nome desejado para o banco de dados. Por exemplo:

#### Criando um banco de dados utilizando linguagem SQL:

O comando CREATE DATABASE é usado para criar um banco de dados no PostgreSQL. Ele pode ser executado tanto no utilitário de linha de comando psql quanto em outras ferramentas que suportam a execução de comandos SQL.

```
CREATE DATABASE nome_do_banco_de_dados;
```

É possível especificar outras opções ao criar um banco de dados, como o proprietário do banco de dados, a codificação de caracteres e a localização do banco de dados. Algumas opções comuns incluem:

- **OWNER** para definir o proprietário do banco de dados.
- **ENCODING** para definir a codificação de caracteres do banco de dados.
- **LC_COLLATE** e **LC_CTYPE** para definir as configurações de localização do banco de dados.

Por exemplo, o seguinte comando cria um banco de dados chamado "minha_base_de_dados" com o proprietário "meu_usuario" e codificação de caracteres "UTF8":

```
CREATE DATABASE minha_base_de_dados
WITH    OWNER meu_usuario
        ENCODING 'UTF8'
        LC_COLLATE 'pt_BR.UTF-8'
        LC_CTYPE 'pt_BR.UTF-8';
```

#### Removendo um banco de dados com o comando dropdb

Para remover um banco de dados usando o dropdb, basta executar o seguinte comando no terminal:
```
dropdb <nome_do_banco_de_dados>
```
#### Removendo um banco de dados utilizando linguagem SQL

Para remover um banco de dados existente utilizando linguagem SQL, basta executar o comando:
```
DROP DATABASE nome_do_banco_de_dados;
```

Além disso, podemos adicionar o parâmetro **IF EXISTS**, ele funciona como um validador para quando o banco de dados mencionado não existir, o PostgreSQL somente ignorar ao invés de retornar um erro.
```
DROP DATABASE IF EXISTS meu_banco_bonito;
```
### Criação de tabelas

Para criar uma tabela no PostgreSQL, você precisa usar a linguagem DDL (*Data Definition Language*) e a sintaxe é a seguinte:

```
CREATE TABLE nome_da_tabela (
  nome_do_campo1 tipo_do_campo1,
  nome_do_campo2 tipo_do_campo2,
  ...,
  nome_do_campoN tipo_do_campoN
);
```
Por exemplo, para criar uma tabela chamada "clientes" com dois campos, "id" e "nome", o comando seria o seguinte:
````
CREATE TABLE clientes (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(50)
);

````
Este comando cria uma tabela "clientes" com um campo "id" que é um número serial (ou seja, um número sequencial gerado automaticamente pelo PostgreSQL) e um campo "nome" que é uma *string* de até 50 caracteres.

### Edição de Tabela

Para editar uma tabela existente no PostgreSQL, você pode usar o comando **ALTER TABLE**. Por exemplo, se você quiser adicionar um novo campo "email" à tabela "clientes", o comando seria o seguinte:
````
ALTER TABLE clientes ADD COLUMN email VARCHAR(50);
````
Este comando adiciona um novo campo chamado "email" à tabela "clientes" com um comprimento máximo de 50 caracteres.

#### Exclusão de tabelas
Para excluir uma tabela no PostgreSQL, você pode usar o comando **DROP TABLE**. Por exemplo, se você quiser excluir a tabela "clientes", o comando seria o seguinte:

```
DROP TABLE clientes;
```

Este comando exclui a tabela "clientes" e todos os dados armazenados nela.


## Aula 2

### Tipos de dados mais comuns
Nos exemplos acima, falamos dos tipos ``int`` e ``varchar``, porém, existem alguns outros tipos de dados que são possíveis de serem utilizados, que nos auxiliam para situações específicas.

- Tipos numéricos:

    ``INTEGER``: armazena números inteiros com sinal. O tamanho padrão é de 4 bytes, mas pode ser especificado um tamanho maior ou menor. É usado para armazenar dados numéricos que representam quantidades inteiras, como a quantidade de itens em um pedido.

    ``BIGINT``: armazena números inteiros com sinal de 8 bytes. É usado para armazenar dados numéricos que representam quantidades maiores que o INTEGER, como o número de habitantes de uma cidade ou país.

    ``NUMERIC``: armazena números decimais com precisão arbitrária. É usado para armazenar valores monetários ou outros dados numéricos que requerem alta precisão.

    ``DOUBLE PRECISION``: armazena números de ponto flutuante de dupla precisão. É usado para armazenar dados numéricos que requerem alta precisão e uma grande faixa de valores, como as coordenadas geográficas de um local.

- Tipos de texto

    ``VARCHAR``: armazena *strings* de comprimento variável. É usado para armazenar dados de texto de comprimento variável, como nomes de pessoas ou endereços de e-mail.

    ``CHAR``: armazena strings de comprimento fixo. É usado para armazenar dados de texto de comprimento fixo, como códigos postais ou números de identificação.

    ``TEXT``: armazena strings de comprimento variável sem limite. É usado para armazenar grandes volumes de dados de texto, como descrições de produtos ou comentários em um *site*.


- Tipos de data e hora

    ``DATE``: armazena datas (ano, mês, dia). É usado para armazenar informações de datas, como datas de nascimento ou datas de eventos.

    ``TIME``: armazena horas do dia. É usado para armazenar informações de hora, como horários de início ou fim de eventos.

    ``TIMESTAMP``: armazena datas e horas com precisão de milissegundos. É usado para armazenar informações de datas e horas precisas, como timestamps de criação ou modificação de registros.

- Tipos booleanos

    ``BOOLEAN``: armazena valores verdadeiro ou falso. É usado para armazenar dados booleanos, como se um usuário está conectado ou desconectado.

- Tipos de array

    ``ARRAY``: armazena uma lista de valores de um tipo de dado específico. É usado para armazenar coleções de dados, como uma lista de itens em um pedido ou as cores favoritas de um usuário.

- Tipos especiais

    ``JSON`` e ``JSONB``: armazena dados em formato JSON (*JavaScript Object Notation*), usado para armazenar dados semiestruturados que podem ser facilmente lidos por outras aplicações ou sistemas.

    ``UUID``: armazena identificadores únicos universais (UUIDs), que são frequentemente usados em sistemas distribuídos para identificar de forma única recursos em um cluster.

- ***Default values***

Em PostgreSQL, um valor padrão (ou "*default value*") é um valor que é automaticamente atribuído a uma coluna se nenhum valor é especificado para ela durante a inserção de dados.

Aqui está um exemplo de como definir um valor padrão em PostgreSQL:

````
CREATE TABLE clientes (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(100),
    email VARCHAR(100),
    data_de_cadastro TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
````

Neste exemplo, a coluna "data_de_cadastro" é definida com um valor padrão de "``CURRENT_TIMESTAMP``", que é uma função que retorna a data e hora atual do sistema. Isso significa que, se nenhum valor for especificado para essa coluna durante a inserção de dados, o PostgreSQL irá automaticamente inserir a data e hora atual.

Outro exemplo pode ser de uma tabela de pedidos, onde a coluna "*status*" pode ter um valor padrão "pendente" para todos os novos pedidos:

````
CREATE TABLE pedidos (
    id SERIAL PRIMARY KEY,
    descricao VARCHAR(100),
    valor DECIMAL(10,2),
    status VARCHAR(20) DEFAULT 'pendente'
);
````

Neste exemplo, a coluna "status" é definida com um valor padrão "pendente", que será automaticamente inserido se nenhum valor for especificado durante a inserção de dados.

Além disso, é importante observar que um valor padrão pode ser definido para qualquer tipo de coluna, incluindo texto, números, datas, booleanos etc. É uma ferramenta útil para garantir a consistência dos dados em uma tabela e simplificar a inserção de dados.

## Aula 3

## Aula 4

## Aula 5

## Aula 6

## Aula 7