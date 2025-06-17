---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-09
título_alternativo:
---
Temos dois tipos de conceitos de segurança. Safety in Transport e Safety at Rest. 
- **Segurança em transporte**
	Em uma aplicação web, temos o HTTPS.
	Importante saber emitir certificados, saber quando vão vencer.
- **Segurança em repouso**
	- **Criptografar** disco, banco de dados, back-ups.
	- **Anonimização** é uma forma de não guardar dados que se possa descobrir alguma informação como número de cartão de crédito, endereço e dados pessoais de algum cliente.
### Autenticação
Cada requisição deve informar quem é o cliente. A partir da informação a aplicação pode decidir se a operação será realizada ou não. 
#### Basic Authorization HTTP
Em todas as requisições enviar o usuário e senha no cabeçalho. Isso exige que o cliente armazene o usuário e senha. Isso gera insegurança.
#### Chave Única / Token 
Uma chave é gerada uma única vez e o cliente armazena essa chave. Toda vez que for feita uma requisição essa chave é repassada.
#### Token JWT
Um token é gerado quando o cliente passa um usuário e senha e esse token é utilizado para fazer as requisições enquanto a sessão durar. Se perder o token, sem problemas, só enviar usuário e senha que gera o token novamente.
#### OAuth
Se utiliza certificados e fala com serviços de terceiros. Aprovar o usuário e senha é de responsabilidade de um terceiro. Delega a responsabilidade de alguém maior. 
#### OpenID Connect
Parecida com o OAuth em que se cria um certificado e se delega para outra entidade guardar e validar o usuário e senha.
### Autorização
Limitar certas funcionalidades no sistema. É o que pode fazer dentro de um sistema. Algumas técnicas podem ser utilizadas.
#### ACL - Access control list
Todos que estiverem dentro de uma lista podem fazer determinada coisa. Pode-se ter uma lista para cada funcionalidade ou uma lista que dá acesso global.
#### RBAC (Role-based access control)
Controle de acesso com base em papéis. Eu sou um aluno e professor. Com base no papel que eu eu tenha no sistema eu posso ter determinadas funções. Se eu tiver o papel de instrutor eu tenho acesso a determinada função. Se tiver papel de aluno, tenho acesso a outras funcionalidades.
#### On behalf of
É quando se chama um sub-serviço mas você diz quem é o usuário que está acessando a informação. É como se estivesse chamado o serviço em nome de uma outra pessoa. 
### Segurança via rede
Para garantir que nenhum outro serviço acesse um conjunto de microserviços é possível restringir via rede.
Se cria uma rede virtual em que só os microserviços são acessíveis entre si. Para acessar o mundo externo se coloca um [[API Gateway]]] com regras de firewall e para um eventual sistema de administração mais restrito se permite o acesso via uma lista de IPs permitidos que podem inclusive serem acessados via uma VPN.

![[Pasted image 20240908163641.png]]
### Defense in depth
Todo sistema está propenso a ataque. Precisa se incluir vários pontos de defesa. Precisa de redundância.

Por exemplo: 
- Rede separada
- Liberar só para o API Gateway
- Ter um firewall
- Ter autenticação
- Ter autorização

Deve-se colocar na balança, porque pode ter uma redução de performance. Então, colocar segurança em dados públicos, talvez não tenha sentido. Defesa em profundidade é colocar camada acima de camada. 
\
Dicas:
- Estude ataques que os hackers fazem. 
- Tenha uma equipe de infosec e execute pentestes. 
- Testes de segurança com certificados inválidos, usuários não autorizados. 
- Monitore e detecte ataques em tempo real. 
- Tenha log e audite os sistemas com frequência. 
# Fonte
