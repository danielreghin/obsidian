[🇿](zotero://select/library/items/V8JJK49C)

Autor: [[People/ TOGAF]]  

# Conteúdo

# Capítulo 1 - Introdução

### 1.1 - Introdução ao TOGAF

Framework de arquitetura para auxiliar na aceitação, produção, uso e manutenção de arquiteturas. É um processo iterativo e modular. Pode, também, ser usado em conjunto com outros frameworks.

A chave para o TOGAF é desenvolver uma arquitetura corporativa que atenda às necessidades do negócio. Isso é feito através do método ADM:

ADM - Método de Desenvolvimento da Arquitetura

O documento é organizado da seguinte forma:

- Parte I: Conceitos de arquitetura e termos usados
- Parte II: Detalha o Método ADM, entradas e saídas e objetivo de cada fase
- Parte III: Orientações de como aplicar o ADM em cada fase
- Parte IV: Contém o metamodelo de artefatos e visão geral de entregas
- Parte V: Taxonomias e ferramentas para armazenar os resultados das atividades
- Parte VI: Dois modelos de arquitetura de referência MRT e o III-MR
- Parte VII: Como organizar os processos, capacidades, papéis e responsabilidades para se montar uma organização

### O que é arquitetura para o TOGAF?

O ISO/IEC 42010:2007 define “arquitetura” como:

“A organização fundamental de um sistema, incorporado em seus componentes, suas relações entre si e o ambiente e os princípios que orientam a sua concepção e evolução.”

O TOGAF estende para dois significados:

1. Descrição formal de um sistema ou um planejamento detalhado do sistema no nível de componente para orientar a sua execução.
2. Estrutura dos componentes, seus inter-relacionamentos, e os princípios e orientações que regem sua concepção e evolução ao longo do tempo.

### Arquiteturas tratadas no TOGAF

As arquiteturas podem ser para o TOGAF.

- Negócio: Estratégia, governança e processos de negócio
- Dados: Estrutura de dados física ou lógica os recursos para gerenciá-los
- Aplicativos: Aplicativos individuais implementados e a relação com os processo de negócio da organização
- Tecnologia: Softwares e Hardwares necessários para suportar a implementação de negócio, dados e aplicativos: Infra, Middleware, Redes, padrões, processamentos e comunicações

O TOGAF contém as seguintes informações:

O Método de desenvolvimento de arquitetura (ADM) descreve como obter uma arquitetura corporativa que atenda aos requisitos de negócio. O TOGAF fornece orientação em vários níveis:

- Template de um processo: Fase de construção da arquitetura
- Detalhe de cada fase: Entradas, saídas e as entregas para cada fase do ADM

# Capítulo 2 - O Método de Desenvolvimento da Arquitetura (ADM)

Contém em detalhe cada fase do ADM, o objetivo, dados de entrada e saída e o escopo da atividade de arquitetura

### O que é o ADM?

É um método para obter arquiteturas corporativas que atendam os requisitos de negócio. Ele descreve:

- Como desenvolver e utilizar uma arquitetura corporativa
- Um método que garanta que os requisitos de negócio sejam tratados para diferentes níveis (negócio, aplicativo, dados e tecnologia)
- Conjunto de orientações e técnicas

### Fases do ADM

O ADM foi organizado em fases que garantam que o arquiteto trate os requisitos de negócio de forma adequada. Ele é aplicado iterativamente e o resultado atingido deve ser constantemente validado contra os requisitos originais.

A iteração é feita da seguinte forma:

- Cada fase alimenta a próxima fase
- É possível retornar a fases anteriores

## Fases do ADM

### Preliminar

Prepara a organização para projetos de arquitetura. Há a escolha de ferramentas e definição dos princípios da arquitetura.

### Gerenciamento de Requisitos

O ADM existe para que os requisitos de negócio sejam atendidos. Todas as fases precisam atender aos requisitos e portanto uma validação se isso acontece é sempre importante. Requisitos precisam ser identificados e registrados para que o ADM direcione e priorize-os.

### A. Visão da Arquitetura

Define o escopo, restrições, as partes interessadas, obtém aprovações para o início. Produz a Declaração de Trabalho da Arquitetura.

### B. Arquitetura de Negócio / C. Arquitetura de Sistemas de Informação / D. Arquitetura de Tecnologia

Desenvolve as arquiteturas de negócio, dados, aplicativos e tecnologia.Para cada caso, cria a arquitetura _base_ e a arquitetura _alvo_ e compara as diferenças entre elas.

### E. Oportunidades de Soluções

Faz o planejamento das soluções (Arquitetura de soluções?), determina uma abordagem incremental e se necessário desenha uma arquitetura de transição.

### F. Planejamento de Migração

Planejamento de migração e/ou implementação para sair da arquitetura atual ou base para a arquitetura alvo.

### G. Governança da implementação

Supervisiona a implementação através de um comitê de governança de implementação. Certifica se o projeto implementado está de acordo com a arquitetura.

### H. Gerenciamento de Mudança na Arquitetura

Monitoramento contínuo se o processo da arquitetura está respondendo às necessidades da organização, maximizando o valor para o negócio.

Cada uma das fases estão descritas em notas separadas para melhor organização e pesquisa posterior

## O escopo da atividade de arquitetura

O Método de Desenvolvimento da Arquitetura (ADM) define uma sequência recomendada de fases e passos, mas não define o escopo. Isso acontece porque pode-se não ter autoridade organizacional da equipe, partes interessadas podem não querem que itens sejam tratados pela arquitetura ou haja limitação de pessoal, financeira ou recursos.

De qualquer modo, uma vez que o escopo seja definido é importante que os arquitetos sejam governados e integrados na organização. Pode-se particionar os arquitetos tomando cuidado para não se sobreporem.

O escopo pode ser definido e limitado em quatro dimensões:

1. Abrangência
    
    1. Qual é a extensão do empreendimento e em qual parte o arquiteto deve desempenhar
    2. Diversas organizações são tão grandes que podem existir unidades organizacionais dentro de uma própria empresa.
    3. Uma organização estende-se além dos limites do negócio englobando fornecedores, clientes e parceiros
2. Profundidade
    
    1. Qual o nível de detalhe? Qual a arquitetura é suficiente?
    2. Qual é a demarcação adequada entre os esforço da arquitetura e as outras atividades relacionadas (Modelagem, Engenharia, Desenvolvimento, Testes e etc)
3. Período de tempo
    
    1. Qual é o período de tempo que precisa ser articulado para a Visão de Arquitetura, e faz sentido (em termos de praticidade e recursos) para o mesmo de tempo usado na descrição detalhada da arquitetura?
    2. Se não, quantas arquiteturas de Transição devem ser definidas e qual o prazo?
4. Domínios de arquitetura
    
    1. Uma descrição completa deve conter os quatro domínios (negócio, dados, aplicativos e tecnologia)
    2. Restrição de tempo, prazo e recursos podem limitar quais arquiteturas serão abraçadas

# Capítulo 2 - Objetivos, Entradas e Saídas por Fase

## Fase 0 - Preliminar

Prepara uma organização para projetos de arquitetura.

## Objetivos

Identifica qual nível de profundidade que a organização deseja para a “capacidade” de arquitetura:

- Revisar o contexto organizacional. Qual momento da companhia.
- Quais elementos da organização são afetados pela arquitetura.
- Quais frameworks e processos fazer intersecção com a arquitetura.
- Qual o alvo de maturidade desejada.

Estabelecer a capacidade da arquitetura:

- Modelo organizacional para a arquitetura
- Processo e recursos para governar a arquitetura
- Selecionar e definir ferramentas
- Definir os princípios

## Passos sugeridos

1. Definir o escopo organizacional
2. Governança e frameworks de apoio
3. Definir equipe, estrutura e como serão organizados
4. Definir os princípios
5. Adaptar o TOGAF e/ou outros frameworks
6. Implementar ferramentas

## Entradas e Saídas

Entradas:

- TOGAF
- Outros frameworks de arquitetura
- Dados de negócio (Comitês de estratégia, planejamentos de negócio, estratégia de negócio, estratégia de TI,  princípios metas e motivadores de negócio)
- Frameworks de Governança e Legais
- Capacidade de Arquitetura
- Acordos de parceria e contrato
- Modelo organizacional da empresa
- Frameworks de arquitetura existentes

Saídas:

- 3.1 Framework de arquitetura customizado
- 3.2 Modelo organizacional para arquitetura corporativa
- 3.4 Princípios, metas e motivadores de negócio
- 3.5 Repositório arquitetura
- 3.7 Requisição para Trabalho de Arquitetura
- Framework de Governança

## Fase Interna - Gerenciamento de Requisitos

Essa etapa aplica-se a todas as fases do ciclo ADM. Ele é dinâmico, sendo armazenado e alimentado nas entradas e saídas das fases. Deve-se ficar atento as mudanças e responder a elas. Arquitetura lida com incertezas e expectativas das partes interessadas e deve-se entregar uma solução prática e objetiva.

### Objetivo

- Garantir que o processo de gerenciamento de requisitos seja mantido e opere em todas as fases relevantes do ADM
- Gerenciar requisitos de arquitetura identificados durante a execução de um ciclo do ADM ou uma fase.
- Garantir que requisitos relevantes de arquitetura estejam disponíveis para uso de cada fase enquanto ela é executada

### Passos

- Identificar / documentar requisitos
- Gerar requisitos de Linha de Base
- Monitorar requisitos de Linha de Base
- Identificar requisitos de mudança; remover, modificar e reavaliar prioridades
- Identificar requisitos de mudança e registrar prioridades; identificar e resolver conflitos; gerar declarações de impacto de requisitos
- Avaliar impacto de requisitos de mudança nas fases atuais e anteriores do ADM
- Implementar requisitos advindos da fase H
- Atualizar o repositório de requisitos
- Implementar mudança na fase atual
- Avaliar e revisar a análise de diferenças das fases anteriores

### Entrada

- Requisitos relacionados com saída de cada fase do ADM
- Primeiros requisitos são produzidos como parte da Visão de Arquitetura
- Cada domínio gera requisitos detalhados, por exemplo requisitos de conformidade

### Saída

- Requisitos de mudança
- Avaliação de Impacto de Requisitos
    
    - Quais fases do ADM que precisam ser revisadas para direcionar as alterações
    - A versão final deve incluir todas as implicações dos requisitos (ex: custos, prazos e métricas de negócio)

## Fase A - Visão da Arquitetura

Aqui começa uma iteração de um ciclo de desenvolvimento de arquitetura. Importante definir o escopo, as restrições e as expectativas para a iteração. Necessário validar o contexto empresarial para criar e aprovar a Declaração de Trabalho da Arquitetura.

## Objetivos

- Criar uma visão de alto nível das capacidades e valores entregues com a arquitetura corporativa.
- Aprovar a declaração de trabalho da arquitetura para desenvolver e implantar a arquitetura descrita na visão da arquitetura

## Passos

1. Criar o projeto de arquitetura
2. Identificar as partes interessadas e as preocupações com os requisitos de negócio
3. Confirmar metas, geradores e restrições de negócio
4. Avaliar as capacidades de negócio
5. Avaliar o quanto o negócio está de prontidão para fazer uma transformação
6. Definir o escopo
7. Confirmar ou elaborar os princípios de arquitetura e de negócio
8. Desenvolver a visão de arquitetura
9. Definir a proposição de valor da arquitetura alvo e KPIs
10. Identificar os riscos da transformação do negócio e como mitigá-los
11. Desenvolver a declaração de trabalho da arquitetura e obter a aprovação

## Entradas e Saídas

Entrada:

- Requisição para Trabalho de Arquitetura -> 0
- Princípios, metas e motivadores do negócio -> 0
- Framework de arquitetura adaptado (método, conteúdos e princípios de arquitetura , ferramentas configuradas e implantadas). -> 0
- Repositório de arquitetura (com frameworks, linhas de bases existentes) -> 0

Saída:

- 3.8 Declaração de Trabalho da Arquitetura (aprovada)
- Princípios, metas e motivadores de negócio (refinado).
- Princípios da arquitetura
- Avaliação de capacidades
- Framework de Arquitetura Customizado.
- 3.9 Visão da arquitetura com:
    
    - Requisitos chaves de negócio
    - Documento de Definição de Arquitetura
        
        - Arquiteturas de alto nível para linhas base e alvo para: Arquitetura de negócio, dados, aplicativo e tecnologia.
- 3.11 Planejamento de comunicação
- Repositório de Arquitetura (populado)

## Fase B - Arquitetura de Negócio

Desenvolvimento da arquitetura de negócio para suporte a visão de arquitetura acordada.

## Objetivo

- Arquitetura de negócio alvo: Como a organização  deve operar para atingir as metas de negócio
- Identificar arquiteturas candidatas
- Definição do roteiro entre linha base e arquitetura alvo

## Passos

- Selecionar modelos de referência, pontos de vista e ferramentas
- Descrever linha de base do negócio e arquitetura de negócio alvo. Ver a diferença entre elas
- Definir roteiro candidato
- Identificar e resolver impactos
- Revisar com partes interessadas
- Concluir arquitetura de negócio e criar documento

## Entradas e Saídas

Entradas:

- Modelo organizacional para a arquitetura corporativa -> 0
- Requisição de Trabalho de Arquitetura -> 0
- Princípios, metas e motivadores de negócio -> 0,A
- Avaliação de Capacidades -> A
- Planejamento de Comunicação -> A
- Framework de Arquitetura Customizado -> A
- Declaração de Trabalho de Arquitetura aprovado -> A
- Princípios de arquitetura incluindo princípios de negócio, quando pré existente -> A
- Continuum Corporativo
- Repositório de Arquitetura -> 0,A
- Visão da Arquitetura -> A
    
    - Requisitos refinados de alto nível das principais partes interessadas
    - Rascunho Documento de definição de arquitetura ( com linhas de base de alto nível e arquitetura alvo de alto nível, para as quatro arquiteturas)

Saídas:

- Declaração de Trabalho de Arquitetura atualizado
- Princípios, metas e motivadores de negócio validados
- Princípios da Arquitetura de Negócio elaborados
- Rascunho do Documento de Definição de Arquitetura atualizado
    
    - Linha base e alvo da arquitetura de negócio (detalhado)
    - Visão da arquitetura de negócio, preocupações e pontos de vista das partes interessadas
- Rascunho da Especificação dos Requisitos de Arquitetura, atualizado
    
    - Resultado da análise das diferenças
    - Requisitos técnicos
    - Requisitos de negócio atualizados
- Componentes da Arquitetura de Negócio de um Roteiro de Arquitetura

## Fase C - Arquitetura de Sistemas de Informação

São dois passos nessa fase que podem ser feitos em sequência ou ao mesmo tempo.

## Arquitetura de Dados

### Objetivos

- Desenvolver a arquitetura de dados alvo que suporta a arquitetura de negócio e a visão de arquitetura, enquanto direciona a Requisição de Trabalho de Arquitetura e as preocupações das partes interessadas
- Identificar os componentes candidatos do Roteiro da Arquitetura, com base nas diferenças entre as Arquiteturas Linha de Base e Alvo

### Passos

1. Selecionar modelos de referência, pontos de vista e ferramentas
2. Descrever a linha de base da arquitetura de dados
3. Descrever o alvo da arquitetura de dados
4. Realizar a análise das diferenças
5. Definir os componentes candidatos do roteiro
6. Resolver os impactos no panorama de arquitetura
7. Conduzir uma revisão formal com as partes interessadas
8. Finalizar a arquitetura de dados
9. Criar o documento de definição de arquitetura

### Entradas

- Requisição de Trabalho de Arquitetura -> 0
- Avaliação de Capacidades -> A
- Planejamento de Comunicação -> A
- Modelo organizacional para a arquitetura corporativa -> 0
- Framework de Arquitetura Customizado -> A
- Princípios de Dados
- Declaração de Trabalho de Arquitetura -> A, B
- Visão da Arquitetura -> A, B
- Repositório de Arquitetura -> 0,A
- Rascunho do Documento de Definição de Arquitetura atualizado -> B
    
    - Linha base e alvo da arquitetura de negócio (detalhado)
    - Linha base e alvo da arquitetura de dados, aplicativo e tecnologia (alto nível)
- Rascunho da Especificação dos Requisitos de Arquitetura, atualizado -> B
    
    - Resultado da análise das diferenças
    - Requisitos técnicos
- Componentes da arquitetura de Negócio do Roteiro de Arquitetura

### Saída

- Declaração de Trabalho de Arquitetura atualizado
- Princípios de Dados validados ou atualizados
- Rascunho do Documento de Definição de Arquitetura atualizado
    
    - Linha base e alvo da arquitetura de dados (detalhado)
    - Visões da arquitetura de dados, preocupações e pontos de vista das partes interessadas
- Rascunho da Especificação dos Requisitos de Arquitetura, atualizado
    
    - Resultado da análise das diferenças
    - Requisitos de interoperabilidade de dados
    - Requisitos técnicos relevantes que se aplicam à evolução do ciclo de desenvolvimento da arquitetura
    - Restrições na arquitetura de tecnologia
    - Requisitos de negócio atualizados
    - Requisitos de aplicativo atualizados
- Componentes da Arquitetura de Dados do Roteiro de Arquitetura

## Arquitetura de Aplicativo

### Objetivos

- Desenvolver a arquitetura de aplicativo alvo que suporta a arquitetura de negócio e a visão de arquitetura, enquanto direciona a Requisição de Trabalho de Arquitetura e as preocupações das partes interessadas
- Identificar os componentes candidatos do Roteiro da Arquitetura, com base nas diferenças entre as Arquiteturas Linha de Base e Alvo

### Passos

1. Selecionar modelos de referência, pontos de vista e ferramentas
2. Descrever a linha de base da arquitetura de aplicativo
3. Descrever o alvo da arquitetura de aplicativo
4. Realizar a análise das diferenças
5. Definir os componentes candidatos do roteiro
6. Resolver os impactos no panorama de arquitetura
7. Conduzir uma revisão formal com as partes interessadas
8. Finalizar a arquitetura de aplicativo
9. Criar o documento de definição de arquitetura

### Entradas

- Requisição de Trabalho de Arquitetura -> 0
- Avaliação de Capacidades -> A
- Planejamento de Comunicação -> A
- Modelo organizacional para a arquitetura corporativa -> 0
- Framework de Arquitetura Customizado -> A
- Princípios de Aplicativos
- Declaração de Trabalho de Arquitetura -> A, B
- Visão da Arquitetura -> A, B
- Repositório de Arquitetura -> 0,A
- Rascunho do Documento de Definição de Arquitetura atualizado -> B
    
    - Linha base e alvo da arquitetura de negócio (detalhado)
    - Linha base e alvo da arquitetura de dados (detalhado ou alto nível)
    - Linha base e alvo da arquitetura de aplicativo e tecnologia (alto nível)
- Rascunho da Especificação dos Requisitos de Arquitetura, atualizado -> B
    
    - Resultado da análise das diferenças
    - Requisitos técnicos
- Componentes da arquitetura de Negócio do Roteiro de Arquitetura

### Saída

- Declaração de Trabalho de Arquitetura atualizado
- Princípios de Dados validados ou atualizados
- Rascunho do Documento de Definição de Arquitetura atualizado
    
    - Linha base e alvo da arquitetura de aplicativo (detalhado)
    - Visões da arquitetura de aplicativo, preocupações e pontos de vista das partes interessadas
- Rascunho da Especificação dos Requisitos de Arquitetura, atualizado
    
    - Resultado da análise das diferenças
    - Requisitos de interoperabilidade de aplicativos
    - Requisitos técnicos relevantes que se aplicam à evolução do ciclo de desenvolvimento da arquitetura
    - Restrições na arquitetura de tecnologia
    - Requisitos de negócio atualizados
    - Requisitos de aplicativo atualizados
- Componentes da Arquitetura de Aplicativos do Roteiro de Arquitetura

## Fase D - Arquitetura de Tecnologia

Uso para tecnologia de hardware, software e comunicações

### Objetivos

- Desenvolver a arquitetura de tecnologia alvo que suporte o aplicativo lógico e físico, os componentes de dados e a visão da arquitetura, direcionando a Requisição de Trabalho de Arquitetura e as preocupações das partes interessadas
- Identificar os componentes candidatos do Roteiro da Arquitetura, com base nas diferenças entre as Arquiteturas Linha de Base e Alvo

### Passos

1. Selecionar modelos de referência, pontos de vista e ferramentas
2. Descrever a linha de base da arquitetura de tecnologia
3. Descrever o alvo da arquitetura de tecnologia
4. Realizar a análise das diferenças
5. Definir os componentes candidatos do roteiro
6. Resolver os impactos no panorama de arquitetura
7. Conduzir uma revisão formal com as partes interessadas
8. Finalizar a arquitetura de tecnologia
9. Criar o documento de definição de arquitetura

### Entradas

- Requisição de Trabalho de Arquitetura -> 0
- Avaliação de Capacidades -> A
- Planejamento de Comunicação -> A
- Modelo organizacional para a arquitetura corporativa -> 0
- Framework de Arquitetura Customizado -> A
- Princípios de Tecnologia
- Declaração de Trabalho de Arquitetura -> A, B
- Visão da Arquitetura -> A, B
- Repositório de Arquitetura -> 0,A
- Rascunho do Documento de Definição de Arquitetura atualizado -> B
    
    - Linha base e alvo da arquitetura de negócio,dados e aplicativo (detalhado)
    - Linha base e alvo da arquitetura de tecnologia (alto nível)
- Rascunho da Especificação dos Requisitos de Arquitetura, atualizado -> B
    
    - Resultado da análise das diferenças
    - Requisitos técnicos
- Componentes da arquitetura de Negócio do Roteiro de Arquitetura

### Saída

- Declaração de Trabalho de Arquitetura atualizado
- Princípios de Tecnologia validados ou atualizados
- Rascunho do Documento de Definição de Arquitetura atualizado
    
    - Linha base e alvo da arquitetura de tecnologia (detalhado)
    - Visões da arquitetura de tecnologia, preocupações e pontos de vista das partes interessadas
- Rascunho da Especificação dos Requisitos de Arquitetura, atualizado
    
    - Resultado da análise das diferenças
    - Requisitos gerados nas fases B e C
    - Requisitos de tecnologia atualizados
- Componentes da Arquitetura de Tecnologia do Roteiro de Arquitetura

## Fase E - Oportunidades e Soluções

É a primeira fase relacionada a implementação. Descreve o que será entregue (projeto, programa ou portfólios) que forneçam a arquitetura alvo.

### Objetivos

- Gerar a versão inicial completa do Roteiro de Arquitetura, com base na análise de diferenças e nos componentes candidatos do Roteiro de Arquitetura das Fases B, C e D
- Determinar se é necessária uma abordagem incremental e em caso afirmativo identificar as Arquiteturas de Transic’~ao que vão entregar contínuo valor ao negócio

### Passos

- Determinar/confirmar atributos chaves de mudança corporativa
- Determinar as restrições de negócio para a implementação
- Revisar e consolidar o resultado da análise de diferenças de Fases B para D
- Revisar requisitos consolidados através de funções de negócio relacionadas
- Consolidar e conciliar os requisitos de interoperabilidade
- Refinar e validar dependências
- Confirmar prontidão e risco para a transformação do negócio
- Formular a Estratégia de implementação da migração
- Identificar e agrupar os principais pacotes
- Identificar Arquiteturas de Transição
- Criar roteiro de arquitetura e implementação e planejamento de migração

### Entradas

- Informação do produto
- Requisição de Trabalho de Arquitetura -> 0
- Avaliação de Capacidades -> A
- Planejamento de Comunicação -> A
- Metodologias de Planejamento
- Modelos de Governança e Frameworks
- Framework de Arquitetura Customizado -> A
- Declaração de Trabalho de Arquitetura -> A, B
- Visão da Arquitetura -> A, B
- Repositório de Arquitetura -> 0,A
- Rascunho da Especificação de Requisitos da Arquitetura
- Requisição de Mudança para programas e projetos existentes
- Componentes candidatos do Roteiro de Arquitetura para as Fases B, C e D

### Saída

- Declaração de Trabalho de Arquitetura, atualizado
- Visão da Arquitetura, atualizado
- Rascunho do Documento de Definição de Arquitetura, atualizado
    
    - Arquitetura de transição, número e escopo, se houver
- Rascunho da Especificação dos Requisitos de Arquitetura, atualizado
- Avaliação de Capacidade, incluindo:
    
    - Capacidades de Negócio
    - Capacidades de TI
- Roteiro de Arquitetura, incluindo:
    
    - Portfólio do pacote de trabalho
    - Identificação de Arquiteturas de Transição, se houver
    - Recomendações de implementação
- Planejamento da Migração e Implementação (contorno), incluindo:
    
    - Estratégia de Migração e Implementação

## Fase F - Planejamento da Migração

Como mover da linha de base para a arquitetura alvo e finaliza o Planejamento da Migração e Implementação

### Objetivos

- Finalizar o Roteiro de Arquitetura e o Planejamento da Migração e Implementação que o suporta
- Garantir que o Planejamento da Migração e Implementação esteja de acordo com a abordagem para gerenciamento e implementação de mudança no portfólio de mudança
- Assegurar que o valor para o negócio e o custo dos pacotes de trabalho e Arquitetura de Transição seja compreendidos pelos principais interessados

### Passos

- Confirmar as interações dos frameworks de gerenciamento para o Planejamento da Migração e Implementação
- Atribuir um valor de negócio para cada pacote de trabalho
- Estimar os requisitos de recursos, intervalos de projetos e veículo de entrega/disponibilidade
- Priorizar os projetos de migração através da condução de uma validação de avaliação de custo/benefício e risco
- Confirmar o Roteiro de Arquitetura e atualizar o Documento de Definição de Arquitetura
- Concluir o Planejamento da Migração e Implementação
- Completar o ciclo de desenvolvimento e o documento de lições aprendidas

### Entradas

- Requisição de Trabalho de Arquitetura -> 0
- Planejamento de Comunicação -> A
- Modelo para a arquitetura corporativa da organização
- Modelos de Governança e Frameworks
- Framework de Arquitetura Customizado -> A
- Declaração de Trabalho de Arquitetura -> A, B
- Visão da Arquitetura -> A, B
- Repositório de Arquitetura -> 0,A
- Rascunho do Documento de Definição da Arquitetura, incluindo:
    
    - Arquiteturas de transição, se houver
- Rascunho da Especificação de Requisitos da Arquitetura
- Solicitações de Mudança para programas e projetos existentes
- Roteiro de Arquitetura
- Avaliação de Capacidades, incluindo:
    
    - Capacidade de Negócio
    - Capacidade de TI
- Planejamento da Migração e Implementação, incluindo:
    
    - Estratégia de Migração
    - Implementação de alto nível

### Saída

- Planejamento da Migração e Implementação detalhado, incluindo:
    
    - Estratégia de Migração e Implementação
    - Repartição de projeto e portfólio de implementação
    - Planos iniciais do projeto (opcional)
- Documento de Definição de Arquitetura finalizado, incluindo:
    
    - Arquitetura de Transição finalizadas, se houver
- Especificação dos Requisitos de Arquitetura, finalizado
- Roteiro de Arquitetura, finalizado
- Blocos de Construção de Arquitetura reutilizáveis
- Requisição para Trabalho de Arquitetura para novas Iterações do ADM (se houver)
- Modelo de Governança de Implementação
- Requisições de Mudança da Capacidade da Arquitetura identificadas a partir das lições aprendidas

## Fase G - Governança da Implementação

Define como os projetos são restritos pela arquitetura, monitora a construção e produz o contrato de arquitetura assinado

### Objetivos

- Assegurar a conformidade com a Arquitetura Alvo através da implementação de projetos
- Executar as funções da Governança da Arquitetura apropriadas para a solução e qualquer implementação direcionada a Requisição de Mudança de arquitetura

### Passos

- Confirmar o escopo e as prioridades para a implantação com o gerenciamento de desenvolvimento
- Identificar as competências e recursos de implantação
- Desenvolver as orientações de implantação de soluções
- Realizar avaliações de conformidade da arquitetura corporativa
- Implementar as operações de negócio e TI
- Executar revisão pós implementação e fechar a implementação

### Entradas

- Requisição de Trabalho de Arquitetura -> 0
- Avaliação de Capacidades
- Modelo para a arquitetura corporativa da organização
- Framework de Arquitetura Customizado -> A
- Declaração de Trabalho de Arquitetura -> A, B
- Visão da Arquitetura -> A, B
- Repositório de Arquitetura -> 0,A
- Documento de Definição da Arquitetura
- Especificação de Requisitos da Arquitetura
- Roteiro de Arquitetura
- Modelo de Governança de Implementação
- Requisição para Trabalho de Arquitetura identificados nas fases E e F
- Planejamento da Migração e Implementação

### Saída

- Contrato de Arquitetura, assinado
- Avaliação de Conformidade
- Requisições de Mudança
- Análise de Impacto - Recomendações de Implementação
- Soluções implantadas em conformidade com a Arquitetura, incluindo:
    
    - Sistema implementado em conformidade com a arquitetura
    - Repositório de Arquitetura populado
    - Recomendações e dispensas em conformidade com a Arquitetura
    - Recomendações sobre os requisitos de entrega de serviço
    - Recomendações sobre métricas de desempenho
    - Acordos de Nível de Serviço (ANS)
    - Visão da Arquitetura, atualizada após implementação
    - Documento de definição da Arquitetura, atualizado após implementação
    - Modelos de operação de negócio e TI para as soluções implementadas

## Fase H - Gerenciamento de Mudança na Arquitetura

Alterações na arquitetura são gerenciadas de forma adequada

### Objetivos

- Garantir que o ciclo de vida de arquitetura seja mantido
- Garantir que o Framework de Governança de Arquitetura seja executado
- Garantir que a capacidade da Arquitetura da organização atenda aos requisitos atuais

### Passos

- Estabelecer o processo de realização de valor
- Implantar ferramentas de monitoramento
- Gerenciar Riscos
- Fornecer uma análise para gerenciamento de mudança da arquitetura
- Desenvolver requisitos de mudança para atender às metas de desempenho
- Ativar o processo para implementar mudanças

### Entradas

- Requisição de Trabalho de Arquitetura -> 0
- Modelo para a arquitetura corporativa da organização
- Framework de Arquitetura Customizado -> A
- Declaração de Trabalho de Arquitetura -> A, B
- Visão da Arquitetura -> A, B
- Repositório de Arquitetura -> 0,A
- Documento de Definição da Arquitetura
- Especificação de Requisitos da Arquitetura
- Roteiro de Arquitetura
- Requisição de Mudanças devidas a mudanças de tecnologia
- Requisição de Mudanças devidas a mudanças no negócio
- Requisição de Mudanças geradas por lições aprendidas
- Modelo de Governança de Implementação
- Contrato de Arquitetura, assinado
- Avaliações de conformidade
- Planejamento da Migração e Implementação

### Saída

- Atualizações da Arquitetura
- Mudanças no framework e princípios de arquitetura
- Nova Requisição para Trabalho de Arquitetura, para iniciar outro ciclo de ADM
- Declaração de Trabalho da Arquitetura, atualizado
- Contrato de Arquitetura, atualizado
- Avaliação de conformidade, atualizado

# Capítulo 3 - Principais Técnicas e entregáveis do Ciclo do ADM

Esse é o principal capítulo com o detalhe das técnicas e entregáveis do Método de Desenvolvimento de Arquitetura

A seguir cada uma das técnicas e seus resumos

|   |   |
|---|---|
|**DOCUMENTO**|**FASE**|
|### 3.1 - Framework de Arquitetura Customizado<br><br>- Adaptar o TOGAF e outros frameworks, com seus entregáveis, artefatos e técnicas para ser utilizado por uma corporação|Preliminar|
|### 3.2 - Modelo Organizacional para Arquitetura Corporativa<br><br>- Descreve como a Arquitetura atuará na organização. Papéis, responsabilidades, orçamento, pessoas, áreas impactadas, maturidade e etc.|Preliminar|
|### 3.3 - Princípios de Arquitetura<br><br>- Conjunto de documentos com regras e diretrizes para cada arquitetura: Princípios de negócio, dados, aplicativos e tecnologia.<br>- Aprovados no Comitê de arquitetura.<br>- Contém: Nome, declaração, racional (benefícios) e implicações.<br>- São influenciados por tendências de tecnologias, sistemas atuais, iniciativas da organização. Ex: Princípios de acessibilidade, segurança|Prelliminar|
|**3.4 - Princípios, Objetivos e Motivadores de Negócio**<br><br>- Definidos pela empresa<br>- Atualizados na saída da fase Preliminar e revisto na Fase A|Preliminar<br><br>A. Visão da Arquitetura|
|**3.5 - Repositório de Arquitetura**<br><br>- Área de Armazenamento|Preliminar|
|**3.6 - Ferramentas de Arquitetura**<br><br>- Selecionar ferramentas (Desenho, Artefatos, Componentes e etc)|Preliminar|
|**3.7 - Requisição para Trabalho de Arquitetura**<br><br>- Documento enviado pelo solicitante para arquitetura para iniciar o ciclo ADM<br>- Contém detalhe do pedido (prazo, objetivo, restrições, sistema atual etc)|Preliminar|
|**3.8 - Declaração de Trabalho da Arquitetura**<br><br>- Contrato com o solicitante do que será feito<br>- Contém descrição, papéis e responsabilidades, prazo e aprovações|A. Visão da Arquitetura|
|**3.9 - Visão da Arquitetura**<br><br>- Mudanças que serão feitas ao implantar a arquitetura alvo. Acordar o resultado desejado.<br>- Contém: Problema a ser resolvido, resumo da declaração de trabalho, visões de alto nível das arquiteturas de negócio, aplicativo, dados e tecnologia|A. Visão da Arquitetura|
|**3.10 - Gerenciamento das partes interessadas**<br><br>- Identifica os atores principais / os atualiza a cada fase.<br>- Partes mais poderosas, modelo de comunicação, antecipação de reações, objetivos conflitante entre eles e etc.<br>- Garantir que todos compreendam sobre arquitetura corporativa e vai tratar das suas preocupações<br><br>TOGAF sugere alguns modelos para ajudar nisso. Ver artefatos de apoio ao final.|A. Visão da Arquitetura|
|**3.11 - Planejamento de Comunicação**<br><br>- Fazer comunicações efetivas e na hora certa<br>- Mensagens chave e modelos: reuniões, boletins<br>- Definir calendário, periodicidade e local|A. Visão da Arquitetura|
|**3.12 - Avaliação da Prontidão para Transformação do Negócio**<br><br>- Técnica para avaliar o quanto a organização está pronta para uma transformação e disposição para aceitar a mudança.<br>- Determinar fatores de prontidão com modelos de maturidade, bem como avaliar riscos e determinar ações<br>- Documentar na Avaliação de Capacidades|A. Visão da Arquitetura|
|**3.13 - Avaliação de Capacidades**<br><br>- Entender a capacidade alvo e base da empresa. Feita na fase A e atualizada na E.<br>- Como empresa pretende aumentar ou otimizar as capacidades<br>- Qual é a capacidade ou maturidade de TI e qual estilo de arquitetura, nível de formalidade e detalhes que se adaptarão à cultura da empresa<br>- Quais ativos de arquitetura existem, quais padrões e modelos devem ser considerados. O quanto o negócio está pronto para mudar inclusive culturalmente.<br>- Entregáveis: Avaliação da capacidade de negócio e de Ti, Maturidade de Arquitetura e Avaliação da prontidão para transformação de negócio|A. Visão da Arquitetura<br><br>E. Oportunidades e Soluções|
|**3.14 - Gerenciamento de Risco**<br><br>- Técnica para gerenciar o risco<br>- Identificando o risco, formas de mitigar e monitoramento<br>- Atividades que devem ser documentadas na Declaração de Trabalho de Arquitetura|A. Visão da Arquitetura|
|**3.15 - Documento de Definição da Arquitetura**<br><br>- Grupo de entregáveis criados. É uma das principais fases.<br>- Abrange: Negócio, Dados, Aplicativo e Tecnologia<br>- Acompanha a Especificação de Requisitos de Arquitetura.<br>- Contém: Linha Base da Arquitetura, Modelos das arquiteturas de negócio, dados, aplicativos e tecnologia, Mapeia os modelos de referências, padrões, componentes de reúso, impactos e Transições<br>    <br>    São divididos entre:<br>    <br>- Arquitetura de Negócio: Estrutura organizacional, metas, funções e serviços de negócio. Seus processos, modelos de trabalho e etc<br>- Arquitetura de Dados: Linha de Base e Arquitetura Alvo, contendo: Modelo de dados, modelo lógico, processo para gerenciar os dados<br>- Arquitetura de Sistemas de informação: Linha de base e alvo do aplicativo contendo: Processos, locais, tempo e pessoas<br>- Arquitetura de Tecnologia: Tecnologia Base e Alvo, contendo: Componentes e suas relações, plataformas tecnológicas e a pilha de tecnologia. Ambiente e locais, carga de processamento esperado, especificações de hardware e rede|A. Visão da Arquitetura<br><br>B. Arquitetura de Negócio<br><br>C. Arquitetura de Sistemas<br><br>D. Arquitetura da Tecnologia|
|**3.16 - Especificação de requisitos de arquitetura**<br><br>- Descreve o que um projeto de implementação deve fazer para cumprir com a arquitetura<br>- Contém: Métricas de sucesso, diretrizes para implementação, padrões de implementação, interoperabilidade e requisitos de gerenciamento de serviços, análise de diferenças (gaps) e eoutrods|Fase B, C e D|
|**3.17 - Roteiro (Roadmap) de Arquitetura**<br><br>- Linha do tempo para mostrar a progressão da arquitetura<br>- Arquitetura de Transição e passos intermediários<br>- Contém: Portfólio com pacote de trabalho que tem: Requisitos, documentos de definição e requisitos de arquitetura, riscos, diferenças, arquitetura de transição, recomendações de implementação e etrc.|Fase B, C, D, E e F|
|**3.18 - Cenários de Negócio**<br><br>- Técnica para identificar necessidades de negócio que geram novas funcionalidades que atendem motivadores de negócio chave.<br>- Processo passa por: Documentar problema, onde ocorre, quais atores, objetivos desejados e etc.|Fases A e B|
|**3.19 - Análise de diferenças (Gap Analysis)**<br><br>- Usada para validar uma arquitetura sendo desenvolvida. Destaca um déficit entre a arquitetura base e a alvo.<br>- Veja nos artefatos de apoio uma tabela que mostra isso. No documento original há a explicação de como montar essa tabela|Fase B, C, D e E|
|**3.20 - Pontos de Vista de Arquitetura**<br><br>- Visão é o que Vê. Ponto de Vista é a partir de onde você está olhando.<br>- Pode-se utilizar pontos de vista entre arquiteturas diferentes.<br>- Ex: Um sistema de avião (o operador tem um ponto de vista diferente do piloto)<br>- Visão pode ser um subconjunto do sistema|Fases A, B, C e D|
|**3.21 - Visões de Arquitetura**<br><br>- Representações de uma arquitetura através de um ponto de vista e que as partes interessadas compreendam.<br>- Deve-se escolher qual visão deve ser desenvolvida, não tão genérica, mas nem tão detalhada.|Fases A, B, C e D|
|**3.22 - Blocos de Construção de Arquitetura (BCA)**<br><br>- Documentos de Arquitetura e de modelos classificados de acordo com o Continuum da Arquitetura<br>- Capturam requisitos e direcionam Blocos de Construção de Solução<br>- Contém: Funcionalidades, interfaces escolhida, interoperabilidade e relacionamento e outros.<br>- Devem ser reutilizáveis|Fases B, C, D e E|
|**3.23 - Blocos de Construção de Solução (BCS)**<br><br>- Implementações das arquiteturas. Podendo ser adquiridos ou desenvolvidos<br>- Contém: Detalhe das funcionalidades, interfaces, atributos, mapeamento até a topologia e políticas operacionais, desempenho, adaptabilidade e relação com BCA.|Fases B,C, D e E|
|**3.24 - Planejamento Baseado em Capacidades**<br><br>- É uma técnica de planejamento baseado nos resultados de negócio.<br>- Tem relação com o planejamento das capacidades, arquitetura corporativa e gerenciamento de projetos/portfólio. Ver figura nos artefatos de apoio|Fases E e F|
|**3.25 - Técnicas de Planejamento da Migração**<br><br>- Técnicas para apoiar nas fases E de Oportunidades e Soluções e no F no Planejamento de Migrações. Veja abaixo, cada uma delas e materiais de apoio nos artefatos de apoio:<br>- Fator de Implementação e Matriz de dedução: Usada para documentar fatores que impactem na migração de implementação da arquitetura. Contém: Riscos, problemas, pressupostos, dependências, ações e impactos.<br>- Diferenças (Gaps) consolidados, soluções de dependências: Avaliar soluções para os gaps encontrados. Pode ser usado para apoiar na criação de pacotes de trabalho.<br>- Incrementos de Definição da Arquitetura: Usado para planejar arquiteturas de transição.<br>- Evolução do Estado da Arquitetura de Transição: Mostre o estado das arquiteturas, usando o modelo MRT (Modelo de Referência Técnica). Contém: Descrição do BCS com classificações como nova, manter, transição ou substituição.<br>- Avaliação de Valor de Negócio: Dimensão de valor e risco, onde o tamanho do projeto representa a “bola”.|Fases E e F|
|**3.26 - Planejamento de Migração e Implementação**<br><br>- Agenda de projetos para atingir a arquitetura alvo. Inclui os projetos agrupados em portfólios e programas.<br>- Contém: Estratégia de Migração, fragmentação do projeto, pode ter o termo de abertura do projeto.|Fases E e F|
|**3.27 - Arquitetura de Transição**<br><br>- Descreve arquiteturas intermediárias necessárias para se chegar em uma arquitetura alvo.<br>- Contém: Estado da arquitetura de transição, arquitetura de transição para negócio, dados, aplicativo e tecnologia.|Fases E e F|
|**3.28 - Modelo de Governança de Implementação**<br><br>- São processos que garantem a transição suave para a arquitetura apropriada<br>- Contém: Processo, estrutura organizacional, papéis e responsabilidades, pontos de verificação, critérios de sucesso e falha.|Fases E, F, G e H|
|**3.29 - Contratos de Arquitetura**<br><br>- Acordos entre solicitantes e executores sobre os entregáveis<br>- Ao Governar os ‘contratos’, se garante: monitoração para integridade, mudanças, adesão aos princípios e padrões, identificação de riscos de políticas, produtos, operacionais, processos para prestação de contas.<br>- Podem ser dois contratos:<br>- Contrato de Desenvolvimento e Desenho de Arquitetura: Escopo, requisitos de conformidade, medidas, fases, planejamento, tempo e entregas<br>- Contrato de Arquitetura para Usuários de Negócio: Contexto, escopo, requisitos estratégicos, conformidade, tempo, métricas e nível de serviço.|Fases G e H|
|**3.30 - Requisição de Mudança**<br><br>- Mudança caso os requisitos originais da arquitetura não sejam mais adequados. Deve-se desviar do alvo final ou pedir extensão de prazo.<br>- Fatores externos podem contribuir como: Mercado, nova estratégia, novas tecnologias<br>- Contém: Descrição, racional, impacto gerado nas fases, prazo, escopo, priorização e etc|Fases G e H|
|**3.31 - Avaliação da Conformidade**<br><br>- Garantir que o que foi implementado atende a arquitetura alvo definida<br>- Contém: Visão do projeto e status, arquitetura alvo, lista de verificação de hardware, software / middleware, aplicativos, segurança etc etc|Fases G e H|
|**3.32 - Avaliação do Impacto de Requisitos**<br><br>- Novos dados geram impactos e invalidam aspectos da arquitetura. Necessário identificar alterações que devam ser feitas<br>- Documenta as mudanças e recomendações com: Requisitos específicos, prioridade, fases a serem revisadas, recomendações.|Fase H|

## Artefatos de Apoio

### 3.10 - Gerenciamento das partes interessadas

Matriz de Poder

Análise de partes interessadas

Adaptar os Entregáveis de Engajamento

### 3.19 - Análise de Diferenças (Gap Analysis)

Matriz de Poder

### 3.24 - Planejamento Baseado e Capacidades

**3.25 - Técnicas de Planejamento da Migração**

# Capítulo 4 - Orientações para Adaptar o ADM

Pode-se adaptar o ADM, diminuindo-o ou aumentando-o de acordo com a organização. Uma das principais fases iniciais é revisar o processo e suas saídas.

Algumas das razões para se adaptar o ADM é :

- Maturidade da Arquitetura ou da empresa.
- Ajustar a ordem das fases a depender da companhia
- Adicionar outro framework a depender do segmento de negócio
- Complementar outros frameworks de governança corporativa
- Práticas de Outsourcing

### Iteração no ADM

O ADM por ser iterado a fim de que ciclos gerem benefícios ao se tratar fases simultaneamente, conduzir projetos separados em paralelo. Pode-se alternar fases para que o tema se torne mais maduro.

Pode-se iterar, por exemplo:

- Capacidade de arquitetura: Se define e ajusta como a arquitetura trabalha e o seu objetivo
- Desenvolvimento da arquitetura: Se cria os desenhos da solução para as inúmeras fases de forma gradual.
- Planejamento de transição: Criação de roteiros de mudanças.
- Governança de arquitetura: Atividades e mudanças para se chegar a uma arquitetura alvo

Existem dois estilos de definição:

- Linha de Base Primeiro: Se avalia o estado atual e se vai criando o alvo.
- Alvo Primeiro: Alvo é elaborado em detalhes e depois de mapeia de volta para a linha de base.

Também se tem uma aplicação hierarquica

Esse tipo de iteração precisa da arquitetura de alto nível para orientar e **restringir a arquitetura** de forma mais detalhada.

### Aplicando o ADM em todo o panorama de arquitetura

A arquitetura pode ser mais abrangente (estratégica) ou mais detalhada (por capacidade), para se definir isso, o TOGAF utiliza o conceito de níveis e o Continuum Corporativo.  
Os níveis são framework que definem atividade operacionais e de mudança.

- Arquitetura estratégica: Para nível executivo
- Arquitetura de Segmento: Para um projeto, programa ou portfólio
- Arquitetura de Capacidade: Para um incremento evolutivo ou corretivo.

### Arquitetura de Segurança

Existem orientações de segurança no TOGAF, com passos que devem ser tomados e artefatos que devem ser criados. As áreas de preocupação dos arquitetos de segurança geralmente são:

- Autenticação: Identidade
- Autorização: Capacidades permitidas
- Auditoria: Dados Forenses
- Garantia: Testar e provar que se tem atributos de segurança
- Disponibilidade: Sem interrupção
- Proteção de ativos: Contra perda e divulgação não intencional
- Administração: Mudança de políticas e como pessoas a utilizam
- Gestão de Riscos: Tolerância a riscos

Os artefatos geralmente são: Regras, políticas, documentação de análise de risco, de classificação de dados, de custódia de ativos e etc.

### Arquitetura Orientada a Serviços (SOA)

O TOGAF descreve a Arquitetura Orientada a Serviço (SOA) como um estilo de arquitetura que simplifica o negócio através da interoperabilidade de suas partes, a estruturação de capacidades granulares bem definidas.

Usando serviços é possível identificar claramente as capacidades funcionais de uma companhia e evitar duplicidades.Benefícios:

- Abstrações e entregáveis de alto nível
- Articulação via diferentes perspectivas
- Identificar roteiros claros
- Avaliação de impacto
- Rastreabilidade

A arquitetura corporativa se torna uma base para implantação de uma abordagem SOA, ligando as partes interessadas, ligando negócio e TI, deixando claro os serviços que precisam ser desenhados e construídos. Sem isso, há acumulo de serviços, múltiplos SOAs em silos, baixa reutilização de serviços.

Os detalhes disso estão do TOGAF parte III, capítulo 22. Para se utilizar o TOGAF no SOA adaptações devem ser feitas para identificar entradas, metamodelos, artefatos e etc. Para isso a atividade preliminar deve ser bem conduzida.

Existem ferramentas específicas do The OpenGroup para o SOA: O SIMM, o SGVM.

# Capítulo 5 - Framework de Conteúdo de Arquitetura (*)

Fornece um metamodelo para artefatos de arquitetura. Dessa forma tudo o que é produzido está consistente e estruturado. Muitas vezes esse Framework com tudo que é produzido é chamado de “Arquitetura Corporativa”

Obs: Existem outros frameworks de conteúdo (ArchiMate e Framework Zachman) que podem ser usados em conjunto ou adaptados.

Existem três categorias para classificar novos produtos de trabalho produzidos:

- Entrega: Geralmente saída de projetos que podem ser assinadas formalmente
- Artefato: Descreve um aspecto da arquitetura.
    
    - Catálogo (lista de coisas)
    - Matrizes (Relação entre coisas)
    - Diagramas (imagens de coisas)
- Bloco de Construção: Componente potencialmente reutilizável de negócio, TI ou capacidade de arquitetura.
    
    - BCA ou Blocos de Construção de Arquitetura: Capacidade necessária para moldar os BCS
    - BCS ou Blocos de Construção de Solução: Capacidade para entregar a solução

## Metamodelo de Conteúdo

O Framework de conteúdo de arquitetura é baseado em um metamodelo que fornece uma definição para todos os blocos de construção da arquitetura. Preocupação para definir, gerar relações e representar de forma estruturada os blocos de construção com, por exemplo:

- Serviços de negócio
- Atores
- Aplicações
- Entidades de dados
- Tecnologias

O metamodelo possui: Núcleo e Extensões. Onde núcleo descreve um conjunto mínimo e extensões servem para uma modelagem mais específica. Extensões são opcionais.

O Metamodelo ajuda a estrutura mas, talvez não sejam úteis para todas as partes interessadas. Por isso, usar catálogos, matrizes e diagramas é feito para facilitar o entendimento.

- Catálogos: Lista de blocos de construção
- Matrizes: relações entre duas ou mais entidades
- Diagramas: Representação gráficas do conteúdo arquitetural

O resultado de uma arquitetura desenvolvida (ADM) é um número de BCAs definidos e populados no catálogo de arquitetura as suas relações (entre eles) em matrizes e a representação deles em um diagrama.

## Artefatos de Arquitetura

São produtos de trabalhos rotulados como artefatos que representam um modelo individual de um sistema, solução ou estado corporativo que podem ser reusados em vários contextos.

Ele não é um entregável (saída de um projeto). As entregas conterão artefatos e ele poderá existir em inúmeras entregas.

Conceitos adaptados da ISO 42010:2007

- Sistema: Conjunto de componentes para realizar função específica.
- Arquitetura: Organização de um sistema, com seus componentes, suas relações, o ambiente e princípios orientadores da criação e evolução.
- Descrição Arquitetural: Coleção de artefatos que documenta uma arquitetura. A Visão de Arquitetura é um artefato chave para a descrição arquitetural.
- Partes interessadas: Pessoas com papéis chaves e preocupações diferentes (indivíduos, equipes ou organizações)
- Preocupações: Interesses de pessoas chaves ou sistemas que determinam se um sistema será aceito: desempenho, confiabilidade, segurança, distribuição e capacidade evolutiva.
- Visão: Representação de um sistema a partir da perspectiva de preocupações. Modelos são selecionados para demonstrar a uma parte interessada que suas preocupações são abordadas de forma adequada no desenho.
- Ponto de Vista: Perspectiva da qual uma visão é tomada. Ou seja, como construir e utilizar uma visão a partir de um ponto de vista que é para o propósito de um público alvo.

Os artefatos recomendados pelo TOGAF são:

## Entregáveis de Arquitetura

O capítulo IV, no capítulo 36 fornece um ponto de partida para os entregáveis da arquitetura. Ou veja capítulo 3

## Blocos de Construção

É um termo abrangente, sendo um pacote de funcionalidades definidas para atender às necessidade de negócio. Cada organização deve decidir como deve ser definido, quais níveis de detalhes eles devem ser classificados.Pode ser:

- BCA: Grupos simples de funcionalidades como bancos, algumas ferramentas e etc
- BCS: Mais detalhados com as ferramentas, componentes, tipos de banco detalhados e etc.

São definidos na fase A como visões mais abstratas. Nas fases B,C e D cada arquitetura evolui essa visão abstrata e na fase E eles são transferidos para os BCS para que os detalhes da implementação sejam feitos.

# Capítulo 6 - O Continuum Corporativo

É um modelo para estruturar um repositório virtual e métodos para classificação dos artefatos de arquitetura e de solução. Mostram como eles evoluem e como podem ser reutilizados.Pode se ter um Continuum de Arquitetura e outro de solução para diferenciar o arquitetura e como a solução foi implementada.

O objetivo é evitar reinvenção e propor reuso, eliminando a ambiguidade e facilitar compreensão para possíveis conflitos.

O uso do Continuum aumenta os ativos de arquitetura e das soluções associadas a eles. Os ativos podem ser entregáveis da arquitetura “anterior” que estão disponíveis para reutilização. Outros ativos podem ser modelos de referência da indústria ou padrões de arquitetura tais como o TOGAF (MRT), ISO, Normas da industria (CVM, etc etc). Outro modelo que também pode ser incluído é o MR-III ou Modelo de Referência de Infraestrutura de Informações Integradas.

### Particionamento da Arquitetura

Criar partições ajudam a organizar e governar a arquitetura, para que:

- Arquiteturas de unidades organizacionais não se conflitam
- Equipes diferentes possam trabalhar de forma específica
- Reuso de partes (segmento) em um todo (visão corporativa)

Cada organização deve adotar o seu melhor modelo de partição e isso é feito na fase preliminar do ADM. Por isso, na fase preliminar se determina a estrutura da organização e como a arquitetura irá funcionar, as responsabilidades e relações entre as áreas. Uma vez que essa fase esteja concluída, cada equipe devem ter seu escopo e responsabilidade definida.

### Repositório de arquitetura

Para que o Continuum funcione é necessário que se tenha um repositório de arquitetura para se armazenar aquilo que é produzido. Os principais componentes dentro do repositório são:

- Metamodelo da Arquitetura: framework customizado
- Capacidade da Arquitetura: parâmetros, estruturas e processos
- Panorama da Arquitetura: Visão arquitetural dos blocos de construção e como estão em uso
- Base de Informações de Padrões: Quais padrões novas arquiteturas devem obedecer (padrões de indústria)
- Biblioteca de Referência: Diretrizes, modelos e aceleradores.
- Registro de Governança: Atividades de governança da corporação

O repositório da arquitetura é uma parte do repositório corporativo, esse, que suporta inúmeros outros documentos e processos.

# Capítulo 7 - Modelos de Referência do TOGAF

O TOGAF é uma arquitetura que fornece uma base sobre a qual arquiteturas e componentes de arquitetura podem ser construídos.

### MRT - Modelo de Referência Técnico

Essa arquitetura de fundação está contida no Modelo de Referência Técnica (MRT).O MRT é um modelo de taxonomia de serviços de plataforma genérica. O objetivo é dar uma descrição conceitual de um sistema de informação

### III-RM - Modelo de Referência de Infraestrutura de Informações Integrada

Ele concentra no software aplicativo. É um subconjunto do MRT mas expande partes como aplicativos de negócio e de infraestrutura.

# Capítulo 8 - Framework de Capacidade de Arquitetura

Parte VII do TOGAF, fornece uma referência para explicar como se estabelece a função da arquitetura dentro da corporação. Esse capítulo tem esse resumo:

- Estabelecendo uma Capacidade
- Comitê de Arquitetura
- Conformidade de Arquitetura
- Contratos de Arquitetura
- Governança de Arquitetura
- Modelos de Maturidade
- Framework de Competências

Cada um dos itens acima estão resumidos abaixo:

### Estabelecendo uma Capacidade de Arquitetura

Para implementar uma capacidade de arquitetura precisamos desenhar quadro domínios:

- Negócio: Destaca a governança, os processos, estrutura, requisitos e produtos da arquitetura.
- Dados: Define a estrutura do Continuum e o repositório.
- Aplicativo: As funcionalidades ou serviços de aplicativo para habilitar a prática da arquitetura.
- Tecnologia: Requisitos de infra para suportar o aplicativo de arquitetura e o Continuum Corporativo.

Ou seja, o que é preciso para que se crie uma estrutura de arquitetura dentro de uma organização, seus processos, governança, onde esses dados serão armazenados, se precisaremos de um aplicativo de apoio e quais tecnologias precisarão ser habilitadas.

### Governança da Arquitetura

Capacidade pela qual as arquiteturas são gerenciadas e controladas com um:

- Controle e monitoramento sobre os componentes e atividades de arquitetura.
- Assegurar conformidade com padrões internos, externos e regulações
- Criar processos para que tudo funcione
- Definir estruturas de decisão
- Praticas que as partes interessadas se sintam identificadas com a arquitetura

### Comitê de Arquitetura

É um estrutura de decisão responsável por resolver conflitos que possam surgir. Deve conter todas as partes interessadas por exemplo: time de negócios, arquitetos, engenheiros e gestores de programas.

Além disso, são responsáveis também por garantir que todas as informações disponíveis para tomada de decisão estejam ali, hajam consistências entre as inúmeras arquiteturas, se identifique componentes reutilizáveis, deem flexibilidade para que a arquitetura atenda ao negócio, garantam que haja conformidade com arquitetura e que as evoluções melhorem o nível de maturidade entre outros.

O Comitê também monitora e controla os contratos de arquitetura, enfim:

- Atribui tarefas de arquitetura
- Aprova formalmente produtos de arquitetura
- Resolve conflitos

### Conformidade da Arquitetura

Seguir uma arquitetura garante o correto desenvolvimento de aplicativos e sistemas. Se isso não acontecer uma boa justificativa deve ser apresentada. Para saber se um sistema está ou não em conformidade uma Estratégia de Conformidade de Arquitetura deve ser aplicada, incluindo:

- Avaliações de impactos em produtos e projetos da organização
- O processo (descrito abaixo) da Revisão de Conformidade de Arquitetura

### Framework de Competências de Arquitetura

É responsável para fornecer definições das competências e níveis de proficiência para profissionais/pessoal, interno ou externo. Termos como “Arquitetura Corporativa”e “Arquiteto Corporativo” são mal utilizados e definidos.

Portanto, fornece:

- Competências Genéricas: Como liderança, trabalho em equipe e capacidade de relacionamento.
- Competências de Negócios & Métodos: Casos de negócio, processos de negócio, planejamento estratégico.
- Competência de Arquitetura Corporativa: Modelagem, blocos de construção, papéis e aplicativos, integração de sistemas e etc.
- Competência de Gerenciamento de Projetos ou Programas: Gerenciamento de mudança, métodos e ferramentas para gerenciamento de projetos.
- Competência Gerais de Conhecimento de TI: Mediação, gerenciamento de ativos, migração, SLAs,
- Competências Técnicas de TI: Conhecimento de Engenharia de Software, segurança, dados
- Ambiente Legal: Leis de proteção de dados, legislação, fraudes e etc.

# 0 - Capa, prefácio, organização e termos importantes

## Prefácio

O documento é indicado para arquitetos corporativos, de negócio, de TI, dados, sistemas, soluções e gerentes seniores que precisam de uma primeira introdução ao TOGAF.

O TOGAF tem uma estrutura modular que pode ser adotado em partes e gradualmente. Ele apresenta um conjunto de conceitos e orientações para criar uma arquitetura de desenvolvimento por grandes corporações.

Conceitos como:

- Participar uma arquitetura em uma organização
- Armazenar os modelos e documentos
- Capacidades como organização competências, papéis e responsabilidades para operar uma arquitetura

Na parte III onde existem orientações e técnicas possui um conjunto de materiais de apoio para serem aplicados, como eles se relacionam com arquitetura orientada a serviço e arquitetura de segurança.

### Organização

Esse resumo será organizado pelos capítulos e também pelas fases do TOGAF a fim de consolidar melhor os conceitos e como eles devem ser aplicados.

### Termos

Capacidade

- Habilidade de um sistema atender a um conjunto específicos de requisitos ou funcionalidades

Continuum Corporativo

- Mecanismo para classificar artefatos de arquitetura e de soluções a medida que evoluem
    

Arquitetura (ISO 42010:2007)

- Organização de um sistema, com seus componentes, suas relações, o ambiente e princípios orientadores da criação e evolução.

Arquitetura (segundo TOGAF)

- Descrição formal de um sistema ou um planejamento detalhado do sistema no nível de componente para orientar a sua execução.
- Estrutura dos componentes, seus inter-relacionamentos, e os princípios e orientações que regem sua concepção e evolução ao longo do tempo.

TOGAF

- O TOGAF é uma arquitetura que fornece uma base sobre a qual arquiteturas e componentes de arquitetura podem ser construídos

