# [Passo 1] Solicitando Consulta
Como explicado nos [Primeiros Passos](01_PrimeirosPassos.md), efetuaremos uma consulta com os parâmetros necessários para que a consulta seja gerada.
Os parâmetros vão variar com a base a ser acessada. 
A nossa API está localizada no servidor `cepesp.io` e todas as requisições devem partir desse endereço.

O endpoint para realizar a consulta é:

[GET] `/api/consulta/athena/query?table=<TABELA>&<ARGUMENTOS>`

Para solicitar uma consulta deve ser passado obrigatóriamente o nome da base (`?table=TABELA`) que está sendo acessada.

Atualmente existem 5 bases disponíveis para consulta:

| Nome da Base                  | TABELA        |
|-------------------------------|---------------|
| Base de Candidatos            | candidatos    |
| Base de Coligações/Legendas   | legendas      |
| Base de Votos                 | votos         |
| Base de Consolidado dos Votos | tse           |
| Base de Bens do Candidato     | bem_candidato |
| Base de Bens do Candidato     | secretarios   |
| Base de Bens do Candidato     | filiados.     |

Em seguida vem os <ARGUMENTOS> que dependem da base a ser acessada.
Listamos abaixo um resumo dos argumentos possíveis e onde estão disponíveis:

| Argumento                     | Bases Suportadas                                |
|-------------------------------|-------------------------------------------------|
| anos                          | tse, candidatos, legendas, votos, bem_candidato |
| cargo                         | tse, candidatos, legendas, votos                |
| agregacao_regional            | tse, votos                                      |
| agregacao_politica            | tse                                             |
| uf_filter                     | tse, votos, bem_candidato, filiados             |
| mun_filter                    | tse, votos                                      |
| only_elected                  | tse, candidatos                                 |
| brancos                       | tse, votos                                      |
| nulos                         | tse, votos                                      |
| name_filter                   | secretarios                                     |
| goverment_period              | secretarios                                     |
| party                         | filiados                                        |
 
Também é possível selecionar as colunas que aparecerão no resultado da consulta. 
Para isso, deve se passar o argumento `&c[]=<COLUNA>` para cada coluna que se deseja adicionar.

Filtrar os resultados direto na consulta também é possível através do argumento `&filters[<COLUNA>]=<VALOR>`.

[Clique aqui](https://github.com/Cepesp-Fgv/tse-dados/wiki/Colunas) para ver quais as colunas estão disponíveis por base.

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

O cliente deverá guardar o `"id":9999` durante todo o processo.

[Clique aqui para ir para o **Próximo Passo**](03_Espera.md)
