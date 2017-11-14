# Eleições por Cargo
  Consulte os votos agregados regionalmente

## URL

  http://cepesp.io/api/consulta/votos

## Método
  
  `GET`
  
## Parâmetros da URL

   **Obrigatórios:**
   
   `cargo=[integer]`
 
   `ano=[integer]` ou `anos=[string]`
   <_Exemplo: `&ano=1998` ou `&anos="1998,2000"`_>
   
   `agregacao_regional=[integer]`
   
   **Opcionais:**
   
   `uf_filter=[string]` **Obrigatório somente quando agregação regional é `Votação Seção`
 
   `lang=[string]` <_`pt`|`en`_>
   
   `format=[string]` <_`csv`|`gzip`_>
   
   `selected_columns[]=[string]`

## Exemplos:

  ```bash
  curl -i -X GET "http://cepesp.io/api/consulta/votos?ano=2014&cargo=1&agregacao_regional=0"
  ```
  
  ```bash
  curl -i -X GET "http://cepesp.io/api/consulta/votos?anos="2014,2010"&cargo=3&agregacao_regional=1"
  ```

  ```bash
  curl -i -X GET "http://cepesp.io/api/consulta/votos?anos="2014"&cargo=1&agregacao_regional=9&uf_filter=CE"
  ```

  ```bash
  curl -i -g -X GET "http://cepesp.io/api/consulta/votos?ano=2010&cargo=3&agregacao_regional=1&selected_columns[]="NUM_TURNO"&selected_columns[]="NOME_MACRO"&selected_columns[]="DESCRICAO_CARGO"&selected_columns[]="QTDE_VOTOS""
  ```

## Cargo:

| Cargo(position)      | Número |
| ------------------------- |:------:|
| Presidente                |   1    |
| Governador                |   3    | 
| Senador                   |   5    |
| Deputado Federal          |   6    | 
| Deputado Estadual         |   7    | 
| Deputado Distrital        |   8    | 
| Prefeito                  |   11   |
| Vereador                  |   13   |

## Ano:

| Ano      | Cargos Disponíveis (Descrição) | Cargos Disponíveis (Numero) | 
| ------------------------- |:------|:-----:|
| 1998                |   Presidente, Governador, Senador, Deputado Federal, Deputado Estadual, Deputado Distrital   | 1,3,5,6,7,8 |
| 2000                |   Prefeito, Vereador    | 11, 13 |
| 2002                |   Presidente, Governador, Senador, Deputado Federal, Deputado Estadual, Deputado Distrital    | 1,3,5,6,7,8 |
| 2004                |   Prefeito, Vereador    | 11, 13 | 
| 2006                |   Presidente, Governador, Senador, Deputado Federal, Deputado Estadual, Deputado Distrital    | 1,3,5,6,7,8 |
| 2008                |   Prefeito, Vereador    | 11, 13 |
| 2010                |   Presidente, Governador, Senador, Deputado Federal, Deputado Estadual, Deputado Distrital    |  1,3,5,6,7,8 |
| 2012                |   Prefeito, Vereador    | 11, 13 |
| 2014                |   Presidente, Governador, Senador, Deputado Federal, Deputado Estadual, Deputado Distrital    |  1,3,5,6,7,8 |
| 2016                |   Prefeito, Vereador    | 11, 13 |


## Colunas Disponíveis:

Cada tipo de agregação regional adiciona colunas diferentes.

### Colunas padrões

- DATA_GERACAO
- HORA_GERACAO
- ANO_ELEICAO
- SIGLA_UE
- NUM_TURNO
- DESCRICAO_ELEICAO
- CODIGO_CARGO
- DESCRICAO_CARGO
- NUMERO_CANDIDATO
- QTDE_VOTOS

### Agregação Regional

#### Macro 
  _Código: *1*_
  - CODIGO_MACRO
  - NOME_MACRO

#### UF 
  _Código: *2*_
  - CODIGO_MACRO
  - NOME_MACRO
  - UF
  - NOME_UF

#### Meso 
  _Código: *4*_
  - CODIGO_MACRO
  - NOME_MACRO
  - UF
  - NOME_UF
  - CODIGO_MESO
  - NOME_MESO

#### Micro 
  _Código: *5*_
  - CODIGO_MACRO
  - NOME_MACRO
  - UF
  - NOME_UF
  - CODIGO_MESO
  - NOME_MESO
  - CODIGO_MICRO
  - NOME_MICRO

#### Município 
  _Código: *6*_
  - CODIGO_MACRO
  - NOME_MACRO
  - UF
  - NOME_UF
  - CODIGO_MESO
  - NOME_MESO
  - CODIGO_MICRO
  - NOME_MICRO
  - COD_MUN_TSE
  - COD_MUN_IBGE
  - NOME_MUNICIPIO

#### Município-Zona 
  _Código: *7*_
  - CODIGO_MACRO
  - NOME_MACRO
  - UF
  - NOME_UF
  - CODIGO_MESO
  - NOME_MESO
  - CODIGO_MICRO
  - NOME_MICRO
  - COD_MUN_TSE
  - COD_MUN_IBGE
  - NOME_MUNICIPIO
  - NUM_ZONA

#### Zona 
  _Código: *8*_
  - CODIGO_MACRO
  - NOME_MACRO
  - UF
  - NOME_UF
  - CODIGO_MESO
  - NOME_MESO
  - CODIGO_MICRO
  - NOME_MICRO
  - NUM_ZONA

#### Votação Seção 
  _Código: *9*_
 - CODIGO_MACRO
 - NOME_MACRO
 - UF
 - NOME_UF
 - CODIGO_MESO
 - NOME_MESO
 - CODIGO_MICRO
 - NOME_MICRO
 - COD_MUN_TSE
 - COD_MUN_IBGE
 - NOME_MUNICIPIO
 - NUM_ZONA
 - NUM_SECAO
