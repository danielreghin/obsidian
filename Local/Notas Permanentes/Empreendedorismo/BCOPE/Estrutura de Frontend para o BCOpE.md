---
tags: 
revisões: -1
criado: 
título_alternativo:
---
## Fluxo de dados na página
O estado dos atributos e variáveis são controlador via Flutter Hooks.
Para acessar o backend, primeiro se captura o dados dos hooks e passa para um controller que chama o backend.. O Controller é gerenciado via Riverpod.

![[Pasted image 20250121115817.png]]


## Navegação
Cada módulo tem uma pasta com o nome 
	/routes
Nela é possível encontrar as rotas de todas as navegações, dos menus e fora dos menus.
	modulo_menus.dart
		Logal que tem os itens de menu
	modulo_routes.dart
		Todas as rotas para as páginas
## Classes primitivas escritas
Todas as classes próprias são chamadas de 
	CustomField
	CustomFormField
	CustomForm
	CustomPrimitive

## Desktop - Aplicativo
A configuração do desktop com menu, área interna e footer são configurados no:
	DesktopPage
## Rotas de navegação
As rotas de navegação são configuradas no provider 
	*goRouterProvider*
Nesse arquivo que se configura o local padrão de abertura do aplicativo. 
Temos uma configuração por cada módulo
	rotasCoreProvider
	rotasAccountProvider
	rotasCoreFooterProvider
	rotasCRMProvider
	rotasLoanProvider
	rotasPersonaProvider
## Cores
Os objeto que contém as cores do app é o 
	*AppThemeModel*
Esse objeto é configurado no Riverpod e é acessado ao longo do app pelo método watch. 
	AppThemeController
De qualquer maneira o fluent_ui tem uma configuração que é feita no *FluentThemeData*), tanto uma versão dark quanto uma light:
	*BCOpeApp*
A configuração pluto grid é feita no objeto *PlutoGridStyleConfig* que está no:
	SearchPageMixin.plutoGridConfiguration

