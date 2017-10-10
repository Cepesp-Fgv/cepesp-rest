# Candidatos
  Consulte os candidatos

## URL

  http://cepesp.io/api/consulta/candidatos

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
  curl -i -X GET "http://cepesp.io/api/consulta/candidatos?ano=2014&cargo=1"
  ```
  
  ```bash
  curl -i -X GET "http://cepesp.io/api/consulta/candidatos?anos="2014,2010"&cargo=3"
  ```

  ```bash
  curl -i -g -X GET "http://cepesp.io/api/consulta/candidatos?ano=2010&cargo=3&selected_columns[]="ANO_ELEICAO"&selected_columns[]="NUM_TURNO"&selected_columns[]="CODIGO_CARGO"&selected_columns[]="NOME_URNA_CANDIDATO"&selected_columns[]="NUMERO_CANDIDATO""
  ```

## Colunas Disponíveis:

  - DATA_GERACAO
  - HORA_GERACAO
  - ANO_ELEICAO
  - NUM_TURNO
  - DESCRICAO_ELEICAO
  - SIGLA_UF
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
  - NOME_COLIGACAO
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
  - CODIGO_NACIONALIDADE
  - DESCRICAO_NACIONALIDADE
  - SIGLA_UF_NASCIMENTO
  - CODIGO_MUNICIPIO_NASCIMENTO
  - NOME_MUNICIPIO_NASCIMENTO
  - DESPESA_MAX_CAMPANHA
  - COD_SIT_TOT_TURNO
  - DESC_SIT_TOT_TURNO