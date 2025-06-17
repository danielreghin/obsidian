---
tags:
  - tecnologia/arquitetura
revisões: 0
criado: 2024-07-12
título_inglês: 
ano_publicação: 2020
autor: Gartner
qtd_páginas: 
ISBN:
---
## 0 - Síntese

O estudo sugere 6 técnicas e processos para ajudar a tratar a documentar as decisões tomadas e reduzindo o risco de decisões ruins. Comenta que as decisões podem ser feitas pelo time, dado que o arquiteto nesse cenário não é um papel e sim quem toma as decisões.

As recomendações finais são:

- Registre sempre as decisões arquiteturais
- Gaste o tempo do arquiteto com sabedoria
- Faça experimentos controlados para gerar dados
- Use dados de negócio/econômicos para direcionar decisões
- Direcione o investimento à mitigação de riscos com base em dados
- Faça estimativas rápidas para colaborar nas decisões

## 1 - Resumo


As decisões arquiteturais são feitas no início do projeto e com dados limitados. Elas por outro lado impactam consideravelmente na estrutura e no futuro do sistema.

As decisões variam de:

- Estrutura (Interconexão, bases de dados)
- Plataforma de uso (linguagem, Make or buy)
- Codificação (Estilo, API, Eventos)

O estudo sugere 6 técnicas e processos para ajudar a tratar a documentar as decisões tomadas e reduzindo o risco de decisões ruins.

### Técnica 1 - Criar um ADR - Architecture Decision Record

As pessoas não lembram quem tomou a decisões, porque e em qual cenário e escopo. Não deve ser um documento vivo e sim um registro da tomada de decisão do passado.

Estrutura do documento:

- Título: O nome da decisão
- Status: Proposto, Aceito, Rejeitado, Descontinuado, Substituído
- Contexto: Necessidade que gerou essa decisão e que domínios as decisões se aplicam
- Decisão: A decisão que está sendo proposta
- Participantes: Quem estava envolvido
- Consequências: O que ficou mais fácil ou difícil de se fazer com base na decisão

Deixe o documento pequeno, com frases simples e objetivas. Evitar mais do que duas páginas. Só atualize o status. Não trate como documento restrito. Não crie processos em volta desse documento. Crie uma numeração sequencial: ADR-1, ADR-2 e assim por diante.

### Técnica 2 - Priorizar decisões usando “tipificação de decisão”

Os arquitetos não tem tempo suficiente para fazer uma análise detalhada. Técnica baseada em Jeff Bezos, Carta de 2015.  

Se tipifica a decisão em dois tipos.

- Tipo 1: Afeta grande parte do sistema e mudá-la é difícil. Precisa de mais atenção e por isso deve ser de responsabilidade do time de arquitetos
    
    - Make or Buy
    - Qual linguagem usar
- Tipo 2: Afeta poucas áreas do sistema e deve ser feita por pessoas com grande quantidade de contexto e das consequências da decisão. Pode ser feita pelo time de desenvolvedores usando os guias da arquitetura corporativa.
    
    - Qual algoritmo utilizar
    - Tecnologia a ser utilizada para a criação de um serviço (evento, api e etc)

Se tiver dificuldade em identificar, assuma que é do tipo 1. Pode-se usar um Spike de arquitetura para gerar informação suficiente, o problema é que a decisão é atrasada.

O problema dessa solução é descentralizar decisões importantes. Ou tratar todas as decisões como importantes e do tipo 1.

### Técnica 3 - Gerar informação arquitetural rápida com Spikes de arquitetura

Nem sempre se tem informações suficientes para tomar uma decisão arquitetural. Uma spike explora soluções potenciais. Pode-se instalar, usar e experimentar uma solução, ler documentação, criar código para explorar o problema.

A técnica:

- Defina um critério de aceite e falha
- Defina um período de tempo para o estudo
- Documente e compartilhe os resultados
- Jogue fora qualquer código produzido durante o período

