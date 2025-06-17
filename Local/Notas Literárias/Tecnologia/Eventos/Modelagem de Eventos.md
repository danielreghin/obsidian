---
tags:
  - tecnologia/arquitetura
revisões: 0
criado: 2024-08-16
título_inglês: Event Modelling
---
É um método que descreve os sistemas usando fluxo de informações e como as informações são modificadas ao longo do tempo. 

Algumas fases:
- Brainstorming
	Traz os participantes e descrevem os eventos que vem a mente. Somente deve-se ter eventos que alteram o estado da aplicação.
	Exemplo: Em uma reserva de hotel, olhar a disponibilidade do hotel, não altera o status e portanto, não entra como um evento.
	Ao final se tem uma pilha de eventos não organizada.	
	![[Pasted image 20240816083741.png]]
	
- Ordenação lógica (the plot)
	Organizar os eventos em uma linha do tempo. 
	Exemplo: Se registrou, reservou, quarto ficou pronto, pagamento requisitado e pagamento com sucesso. 
	![[Pasted image 20240816083806.png]]
- Storyboard
	Criar interfaces / mockups / wireframes para os eventos. Pode-se identificar que um evento acontece em mais de uma tela
	![[Pasted image 20240816083839.png]]
- Identificação de entradas
	Se o hospede vai se registrar, e nos quadrados azuis, identificamos o que vai ser preciso para que o evento funcione.
	![[Pasted image 20240816083853.png]]

- Identificação de saídas
	Atualizar o que vai ser exibido no sistema. 
	![[Pasted image 20240816083345.png]]

- Lei de conway
	Quando uma empresa desenvolve o atualiza o sistema. Ou seja, vai seguir uma estrutura do sistema = estrutura da empresa. Vamos separar os eventos em raias e cada uma das raias pode ser um departamento da empresa ou equipes. 
	Ex: Parte de quarto está em raia diferente da parte de pagamentos.
	![[Pasted image 20240816083922.png]]

- Elaboração de cenários
	Vamos elaborar cada um dos cenários, se tem pré-condições e etc. 

A principal vantagens dessa modelagem, por mais que se complexa, a adição de novas histórias não afetam o que já foi criado. Se tem uma fácil visualização de como as coisas funcionam. Algumas pessoas não veem uma vantagem. 
# Fonte
https://cursos.alura.com.br/extra/alura-mais/modelagem-de-eventos-c1143
