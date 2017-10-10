# Votação Seção
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
  curl -i -g -X GET "http://cepesp.io/api/consulta/votos?ano=2010&cargo=3&agregacao_regional=1&selected_columns[]="NUM_TURNO"&selected_columns[]="NOME_MACRO"&selected_columns[]="DESCRICAO_CARGO"&selected_columns[]="QTDE_VOTOS""
  ```

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
