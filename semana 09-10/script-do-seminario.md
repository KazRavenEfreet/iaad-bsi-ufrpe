# 💚 Seminário prático sobre MongoDB

![mongodb logo](https://webimages.mongodb.com/_com_assets/cms/kuyjf3vea2hg34taa-horizontal_default_slate_blue.svg?auto=format%252Ccompress)

## Introdução ao MongoDB
- O que é o mongo db?
É o banco de dados orientado a objetos mais popular, estando em 5º lugar dos bancos mais usados no mundo e em primeiro como banco de dados NoSQL.
Ele armazena os dados num formado semelhante ao JSON e é de esquema livre.

- Para que serve o mongodb?
Ele foi criado em 2007, por componentes da Double Click, uma empresa que veícula cerca de 400.000 anúncios por segundo, mas muitas vezes sofria com escalabilidade e agilidade.

- Onde é usado o mongodb?
Em cenários de Big Data.

- Como o mongodb armazena os dados?
![How-mongodb-works](https://miro.medium.com/max/1400/1*fQbtENxfv757UXuzGQQ3gQ.png)

- Vantagens e desvantagens

![aplicações](https://blog.couchbase.com/wp-content/uploads/2017/04/nosql-vs-sql-overview-1.png)

- Funcionalidades gerais
* Escalabilidade horizontal (sharding)
* Suporte de múltiplos engines de armazenamento
* Alta performance

## Processo de instalação

Há diversas formas de usar o MongoDB, entre elas destaco:

> * Em um container Docker
> * Executável
> * Usando na núvem
> * Sandbox

Para este seminário, optei por mostrar a configuração do ambiente usando o Docker.

### Usando MongoDB no Docker

O Docker é uma ferramenta para criar, implantar e rodar aplicações usando facilmente containers.
Um contêiner é uma unidade padrão de software que pode ser usada para
empacotar aplicativos e todas as dependências em um único pacote.
Esses contêineres podem ser executados em qualquer plataforma de servidor,
independentemente da configuração subjacente ou da estrutura de hardware.


> acesse o [Play With Docker](https://labs.play-with-docker.com/) e execute os passos abaixo.

Primeiro vamos baixar a imagem oficial do MongoDB por meio do seguinte comando:
```bash
$ docker pull mongo:latest
```

> Para saber se a imagem foi realmente instalada,
> basta executar ```$ docker image ls```, para listar todas as imagens instaladas.

Tendo instalado a imagem do MongoDB, basta instanciar um container MongoDB por meio do comando abaixo:

```bash
$ docker run -d  --name mongo-on-docker -p 27888:27017 -e MONGO_INITDB_ROOT_USERNAME=mongoadmin -e MONGO_INITDB_ROOT_PASSWORD=secret mongo
```

![docker-ports](https://www.code4it.dev/static/7e983e27425fb44d41cf3189d3835b92/84f4d/Docker-ports.png)


Agora, tendo uma instância do MongoDB, basta executar o comando abaixo para rodar o container:

```sh
docker exec -it mongo-on-docker mongosh --port 27017  --authenticationDatabase "admin" -u "mongoadmin" -p
```

Simples assim, com apenas três comandos você já consegue instalar, configurar e executar o MongoDB.

[Mongo Official Image | Docker Hub](https://hub.docker.com/_/mongo)

## Configurações Iniciais


### Exemplo prático das operações CRUD envolvendo o esquema empresa:


![Esquema empresa](https://raw.githubusercontent.com/jsvitor/iaad-bsi-ufrpe/main/semana%2003-04/empresa_diagram.png)

<details>
  <summary>Comandos</summary>

#### Para exibir os bancos de dados existentes:

```sh
show dbs;
```

#### Para alterar o database:

```sh
use nome-do-database-desejado
```

### Para criar uma Collection

```sh
db.createCollection('nome-da-collection')
```

### Para listar os bancos de dados:

```sh
show dbs;
```

###

```sh

```

</details>

#### [Operações CRUD](https://docs.mongodb.com/manual/crud/)

## Referências:

* https://medium.com/dockerbr/mongodb-no-docker-dd3b72c7efb7
* https://www.code4it.dev/blog/run-mongodb-on-docker
* https://www.youtube.com/watch?v=DbKPeaVHwdE
* https://hub.docker.com/_/mongo
* https://docs.mongodb.com/manual/crud/
