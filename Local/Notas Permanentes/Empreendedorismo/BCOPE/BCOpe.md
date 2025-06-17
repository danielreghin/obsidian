---
tags:
  - empreendedorismo/bcope
revisões: 0
criado: 2025-01-16
título_alternativo:
---
Aplicação  que irá ser um provedor de soluções para bancos em todo tipo de inovação necessária. Também servirá como chassi para qualquer tipo de aplicação a ser desenvolvida.

A aplicação se divide em três grupo de componentes:
- **common_library**
	Bibliotecas que são comuns entre o backend e frontend. A [[Estrutura do Common para BCOpE]] pode ser consultada para maiores detalhes
- **backend**
	A [[Estrutura Backend para o BCOpE]] deve ser criada por cada módulo a ser desenvolvido. 
- **frontend**
	A [[Estrutura de Frontend para o BCOpE]] é única para cada aplicação.

## Relação Backend e Frontend
A estrutura de componentes se relacionam conforme abaixo.

![[Pasted image 20250211181630.png]]
### Transferência de objetos
A transferência de objetos REST ou GRPC são diferentes entre si. E seguem conforme a forma abaixo.
#### Objetos REST
Os objetos seguem o seguinte formato:

**Sucesso**: 
body: {
	 objeto (vindo do objeto toJson do freezed)
	 }
	statuscode: código do sucesso
	
**Fracasso:**
body: {
        'message': message,
        'errors': errors,
        'logId': logId,
      },
      statusCode: statusCode,
#### Status Code: 

| Tipo    | Código | Detalhe |
| ------- | ------ | ------- |
| Sucesso | OK     |         |
| Sucesso |        |         |
#### Lançamento de erros
Quando há um erro, uma exception é lançada no lado do cliente
	DioRemoteServiceException

## Atalhos
- Ctrl + Alt + (+): Mostra arquivos ocultos 
- Ctrl + Shift + P: Executar tarefas para compilação, subir servidores e compilação

Para subir o servidor ir para a mesma janela de subida do servidor 

## Próximas atividades


Fazendo código de testes de GRPC
- Lançar exceções com logId e com mensagens adequadas de erros. (ver: https://grpc.io/docs/guides/error/)

- Não estou conseguindo chamar o backend do frontend. O Derry do frontend está dando pau. Preciso arrumar isso primeiro.

Olhar o [[Backlog de atividades - BCOPE]] para maiores detalhes. e