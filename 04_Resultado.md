# O Resultado

Uma vez que a consulta ficou pronta, você consegue acessá-la por meio do link:

**[GET]** `cepesp.io/api/consulta/athena/result?id=<ID>&ignore_version=true`

O cliente deve fornecer o \<ID\> recebido no passo 1.

> Vale ressaltar que é necessário o parâmetro `&ignore_version=true` para que você não receba mensagens do controle de versão das APIs Python e R.

A resposta do servidor será o output do arquivo CSV gerado. 
O arquivo vem sempre com um cabeçalho com as colunas. 
As colunas são sempre separadas por vírgulas.

Exemplo de resposta:

Arquivo: _LEGENDAS_PRESIDENTE_2018.csv_
```
"ANO_ELEICAO","NUM_TURNO","SIGLA_UF","SIGLA_UE","CODIGO_CARGO","TIPO_LEGENDA","NUMERO_PARTIDO","SIGLA_PARTIDO","COMPOSICAO_COLIGACAO"
"2018","1","BR","BR","1","COLIGACAO","10","PRB","PSDB / PTB / PP / PR / DEM / SOLIDARIEDADE / PPS / PRB / PSD"
"2018","1","BR","BR","1","COLIGACAO","11","PP","PSDB / PTB / PP / PR / DEM / SOLIDARIEDADE / PPS / PRB / PSD"
"2018","1","BR","BR","1","COLIGACAO","12","PDT","PDT / AVANTE"
"2018","1","BR","BR","1","COLIGACAO","13","PT","PT / PC do B / PROS"
"2018","1","BR","BR","1","COLIGACAO","14","PTB","PSDB / PTB / PP / PR / DEM / SOLIDARIEDADE / PPS / PRB / PSD"
"2018","1","BR","BR","1","COLIGACAO","15","MDB","MDB / PHS"
"2018","1","BR","BR","1","PARTIDO ISOLADO","16","PSTU","PSTU"
"2018","1","BR","BR","1","COLIGACAO","17","PSL","PSL / PRTB"
"2018","1","BR","BR","1","COLIGACAO","18","REDE","REDE / PV"
"2018","1","BR","BR","1","COLIGACAO","19","PODE","PODE / PRP / PSC / PTC"
"2018","1","BR","BR","1","COLIGACAO","20","PSC","PODE / PRP / PSC / PTC"
"2018","1","BR","BR","1","COLIGACAO","21","PCB","PSOL / PCB"
"2018","1","BR","BR","1","COLIGACAO","22","PR","PSDB / PTB / PP / PR / DEM / SOLIDARIEDADE / PPS / PRB / PSD"
"2018","1","BR","BR","1","COLIGACAO","23","PPS","PSDB / PTB / PP / PR / DEM / SOLIDARIEDADE / PPS / PRB / PSD"
"2018","1","BR","BR","1","COLIGACAO","25","DEM","PSDB / PTB / PP / PR / DEM / SOLIDARIEDADE / PPS / PRB / PSD"
"2018","1","BR","BR","1","PARTIDO ISOLADO","27","DC","DC"
"2018","1","BR","BR","1","COLIGACAO","28","PRTB","PSL / PRTB"
"2018","1","BR","BR","1","PARTIDO ISOLADO","30","NOVO","NOVO"
"2018","1","BR","BR","1","COLIGACAO","31","PHS","MDB / PHS"
"2018","1","BR","BR","1","COLIGACAO","36","PTC","PODE / PRP / PSC / PTC"
"2018","1","BR","BR","1","COLIGACAO","43","PV","REDE / PV"
"2018","1","BR","BR","1","COLIGACAO","44","PRP","PODE / PRP / PSC / PTC"
"2018","1","BR","BR","1","COLIGACAO","45","PSDB","PSDB / PTB / PP / PR / DEM / SOLIDARIEDADE / PPS / PRB / PSD"
"2018","1","BR","BR","1","COLIGACAO","50","PSOL","PSOL / PCB"
"2018","1","BR","BR","1","PARTIDO ISOLADO","51","PATRI","PATRI"
"2018","1","BR","BR","1","PARTIDO ISOLADO","54","PPL","PPL"
"2018","1","BR","BR","1","COLIGACAO","55","PSD","PSDB / PTB / PP / PR / DEM / SOLIDARIEDADE / PPS / PRB / PSD"
"2018","1","BR","BR","1","COLIGACAO","65","PC do B","PT / PC do B / PROS"
"2018","1","BR","BR","1","COLIGACAO","70","AVANTE","PDT / AVANTE"
"2018","1","BR","BR","1","COLIGACAO","77","SOLIDARIEDADE","PSDB / PTB / PP / PR / DEM / SOLIDARIEDADE / PPS / PRB / PSD"
"2018","1","BR","BR","1","COLIGACAO","90","PROS","PT / PC do B / PROS"
```

Caso haja algum problema na consulta, é possível checar o status da consulta no [Passo 2: Esperando o resultado](03_Espera.md).
