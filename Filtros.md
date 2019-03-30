# Aplicando Filtros

Em qualquer tabela é possível aplicar filtros direto na consulta, para isso é necessário informar a coluna
que deve ser filtrada e também o valor do filtro.

Ex.:
 - Para consultar o ano 2014 adicionamos ```?ano=2014```
 - Para consultar o cargo Presidente adicionamos ```&cargo=1```
 - Para agregar os resultados por UF adicionamos ```&agregacao_regional=2```
 - Para selecionar as colunas NUM_TURNO, NOME_MACRO, DESCRICAO_CARGO, UF, QTDE_VOTOS adicionamos ```&c[]="NUM_TURNO"&c[]="NOME_MACRO"&c[]="DESCRICAO_CARGO"&c[]="UF"&c[]="QTDE_VOTOS"```
 - Para o filtro do *UF="ES"* adicionamos ```uf_filter="ES"```_
 - Para o filtro do *NUM_TURNO="1"* adicionamos ```&filters[NUM_TURNO]="1"```
```bash
  curl -i -g -X GET "http://cepesp.io/api/consulta/votos?cargo=1&agregacao_regional=2&anos=2014&c[]=ANO_ELEICAO&c[]=NOME_MACRO&c[]=NUM_TURNO&c[]=DESCRICAO_CARGO&c[]=NUMERO_CANDIDATO&c[]=QTDE_VOTOS&ignore_version=true"
```

# Formato

&filters[**NOME_DA_COLUNA**]="**VALOR_DA_BUSCA**"

 TAG             | Descrição
---------------- | ------------------------------------------------------------                                  
NOME_DA_COLUNA   | O nome da coluna da tabela, ex: NUM_TURNO, NOME_MACRO, etc.
VALOR_DA_BUSCA   | O valor que deseja ser buscado.                            
