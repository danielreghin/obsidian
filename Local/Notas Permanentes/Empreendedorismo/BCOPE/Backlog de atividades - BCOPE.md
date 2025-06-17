---
tags: 
revisões: -1
criado: 
título_alternativo:
---
## Próximos Atividades
- Entender como exceções trafegam do backend para o frontend 
- Fazer Classe de Testes para o backend
- Criar um frontend que chama um GRPC e um outro que chama um REST

## Backlog (arquivo antigo)

BACKEND
 - OK Criar filtro por nome e CPF
 - Criar paginação: https://medium.com/@gdr2409/pagination-with-postgresql-18e0b89e0b1c
                  : https://www.cybertec-postgresql.com/en/pagination-problem-total-result-count/
                  : https://dev.to/pragativerma18/unlocking-the-power-of-api-pagination-best-practices-and-strategies-4b49
                  : https://www.solwey.com/posts/ids-integer-vs-uuid-vs-ulid (Ler último comentário) - Ter um ID e um ULID para manter o id privado.¬
 
   
   - URGENTE -> FECHAR CONEXAO POSTGRES
   - Ajustar design de api para ter padrão: data, erro, paginacao
  - Testar se a regra de mensagens de log e retorno da API + ID de Log
  - Implementar gravação de log em alguma ferramenta de Cloud, por enquanto colocar na output do console
  - Fazer teste de API/backend com cobertura.
  - Delete não está funcionando corretamente, sem resposta
  - Colocar mensagens em arquivo único de constante e internalizar
 - Olhar em projetos de API se há algum código de mensagem detalhado
 - Melhorar os Validates dos DTOs de entrada para que os erros sejam melhor explanados e/ou retornados
 - Ajustar o insert para que dados nulos não sejam gravados
 - Colocar documentação OpenApi
 - Colocar KRONOS   
   - Log de Auditoria
   - Log de erro
   - Log de Performance
   - Log de Cobrança
   - Monitoramento
   - O que mais tiver no Kronos

FRONTEND
 OK - Formulário com obrigatoriedade genérica (*) e validação automática.
  - Mensagem de sucesso não funciona corretamente.
  - Fazer formulário genérico -> Mensagem, erro, loading e status

Fazer página de erro genérica.
Estudar o FlutterHoocks

Arrumar o código: Dialogo em local único.
Fazer tratamento de layout (internacionalização, teclas de atalho)

-- Fazer artigo no Medium para Flutter_hocks + Riverpod
 - Corrigir o JWT no backend para buscar corretamente o usuário e validar o login

Meta: 26/11/2023

Todo dia estudar algo
GoRouter
Riverpod
Base Flutter
Fluent_UI
dart_frog


14/07/2023 - META
-   Gerar Front End (com criação de form) e integrar com backend
-   Colocar segurança nas APIs
-   Gerar documentação de API
-   Planejar o restante.... :)
-   Criar a ferramenta de teste do backend
-   Padronizar a gravação de logs tratados e não tratados
-   Arrumar os Failues e Exception para casar com erros 400, 500 e etc etc.
-   [OK] Tentar ver se há alguma forma de mapear os atributos de um método com o nome Json e nome da tabela
-   Estudar como fazer Joins entre bases de dados / melhores práticas
-   No Controller melhorar o gerar Json
-   Testar se a cada request um objeto de conexão é criado
-   Alterar a forma como os dados de parâmetros são carregados do .env
-   Gerar log de aplicação no Google Cloud Log
Estudo
 - Testar outros frameworks API
    - Conduit
 - Testar soluções de ORM
