# Aplicação Mobile - Backend

<br />

## Índice

1. [Introdução](#introducao)
2. [Tecnologias Utilizadas](#tecnologias)
3. [Estrutura do Projeto](#estrutura-do-projeto)
4. [Configuração](#configuracao)
    - 4.1 [Banco de Dados](#banco-de-dados)
    - 4.2 [Docker Compose](#docker-compose)
5. [Endpoints da API](#endpoints-da-api)
   - 5.1. [Cidades](#cidades)
        - 5.1.1. [GET /simfonia/api/cidades/:id](#get-apicidadeid)
        - 5.1.2. [GET /simfonia/api/cidades/nome](#get-apicidadenome)
        - 5.1.3. [GET /simfonia/api/cidades/](#get-apiallcidades)
        - 5.1.4. [GET /simfonia/api/cidades/csv](#get-apiallcidadescsv)
        - 5.1.5. [POST /simfonia/api/cidades/](#post-apicreatecidade)
        - 5.1.6. [POST /simfonia/api/cidades/csv](#post-apicreatecidadecsv)
        - 5.1.7. [PUT /simfonia/api/cidades/:id](#put-apiupdatecidade)
        - 5.1.8. [DELETE /simfonia/api/cidades/:id](#delete-apideletecidadeid)
    - 5.2. [Números Telefônicos](#numeros-telefonicos)
        - 5.2.1. [GET /simfonia/api/numerostelefonicos/:id](#get-apinumerosid)
        - 5.2.2. [GET /simfonia/api/numerostelefonicos/numero](#get-apinumerosnumero)
        - 5.2.3. [GET /simfonia/api/numerostelefonicos/simcard/:id](#get-apinumerossimcardid)
        - 5.2.4. [GET /simfonia/api/numerostelefonicos/simcard](#get-apinumerossimcard)
        - 5.2.5. [GET /simfonia/api/numerostelefonicos/](#get-apiallnumeros)
        - 5.2.6. [GET /simfonia/api/numerostelefonicos/csv](#get-apiallnumeroscsv)
        - 5.2.7. [POST /simfonia/api/numerostelefonicos/](#post-apicreatenumero)
        - 5.2.8. [POST /simfonia/api/numerostelefonicos/csv](#post-apicreatenumerocsv)
        - 5.2.9. [PUT /simfonia/api/numerostelefonicos/:id](#put-apiupdatenumero)
        - 5.2.10. [DELETE /simfonia/api/numerostelefonicos/:id](#delete-apideletenumeroid)
    - 5.3. [Operadoras](#operadoras)
        - 5.3.1. [GET /simfonia/api/operadoras/:id](#get-apioperadorasid)
        - 5.3.2. [GET /simfonia/api/operadoras/nome](#get-apioperadorasnome)
        - 5.3.3. [GET /simfonia/api/operadoras/abreviacao](#get-apioperadorasabreviacao)
        - 5.3.4. [GET /simfonia/api/operadoras/](#get-apialloperadoras)
        - 5.3.5. [GET /simfonia/api/operadoras/csv](#get-apialloperadorascsv)
        - 5.3.6. [POST /simfonia/api/operadoras/](#post-apicreateoperadoras)
        - 5.3.7. [POST /simfonia/api/operadoras/csv](#post-apicreateoperadorascsv)
        - 5.3.8. [PUT /simfonia/api/operadoras/:id](#put-apiupdateoperadoras)
        - 5.3.9 [DELETE /simfonia/api/operadoras/:id](#delete-apideleteoperadorasid)
    - 5.4. [SimCard](#simCard)
        - 5.4.1. [GET /simfonia/api/simcard/:id](#get-apisimcardid)
        - 5.4.2. [GET /simfonia/api/simcard/telefonianumero/:id](#get-apisimcardnumeroid)
        - 5.4.3. [GET /simfonia/api/simcard/telefonianumero](#get-apisimcardnumero)
        - 5.4.4. [GET /simfonia/api/simcard/](#get-apiallsimcard)
        - 5.4.5. [GET /simfonia/api/simcard/csv](#get-apiallsimcardcsv)
        - 5.4.6. [POST /simfonia/api/simcard/](#post-apicreatesimcard)
        - 5.4.7. [POST /simfonia/api/simcard/csv](#post-apicreatesimcardcsv)
        - 5.4.8. [PUT /simfonia/api/simcard/:id](#put-apiupdatesimcard)
        - 5.4.9. [DELETE /simfonia/api/simcard/:id](#delete-apideletesimcardid)   
    - 5.5. [Estados SimCard](#simCard-estados)
        - 5.5.1. [GET /simfonia/api/simcardestado/:id](#get-apisimcardestadoid)
        - 5.5.2. [GET /simfonia/api/simcardestado/estado](#get-apisimcardestadoestado)
        - 5.5.3. [GET /simfonia/api/simcardestado/](#get-apiallsimcardestado)
        - 5.5.4. [GET /simfonia/api/simcardestado/csv](#get-apiallsimcardestadocsv)
        - 5.5.5. [POST /simfonia/api/simcardestado/](#post-apicreatesimcardestado)
        - 5.5.6. [POST /simfonia/api/simcardestado/csv](#post-apicreatesimcardestadocsv)
        - 5.5.7. [PUT /simfonia/api/simcardestado/:id](#put-apiupdatesimcardestado)
        - 5.5.8. [DELETE /simfonia/api/simcardestado/:id](#delete-apideletesimcardestadoid)   
6. [Modelos de Dados](#modelos-de-dados)
    - 6.1. [Cidades](#modelo-cidade)
    - 6.2. [Números Telefônicos](#modelo-numerotelefonico)
    - 6.3. [Operadoras](#modelo-operadoras)
    - 6.4. [SimCards](#modelo-simcards)
    - 6.5. [Estados SimCards](#modelo-simcardestado)
7. [Serviços](#servicos)
    - 7.1. [CidadeService](#cidadeService)
    - 7.2. [NumeroTelefonicoService](#numerosTelefonicosService)
    - 7.3. [OperadoraService](#operadorasService)
    - 7.4. [SimCardService](#simCardService)
    - 7.5. [SimCardEstadoService](#simCardEstadoService)
8. [Controladores](#controladores)
9. [Instruções para Execução](#instrucoes-para-execucao)

<br />

<span id="introducao">
    
## 1. Introdução

Esta documentação descreve uma API CRUD desenvolvida em Golang usando o framework Gin. A API permite criar, ler, atualizar e excluir usuários em um banco de dados PostgreSQL.

<br />

<span id="tecnologias">
    
## 2. Tecnologias Utilizadas

<img src="https://img.shields.io/badge/Golang-CED4DA?style=for-the-badge&logo=go&logoColor=79d4fd" alt="Figma" /> 

<br />
<br />

<span id="estrutura-do-projeto">

## 3. Estrutura do Projeto

```plaintext
app/
├── controller/
│   └── cidadeController.go
│   └── numerosTelefonicosController.go
│   └── operadorasController.go
│   └── simCardController.go
│   └── simCardEstadoController.go
├── db/
│   └── db.go
├── model/
│   └── cidades.go
│   └── numerosTelefonicos.go
│   └── operadoras.go
│   └── simCard.go
│   └── simCardEstado.go
│   └── parametrosDeBusca/
│       └── cidades/
│           └── nome.go
│       └── numerosTelefonicos/
│           └── numero.go
│       └── operadoras/
│           └── abreviacao.go
│           └── nome.go
│       └── simCardEstado/
│           └── nome.go
├── service/
│   └── cidadesService.go
│   └── numerosTelefonicosService.go
│   └── operadorasService.go
│   └── simCardService.go
│   └── simCardEstadoService.go
├── main.go
├── go.sum
└── go.mod

```

<br />

<span id="configuracao">

# 4. Configuração

<span id="banco-de-dados">

## 4.1 Banco de Dados

A configuração do banco de dados está definida no arquivo `db/connection.go`. Um banco de dados PostgreSQL é utilizado, com as seguintes credenciais:

- **Usuário**: postgres
- **Senha**: example
- **Host**: localhost
- **Porta**: 5432
- **Nome do Banco de Dados**: postgres (será criado um banco de dados chamado `usuario`)

<span id="docker-compose">

## 4.2 Docker Compose

Para rodar o banco de dados PostgreSQL e o Adminer, você pode usar o seguinte arquivo `docker-compose.yml`:

```yaml
version: '3.1'

services:
  db:
    image: postgres
    restart: always
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: example
      POSTGRES_DB: postgres
    ports:
      - "5432:5432"

  adminer:
    image: adminer
    restart: always
    ports:
      - "8080:8080"
```

<br />

<span id="endpoints-da-api">

# 5. Endpoints da API

<span id="cidades">

## 5.1 Cidades 

<span id="get-apicidadeid">

### 5.1.1. GET /simfonia/api/cidades/:id

#### Descrição

Recupera uma cidade pelo ID.

#### Exemplo de Requisição

```http
GET /simfonia/api/cidades/2
```

#### Exemplo de Resposta

```json
{
    "ID": 2,
    "UUID": "123456789-1234-1234-1234-1234567890ab",
    "Nome": "São Paulo",
    "CodIBGE": 1234567,
    "UF": "RJ",
    "CodArea": 12
}
```

<span id="get-apicidadenome">

### 5.1.2. GET /simfonia/api/cidades/nome

#### Descrição

Recupera uma cidade pelo nome.

#### Exemplo de Requisição

```json
{
    "Nome": "São Paulo"
}
```

#### Exemplo de Resposta

```json
{
    "ID": 2,
    "UUID": "123456789-1234-1234-1234-1234567890ab",
    "Nome": "São Paulo",
    "CodIBGE": 1234567,
    "UF": "RJ",
    "CodArea": 12
}
```

<span id="get-apiallcidades">

### 5.1.3. GET /simfonia/api/cidades/

#### Descrição

Recupera todas as cidades do banco.

#### Exemplo de Requisição

```http
GET simfonia/api/cidades/
```

#### Exemplo de Resposta

```json
[
    {
        "ID": 2,
        "UUID": "123456789-1234-1234-1234-1234567890ab",
        "Nome": "São Paulo",
        "CodIBGE": 1234567,
        "UF": "RJ",
        "CodArea": 12
    },
    {
        "ID": 3,
        "UUID": "123456789-1234-1234-1234-1234567890ab",
        "Nome": "Rio de Janeiro",
        "CodIBGE": 1234567,
        "UF": "SP",
        "CodArea": 12
    }
]
```

<span id="get-apiallcidadescsv">

### 5.1.4. GET /simfonia/api/cidades/csv

#### Descrição

Recupera todas as cidades do banco e exporta em um arquivo `.csv`.

#### Exemplo de Requisição

```http
GET /simfonia/api/cidades/csv
```

#### Exemplo de Resposta

```csv
    ID,UUID,Nome,CodIBGE,UF,CodArea
    2,832696e8-ab2a-40ed-9733-f3e7c86f14a5,Assis Brasil,1200054,AC,68
    3,df26cb7d-46f5-473c-bf59-d967092b8b41,Brasiléia,1200104,AC,68
    4,097c3b36-4757-48ea-aa81-73a448f3dba6,Bujari,1200138,AC,68
    5,4edfc55f-64e0-49de-9d72-3621041cf43a,Capixaba,1200179,AC,68
    6,bce68ddd-1a31-4f38-a3a5-6ea27ac2de5f,Cruzeiro do Sul,1200203,AC,68
    7,1fee47bc-9d10-4092-8b2b-a19590516b9a,Epitaciolândia,1200252,AC,68
    8,f87785f2-06f2-42ad-b85b-271e546a39af,Feijó,1200302,AC,68
    9,f4a6a716-e30c-4fa9-abc1-cac07bc3f53d,Jordão,1200328,AC,68
    10,35abfd59-ce53-4986-a981-efd1f63d8657,Mâncio Lima,1200336,AC,68
```

<span id="post-apicreatecidade">

### 5.1.5. POST /simfonia/api/cidades/

#### Descrição

Cria uma nova cidade.

#### Exemplo de Requisição

```json

{
    "UUID": "123456789-1234-1234-1234-1234567890ab",
    "Nome": "Rio de Janeiro",
    "CodIBGE": 1234567,
    "UF": "SP",
    "CodArea": 12
}
```

#### Exemplo de Resposta

```json
{
    "ID": 1,
    "UUID": "123456789-1234-1234-1234-1234567890ab",
    "Nome": "Rio de Janeiro",
    "CodIBGE": 1234567,
    "UF": "SP",
    "CodArea": 12
}
```

<span id="post-apicreatecidadecsv">

### 5.1.6. POST /simfonia/api/cidades/csv

#### Descrição

Cria novas cidades em lote, baseados em um arquivo `.csv`.

#### Exemplo de Requisição

```csv
    UUID,Nome,CodIBGE,UF,CodArea
    832696e8-ab2a-40ed-9733-f3e7c86f14a5,Assis Brasil,1200054,AC,68
    df26cb7d-46f5-473c-bf59-d967092b8b41,Brasiléia,1200104,AC,68
    097c3b36-4757-48ea-aa81-73a448f3dba6,Bujari,1200138,AC,68
    4edfc55f-64e0-49de-9d72-3621041cf43a,Capixaba,1200179,AC,68
    bce68ddd-1a31-4f38-a3a5-6ea27ac2de5f,Cruzeiro do Sul,1200203,AC,68
    1fee47bc-9d10-4092-8b2b-a19590516b9a,Epitaciolândia,1200252,AC,68
    f87785f2-06f2-42ad-b85b-271e546a39af,Feijó,1200302,AC,68
    f4a6a716-e30c-4fa9-abc1-cac07bc3f53d,Jordão,1200328,AC,68
    ,35abfd59-ce53-4986-a981-efd1f63d8657,Mâncio Lima,1200336,AC,68
```

```multipart-form
    csv: *arquivo*
```

#### Exemplo de Resposta

```json
{
    "mensagem": "Arquivo carregado e processado com sucesso!"
}
```

<span id="put-apiupdatecidade">

### 5.1.7. PUT /simfonia/api/cidades/:id

#### Descrição

Atualiza uma cidade existente pelo ID.

#### Exemplo de Requisição

```http
    PUT simfonia/api/cidades/1
```

```json
{
    "UUID": "123456789-1234-1234-1234-1234567890ab",
    "Nome": "Rio de Janeiro",
    "CodIBGE": 1234567,
    "UF": "SP",
    "CodArea": 12
}
```

#### Exemplo de Resposta

```json
{
    "ID": 1,
    "UUID": "123456789-1234-1234-1234-1234567890ab",
    "Nome": "Rio de Janeiro",
    "CodIBGE": 1234567,
    "UF": "SP",
    "CodArea": 12
}
```

<span id="delete-apideletecidadeid">

### 5.1.8. DELETE /simfonia/api/cidades/:id

#### Descrição

Exclui uma cidade pelo ID.

#### Exemplo de Requisição

```http
DELETE /simfonia/api/cidades/1
```

#### Exemplo de Resposta

```json
{
    "deletado": true
}
```

<span id="numeros-telefonicos">

## 5.2. Números Telefônicos

<span id="get-apinumerosid">

### 5.2.1. GET /simfonia/api/numerostelefonicos/:id

#### Descrição

Recupera um número telefônico pelo ID.

#### Exemplo de Requisição

```http
GET /simfonia/api/numerostelefonicos/2
```

#### Exemplo de Resposta

```json
{
    "ID": 7,
    "CodArea": 11,
    "Numero": 123456789,
    "Utilizavel": true,
    "PortadoIn": false,
    "PortadoInOperadora": "",
    "PortadoInDate": "2024-07-24T17:21:48.89283-03:00",
    "CodigoCnl": "ABC123",
    "CongeladoAte": null,
    "ExternalID": 1234567890,
    "PortadoOut": false,
    "PortadoOutOperadora": "",
    "PortadoOutDate": "2024-07-24T17:21:48.89283-03:00",
    "DataCriacao": "2024-06-24T10:00:00-03:00",
    "SimCardID": null,
    "SimCard": null,
    "PortadoInOperadoraID": null,
    "PortadoInOperadoraObj": null,
    "PortadoOutOperadoraID": null,
    "PortadoOutOperadoraObj": null
}
```

<span id="get-apinumerosnumero">

### 5.2.2. GET /simfonia/api/numerostelefonicos/numero

#### Descrição

Recupera um número telefônico pelo número.

#### Exemplo de Requisição

```json
{
    "numero": 123456789
}
```

#### Exemplo de Resposta

```json
{
    "ID": 7,
    "CodArea": 11,
    "Numero": 123456789,
    "Utilizavel": true,
    "PortadoIn": false,
    "PortadoInOperadora": "",
    "PortadoInDate": "2024-07-24T17:21:48.89283-03:00",
    "CodigoCnl": "ABC123",
    "CongeladoAte": null,
    "ExternalID": 1234567890,
    "PortadoOut": false,
    "PortadoOutOperadora": "",
    "PortadoOutDate": "2024-07-24T17:21:48.89283-03:00",
    "DataCriacao": "2024-06-24T10:00:00-03:00",
    "SimCardID": null,
    "SimCard": null,
    "PortadoInOperadoraID": null,
    "PortadoInOperadoraObj": null,
    "PortadoOutOperadoraID": null,
    "PortadoOutOperadoraObj": null
}
```

<span id="get-apinumerossimcardid">

### 5.2.3. GET /simfonia/api/numerostelefonicos/simcard/:id

#### Descrição

Recupera um número de telefone pelo id do SimCard correspondente.

#### Exemplo de Requisição

```http
GET /simfonia/api/numerostelefonicos/simcard/235
```

#### Exemplo de Resposta

```json
{
    "ID": 17,
    "CodArea": 12,
    "Numero": 981832641,
    "Utilizavel": true,
    "PortadoIn": false,
    "PortadoInOperadora": "",
    "PortadoInDate": "2024-06-26T16:41:52.571-03:00",
    "CodigoCnl": "0123456789",
    "CongeladoAte": null,
    "ExternalID": 987654321,
    "PortadoOut": false,
    "PortadoOutOperadora": "",
    "PortadoOutDate": "2024-06-26T16:41:52.571-03:00",
    "DataCriacao": "2024-06-26T16:41:52.571-03:00",
    "SimCardID": 235,
    "SimCard": null,
    "PortadoInOperadoraID": null,
    "PortadoInOperadoraObj": null,
    "PortadoOutOperadoraID": null,
    "PortadoOutOperadoraObj": null
}
```

<span id="get-apinumerossimcard">

### 5.2.4. GET /simfonia/api/numerostelefonicos/simcard

##### Descrição

Recupera um número de telefone pelo objeto do SimCard correspondente.

##### Exemplo de Requisição

```http
    TODO
```

##### Exemplo de Resposta

```json
{
    "ID": 17,
    "CodArea": 12,
    "Numero": 981832641,
    "Utilizavel": true,
    "PortadoIn": false,
    "PortadoInOperadora": "",
    "PortadoInDate": "2024-06-26T16:41:52.571-03:00",
    "CodigoCnl": "0123456789",
    "CongeladoAte": null,
    "ExternalID": 987654321,
    "PortadoOut": false,
    "PortadoOutOperadora": "",
    "PortadoOutDate": "2024-06-26T16:41:52.571-03:00",
    "DataCriacao": "2024-06-26T16:41:52.571-03:00",
    "SimCardID": 235,
    "SimCard": null,
    "PortadoInOperadoraID": null,
    "PortadoInOperadoraObj": null,
    "PortadoOutOperadoraID": null,
    "PortadoOutOperadoraObj": null
}
```

<span id="get-apiallnumeros">

### 5.2.5. GET /simfonia/api/numerostelefonicos/

#### Descrição

Recupera todos os números telefônicos do banco.

#### Exemplo de Requisição

```http
GET simfonia/api/numerostelefonicos/
```

#### Exemplo de Resposta

```json
[
    {
        "ID": 7,
        "CodArea": 11,
        "Numero": 123456789,
        "Utilizavel": true,
        "PortadoIn": false,
        "PortadoInOperadora": "",
        "PortadoInDate": "2024-07-24T17:21:48.89283-03:00",
        "CodigoCnl": "ABC123",
        "CongeladoAte": null,
        "ExternalID": 1234567890,
        "PortadoOut": false,
        "PortadoOutOperadora": "",
        "PortadoOutDate": "2024-07-24T17:21:48.89283-03:00",
        "DataCriacao": "2024-06-24T10:00:00-03:00",
        "SimCardID": null,
        "SimCard": null,
        "PortadoInOperadoraID": null,
        "PortadoInOperadoraObj": null,
        "PortadoOutOperadoraID": null,
        "PortadoOutOperadoraObj": null
    },
    {
        "ID": 8,
        "CodArea": 22,
        "Numero": 234567890,
        "Utilizavel": true,
        "PortadoIn": false,
        "PortadoInOperadora": "",
        "PortadoInDate": "2024-07-24T17:21:48.89283-03:00",
        "CodigoCnl": "DEF456",
        "CongeladoAte": null,
        "ExternalID": 2345678901,
        "PortadoOut": false,
        "PortadoOutOperadora": "",
        "PortadoOutDate": "2024-07-24T17:21:48.89283-03:00",
        "DataCriacao": "2024-06-24T11:00:00-03:00",
        "SimCardID": null,
        "SimCard": null,
        "PortadoInOperadoraID": null,
        "PortadoInOperadoraObj": null,
        "PortadoOutOperadoraID": null,
        "PortadoOutOperadoraObj": null
    }
]
```

<span id="get-apiallnumeroscsv">

### 5.2.6. GET /simfonia/api/numerostelefonicos/csv

#### Descrição

Recupera todos os números telefônicos do banco e exporta em um arquivo `.csv`.

#### Exemplo de Requisição

```http
GET /simfonia/api/numerostelefonicos/csv
```

#### Exemplo de Resposta

```csv
    ID,CodArea,Numero,Utilizavel,PortadoIn,PortadoInOperadora,PortadoInDate,CodigoCnl,CongeladoAte,ExternalID,PortadoOut,PortadoOutOperadora,PortadoOutDate,DataCriacao,SimCardID,PortadoInOperadoraID,PortadoOutOperadoraID
7,11,123456789,true,false,1234567890,2024-07-24 17:21:48.89283 -0300 -03,ABC123,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 10:00:00 -0300 -03,null,null,null
8,22,234567890,true,false,2345678901,2024-07-24 17:21:48.89283 -0300 -03,DEF456,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 11:00:00 -0300 -03,null,null,null
9,33,345678901,true,false,3456789012,2024-07-24 17:21:48.89283 -0300 -03,GHI789,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 12:00:00 -0300 -03,null,null,null
10,44,456789012,true,false,4567890123,2024-07-24 17:21:48.89283 -0300 -03,JKL012,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 13:00:00 -0300 -03,null,null,null
11,55,567890123,true,false,5678901234,2024-07-24 17:21:48.89283 -0300 -03,MNO345,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 14:00:00 -0300 -03,null,null,null
12,66,678901234,true,false,6789012345,2024-07-24 17:21:48.89283 -0300 -03,PQR678,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 15:00:00 -0300 -03,null,null,null
13,77,789012345,true,false,7890123456,2024-07-24 17:21:48.89283 -0300 -03,STU901,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 16:00:00 -0300 -03,null,null,null
14,88,890123456,true,false,8901234567,2024-07-24 17:21:48.89283 -0300 -03,VWX234,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 17:00:00 -0300 -03,null,null,null
15,99,901234567,true,false,9012345678,2024-07-24 17:21:48.89283 -0300 -03,YZA567,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 18:00:00 -0300 -03,null,null,null
17,12,981832641,true,false,987654321,2024-06-26 16:41:52.571 -0300 -03,0123456789,null,,false,,2024-06-26 16:41:52.571 -0300 -03,2024-06-26 16:41:52.571 -0300 -03,null,null,null

```

<span id="post-apicreatenumero">

### 5.2.7. POST /simfonia/api/numerostelefonicos/

#### Descrição

Cria um novo número telefônico.

#### Exemplo de Requisição

```json
{
    "CodArea": 22,
    "Numero": 234567890,
    "Utilizavel": true,
    "PortadoIn": false,
    "PortadoInOperadora": "",
    "PortadoInDate": "2024-07-24T17:21:48.89283-03:00",
    "CodigoCnl": "DEF456",
    "CongeladoAte": null,
    "ExternalID": 2345678901,
    "PortadoOut": false,
    "PortadoOutOperadora": "",
    "PortadoOutDate": "2024-07-24T17:21:48.89283-03:00",
    "DataCriacao": "2024-06-24T11:00:00-03:00",
    "SimCardID": null,
    "SimCard": null,
    "PortadoInOperadoraID": null,
    "PortadoInOperadoraObj": null,
    "PortadoOutOperadoraID": null,
    "PortadoOutOperadoraObj": null
}
```

#### Exemplo de Resposta

```json
{
    "ID": 8,
    "CodArea": 22,
    "Numero": 234567890,
    "Utilizavel": true,
    "PortadoIn": false,
    "PortadoInOperadora": "",
    "PortadoInDate": "2024-07-24T17:21:48.89283-03:00",
    "CodigoCnl": "DEF456",
    "CongeladoAte": null,
    "ExternalID": 2345678901,
    "PortadoOut": false,
    "PortadoOutOperadora": "",
    "PortadoOutDate": "2024-07-24T17:21:48.89283-03:00",
    "DataCriacao": "2024-06-24T11:00:00-03:00",
    "SimCardID": null,
    "SimCard": null,
    "PortadoInOperadoraID": null,
    "PortadoInOperadoraObj": null,
    "PortadoOutOperadoraID": null,
    "PortadoOutOperadoraObj": null
}
```

<span id="post-apicreatenumerocsv">

### 5.2.8. POST /simfonia/api/numerostelefonicos/csv

#### Descrição

Cria novos números telefônicos em lote, baseados em um arquivo `.csv`.

#### Exemplo de Requisição

```csv
    CodArea,Numero,Utilizavel,PortadoIn,PortadoInOperadora,PortadoInDate,CodigoCnl,CongeladoAte,ExternalID,PortadoOut,PortadoOutOperadora,PortadoOutDate,DataCriacao,SimCardID,PortadoInOperadoraID,PortadoOutOperadoraID
11,123456789,true,false,1234567890,2024-07-24 17:21:48.89283 -0300 -03,ABC123,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 10:00:00 -0300 -03,null,null,null
22,234567890,true,false,2345678901,2024-07-24 17:21:48.89283 -0300 -03,DEF456,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 11:00:00 -0300 -03,null,null,null
33,345678901,true,false,3456789012,2024-07-24 17:21:48.89283 -0300 -03,GHI789,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 12:00:00 -0300 -03,null,null,null
44,456789012,true,false,4567890123,2024-07-24 17:21:48.89283 -0300 -03,JKL012,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 13:00:00 -0300 -03,null,null,null
55,567890123,true,false,5678901234,2024-07-24 17:21:48.89283 -0300 -03,MNO345,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 14:00:00 -0300 -03,null,null,null
66,678901234,true,false,6789012345,2024-07-24 17:21:48.89283 -0300 -03,PQR678,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 15:00:00 -0300 -03,null,null,null
77,789012345,true,false,7890123456,2024-07-24 17:21:48.89283 -0300 -03,STU901,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 16:00:00 -0300 -03,null,null,null
88,890123456,true,false,8901234567,2024-07-24 17:21:48.89283 -0300 -03,VWX234,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 17:00:00 -0300 -03,null,null,null
99,901234567,true,false,9012345678,2024-07-24 17:21:48.89283 -0300 -03,YZA567,null,,false,,2024-07-24 17:21:48.89283 -0300 -03,2024-06-24 18:00:00 -0300 -03,null,null,null
12,981832641,true,false,987654321,2024-06-26 16:41:52.571 -0300 -03,0123456789,null,,false,,2024-06-26 16:41:52.571 -0300 -03,2024-06-26 16:41:52.571 -0300 -03,null,null,null
```

```multipart-form
    csv: *arquivo*
```

#### Exemplo de Resposta

```json
{
    "mensagem": "Arquivo carregado e processado com sucesso!"
}
```

<span id="put-apiupdatenumero">

### 5.2.9. PUT /simfonia/api/numerostelefonicos/:id

#### Descrição

Atualiza um número telefônico existente pelo ID.

#### Exemplo de Requisição

```http
    PUT /simfonia/api/numerostelefonicos/:id
```

```json
{
    "CodArea": 22,
    "Numero": 234567890,
    "Utilizavel": true,
    "PortadoIn": false,
    "PortadoInOperadora": "",
    "PortadoInDate": "2024-07-24T17:21:48.89283-03:00",
    "CodigoCnl": "DEF456",
    "CongeladoAte": null,
    "ExternalID": 2345678901,
    "PortadoOut": false,
    "PortadoOutOperadora": "",
    "PortadoOutDate": "2024-07-24T17:21:48.89283-03:00",
    "DataCriacao": "2024-06-24T11:00:00-03:00",
    "SimCardID": null,
    "SimCard": null,
    "PortadoInOperadoraID": null,
    "PortadoInOperadoraObj": null,
    "PortadoOutOperadoraID": null,
    "PortadoOutOperadoraObj": null
}
```

#### Exemplo de Resposta

```json
{
    "ID": 8,
    "CodArea": 22,
    "Numero": 234567890,
    "Utilizavel": true,
    "PortadoIn": false,
    "PortadoInOperadora": "",
    "PortadoInDate": "2024-07-24T17:21:48.89283-03:00",
    "CodigoCnl": "DEF456",
    "CongeladoAte": null,
    "ExternalID": 2345678901,
    "PortadoOut": false,
    "PortadoOutOperadora": "",
    "PortadoOutDate": "2024-07-24T17:21:48.89283-03:00",
    "DataCriacao": "2024-06-24T11:00:00-03:00",
    "SimCardID": null,
    "SimCard": null,
    "PortadoInOperadoraID": null,
    "PortadoInOperadoraObj": null,
    "PortadoOutOperadoraID": null,
    "PortadoOutOperadoraObj": null
}
```

<span id="delete-apideletenumeroid">

### 5.2.10. DELETE /simfonia/api/numerostelefonicos/:id</h3>

#### Descrição

Exclui um número telefônico pelo ID.

#### Exemplo de Requisição

```http
DELETE /simfonia/api/numerostelefonicos/8
```

#### Exemplo de Resposta

```json
{
    "deletado": true
}
```

<span id="operadoras">

## 5.3 Operadoras

<span id="get-apioperadorasid">

### 5.3.1. GET /simfonia/api/operadoras/:id</h3>

#### Descrição

Recupera uma operadora pelo ID.

#### Exemplo de Requisição

```http
GET /simfonia/api/operadora/3
```

#### Exemplo de Resposta

```json
{
    "ID": 3,
    "Nome": "Vivo Telecomunicações SP",
    "Abreviacao": "Vivo",
    "NumeroTelefonicosIn": null,
    "NumeroTelefonicosOut": null
}
```

<span id="get-apioperadorasnome">

### 5.3.2. GET /simfonia/api/operadoras/nome

#### Descrição

Recupera uma operadora pelo nome completo.

#### Exemplo de Requisição

```json
{
    "nome": "Vivo Telecomunicações SP"
}
```

#### Exemplo de Resposta

```json
{
    "ID": 3,
    "Nome": "Vivo Telecomunicações SP",
    "Abreviacao": "Vivo",
    "NumeroTelefonicosIn": null,
    "NumeroTelefonicosOut": null
}
```

<span id="get-apioperadorasabreviacao">

### 5.3.3. GET /simfonia/api/operadoras/abreviacao

#### Descrição

Recupera uma operadora pelo nome abreviado.

#### Exemplo de Requisição

```json
{
    "abreviacao": "Vivo"
}
```

#### Exemplo de Resposta

```json
{
    "ID": 3,
    "Nome": "Vivo Telecomunicações SP",
    "Abreviacao": "Vivo",
    "NumeroTelefonicosIn": null,
    "NumeroTelefonicosOut": null
}
```

<span id="get-apialloperadoras">

### 5.3.4. GET /simfonia/api/operadoras/

#### Descrição

Recupera todas as operadoras existentes no banco de dados.

#### Exemplo de Requisição

```http
    /simfonia/api/operadoras/
```

#### Exemplo de Resposta

```json
[
    {
        "ID": 4,
        "Nome": "Tim Telecomunicações",
        "Abreviacao": "Tim",
        "NumeroTelefonicosIn": null,
        "NumeroTelefonicosOut": null
    },
    {
        "ID": 3,
        "Nome": "Vivo Telecomunicações SP",
        "Abreviacao": "Vivo",
        "NumeroTelefonicosIn": null,
        "NumeroTelefonicosOut": null
    }
]
```

<span id="get-apialloperadorascsv">

### 5.3.5. GET /simfonia/api/operadoras/csv</h3>

#### Descrição

Recupera todas as operadoras do banco e exporta em um arquivo `.csv`.

#### Exemplo de Requisição

```http
GET /simfonia/api/operadoras/csv
```

#### Exemplo de Resposta

```csv
    ID,UUID,Nome,CodIBGE,UF,CodArea
    4,Tim Telecomunicações,Tim
    3,Vivo Telecomunicações SP,Vivo

```

<span id="post-apicreateoperadoras">

### 5.3.6. POST /simfonia/api/operadoras/

#### Descrição

Cria uma nova operadora.

#### Exemplo de Requisição

```json
{
    "Nome": "Tim Telecomunicações",
    "Abreviacao": "Tim",
}
```

#### Exemplo de Resposta

```json
{
    "ID": 4,
    "Nome": "Tim Telecomunicações",
    "Abreviacao": "Tim",
    "NumeroTelefonicosIn": null,
    "NumeroTelefonicosOut": null
}
```

<span id="post-apicreateoperadorascsv">

### 5.3.7. POST /simfonia/api/operadoras/csv

#### Descrição

Cria novas operadoras em lote, baseadas em um arquivo `.csv`.

#### Exemplo de Requisição

```csv
    UUID,Nome,CodIBGE,UF,CodArea
    Tim Telecomunicações,Tim
    Vivo Telecomunicações SP,Vivo
```

```multipart-form
    csv: *arquivo*
```

#### Exemplo de Resposta

```json
{
    "mensagem": "Arquivo carregado e processado com sucesso!"
}
```
<span id="put-apiupdateoperadoras">

### 5.3.8. PUT /simfonia/api/operadoras/:id

#### Descrição

Atualiza uma operadora existente pelo ID.

#### Exemplo de Requisição

```http
    PUT /simfonia/api/operadoras/4
```

```json
{
    "Nome": "Claro Telecomunicações",
    "Abreviacao": "Claro",
}
```

#### Exemplo de Resposta

```json
{
    "ID": 5,
    "Nome": "Claro Telecomunicações",
    "Abreviacao": "Claro",
    "NumeroTelefonicosIn": null,
    "NumeroTelefonicosOut": null
}
```

<span id="delete-apideleteoperadorasid">

### 5.3.9. DELETE /simfonia/api/operadoras/:id</h3>

#### Descrição

Exclui uma operadora pelo ID.

#### Exemplo de Requisição

```http
DELETE /simfonia/api/operadoras/4
```

#### Exemplo de Resposta

```json
{
    "deletado": true
}
```

<span id="simCard">

## 5.4. SimCard

<span id="get-apisimcardid">

### 5.4.1. GET /simfonia/api/simcard/:id

#### Descrição

Recupera um SimCard pelo ID.

#### Exemplo de Requisição

```http
GET /simfonia/api/simCard/226
```

#### Exemplo de Resposta

```json
{
    "id" : 226,
    "iccid" : "12345678901234567890",
    "imsi" : "111111111111111",
    "pin" : "1234",
    "puk" : "56789012",
    "ki" : "abcdef1234567890",
    "opc" : "fedcba0987654321",
    "estado_id" : 5,
    "telefonia_numero_id" : null,
    "data_criacao" : "2024-06-24T18:37:30.008Z",
    "data_estado" : "2024-06-24T18:37:30.008Z",
    "atualizado_em" : "2024-06-24T10:00:00.000Z",
    "puk2" : "5678901234",
    "pin2" : "4321"
}
```

<span id="get-apisimcardnumeroid">

### 5.4.2 GET /simfonia/api/simcard/telefonianumero/:id

#### Descrição

Recupera um SimCard pelo id do número de telefone correspondente.

#### Exemplo de Requisição

```http
    GET /simfonia/api/simcard/telefonianumero/7
```

#### Exemplo de Resposta

```json
{
    "id" : 226,
    "iccid" : "12345678901234567890",
    "imsi" : "111111111111111",
    "pin" : "1234",
    "puk" : "56789012",
    "ki" : "abcdef1234567890",
    "opc" : "fedcba0987654321",
    "estado_id" : 5,
    "telefonia_numero_id" : 7,
    "data_criacao" : "2024-06-24T18:37:30.008Z",
    "data_estado" : "2024-06-24T18:37:30.008Z",
    "atualizado_em" : "2024-06-24T10:00:00.000Z",
    "puk2" : "5678901234",
    "pin2" : "4321"
}
```

<span id="get-apisimcardnumero">

### 5.4.3. GET /simfonia/api/simcard/telefonianumero

#### Descrição

Recupera um SimCard pelo objeto do número de telefone correspondente.

<!-- Acredito que seja legal colocar como se fosse o ID, mas com o número do número, não o objeto inteiro -->

#### Exemplo de Requisição

```json
{
    "ID": 8,
    "CodArea": 22,
    "Numero": 234567890,
    "Utilizavel": true,
    "PortadoIn": false,
    "PortadoInOperadora": "",
    "PortadoInDate": "2024-07-24T17:21:48.89283-03:00",
    "CodigoCnl": "DEF456",
    "CongeladoAte": null,
    "ExternalID": 2345678901,
    "PortadoOut": false,
    "PortadoOutOperadora": "",
    "PortadoOutDate": "2024-07-24T17:21:48.89283-03:00",
    "DataCriacao": "2024-06-24T11:00:00-03:00",
    "SimCardID": null,
    "SimCard": null,
    "PortadoInOperadoraID": null,
    "PortadoInOperadoraObj": null,
    "PortadoOutOperadoraID": null,
    "PortadoOutOperadoraObj": null
}
```

#### Exemplo de Resposta

```json
{
    "id" : 226,
    "iccid" : "12345678901234567890",
    "imsi" : "111111111111111",
    "pin" : "1234",
    "puk" : "56789012",
    "ki" : "abcdef1234567890",
    "opc" : "fedcba0987654321",
    "estado_id" : 5,
    "telefonia_numero_id" : null,
    "data_criacao" : "2024-06-24T18:37:30.008Z",
    "data_estado" : "2024-06-24T18:37:30.008Z",
    "atualizado_em" : "2024-06-24T10:00:00.000Z",
    "puk2" : "5678901234",
    "pin2" : "4321"
}
```

<span id="get-apiallsimcard">

### 5.4.4. GET /simfonia/api/simcard/

#### Descrição

Recupera todos os SimCards existentes no banco de dados.

#### Exemplo de Requisição

```http
    GET /simfonia/api/simcard/
```

#### Exemplo de Resposta

```json
[
    {
        "id" : 226,
        "iccid" : "12345678901234567890",
        "imsi" : "111111111111111",
        "pin" : "1234",
        "puk" : "56789012",
        "ki" : "abcdef1234567890",
        "opc" : "fedcba0987654321",
        "estado_id" : 5,
        "telefonia_numero_id" : null,
        "data_criacao" : "2024-06-24T18:37:30.008Z",
        "data_estado" : "2024-06-24T18:37:30.008Z",
        "atualizado_em" : "2024-06-24T10:00:00.000Z",
        "puk2" : "5678901234",
        "pin2" : "4321"
    },
    {
        "id" : 227,
        "iccid" : "23456789012345678901",
        "imsi" : "222222222222222",
        "pin" : "2345",
        "puk" : "67890123",
        "ki" : "bcdef12345678901",
        "opc" : "edcba0987654321",
        "estado_id" : 5,
        "telefonia_numero_id" : null,
        "data_criacao" : "2024-06-24T18:37:30.008Z",
        "data_estado" : "2024-06-24T18:37:30.008Z",
        "atualizado_em" : "2024-06-24T11:00:00.000Z",
        "puk2" : "6789012345",
        "pin2" : "5432"
    }
]
```

<span id="get-apiallsimcardcsv">

### 5.4.5. GET /simfonia/api/simcard/csv

#### Descrição

Recupera todos os SimCards do banco e exporta em um arquivo `.csv`.

#### Exemplo de Requisição

```http
GET /simfonia/api/simcard/csv
```

#### Exemplo de Resposta

```csv
    "id","iccid","imsi","pin","puk","ki","opc","estado_id","telefonia_numero_id","data_criacao","data_estado","atualizado_em","puk2","pin2"
    226,"12345678901234567890","111111111111111","1234","56789012",abcdef1234567890,fedcba0987654321,5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 07:00:00.000 -0300,"5678901234","4321"
    227,"23456789012345678901","222222222222222","2345","67890123",bcdef12345678901,edcba0987654321,5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 08:00:00.000 -0300,"6789012345","5432"
    228,"34567890123456789012","333333333333333","3456","78901234",cdef12345678901,dcba0987654321,5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 09:00:00.000 -0300,"7890123456","6543"
    229,"45678901234567890123","444444444444444","4567","89012345",def1234567890123,cba0987654321,5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 10:00:00.000 -0300,"8901234567","7654"
    230,"56789012345678901234","555555555555555","5678","90123456",ef1234567890123,ba0987654321,5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 11:00:00.000 -0300,"9012345678","8765"
    231,"67890123456789012345","666666666666666","6789","01234567",f1234567890123,b0987654321,5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 12:00:00.000 -0300,"0123456789","9876"
    232,"78901234567890123456","777777777777777","7890","12345678","12345678901234","0987654321",5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 13:00:00.000 -0300,"1234567890","0987"
    233,"89012345678901234567","888888888888888","8901","23456789","23456789012345","9876543210",5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 14:00:00.000 -0300,"2345678901","1098"
    234,"90123456789012345678","999999999999999","9012","34567890","34567890123456","8765432109",5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 15:00:00.000 -0300,"3456789012","2109"

```

<span id="post-apicreatesimcard">

### 5.4.6. POST /simfonia/api/simcard/

#### Descrição

Cria um novo SimCard.

#### Exemplo de Requisição

```json
{
    "iccid" : "23456789012345678901",
    "imsi" : "222222222222222",
    "pin" : "2345",
    "puk" : "67890123",
    "ki" : "bcdef12345678901",
    "opc" : "edcba0987654321",
    "estado_id" : 5,
    "telefonia_numero_id" : null,
    "data_criacao" : "2024-06-24T18:37:30.008Z",
    "data_estado" : "2024-06-24T18:37:30.008Z",
    "atualizado_em" : "2024-06-24T11:00:00.000Z",
    "puk2" : "6789012345",
    "pin2" : "5432"
}
```

#### Exemplo de Resposta

```json
{
    "id" : 227,
    "iccid" : "23456789012345678901",
    "imsi" : "222222222222222",
    "pin" : "2345",
    "puk" : "67890123",
    "ki" : "bcdef12345678901",
    "opc" : "edcba0987654321",
    "estado_id" : 5,
    "telefonia_numero_id" : null,
    "data_criacao" : "2024-06-24T18:37:30.008Z",
    "data_estado" : "2024-06-24T18:37:30.008Z",
    "atualizado_em" : "2024-06-24T11:00:00.000Z",
    "puk2" : "6789012345",
    "pin2" : "5432"
}
```

<span id="post-apicreatesimcardcsv">

### 5.4.7. POST /simfonia/api/simcard/csv</h3>

#### Descrição

Cria novos SimCards em lote, baseados em um arquivo `.csv`.

#### Exemplo de Requisição

```csv
    "iccid","imsi","pin","puk","ki","opc","estado_id","telefonia_numero_id","data_criacao","data_estado","atualizado_em","puk2","pin2"
    "12345678901234567890","111111111111111","1234","56789012",abcdef1234567890,fedcba0987654321,5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 07:00:00.000 -0300,"5678901234","4321"
    "23456789012345678901","222222222222222","2345","67890123",bcdef12345678901,edcba0987654321,5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 08:00:00.000 -0300,"6789012345","5432"
    "34567890123456789012","333333333333333","3456","78901234",cdef12345678901,dcba0987654321,5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 09:00:00.000 -0300,"7890123456","6543"
    "45678901234567890123","444444444444444","4567","89012345",def1234567890123,cba0987654321,5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 10:00:00.000 -0300,"8901234567","7654"
    "56789012345678901234","555555555555555","5678","90123456",ef1234567890123,ba0987654321,5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 11:00:00.000 -0300,"9012345678","8765"
    "67890123456789012345","666666666666666","6789","01234567",f1234567890123,b0987654321,5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 12:00:00.000 -0300,"0123456789","9876"
    "78901234567890123456","777777777777777","7890","12345678","12345678901234","0987654321",5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 13:00:00.000 -0300,"1234567890","0987"
    "89012345678901234567","888888888888888","8901","23456789","23456789012345","9876543210",5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 14:00:00.000 -0300,"2345678901","1098"
    "90123456789012345678","999999999999999","9012","34567890","34567890123456","8765432109",5,,2024-06-24 15:37:30.008 -0300,2024-06-24 15:37:30.008 -0300,2024-06-24 15:00:00.000 -0300,"3456789012","2109"
```

```multipart-form
    csv: *arquivo*
```

#### Exemplo de Resposta

```json
{
    "mensagem": "Arquivo carregado e processado com sucesso!"
}
```

<span id="put-apiupdatesimcard">

### 5.4.8. PUT /simfonia/api/simcard/:id

#### Descrição

Atualiza um SimCard existente pelo ID.

#### Exemplo de Requisição

```http
    PUT /simfonia/api/simcard/227
```

```json
{
    "iccid" : "23456789012345678901",
    "imsi" : "222222222222222",
    "pin" : "2345",
    "puk" : "67890123",
    "ki" : "bcdef12345678901",
    "opc" : "edcba0987654321",
    "estado_id" : 5,
    "telefonia_numero_id" : null,
    "data_criacao" : "2024-06-24T18:37:30.008Z",
    "data_estado" : "2024-06-24T18:37:30.008Z",
    "atualizado_em" : "2024-06-24T11:00:00.000Z",
    "puk2" : "6789012345",
    "pin2" : "5432"
}
```

#### Exemplo de Resposta

```json
{
    "id": 227,
    "iccid" : "23456789012345678901",
    "imsi" : "222222222222222",
    "pin" : "2345",
    "puk" : "67890123",
    "ki" : "bcdef12345678901",
    "opc" : "edcba0987654321",
    "estado_id" : 5,
    "telefonia_numero_id" : null,
    "data_criacao" : "2024-06-24T18:37:30.008Z",
    "data_estado" : "2024-06-24T18:37:30.008Z",
    "atualizado_em" : "2024-06-24T11:00:00.000Z",
    "puk2" : "6789012345",
    "pin2" : "5432"
}
```

<span id="delete-apideletesimcardid">

### 5.4.9. DELETE /simfonia/api/simcard/:id

#### Descrição

Exclui um SimCard pelo ID.

#### Exemplo de Requisição

```http
DELETE /simfonia/api/simcard/227
```

#### Exemplo de Resposta

```json
{
    "deletado": true
}
```

<span id="simCard-estados">

## 5.5 Estados SimCard

<span id="get-apisimcardestadoid">

### 5.5.1. GET /simfonia/api/simcardestado/:id

#### Descrição

Recupera um Estado de SimCard pelo ID.

#### Exemplo de Requisição

```http
GET /simfonia/api/simcardestado/4
```

#### Exemplo de Resposta

```json
{
    "ID": 4,
    "Estado": "Baixa Perda",
    "Descricao": "Baixo por conta de perda",
    "SimCards": null
}
```

<span id="get-apisimcardestadoestado">

### 5.5.2. GET /simfonia/api/simcardestado/estado

#### Descrição

Recupera um Estado de SimCard pelo nome do estado.

#### Exemplo de Requisição

```json
{
    "Estado": "Ativo"
}
```

#### Exemplo de Resposta

```json
{
    "ID": 5,
    "Estado": "Ativo",
    "Descricao": "SimCards Ativos",
    "SimCards": null
}
```

<span id="get-apiallsimcardestado">

## 5.5.3. GET /simfonia/api/simcardestado/

#### Descrição

Recupera todos os Estados de SimCards existentes no banco de dados.

#### Exemplo de Requisição

```http
    GET /simfonia/api/simcard/
```

#### Exemplo de Resposta

```json
[
    {
        "ID": 4,
        "Estado": "Baixa Perda",
        "Descricao": "Baixo por conta de perda",
        "SimCards": null
    },
    {
        "ID": 5,
        "Estado": "Ativo",
        "Descricao": "SimCards Ativos",
        "SimCards": null
    },
    {
        "ID": 6,
        "Estado": "Baixo Pagamento",
        "Descricao": "Baixo por conta de pagamento",
        "SimCards": null
    }
]
```

<span id="get-apiallsimcardestadocsv">

### 5.5.4. GET /simfonia/api/simcardestado/csv

#### Descrição

Recupera todos os Estados de SimCards do banco e exporta em um arquivo `.csv`.

#### Exemplo de Requisição

```http
    GET /simfonia/api/simcardestado/csv
```

#### Exemplo de Resposta

```csv
    ID,Estado,Descricao
    4,Baixa Perda,Baixo por conta de perda
    5,Ativo,SimCards Ativos
    6,Baixo Pagamento,Baixo por conta de pagamento

```

<span id="post-apicreatesimcardestado">

### 5.5.5. POST /simfonia/api/simcardestado/

#### Descrição

Cria um novo Estado de SimCard.

#### Exemplo de Requisição

```json
{
    "Estado": "Baixo Furto",
    "Descricao": "Baixo por conta de furto"
}
```

#### Exemplo de Resposta

```json
{
    "ID": 7,
    "Estado": "Baixo Furto",
    "Descricao": "Baixo por conta de furto",
    "SimCards": null
}
```

<span id="post-apicreatesimcardestadocsv">

### 5.5.6. POST /simfonia/api/simcardestado/csv

#### Descrição

Cria novos Estados de SimCards em lote, baseados em um arquivo `.csv`.

#### Exemplo de Requisição

```csv
    Estado,Descricao
    Baixa Perda,Baixo por conta de perda
    Ativo,SimCards Ativos
    Baixo Pagamento,Baixo por conta de pagamento
```

```multipart-form
    csv: *arquivo*
```

#### Exemplo de Resposta

```json
{
    "mensagem": "Arquivo carregado e processado com sucesso!"
}
```

<span id="put-apiupdatesimcardestado">

### 5.5.7. PUT /simfonia/api/simcardestado/:id

#### Descrição

Atualiza um Estado de SimCard existente pelo ID.
Atualiza um Estado de SimCard existente pelo ID.

#### Exemplo de Requisição

```http
    PUT /simfonia/api/simcard/6
```

```json
{
    "Estado": "Baixo Furto",
    "Descricao": "Baixo por conta de furto"
}
```

#### Exemplo de Resposta

```json
{
    "ID": 7,
    "Estado": "Baixo Furto",
    "Descricao": "Baixo por conta de furto",
    "SimCards": null
}
```

<span id="delete-apideletesimcardestadoid">

### 5.5.8. DELETE /simfonia/api/simcardestado/:id

#### Descrição

Exclui um Estado de SimCard pelo ID.

#### Exemplo de Requisição

```http
DELETE /simfonia/api/simcardestado/6
```

#### Exemplo de Resposta

```json
{
    "deletado": true
}
```

<br />

<span id="modelos-de-dados">

## 6. Modelos de Dados

<span id="modelo-cidade">

### 6.1. Cidades

O modelo `Cidade` está definido no arquivo `model/cidades.go`.

```go
package model

import (
    "github.com/google/uuid"
)

type Cidade struct {
    ID      uint64    `gorm:"primaryKey;autoIncrement"`
    UUID    uuid.UUID `gorm:"type:uuid;"`
    Nome    string    `gorm:"not null" validate:"required"`
    CodIBGE int       `gorm:"unique;not null" validate:"required"`
    UF      string    `gorm:"size:2;not null" validate:"required, len=2"`
    CodArea int       `gorm:"not null" validate:"required"`
}

func (Cidade) TableName() string {
    return "t_cidades"
}

```

<span id="modelo-numerotelefonico">

### 6.2. Números Telefonicos

O modelo `NumeroTelefonico` está definido no arquivo `model/numerosTelefonicos.go`.

```go
package model

import (
    "time"
)

type NumeroTelefonico struct {
    ID                     uint64     `gorm:"primaryKey;autoIncrement"`
    CodArea                *int       `gorm:"size:4" validate:"len=4"`
    Numero                 uint64     `gorm:"unique;not null" validate:"required"`
    Utilizavel             bool       `gorm:"default:true"`
    PortadoIn              bool       `gorm:"default:false"`
    PortadoInOperadora     *string    `gorm:"size:50" validate:"len=50"`
    PortadoInDate          *time.Time `gorm:"default:CURRENT_TIMESTAMP"`
    CodigoCnl              string     `gorm:"size:10;not null" validate:"required, len=10"`
    CongeladoAte           *time.Time `gorm:"type:date"`
    ExternalID             *uint64
    PortadoOut             bool       `gorm:"default:false"`
    PortadoOutOperadora    *string    `gorm:"size:50" validate:"len=50"`
    PortadoOutDate         *time.Time `gorm:"default:CURRENT_TIMESTAMP"`
    DataCriacao            *time.Time `gorm:"default:CURRENT_TIMESTAMP"`
    SimCardID              *uint64
    SimCard                *SimCard `gorm:"foreignKey:SimCardID;references:ID"`
    PortadoInOperadoraID   *uint64
    PortadoInOperadoraObj  *Operadora `gorm:"foreignKey:PortadoInOperadoraID;references:ID"`
    PortadoOutOperadoraID  *uint64
    PortadoOutOperadoraObj *Operadora `gorm:"foreignKey:PortadoOutOperadoraID;references:ID"`
}

func (NumeroTelefonico) TableName() string {
    return "t_telefonia_numero"
}

```

<span id="modelo-operadoras">

### 6.3 Operadoras

O modelo `Operadora` está definido no arquivo `model/operadoras.go`.

```go
package model

type Operadora struct {
    ID                   uint64             `gorm:"primaryKey;autoIncrement"`
    Nome                 string             `gorm:"unique;not null" validate:"required"`
    Abreviacao           string             `gorm:"unique;not null" validate:"required"`
    NumeroTelefonicosIn  []NumeroTelefonico `gorm:"foreignKey:PortadoInOperadoraID"`
    NumeroTelefonicosOut []NumeroTelefonico `gorm:"foreignKey:PortadoOutOperadoraID"`
}

func (Operadora) TableName() string {
    return "t_operadoras"
}

```

<span id="modelo-simcards">

### 6.4. SimCards

O modelo `SimCard` está definido no arquivo `model/simCard.go`.

```go
package model

import (
    "time"
)

type SimCard struct {
    ID                uint64            `gorm:"primaryKey;autoIncrement"`
    ICCID             string            `gorm:"size:20;not null" validate:"required, len=20"`
    IMSI              string            `gorm:"size:15;not null" validate:"required, len=15"`
    PIN               string            `gorm:"size:8;not null" validate:"required, len=8"`
    PUK               string            `gorm:"size:10;not null" validate:"required, len=10"`
    KI                string            `gorm:"size:16;not null" validate:"required, len=16"`
    OPC               string            `gorm:"size:16;not null" validate:"required, len=16"`
    EstadoID          *uint64           `gorm:"size:4" validate:"len=4"`
    Estado            SimCardEstado     `gorm:"foreignKey:EstadoID"`
    TelefoniaNumeroID *uint64           `gorm:"size:8" validate:"len=8"`
    TelefoniaNumero   *NumeroTelefonico `gorm:"foreignKey:TelefoniaNumeroID"`
    DataCriacao       time.Time         `gorm:"default:CURRENT_TIMESTAMP"`
    DataEstado        time.Time         `gorm:"default:CURRENT_TIMESTAMP"`
    AtualizadoEm      time.Time         `gorm:"default:CURRENT_TIMESTAMP"`
    PUK2              string            `gorm:"size:10" validate:"len=10"`
    PIN2              string            `gorm:"size:8" validate:"len=8"`
}

func (SimCard) TableName() string {
    return "t_simcard"
}

```

<span id="modelo-simcardestado">

### 6.5. Estados SimCards

O modelo `SimCardEstado` está definido no arquivo `model/simCardEstado.go`.

```go
package model

type SimCardEstado struct {
    ID        uint64    `gorm:"primaryKey;autoIncrement"`
    Estado    string    `gorm:"size:20;not null"`
    Descricao string    `gorm:"type:text"`
    SimCards  []SimCard `gorm:"foreignKey:EstadoID"`
}

func (SimCardEstado) TableName() string {
    return "t_simcard_estado"
}
```

<br />

<span id="servicos">

## 7. Serviços

<span id="cidadeService">

### 7.1 CidadeService

Os serviços relacionados às cidades estão definidos no arquivo `service/cidadesService.go`.

- **FindCidadeById(id uint64)**: Busca uma cidade pelo ID.
- **FindCidadeByNome(nome string)**: Busca uma cidade pelo nome.
- **FindAllCidades()**: Busca por todas as cidades da tabela.
- **CreateCidade(usuario model.Cidade)**: Cria uma nova cidade.
- **UpdateCidade(cidadeRecebida model.Cidade, id uint64)**: Atualiza uma cidade existente.
- **DeleteCidadeById(id uint64)**: Exclui uma cidade pelo ID.
- **validateCidade(cidade model.Cidade)**: Valida se o objeto cidade está de acordo com as restrições da tabela.

<span id="numerosTelefonicosService">

### 7.2. NumeroTelefonicoService

Os serviços relacionados aos números telefônicos estão definidos no arquivo `service/numerosTelefonicos.go`.

- **FindNumeroTelefonicoById(id uint64)**: Busca um número telefônico pelo ID.
- **FindNumeroTelefonicoByNumero(numero int)**: Busca um número telefônico pelo número.
- **FindNumeroTelefonicoBySimCardId(id int)**: Busca um número telefônico pelo SimCard correspondente.
- **FindAllNumeroTelefonicos()**: Busca por todos os números telefônicos da tabela.
- **CreateNumeroTelefonico(numeroTelefonico model.NumeroTelefonico)**: Cria um novo número telefônico.
- **UpdateNumeroTelefonico(numeroTelefonicoRecebido model.NumeroTelefonico, id uint64)**: Atualiza um número telefônico existente.
- **DeleteNumeroTelefonicoById(id uint64)**: Exclui um número telefônico pelo ID.
- **validateNumeroTelefonico(numeroTelefonico model.NumeroTelefonico)**: Valida se o objeto numeroTelefonico está de acordo com as restrições da tabela.

<span id="operadorasService">

### 7.3. OperadoraService

Os serviços relacionados às operadoras estão definidos no arquivo `service/operadorasService.go`.

- **FindOperadoraById(id uint64)**: Busca uma operadora pelo ID.
- **FindOperadoraByNome(nome string)**: Busca uma operadora pelo nome completo.
- **FindOperadoraByAbreviacao(abreviacao string)**: Busca uma operadora pelo nome abreviado.
- **FindAllOperadoras()**: Busca por todas as operadoras da tabela.
- **CreateOperadora(operadora model.Operadora)**: Cria uma nova operadora.
- **UpdateOperadora(operadoraRecebida model.Operadora, id uint64)**: Atualiza uma operadora existente.
- **DeleteOperadoraById(id uint64)**: Exclui uma operadora pelo ID.
- **validateOperadora(operadora model.Operadora)**: Valida se o objeto operadora está de acordo com as restrições da tabela.

<span id="simCardService">

### 7.4. SimCardService

Os serviços relacionados ao usuário estão definidos no arquivo `service/simCardService.go`.

- **FindSimCardById(id uint64)**: Busca um SimCard pelo ID.
- **FindSimCardByTelefoniaNumeroID(id int)**: Busca um SimCard pelo id do número telefônico correspondente.
- **FindAllSimCards()**: Busca por todos os SimCards da tabela.
- **CreateSimCard(simCard model.SimCard)**: Cria um novo SimCard.
- **UpdateSimCard(simCardRecebido model.SimCard, id uint64)**: Atualiza um SimCard existente.
- **DeleteSimCardById(id uint64)**: Exclui um SimCard pelo ID.
- **validateSimCard(simCard model.SimCard)**: Valida se o objeto simCard está de acordo com as restrições da tabela.

<span id="simCardEstadoService">

### 7.5. SimCardEstadoService

Os serviços relacionados ao usuário estão definidos no arquivo `service/cidadesService.go`.

- **FindSimCardEstadoById(id uint64)**: Busca um Estado de SimCard pelo ID.
- **FindSimCardEstadoByEstado(estado string)**: Busca um Estado de SimCard pelo nome.
- **FindAllSimCardEstados()**: Busca por todos os Estados de SimCard da tabela.
- **CreateSimCardEstado(simCardEstado model.SimCardEstado)**: Cria um novo Estado de SimCard.
- **UpdateSimCardEstado(simCardEstadoRecebido model.SimCardEstado, id uint64)**: Atualiza um Estado de SimCard existente.
- **DeleteSimCardEstadoById(id uint64)**: Exclui um Estado de SimCard pelo ID.
- **validateSimCardEstado(simCardEstado model.SimCardEstado)**: Valida se o objeto simCardEstado está de acordo com as restrições da tabela.

<br />

<span id="controladores">

## 8. Controladores

Os controladores estão definidos nos arquivos abaixo:

```plaintext
app/
├── controller/
│   └── cidadeController.go
│   └── numerosTelefonicosController.go
│   └── operadorasController.go
│   └── simCardController.go
│   └── simCardEstadoController.go
```

E possuem os seguintes métodos:

- **InitRoutes()**: Inicializa as rotas da API.
- Todos os outros métodos recebem `context *gin.Context` como parâmetro e são todos aqueles já citados nos endpoints da API.

<br />

<span id="instrucoes-para-execucao">

## 9. Instruções para Execução

### Pré-requisitos

- [Go](https://golang.org/doc/install)
- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

### Passos para Execução

1. **Criar imagem simfonia**:

   ```sh
   docker build -t simfonia .
   ```

2. **Inicie o banco de dados PostgreSQL**:

   ```sh
   docker compose up
   ```

3. **Execute o aplicativo Go**:

   ```sh
   go run main.go
   ```

4. **Acesse a API**:

   - A API estará disponível em `http://localhost:8601`.

Esta documentação cobre os principais aspectos da API CRUD desenvolvida em Go com o framework Gin. Ela inclui detalhes sobre a estrutura do projeto, configuração, endpoints da API, modelos de dados, serviços, controladores e instruções para execução.
