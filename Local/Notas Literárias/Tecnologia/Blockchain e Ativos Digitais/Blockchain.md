---
tags:
  - tecnologia/blockchain
revisões: 0
criado: 2024-10-23
título_alternativo:
---
É uma infraestrutura de registros digitais com carimbo data/hora, imutável e que possui blocos de informações atrelados e criptografados. Portanto é uma rede capaz de compartilhar valores. Ficou popularizada com o [[Bitcoin]] em 2008.

As cinco principais características da blockchain são:
- Descentralização: É mantida por nós que validam e registram uma transação.
- Imutabilidade: Uma vez que uma transação seja adicionada, ela não pode ser modificada.
- Transparência: Todas as transações são registradas em um livro-razão (ledger) público, acessível a todos participantes.
- Segurança: Usa criptografia para que apenas pessoas autorizadas possam acessar as transações.
- Consenso: Usa mecanismos como [[POW - Proof of Work]] e [[POS - Proof of Stake]] para garantir que todos concordem com o estado atual da rede. 
## História
Ela foi criada em 1991 por Stuart Haber e W. Scott Stornetta em 1991 para armazenar documentos digitais de uma forma que não pudesse ser modificada. A motivação foi oriunda de um artigo de biologia que foi modificado gerando uma fraude.  A primeira implantação bem sucedida da blockchain foi o [[Bitcoin]].
## Padronização
Existem alguns consórcios criados para estabelecer padronização e pesquisa dentro da blockchain, como a [[Hyperledger]]
## Como funciona
Ela é uma máquina de estados, que a cada transação, se faz uma proposta de alteração daquele estado. Exercício feito pelo site: [Demo da blockchain](https://andersbrownworth.com/blockchain/)
### Geração do hash
É uma função determinística. Dado uma entrada, você tem sempre o mesmo retorno, a mesma saída, com isso, você consegue validar a autenticidade de uma informação. 

![[Pasted image 20241029100720.png]]
### Bloco e Mineração
Um bloco é um conjunto de transações que podem modificar o estado da blockchain. Uma vez que o bloco foi validado (Minerado), se entende que é uma transação válida. 

No exemplo abaixo, um bloco é entendido como minerado uma vez que o hash gerado começa com 4 zeros. Para fazer isso, o código de mineração modifica o número nonce até que o número nonce identificado faz com que os primeiros 4 zeros apareçam no hash.

![[Pasted image 20241029101310.png]]

### Encadeamento de blocos

Os blocos são encadeados e se tornam válidos a partir do momento que são minerados
![[Pasted image 20241029164925.png]]

# Fonte
Treinamento Alura de Smart contracts
Livro: What Is Blockchain?

https://www.ufsm.br/pet/sistemas-de-informacao/2021/11/29/contextualizacao-e-introducao-ao-blockchain
