---
tags:
  - tecnologia/devops
revisões: 0
criado: 2024-07-17
título_inglês: Implantação Canário
---
É uma forma de implantação de sistemas em que a nova versão da aplicação é implantada para um grupo reduzido de clientes. Algumas estratégias de entrega podem ser usada:
- Percentual de clientes
- Localização geográfica

Pode se usar algum tipo de validação automatizada do sucesso. O uso de chaveamento de funcionalidade também pode ser usada ([[Feature Toggle|Feature Toggle]]).


![[Pasted image 20240717094804.png]]

A nova versão é validada em ambiente de produção e caso hajam problemas o *Rollback* é facilmente feito. 
# Fonte
https://cloud.google.com/deploy/docs/deployment-strategies/canary?hl=pt-br
https://martinfowler.com/bliki/CanaryRelease.html
