---
tags:
  - tecnologia/devops
revisões: 0
criado: 2024-09-11
título_alternativo: SRE - Engenharia de Confiabilidade de Sites
---
Disciplina da engenharia de software para aumentar a confiabilidade do software através do gerenciamento de sistemas, solução de problemas e automação de tarefas. Isso traz resiliência, escalabilidade e confiabilidade para a solução. O uso de ferramentas de monitoramento e visibilidade aliada a uma cultura forma de automação trazer a confiabilidade necessária. O problema de confiabilidade pode ser percebido por diferentes equipes como as equipes de desenvolvimento e equipe de operações. 

Para que o profissional de SRE atinja o seu objetivo ele deve pensar e agir via métricas de dados para: :
- Entender o comportamento de atualizações e versões em um ambiente
	A nova versão é mais performática? Ela adicionou mais erros ao ambiente?
- Entender e propor arquiteturas redundantes e escaláveis
	O Cloud provider é adequado para determinada solução? Tem ferramentas  de monitoramento e contingência?
- Entender a experiência do usuário com base em uma nova versão de sistema
	Usuários estão acessando mais? Está mais performático? Quais funcionalidades mais acessadas? Qual tempo de resposta? Se a aplicação fica fora do ar, o usuário é o primeiro a saber do problema?

Existem também os [[4 Golden Signals]] que são latência, tráfego, erros e saturação. 

Uma outra prática é usar a [[Chaos Engineering]] para periodicamente validar como o ambiente se comporta em uma queda inesperada.

# Fonte
https://cursos.alura.com.br/extra/alura-mais/sre-engenharia-de-confiabilidade-de-sites-c1112