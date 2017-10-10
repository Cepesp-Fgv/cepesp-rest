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
