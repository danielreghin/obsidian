---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-09
título_alternativo: Microservices
---
A implementação de uma [[Arquitetura de Microserviços]] deve ser feita com atenção. Veja se o microserviço implementa os [[The Twelve-Factor App]] em que melhores práticas são sugeridas.

![[Pasted image 20240906162639.png]]

## Tecnologias de microserviços
É possível expor microserviços através de algumas tecnologias como:

Exposição
- [[gRPC]]
- [[Restfull Services]]
- Procedure

Troca de dados
- JSON
- XML
- Binário
- Arquivo texto posicional
## Tipos de microserviços
É possível dividir os microserviços [[Tipos de microserviços]] específicos. Daí, é simples pensar em quais são as responsabilidades de cada um deles. 
## Modelagem de microserviços
A modelagem de microserviços é a estratégia de dividir um sistemas em partes suficientes menores que não tragam complexidade desnecessária. 

A quebra de um monolito em vários microserviços pode ser desafiador. Também iniciar a construção de um sistema já pensando que ele é tem uma grande quantidade de microserviços pode trazer uma complexidade desnecessária. 

Estratégias:
- [[Monolito primeiro]]
- [[DDD - Design de código orientado à domínio]] 
- Desenhar processos de negócio.

Algumas etapas e podem ajudar
- [[Etapas de modelagem de serviços de domínio]] 
- [[Etapas de modelagem de serviços de negócio]]
- [[Process Aggregator Pattern]]

Alguns padrões ajudam a fazer essas separações como o [[Strangler Pattern]] e o [[Sidecar Pattern]].
Para se modelar algumas preocupações são trazidas a tona:
- Quanto dados serão trafegados (muito, pouco)
- Latência
- Escalabilidade
- Interoperabilidade com outras linguagens
## Contratos
Quando um microserviço expor uma comunicação via API, isso se torna um contrato. O programador fica livre para modificar internamente, porém, o contrato sempre será o mesmo.

- Apenas faça modificações aditivas
	- Novos endpoints
	- Novos campos (opcionais) em cada recurso
- Versionamento de APIs
	- Ao lançar uma versão v2, a v1 deve continuar funcionando, inalterada.
- Manter equipes separadas, donas de cada serviço
	- Para adicionar funcionalidades, solicitações formais podem ser feitas.
- Deve-se evitar transformar todos os "substantivos" do sistema em microserviços. Isso gerará muito "data services" (veja [[Tipos de microserviços]]), anêmicos em geral, sem um ganho real. Além disso, terá que ser criado um outro microserviço para agregar todos esses dados

Veja [[Boas práticas de modelagem de APIs REST]].
## Infraestrutura
A infraestrutura a ser montada depende de diversos fatores, como segurança, resiliência, estratégia de comunicação entre outros.

É importante conhecer VPC para saber como o tráfego de rede entra em sua aplicação. Precisa saber o que são subnets públicas e privadas. se quer alta disponibilidade precisa saber como colocar em mais de uma região. Para fazer o chaveamento entre as regiões, saber o que é balanceamento de carga. Se tiver uma máquina virtual é necessário se preocupar com atualizações do SO. Precisa saber sobre TLS para ter tráfego seguro na rede, conhecer os Internet Gateway e firewalls com seus security groups ou grupos de segurança para acessar a sua rede  Para simplificar se pode usar [[Serverless]]. 
![[Pasted image 20240912082704.png]]
### Service Discovery (API Gateway - DNS - Load Balancer)
É interessante que os microserviços sejam protegidos de camadas externas, por segurança ou por conveniência. Uma forma de se fazer isso é colocando uma fachada através de um [[API Gateway]]

Os microserviços podem estar em uma única rede ou em redes separadas. Também, não se precisa registrar um domínio para cada microserviço ou saber o IP, até porque o mundo externo não precisa conhecer todos os microserviços, só a aplicação interna precisaria. 

