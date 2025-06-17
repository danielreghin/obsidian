---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-09
título_alternativo:
---
Importante que os microserviços tenham um mesmo padrão de logs (ex: texto, separado por vírgula, padronização os status). 

Uma saída é ter uma implementação de um [[Sidecar Pattern]] para padronizar esse modelo.  O [[The Twelve-Factor App]] também diz que logs devem ser Stream de dados. 

E todos os logs devem ser ser armazenados em um lugar agregado.

Como há muita complexidade nos microserviços é importante poder rastrear o log e reconstruindo toda a operação através de um identificado, análogo à um call stack de uma aplicação. Ideal usar o padrão trace ID para gerar o log. Existem padrões de trace ID para gerar o melhor modelo.

Usar ferramentas de APM para visualizar as pilhas de logs.

# Fonte
