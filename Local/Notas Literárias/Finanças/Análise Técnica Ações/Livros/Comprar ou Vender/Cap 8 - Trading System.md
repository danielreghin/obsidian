---
tags:
  - finanças/análise_técnica
  - livro
revisões: 0
criado: 2025-01-03
título_alternativo:
---
## 8 - Trading System
Para se ter sucesso na negociação de ativos é necessário se criar um método de negociação. Esse método precisa ser pré-testado para ver a sua validade e uma vez validado pode ser seguido, tanto manualmente quanto automaticamente através de robôs.

Importante se determinar o objetivo, técnicas de análise e regras de compra e venda. Um sistema de negociação evita que se perca nos inúmeros gráficos, na falta de disciplina e na falta de controle emocional.

Negociação na bolsa não é sobre prever o futuro e sim criar cenários onde se avalie a probabilidade dele acontecer. O cenário é planejado antecipadamente e deve-se reagir a cada mudança do cenário.
### Metodologia
- Escolha um período de negociação (diário, intradiário)
- Regras de entrada e filtros (indicadores
- Regras de saída
- Backtesting

Para o período de negociação, se intradiário, se utiliza 15 minutos. Escolha ativos líquidos. Para o backtesting, faça testes por um período passado e veja a performance. Só utilize o conjunto de indicadores e regras se o teste obtiver sucesso contra os fracassos.

**Exemplo**

Um método de trading automatizado por ser vantajoso para alguns ativos e para outros não. O autor na pág 140 descreve um método.

Compra: Quando um CandleCode cruzar a banda inferior (Banda de Bollinger). Saída: inversão do indicador. Se replicar essa regra automaticamente para VALE e PETRO os ganhos foram positivos para para outros passeis não.

Para o autor um sistema automatizado é mais um aliado do que um substituto

### Modelo Turtle
Sistema que foi desenvolvido por Richard Dennis em 1983 que fez com que qualquer pessoa sem grande experiência prévia pudesse operar.

- Estratégia básica: Seguir tendência
- Diversificar ativos
- A posição é inversamente proporcional a volatilidade do ativo
- Entrada: Breakout (Rompimento da máxima). Após uma oscilação após isso, gera um novo empuxo para cima, com alta volatilidade.
- Período: Breakout 20 dias ou Breakout 55 dias.
- Stop: Financeiro com no máximo 2% da carteira
- Saída: Quando Breakout 20 dias (saída mínima de 10 dias). Quando Breakout 55 dias (saída mínima de 20 dias).
- Zerar automaticamente: Quando há um breakout na direção contrária

Para esse método funcionar há de ter muita disciplina. No mercado brasileiro é difícil de seguir dado a pouca quantidade de ativos.
