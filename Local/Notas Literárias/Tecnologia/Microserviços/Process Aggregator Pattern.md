---
tags:
  - tecnologia/microserviço
revisões: 0
criado: 2024-09-05
título_alternativo: Padrão de agregador de processos
---
São sistemas que agregam serviços de negócio que por sua vez agregam serviços de domínio. Pode e deve ter a lógica necessária para o processamento desse processo. 

Por exemplo: se você tem um processo de renovação de matrícula um aluno, você chamaria serviços de inclusão que traria uma resposta de boas vindas. Um agregador poderia retirar essa mensagem, submeter para outro serviço de fidelidade ou coisa do tipo. As mensagens claro que estariam no cliente e não no backend...mas é um exemplo.

A forma de se fazer isso é:
1. Definir um novo domínio ou sub-domínio
	Domínio renovação de matrícula, por exemplo.
1. Pensar no contrato da API
2. Desenvolver

# Fonte
https://cursos.alura.com.br/course/microsservicos-padroes-projeto/task/90632