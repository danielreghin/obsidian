---
tags:
  - tecnologia/metodologia
revisões: 1
criado: 2024-09-25
título_alternativo:
---
É uma metodologia de desenvolvimento, com um conjunto de valores, princípios e práticas que tornam o processo de desenvolvimento mais efetivo e eficaz. Pode ser aderido por equipes de qualquer tamanho.Possui 5 valores, alguns princípios (14) e várias práticas (7).
	**Valores**
		Comunicação, Simplicidade, Feedback, Coragem, Respeito
	 **Princípios**
		Humanidade, Economia, Benefício mútuo, Auto semelhança, Melhoria, Diversidade, Reflexão, Fluxo, Oportunidade, Redundância, Falha, Qualidade, Passos pequenos, Aceitação
	 **Práticas**
		**Gestão:** Cliente presente, time coeso, ritmo sustentável, posse coletiva
		**Projeto:** Metáfora de sistema, Projeto simples
		**Planejamento:** Jogo do planejamento, Histórias de usuário, Testes de aceitação, Pequenas entregas, Spikes de planejamento
		**Codificação:** Padrão de condificação, TDD, Integração contínua, Reunião diária em pé. Programação em par, Refatoração

![[Pasted image 20241003100224.png]]

Como é uma metodologia ágil, o manifesto ágil é também aqui aplicada. Mas, como uma metodologia não quer organizar tarefas, fazer reuniões e quanto tempo leva uma iteração, portanto é comum unir o XP com outras metodologias ágeis. 
## Práticas de planejamento de trabalho
Para se decidir o que precisa ser feito, se utiliza de [[Historias de usuário]]. 
Em seguida se reúnem em uma agenda chamada de [[Jogo do planejamento]] para definir o grupo de itens que será desenvolvido e o quanto cabe no período delimitado, pode-se usar a técnica de [[Planning Poker]] para isso.

Se houver dificuldade para se estimar um trabalho, se pode utilizar de [[Spikes de planejamento]] para realizar uma POC. 

O ideal é se entregar software mais rápido possíveis e para isso se criar entregas pequenas. Para isso [[Testes de aceitação]] automatizados são importantes, o [[BDD - Behavior-Driven Development]] preza por isso. 
## Práticas de codificação
### Padrões de codificação
Manter um padrão de codificação do começo ao fim do código. Ou seja, o padrão deve ser definido no início e seguido por todos e acordados por todos no início do projeto. Se não tiver um padrão defina no início do projeto.
### Teste antes
Faça testes antes através do [[TDD - Test-Driven Development]]. 
### Integração contínua
É uma prática em que o código é desenvolvido, integrado, versionado muitas vezes ao longo do dia. A [[CI - Integração Contínua]] pode ser complementado com [[CD - Continuous Delivery]]. É uma boa prática que o desenvolvimento seja pequeno.
### Refatoração
Sempre deixe o código mais limpo do que quando você o encontrou. Também pode ser chamado de refinamento incremental, nomenclatura que veio do programação orientada a objetos. Sem refatorar, pode-se gerar uma alta [[Dívida técnica]]. 
### Reunião diária em pé
Não adianta ter um bom desenvolvimento se não sabe fazer uma boa comunicação. Por isso, se usa a [[Daily stand up meeting]].
### Programação em pares (piloto e copiloto)
É indicado que o [[Programação em par]] seja feito em códigos que vão para produção. Não é uma mentoria, os dois são responsáveis pelo código.  O ambiente deve ser ergonômico.
## Papéis existentes no XP
O objetivo e extrair o melhor das pessoas.  Um a pessoa pode fazer mais de um papel. Menos que aja conflitos de interesses.
- Desenvolvedor
- Cliente (PO)
- Coach (SM)
- Testador: Extrair os critérios para a aplicação ser testada
- Cleaner: Vai extrair do time as melhores práticas de desenvolvimento
- Tracker: Vê o que deu certo e errado e extrai métricas
- Gerente: Facilita a comunicação entre clientes e equipe
- Existem muitos, como redatores técnicos e outros.
## Valores
Comunicação
	A comunicação presencial é a mais eficaz. Quanto maior a capacidade de compreensão, maiores as chances de tirar ambiguidade e entendimento equivocado.
Simplicidade
	Muitos times estão acostumados com a futurologia. Além de fazer uma coisa, faz também outra, achando que o cliente vai querer. Manter tudo muito simples e sem complicar, principalmente no código. 
Feedback
	Mudar requisitos são bem vindas., mesmo tardiamente no projeto. Quanto mais cedo, melhor e Quanto mais constante, melhor.
Coragem
	As práticas devem dar segurança para que as pessoas tenham coragem para realizar as melhorias no sistema. Após uma crítica, por exemplo. Qualquer pessoa pode alterar códigos dos outros. Coragem para admitir um erro.
Respeito
	Aqueles que se sentem respeitadas se sentem mais valorizadas. Deve-se respeitar cada personalidade, respeitar o cliente, o líder e assim, todos sejam cordiais. 
## Gestão e projeto
Cliente presente
	O cliente precisa estar presente para que se saiba o que precisa ser desenvolvido. Uma especificação completa não é tão efetiva que estar com o cliente esteja presente mais perto do time do desenvolvimento. Tendo coragem para criticar se o cliente fizer sugestões que não fazem sentido. 

Time coeso
	O time precisa estar coeso. A responsabilidade é do time e não de um desenvolvedor. ou seja, o time erra e não o fulano ou ciclano. O time deve ter todas as competências necessárias para executar as tarefas. Esse time tem comunicação, buscam a simplicidade, tem confiança para ter coragem e gerar feedback, por meio do respeito mútuo. É um time auto organizável, fisicamente próximo, buscam melhoria contínua. 

Posse coletiva
	O time têm posse coletiva. Todos são donos do código e de toda parte do código. Encoraja a todos evoluírem o projeto, como build, teste, código e requisitos. 

Ritmo sustentável
	Deve-se ter um ritmo sustentável, constante para que a longo prazo não seja prejudicial. 

Uso de metáforas
	O uso de metáforas pode ajudar na comunicação entre equipes técnicas e não técnicas. Arquivo no computador é uma metáfora para se compreender como algo é guardado no computador. Carrinho de compra é outras metáfora. Uma classe chamada de carrinho pode ajudar. O DDD pode ajudar a modelar os domínios que facilitem a comunicação. 

Simples
	Fazer projetos simples para não desenvolver algo que não vai ser utilizado. O conceito de MVP pode ser utilizado nesse caso. Valor entrega mínima que seja viável para agregar valor. 

## Falha de projetos que motivaram o XP
O XP vêm resolver alguns dos motivos para os projetos falharem:
- Cliente distante
	Está com dúvidas e o PO, cliente não está disponível para resolver.
- Cereja do bolo
	Você quer adicionar alguma funcionalidade no final do projeto e quer pode gerar problemas inesperados.
- Testes no final
	Tá pronto só falta testar. Desenvolvimento e testes devem caminhar juntos. é anti-ético só testar no final.
- Trabalho empurrado
	Fechar um contrato e o sistema deve estar pronto já na próxima semana. Desenvolver a toque de caixa sem planejamento. 
- Dividas técnicas
	Se o sistema é legado, antigo, pode fazer de qualquer jeito. Vai aumentando as dividas técnicas consideravelmente.
# Fonte
Kent Beck, Ron Jeffries, Ward Cunningham e Martin Fowler
Cursos Alura: Extreme Programming: metodologia de desenvolvimento ágil de software