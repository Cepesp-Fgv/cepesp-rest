# Aplicando Filtros

Em qualquer tabela é possível aplicar filtros direto na consulta, para isso é necessário informar a coluna
que deve ser filtrada e também o valor do filtro.



Ex.:
 - Para consultar o ano 2014 adicionamos ```&ano=2014```
 - Para consultar o cargo Presidente adicionamos ```&cargo=1```
 - Para selecionar as colunas NUM_TURNO, NOME_MACRO, DESCRICAO_CARGO, UF, QTDE_VOTOS adicionamos ```&selected_columns[]="NUM_TURNO"&selected_columns[]="NOME_MACRO"&selected_columns[]="DESCRICAO_CARGO"&selected_columns[]="UF"&selected_columns[]="QTDE_VOTOS"```
 - Para o filtro do *UF="ES"* adicionamos ```&columns[0][name]="UF"&columns[0][search][value]="ES"```_
 - Para o filtro do *NUM_TURNO="1"* adicionamos ```&columns[1][name]="NUM_TURNO"&columns[1][search][value]="1"```
```bash
  curl -i -g -X GET "http://cepesp.io/api/consulta/votos?ano=2014&cargo=1&agregacao_regional=2&selected_columns[]="NUM_TURNO"&selected_columns[]="NOME_MACRO"&selected_columns[]="DESCRICAO_CARGO"&selected_columns[]="QTDE_VOTOS"&selected_columns[]="UF"&columns[0][name]="UF"&columns[0][search][value]="ES"&columns[1][name]="NUM_TURNO"&columns[1][search][value]="1""
```

# Formato

&columns[**ÍNDICE**][name]="**NOME_DA_COLUNA**"&columns[**ÍNDICE**][search][value]="**VALOR_DA_BUSCA**"

 TAG             | Descrição
---------------- | ------------------------------------------------------------
ÍNDICE           | Número iniciando em zero (para cada filtro um índice diferente).                                   
NOME_DA_COLUNA | O nome da coluna da tabela, ex: NUM_TURNO, NOME_MACRO, etc.
VALOR_DA_BUSCA | O valor que deseja ser buscado.                            

_Importante: as colunas filtradas devem estar contidas na lista das colunas selecionadas **"selected_columns[]"**_
