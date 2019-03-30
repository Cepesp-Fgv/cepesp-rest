# Suporte à API Antiga

Ainda é possível efetuar consultas através da API Antiga. 

O lado bom é que o processo é mais simples e só é necessário uma consulta para solicitar, esperar e retornar o resultado. 
Com isso, o servidor fica responsável fazer internamente os passos descritos na nova API.

Uma única mudança necessária é adicionar um parâmetro `&ignore_version=true` para não receber uma mensagem de bloqueio utilizada nas APIs Python e R. (As correções devidas nos exemplos foram adicionadas)

Para solicitar utilizando a API antiga segue os passos e exemplos para cada base:
  - [Candidatos](Candidatos.md)
  - [Legendas](Legendas.md)
  - [Votos](EleicoesPorCargo.md)
  - [Consolidado](EleicoesPorCargo_BETA.md)
