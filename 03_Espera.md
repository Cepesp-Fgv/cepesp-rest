# [Passo 2] A Espera
Como explicado nos [Primeiros Passos](01_PrimeirosPassos.md), nesta fase o cliente deverá solicitar o status da consulta até que ela esteja pronta e ele possa prosseguir para o terceiro passo.
O servidor retornará 4 tipos de _status_ diferentes:

- `QUEUED` | _Quando a consulta foi enviada para a fila de processamento e aguarda ser escolhida para processar._
- `RUNNING` | _Quando a consulta foi escolhida e está em processamento._
- `FAILED` | _A consulta falhou._
- `SUCCEEDED` | _A consulta está pronta._

Para solicitar o status o cliente deve acessar:

[GET] `cepesp.io/api/consulta/athena/status?id=<ID>`

No lugar de \<ID\> deve ser passado o id recebido no passo anterior. O servidor deverá responder a requisição HTTP com um status 200 e o seguinte _payload_:

```js
{
   "message":null,
   "status":"SUCCEEDED"
}
```
Quando status retornado é `FAILED`, no campo `message` será retornado a causa do erro.

## Importante
Vale ressaltar que o cliente deve esperar um tempo crescente entre uma solicitação e outra. 
Recomendamos executar a solicitação uma primeira vez e se ela retornar `QUEUED` ou `RUNNING` ele deverá esperar em torno de 16 segundos (o tempo médio de processamento atual) para efetuar a proxima checagem de _status_. 
Se a consulta voltar a retornar `QUEUED` ou `RUNNING` o cliente deverá esperar o dobro do tempo e assim por diante.
Uma vez que o servidor responder com _status_ `SUCCEEDED`, quer dizer que ele já pode processeguir para o terceiro passo.

[Clique aqui para ir para o **Último Passo**](04_Resultado.md)
