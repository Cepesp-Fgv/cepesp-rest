# CEPESP//REST
## Solicitando uma Consulta (Primeiros passos)

A nova API-Rest foi remodelada de forma atender as consultas de forma assíncrona. Antes, todo o processo de leitura, processamento e disponibilização dos dados acontecia no tempo de uma única consulta. Para garantir uma melhor resposta, menor latência e menor desgaste do servidor separamos o processo de solicitar uma consulta em três:
1. Solicitação
2. Espera
3. Resultado

### 1. Solicitação
Nesta fase, é feita uma requisição HTTP com todos os parâmetros necessários para a dada base de dados a ser acessada. 
O servidor responderá instantaneamente com um `id` identificação. 
Guarde essa identificação, ela será utilizada para checar o *status* da consulta e posteriormente para visualizar o resultado.

[Clique aqui](02_SolicitandoConsulta.md) para saber mais.

### 2. Espera
Agora que você já possui a indentificação da consulta.
O cliente efeturará uma nova requisição http passando o `id` recebido e o servidor retornará informado o *status* da consulta.
O _status_ pode ser `QUEUED`, `RUNNING`, `SUCCEEDED` ou `FAILED`. 
Quando o cliente receber os *status* `QUEUED` e `RUNNING` deverá esperar alguns segundos para consultar novamente.
Se o cliente receber o *status* `FAILED`, receberá também a causa do erro.
Se o cliente receber o *status* `SUCCEEDED`, quer dizer que a consulta foi bem sucessidida e ele pode processeguir para o terceiro passo.

[Clique aqui](03_Espera.md) para saber mais.

### 3. Resultado
Após a consulta ter sido processada. O cliente poderá realizar uma terceira requisição passando o `id` e aí então o servidor retornará de imediato o resultado da consulta.

[Clique aqui](04_Resultado.md) para saber mais.
