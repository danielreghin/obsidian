---
tags: 
revisões: -1
criado: ""
título_alternativo:
---
Veio como evolução da [[Arquitetura Data warehouse]] ao passo que permitiu o uso de dados de fontes não estruturadas como dados de mídias sociais, logs, IoT, dados de navegação. Foi possível através do advento do Hadoop e do [[Hadoop]]. 

Permite armazenar dados como CSV, XML, Json, imagens, áudio, bases de dados e vídeos.  

![[Pasted image 20241204155426.png]]
## Características
- Suporte a vários formatos: Suporta dados estruturados como base de dados, semi estruturados como xml e json, não estruturados como textos, áudio e vídeo.
- Schema on reading: Não há restrição de armazenamento de dados. Primeiramente é gravado o dado cru (raw) no formato AS IS, para ao ler, fazer a validação do schema.
- Armazenamento imutável: Não se pode alterar o dado gravado em um HDFS, só se pode adicionar. Soluções modernas em nuvem também têm essa característica.
- Equipamentos básicos: Os equipamentos não precisam ser especializados, pode se usar um HD e máquina comum para armazenamento.
## Benefícios
- Suporta AI/ML por acessar os dados raw.
- Suporta BI: Com o uso do Apache Hive é possível armazenar dados estruturados em cima do HDFS para permitir a criação de relatórios.
- Carga Real Time: Suporta carga via batch ou real time com uma latência de segundos. Para latências menores ver outras soluções. 
- Custos reduzidos: Utiliza hardwares comuns.

## Limitações e desafios
- Baixa performance para BI: HDFS e Hive não são as melhores ferramentas para BI.
- Não suporta [[ACID]]: Base é imutável
- Baixa qualidade: Como os dados são raw e não há validações como no datawarehouse, a baixa qualidade de dados.
- Controle de acesso limitado: Não há uma grande granularidade de controle de acesso.
- Risco de virar um ralo de dados: Os dados são gravados sem critério e armazenados por muitos anos, virando um depósito sem utilidade de dados, pelo baixo critério e controle.

Possui alta disponibilidade, fácil escalar, possui dados estruturados, semi e não estruturados, bem como suporte operações com ML e IA. 

## Soluções em Cloud
Cloud Data Lake
	- Amazon S3
	- ADLS
	- GCS
## Diferença entre [[Arquitetura Data warehouse]]
De forma resumida as diferenças podem ser detalhadas abaixo:
![[Pasted image 20241205111758.png]]

# Fonte
https://learning.oreilly.com/library/view/practical-lakehouse-architecture/9781098153007/ch01.html