Um estratégia é registrar um DNS, público ou privado. O próprio docker ou soluções parecidas conseguem referenciar um serviço através de um nome, isso é um DNS.  Uma cloud pública também tem serviços de DNS e proxys, que se pode, por exemplo, direcionar para um outro servidor caso um deles esteja fora do ar, como um Load Balancer. 
### Servidor
Ao implantar um microserviços deve-se cuidar muito bem como isso será feito a fim de facilitar a implementação e o deploy.
1) Uso de VM
	Uma opção é o uso de máquinas virtuais. Pode-se provisionar uma VM de forma automatizada como infra as code. O problema disso é que dificilmente conseguiremos implantar diversas VMs em uma única máquina. Então, será bastante custoso.

2) Uso de máquinas em nuvem.
	Outra opção são sistemas em nuvem. Também pode-se ter máquinas específicas para cada tipo de serviço. Se tem um ambiente de produção bastante robusto, mas é difícil e custoso ter máquinas em nuvem para ambiente dev.

3) Uso de containers
	A última opção é o uso de containers. Porque se consegue usar microserviços em ambiente local do desenvolvedor e ambientes de nuvem também tem gestão de containers com seus orquestradores. 
### Bancos de dados
Para banco de dados, podemos ter servidores separados ou compartilhados: [[Modelagem de banco de dados para microserviços]]
### Independência e ser autocontido
Um serviço pode ser independente através da criação de um docker, assim cada serviço terá aquilo que precisa para estar no ar, por exemplo, pode subir uma fila, um banco de dados e um servidor web. 
![[Pasted image 20240908171656.png]]
## Comunicação entre microserviços
Algumas dúvidas surgem e para elas não existem regras:
- Todo microserviço pode comunicar com outros microserviços?
- O Frontend pode comunicar com qualquer microserviço.

Os problemas de não se ter regras é o de ter dependências descontroladas, falhas em cascata e performance prejudicada. Ou seja, um serviço que chama um, que chama outro, que chama outro, se o último tiver problemas de performance, toda a aplicação será prejudicada, o mesmo acontece se houver um erro. 

A aplicação de modelo abaixo mostra, por exemplo, um EdgeService para cada tipo de cliente e os microserviços se comunicando via um EventBus.
Veja:
- [[Comunicação síncronas em microserviços]]
- [[Comunicações assíncronas em microserviços]]
## Segurança
O tema [[Segurança de microserviços]] é relevante ao passo que permite que se discuta e decida a melhor estratégia desse tipo de abordagem. 
## Instrumentação
Veja:
- [[Monitoramento com métricas em microserviços]].
- [[Logs em microserviços]]
## Implantação
Existem algumas [[Estratégias de deploy em microserviços]] que podem auxiliar no estudo de impalntação.
## Checklist
- Armazene o código em um repositório como o GIT
- Implemente um CI / CD
- Padronize o código fonte, com ou seu um gerador de código (scaffolding)
- Tenha logs padronizados
- Tenha monitoramento e métricas
- Implemente Health checks
- Mantenha configurações e senhas em locais específicos (Serviços de secrets na nuvem ou arquivos de texto)
- Crie templates de containers com imagens base.
- Utilize os [[The Twelve-Factor App]]
# Fontes
https://cursos.alura.com.br/extra/alura-mais/o-que-sao-microsservicos--c699
https://www.alura.com.br/artigos/rest-conceito-e-fundamentos
https://cursos.alura.com.br/course/microsservicos-padroes-projeto/task/90636
https://learn.microsoft.com/pt-br/dotnet/architecture/cloud-native/introduce-eshoponcontainers-reference-app
https://cursos.alura.com.br/course/fundamentos-microsservicos-aprofundando-conceitos/task/95006
https://cursos.alura.com.br/course/fundamentos-microsservicos-aprofundando-conceitos/task/95007
https://cursos.alura.com.br/course/fundamentos-microsservicos-aprofundando-conceitos/task/95008
https://cursos.alura.com.br/course/fundamentos-microsservicos-aprofundando-conceitos/task/95016