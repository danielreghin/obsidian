---
tags: 
revisões: -1
criado: ""
título_alternativo: O aplicativo com doze fatores
---
São pré-requisitos para se construa sistemas como serviço que: automatizem a configuração inicial, portabilidade para diversos ambientes, implantação em nuvem, minimizem a divergência entre desenvolvimento e produção e escalem sem mudanças siginificativas:

São eles:
1) Base de Código
	Um código sendo controlado por uma ferramenta de gestão de código como GIT e o mesmo código é utilizado para deploys em ambientes diferentes.
2) Dependências
	Isolar as dependências e controlar por uma ferramenta como por exemplo: pub.dev (Yaml), Gradle, Maven e etc.
3) Configurações
	As configurações para um determinado ambiente é armazenado em um local fácil de ser modificado e que seja centralizado. Por exemplo em um docker composer em que as filas são declaras, a string de conexão, usuário e senha com banco de dados também é descrito. O código não precisa ser alterado.
4) Serviços de Apoio
	Trocar serviços sem esforço ou através de configuração. Um serviço de apoio pode ser um banco de dados, um gerenciador de fila, um servidor SMTP. 
	Um banco de dados poderia ser trocado com apenas uma configuração. Postgree por mysql, bastaria trocar uma string de conexão para que isso fosse feito. Um provedor de nuvem GCP para Azure também é um cenário.
5) Construa, lance, execute
	Processo de build, release e deploy de uma aplicação de forma automatizada e com a separação desses estágios
6) Processos
	A aplicação é separada por processos diferentes. Se tem um processo para executar uma atividade e outro para executar outra atividade. Os processos não armazenam estado e são independentes de forma que se poderia trocá-los, sem problemas.
7) Vínculo de portas
	Exposição de serviços via portas. Na prática se exporta um serviço através de uma URL e porta e quem chama esse serviço não se preocupa com isso. 
8) Concorrência
	Aumentar a disponibilidade do serviço através de código (infra as code) ou através de algum serviço de cloud, em que se aumenta máquinas, memória ou outra forma para dar mais disponibilidade ao serviço.
9) Descartabilidade
	Os serviços poderiam subir ou cair a qualquer momento sem que haja problemas de consistências. O código deve estar resiliente a falhas, por exemplo, terminando o estado de cada um deles. 
10) Paridade de desenvolvimento e produção
	Manter o desenvolvimento, homologação e produção o mais similar possível.  Com códigos e ferramentas com versões mais próximas possíveis. 
11) Logs
	Tratar os logs como fluxo de eventos. Dessa forma, um aplicativo não se preocupa com o roteamento, onde será gravado e outros problemas. Para cada ambiente, o log pode ser gravado em lugares distintos.
12) Processos administrativos
	Criar processos que podem ser usados para administrar o sistema de forma periódica como: Migrar base de dados, inspecionar bases de dados, executar scripts para processos específicos e outros.
# Fonte
https://12factor.net/pt_br/