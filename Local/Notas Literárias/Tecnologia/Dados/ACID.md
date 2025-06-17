---
tags:
  - tecnologia/dados
revisões: -1
criado: 
título_alternativo:
---
_ACID_ (atomicity, consistency, isolation, durability)
Quando um banco de dados suporta operações ACID, os seguintes atributos são atendidos:
- Atomicidade: Ou a operação é executada de forma completa ou ela não é executada, nem parte dela. (transação com vários sql em um banco relacional)
- Consistência: Os dados não podem ficar corrompidos. Se se tem 400 em uma conta, ele sempre estará lá. 
- Isolamento: Transações em paralelo não interferem uma entre as outras.
- Durabilidade: Os dados sempre estarão lá, mesmo em caso de falhas por longo período de tempo. 