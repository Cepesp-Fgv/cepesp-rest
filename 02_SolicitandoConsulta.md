# [Passo 1] Solicitando Consulta
O primeiro passo para se utilizar a API Rest é fazer o pedido de consulta com os parâmetros necessários. Os parâmetros vão variar com a base a ser acessada. O formato geral da consulta é:

[GET] `cepesp.io/api/consulta/athena/query?table=<TABELA>&<ARGUMENTOS>`

Para solicitar uma consulta deve ser passado obrigatóriamente o nome da base de dados (`?table=TABELA`) que se deseja acessar.

Atualmente existem 5 bases disponíveis para consulta:

| Nome da Base                  | TABELA        |
|-------------------------------|---------------|
| Base de Candidatos            | candidatos    |
| Base de Coligações/Legendas   | legendas      |
| Base de Votos                 | votos         |
| Base de Consolidado dos Votos | tse           |
| Base de Bens do Candidato     | bem_candidato |
| Base de Bens do Candidato     | secretarios   |

Em seguida, deve-se preencher os `<ARGUMENTOS>`, que variam dependendo da base a ser acessada. Listamos abaixo um resumo dos argumentos possíveis e onde estão disponíveis:

| Argumentos                    | Bases Suportadas ("TABELA")                     |
|-------------------------------|-------------------------------------------------|
| anos                          | tse, candidatos, legendas, votos, bem_candidato |
| cargo                         | tse, candidatos, legendas, votos                |
| agregacao_regional            | tse, votos                                      |
| agregacao_politica            | tse                                             |
| uf_filter                     | tse, votos, bem_candidato                       |
| mun_filter                    | tse, votos                                      |
| only_elected                  | tse, candidatos                                 |
| brancos                       | tse, votos                                      |
| nulos                         | tse, votos                                      |
| name_filter                   | secretarios                                     |
| goverment_period              | secretarios                                     |
 
Também é possível selecionar as colunas que aparecerão no resultado da consulta. Para isso, deve se passar o argumento `&c[]=<COLUNA>` para cada coluna que se deseja adicionar.

Filtrar os resultados direto na consulta também é possível através do argumento `&filters[<COLUNA>]=<VALOR>`. Por exemplo, para filtrar candidatos(as) à Presidência em 2018 que se declaram pretos(as), utilizamos o seguinte link: 

`cepesp.io/api/consulta/athena/query?table=candidatos&anos=2014&cargo=1&c[]=ANO_ELEICAO&c[]=NUM_TURNO&c[]=SIGLA_UE&c[]=DESCRICAO_CARGO&c[]=SIGLA_PARTIDO&c[]=NUMERO_CANDIDATO&c[]=CPF_CANDIDATO&c[]=NOME_URNA_CANDIDATO&c[]=DESCRICAO_SEXO&c[]=DESCRICAO_COR_RACA&c[]=DESC_SIT_TOT_TURNO&filters[DESCRICAO_COR_RACA]=PRETA`

Note que tivemos que acrescentar as colunas desejadas utilizando `&c[]=<COLUNA>`, visto que `DESCRICAO_COR_RACA` não é coluna default da consulta a candidatos.

[Clique aqui](https://github.com/Cepesp-Fgv/tse-dados/wiki/Colunas) para ver quais as colunas estão disponíveis para cada base de dados.

## A resposta do servidor
Quando os argumentos são passados corretamente o servidor responde a requisição HTTP com um status 200 com o seguinte conteúdo:

**[GET]** `http://cepesp.io/api/consulta/athena/query?table=legendas&cargo=1&anos=2018`
```js
{
    "id": 9999,
    "name": "LEGENDAS_PRESIDENTE_2018",
    "sql": "SELECT ANO_ELEICAO AS ANO_ELEICAO, NUM_TURNO AS NUM_TURNO, SIGLA_UE AS SIGLA_UE, DESCRICAO_CARGO AS DESCRICAO_CARGO, TIPO_LEGENDA AS TIPO_LEGENDA, NUMERO_PARTIDO AS NUMERO_PARTIDO, SIGLA_PARTIDO AS SIGLA_PARTIDO, COMPOSICAO_COLIGACAO AS COMPOSICAO_COLIGACAO FROM legendas AS v WHERE p_ano IN ('2018') AND (p_cargo = '1') ORDER BY ANO_ELEICAO ASC, SIGLA_UE ASC, NUMERO_PARTIDO ASC"
}
```

Guarde o `"id":9999` durante todo o processo.

Depois disso você pode fazer download do [**Resultado**](04_Resultado.md).
