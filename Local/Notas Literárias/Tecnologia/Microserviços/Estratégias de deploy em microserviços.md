---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-09
título_alternativo:
---
Se crie uma pipeline de release para poder automatizar e agilizar a entrega em produção. Se crie um build automatizado, testes automatizados e etc.

Podemos ter os seguintes ambientes:
- Desenvolvimento
- Staging/QA 
	- Testes de performance
	- Smoke Tests para garantir o fluxo principal
- Homologação
- Produção
	- Por cliente
	- Por região

Podemos ter configurações para cada um dos ambientes, quantidade de recursos, localização, destino do log, dados de acesso e etc.

Estudar como parametrizar uma aplicação para cada um dos ambientes dentro de uma linguagem de programação.

Algumas estratégias de deploy podem ser: 
- Gerar um arquivo distribuível (.exe, .war e etc)
- Tag no git
- Imagem de container. 

Cada microserviço tenha que ser gerada independente em um monorepo, por exemplo.

Algumas estratégias são:
- Rolling upgrade
	Uma atualização sem nenhum downtime. Você pode ter um loadbalance que vai derrubando os servidores e atualizando. As versões devem ser compatíveis.  
- [[Blue Green Deployment]]
	Se cria dois grupos de servidores um com uma versão mais nova e outra com a antiga. E ao longo do tempo se vai direcionando o trafego para a nova. Se a nova não tiver OK se volta para a antiga.
- Feature Toggle
	Se cria um chaveamento dentro da aplicação para ligar ou desligar uma determinada funcionalidade. Isso pode ser ativado ou desativado para um grupo pequeno e ir aumentando ao longo do tempo.
# Fonte
