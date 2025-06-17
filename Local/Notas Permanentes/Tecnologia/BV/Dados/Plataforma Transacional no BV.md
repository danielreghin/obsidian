---
tags: 
revisões: -1
criado: 
título_alternativo:
---
Contém os dados de transações de sistemas do BV.
São três os bancos de dados relacionais no BV: Mysql (Recomendado), Postgree e Spanner.
### Bancos SQL
#### Cloud SQL for MySql
Serviço gerenciado utilizado através do GCP. Usado quando se quer um banco de dados relacional com suporte a operações [[ACID]]. 

Cenários de uso:
- Atômico conectando
- Spring Batch
- Dataflow
- PowerBi

É monitorado pelo Nimsoft, tem alta disponibilidade de 99,95%. Possui escalabilidade horizontal e vertical. É um serviço oferecido via Paas. 
#### Cloud SQL for Postgree
É um cenário utilizado apenas para pacotes que precisem utilizar essa solução, não podendo ser utilizados por aplicações desenvolvidas no BV. O pacote pode estar OnPrem ou na GCP, mas o banco estará no GCP. O próprio GCP gerencia backups, atualizações de software, patches de segurança. 
#### GCP Cloud Spanner
Banco de dados que garante um tps maior comparado as outras soluções. Tem alta disponibilidade e alta escalabilidade. Suporta o padrão ANSI-2011, mas pode receber migração de outros bancos de dados relacionais. Gera automaticamente grafos, tem integração com Lanchain e VertexAI. 
#### Bancos OnPrem descontinuados
Sybase é uma solução descontinuada, bem como SQL Server e Oracle. 
### Bancos NoSQL
Os bancos desse tipo são recomendados quando:
- Grandes processamentos, não relacionados e com mudança constante.
- Dados sem esquema ou que o esquema é definido pelo aplicativo.
- Quando alto desempenho é mais importante do que consistência forte.

O teorema CAP descreve o comportamento de bancos e o No SQL só pode ter alguns cenários:
- Disponibilidade (Sempre apresenta alguma resposta) + Tolerância a particionamento (Sempre disponível)
- Consistência (ACID) + Disponibilidade 
- Consistência + Tolerância ao Particionamento

Boas Práticas
- Pense em escalabilidade
- Não use Joins
- Não use ORM
- Mantenha os documentos com tamanho pequeno
#### Firestore (Firebase)
Armazena documentos através de chave-valor. Ideal para. Recuperar dados em tempo real. colaboração, mensagens, jogos. Não deve ser usado qual há cenário de alta consistência, Joins, unios, se o documento exceder 1mb. Têm cobrança flexível, por documento utilizado.  É um banco de dados Servless. Considerar usar funções sem servidor do firebase que respondam à eventos.

Cenários de uso:
- Atômico com Springboot
- Cloud Functions
- Trigger de transação que grava em uma fila do Pub/Sub
#### Memory Store for Redis
É uma estrutura de armazenamento de chave valor que está disponível em memória.  Existe um padrão de armazenamento de informações que tem como objetivo ter responsabilidades diferentes para escrita e leitura. Um Atômico escreve no Banco de dados relacional e também do REDIS e outro apenas lê do REDIS, acrônimo para REmote, DIctionary Server.

Cenários de uso:
- Um atômico grava no banco relacional e também do Redis para posterior uso de outro atômico.
- Atômico A carrega dados, atômico B carrega dados e o orquestrador armazena os dados agregados no cache do redis.
- Atômico tenta buscar os dados no cache do redis, caso não encontre os dados vai no banco de dados.
- Pode-se ter no UC4 também o armazenamento de dados em cache.
- Armazenamento de conteúdos estáticos como cabeçalhos, rodapés que não mudam com frequência.
- Cache de sessão com informações de carrinho de compra.
#### Cloud BigTable
Recomendado quando se precisa de alta volume de dados (terabytes/petabytes), abaixo disso a Google não recomenda a sua utilização.  É um banco de dados wide-column. Têm uma alta taxa de transferência 220 MB/s. Não usar com armazenamento HDD e nem quando os dados não iniciarem na faixa do Terabyte. Se também a prioridade não for baixa latência e alto fluxo de transações usar o Firestore. 

Cenários de uso:
- Operações em lote do MapReduce (armazenamento de alto volume distribuído Hadoop)
- Processamento e análise de Stream
- Aplicativos de Machine Learning
- Dados temporais
- Dados de IoT
- Dados financeiros como histórico de transações, cotações.
- Dados de Marketing como histórico de compras e preferências de clientes.

Quando não usar:
- Se precisa ter consultas SQL com suporte à ACID, use Cloud SQL
- Se precisa de processamento analítico, use BigQuery
- Se precisa de processamento em memória, e baixa latência (memory Store)
- Sincronizar dados entre usuários em tempo real (Firebase Realtime Database)