Os riscos dessa técnica é que o que foi feito em um período curto de tempo não funciona em um sistema real. Ficar fixado em uma solução feita durante a Spike e não abrir os olhos para outros caminhos durante a implementação.

### Técnica 4 - Quantificar os “trade-offs” usando um framework financeiro

As decisões arquiteturais são feitas com base em tecnologia e decisões de negócio que podem gerar gastos ou economia para a companhia. Ao priorizar um deles,  o outro pode ser prejudicado, por exemplo, usar uma nova tecnologia pode gerar custos elevados.

Essa técnica traz a luz os impactos no negócio com base nas decisões tomadas. Se usa da seguinte forma:

- Valor gerado: Qual valor (capacidade) se traz para o negócio e cliente
    
    - Alguém irá comprar?
    - Quando se ganhará adicionalmente ao implantá-la.
- Tempo de Entrega: Quando tempo se demorará para desenhar, construir e entregar
    
    - Qual é o custo de se atrasar a entrega?
    - Existe alguma data limite, ex: encerramento de ano?
- Risco: Qual a chance dessa capacidade não ser entregue conforme esperado. Qual é o risco de não se entregar a solução para o negócio? Há algum impacto financeiro?
- Custo de operação: Quanto se custará para implantar e operar (pessoas, hardware)
- Custo de desenvolvimento: Quando se custará para implementar (mão de obra, materiais e etc)

Ao se pensar nisso, fica fácil explanar para executivos uma decisão técnica. O risco da técnica é inflar as estimativas tanto de prazo quando de custos e por isso tomar decisões erradas. Pode-se superestimar os riscos envolvidos.

### Técnica 5 - Priorizar riscos usando FMEA

Ao se implantar um sistema é pensado em falhas possíveis de produção. Como não se tem tempo de pensar em todas elas, é necessário se concentrar nas falhas ou riscos operacionais mais importantes.

A técnica, Análise de Tipo e Efeito de Falha, “Failure Mode and Effects Analysis (FMEA)” foi primeiro usado militarmente em 1940 pelos EUA e depois adotada pela NASA e outras organizações. “Failure Mode” são as causas ou formas que um sistema pode falhar. “Effect Analysis” é o processo de analisar o impacto a sua probabilidade e a dificuldade de capturá-lo.

A técnica consiste em:

1. Para cada parte do sistema questionar: O que pode dar errado por aqui?  
    
    O resultado é o “Failure Mode”
    
2. Para cada um desses “Failure Mode”, avaliar
    
    - Efeito: Qual impacto se o erro acontecer?
    - Gravidade: Qual o nível de gravidade de 1 a 10 (10 pior)
    - Probabilidade: Qual a probabilidade de acontecer de 1 a 10 (10 mais provável)
    - Dificuldade de detectar: Qualifique se é difícil a detecção de 1 a 10 (10 mais difícil)

Baseado nessa tabela, calcular o prioridade do risco (RPN - Risk Priority Number) multiplicando os três últimos números.

Se pode utilizar essa técnica para priorizar os testes da aplicação. Os riscos de se usar essa técnica é de não ter clareza dos riscos que podem acontecer, dar baixa probabilidade e entender que nunca acontecerão ou usar a lista inicial como a definitiva e não atualizá-la ao longo do tempo.

### Técnica 6 - Estimar rapidamente usando estimativa Fermi

Geralmente não se tem informações detalhadas para se fazer uma estimativa acurada. Para o início do projeto não se precisa fazer uma estimativa precisa, o importante é estimar rapidamente usando dados brutos e se fazer uma aproximação.

Como fazer:

- Detalhar o problema
    
    - 1TB será suficiente para uma semana de arquivos de log?
- Quebrar em pequenas partes
    
    - Quantas partes do sistemas emitirão logs? Qual frequência? Qual tamanho do arquivo de log ?
- Estimar cada uma das pequenas partes
- Multiplicar cada uma delas

Se tiver tempo para estimar com mais detalhes, o faça, se não vai assim mesmo.  Sugerido validar as premissas com outras pessoas para tirar os vieses.

