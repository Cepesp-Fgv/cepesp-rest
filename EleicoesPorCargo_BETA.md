# Eleições por Cargo (BETA)
  Consulte os votos agregados regionalmente e politicamente

## URL

  http://cepesp.io/api/consulta/tse

## Método
  
  `GET`
  
## Parâmetros da URL

   **Obrigatórios:**
   
   `cargo=[integer]`
 
   `ano=[integer]` ou `anos=[string]`
   <_Exemplo: `&ano=1998` ou `&anos="1998,2000"`_>
   
   `agregacao_regional=[integer]`
   
   `agregacao_politica=[integer]`
   

   **Opcionais:**
 
   `lang=[string]` <_`pt`|`en`_>
   
   `format=[string]` <_`csv`|`gzip`_>
   
   `c[]=[string]` ou `selected_columns[]=[string]`

## Exemplos:

  ```bash
  curl -i -X GET "http://cepesp.io/api/consulta/tse?ano=2014&cargo=1&agregacao_regional=0&agregacao_politica=2&ignore_version=true"
  ```
  
  ```bash
  curl -i -X GET "http://cepesp.io/api/consulta/tse?anos="2014,2010"&cargo=3&agregacao_regional=1&agregacao_politica=2&ignore_version=true"
  ```

  ```bash
  curl -i -g -X GET "http://cepesp.io/api/consulta/tse?ano=2010&cargo=3&agregacao_regional=1&agregacao_politica=2&c[]="SIGLA_PARTIDO"&c[]="NUM_TURNO"&c[]="NOME_MACRO"&c[]="DESCRICAO_CARGO"&c[]="QTDE_VOTOS"&ignore_version=true"
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

Cada tipo de agregação gera colunas diferentes. (Agregação Regional e Política se combinam gerando uma única tabela)


### Agregação Política

#### Legenda 
  _Código: *1*_
  - ANO_ELEICAO
  - NUM_TURNO
  - DESCRICAO_ELEICAO
  - SIGLA_UE
  - DESCRICAO_UE
  - CODIGO_CARGO
  - DESCRICAO_CARGO
  - NUMERO_PARTIDO
  - SIGLA_PARTIDO
  - NOME_PARTIDO
  - QTDE_VOTOS

#### Candidato 
  _Código: *2*_

  - ANO_ELEICAO
  - NUM_TURNO
  - DESCRICAO_ELEICAO
  - SIGLA_UE
  - DESCRICAO_UE
  - CODIGO_CARGO
  - DESCRICAO_CARGO
  - NOME_CANDIDATO
  - NUMERO_CANDIDATO
  - CPF_CANDIDATO
  - NOME_URNA_CANDIDATO
  - COD_SITUACAO_CANDIDATURA
  - DES_SITUACAO_CANDIDATURA
  - NUMERO_PARTIDO
  - SIGLA_PARTIDO
  - NOME_PARTIDO
  - CODIGO_LEGENDA
  - SIGLA_LEGENDA
  - COMPOSICAO_LEGENDA
  - NOME_LEGENDA
  - CODIGO_OCUPACAO
  - DESCRICAO_OCUPACAO
  - DATA_NASCIMENTO
  - NUM_TITULO_ELEITORAL_CANDIDATO
  - IDADE_DATA_ELEICAO
  - CODIGO_SEXO
  - DESCRICAO_SEXO
  - COD_GRAU_INSTRUCAO
  - DESCRICAO_GRAU_INSTRUCAO
  - CODIGO_ESTADO_CIVIL
  - DESCRICAO_ESTADO_CIVIL
  - CODIGO_COR_RACA
  - DESCRICAO_COR_RACA
  - CODIGO_NACIONALIDADE
  - DESCRICAO_NACIONALIDADE
  - SIGLA_UF_NASCIMENTO
  - COD_MUN_TSE_NASCIMENTO
  - NOME_MUNICIPIO_NASCIMENTO
  - DESPESA_MAX_CAMPANHA
  - COD_SIT_TOT_TURNO
  - DESC_SIT_TOT_TURNO
  - NM_EMAIL
  - TIPO_LEGENDA
  - SIGLA_COLIGACAO
  - NOME_COLIGACAO
  - COMPOSICAO_COLIGACAO
  - QTDE_VOTOS

#### Coligação 
  _Código: *3*_

  - ANO_ELEICAO
  - NUM_TURNO
  - DESCRICAO_ELEICAO
  - SIGLA_UE
  - DESCRICAO_UE
  - CODIGO_CARGO
  - DESCRICAO_CARGO
  - SIGLA_COLIGACAO
  - NOME_COLIGACAO
  - COMPOSICAO_COLIGACAO
  - SEQUENCIA_COLIGACAO

#### Consolidado da Eleição 
  _Código: *4*_

  - ANO_ELEICAO
  - NUM_TURNO
  - DESCRICAO_ELEICAO
  - CODIGO_CARGO
  - DESCRICAO_CARGO
  - QTD_APTOS
  - QTD_COMPARECIMENTO
  - QTD_ABSTENCOES
  - QT_VOTOS_NOMINAIS
  - QT_VOTOS_BRANCOS
  - QT_VOTOS_NULOS
  - QT_VOTOS_LEGENDA
  - QT_VOTOS_ANULADOS_APU_SEP


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
