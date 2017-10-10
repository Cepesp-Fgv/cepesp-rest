# Legendas
  Consulte as legendas

## URL

  http://cepesp.io/api/consulta/legendas

## Método
  
  `GET`
  
## Parâmetros da URL

   **Obrigatórios:**
   
   `cargo=[integer]`
 
   `ano=[integer]` ou `anos=[string]`
   <_Exemplo: `&ano=1998` ou `&anos="1998,2000"`_>
   

   **Opcionais:**
 
   `lang=[string]` <_`pt`|`en`_>
   
   `format=[string]` <_`csv`|`gzip`_>
   
   `selected_columns[]=[string]`

## Exemplos:

  ```bash
  curl -i -X GET "http://cepesp.io/api/consulta/legendas?ano=2014&cargo=1"
  ```
  
  ```bash
  curl -i -X GET "http://cepesp.io/api/consulta/legendas?anos="2014,2010"&cargo=3"
  ```

  ```bash
  curl -i -g -X GET "http://cepesp.io/api/consulta/legendas?ano=2010&cargo=3&selected_columns[]="ANO_ELEICAO"&selected_columns[]="NUM_TURNO"&selected_columns[]="CODIGO_CARGO"&selected_columns[]="NOME_PARTIDO"&selected_columns[]="NUMERO_PARTIDO""
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

- DATA_GERACAO
- HORA_GERACAO
- ANO_ELEICAO
- NUM_TURNO
- DESCRICAO_ELEICAO
- SIGLA_UF
- SIGLA_UE
- CODIGO_CARGO
- DESCRICAO_CARGO
- TIPO_LEGENDA
- NUMERO_PARTIDO
- SIGLA_PARTIDO
- NOME_PARTIDO
- SIGLA_COLIGACAO
- NOME_COLIGACAO
- COMPOSICAO_COLIGACAO
- SEQUENCIAL_COLIGACAO
