---
tags:
  - tecnologia/linguagem
revisões: 0
criado: 2024-09-18
título_alternativo: protobufs
---
É uma forma de representar e transferir dados  entre computadores. Os dados são transferidos de forma binária diferentemente de JSON que é de forma que um humano possa entender. 
A partir dessa representação se pode gerar códigos fontes em diversas linguagens de programação para representar e transferir os dados.
Portanto, protobufs:
- Representam dados 
- Representam serviços
- Geram objetos e serviços em linguagens através de um compilador

Portanto:
- Dados serializados são menores porque são binários
- É rápido de serializar
- Os dados não são compreendidos por seres humanos.
- São [[fortemente tipados]] (type-safety)
- Schema de fácil leitura.

Os objetos são organizados em mensagens que podem ser armazenadas no mesmo arquivo. 
## Mensagens
### Tipos de dados básicos
Os tipos de dados são os seguintes, com os seus valores defaults. Não existe valores nulos, todos receberão os seus valores defaults.  

Não é possível definir constraint de campos de dados, por exemplo: valores devem ser de 0 a 55, isso é feito via código e adicionar no comentário Veja: https://github.com/googleapis/googleapis/blob/master/google/type/date.proto

- Inteiro: **int32**. Default: 0
	- Outras maneiras, específicas para performance e outros casos de uso são: int64,uint32,uint64,sint32,sint64,fixed32,fixed64,sfixed32,sfixed64
	- int32
		- 0 a 4.294.967.295
		- -2.147.483.648 a 2.147.483.647
	- int64
		- 0 a 18.446.744.073.709.551.615
		- -9.223.372.036.854.775.808 a 9.223.372.036.854.775.808
	- uint32 e uint64
		- Não permitem valores negativos
	- sint32 e sint64
		- São melhores para codificar valores negativos.
	- fixed32 e fixed64
		- Fixed32 utilizam 4 bytes de forma constante, melhor se os valores foram maiores do que 2^28
		- Fixed64 utilizam 8 bytes de forma constante, melhor se os valores foram maiores do que 2^56
- Ponto flutuante: **float** (32 bits) ou **double** (64 bits). Default: 0
- Booleano: **bool**. Default: false
- Texto: **string** (deve ser UTF-8 ou 7-bit ASCII). Default: ""
- Bytes: **bytes** (qualquer tipo de dados adiciionais, imagens, por exemplo). Default: bytes vazias

```
syntax="proto3";
message Person{
    int32 age = 1;
    string first_name = 2;
    string last_name = 3;
    bytes small_picture = 4;
    bool is_profile_verified = 5;
    float height = 6;
}
```

A tag (numeação) dos campos são mais importantes do que o nome. Tags de 1 a 15 utilizam 1 byte, de 16 a 2047 usam 2 bytes, portanto, utilize 1 a 15 para dados mais frequentemente populados.

- Lista: **reapeated**. Default: lista vazia

```
repeated string phone_numbers = 7;
```

- Enum: **enum**. Default: O primeiro item da lista e deve começar com a tag 0, que é o valor padrão.
```
   enum EyeColour{
        UNKNOWN_EYE_COLOR = 0;  // Valor default
        EYE_GREEN = 1;
        EYE_BROWN = 2;
        EYE_BLUE = 3;
    }
    // Veja os tipos de dados acima    
    EyeColour eye_colour = 8;
```

Veja um exemplo de enum: https://github.com/googleapis/googleapis/blob/master/google/type/dayofweek.proto

### Tipos de dados avançados
Abaixo tipos de dados avançados
- OneOf
	Somente um valor pode ser usado e não podem ser repetidos.
	`message MyMessage{`
		`int32 id=1;`
		`oneof example_oneof{`
			`string my_string=2;`
			`bool my_bool=3;` 
		`}`
	`}`
	O último valor a ser 'setado' é o que será enviado.

- Maps
	É usado para fazer mapeamentos escalares (exceto float/double). Não podem ser repetidos.
	message MyMessage{
		int32 id=1;
		map<string,Result> results=2;
	}
- Well Known Types
	São campos feitos pelo Google com mais funções, como null
	https://protobuf.dev/reference/protobuf/google.protobuf/

	Timestamp e Duration são  exemplos:
	![[Pasted image 20240929151515.png]]

### Duas mensagens no mesmo arquivo
É possível ter um tipo dentro de uma mensagem ao passo que ele fica restrito àquela mensagem. 

```
message Person{
	Date birthday = 1;
}

message Date{

}
```

Também é possível ter uma definição de uma mensagem dentro de uma própria mensagem. O caminho completo, do exemplo abaixo é: **Person.Address**

```
message Person{
	message Address{
		string city=1;
		/// outros
	}
	Address address = 1;
}
```

### Alterando atributos
É possível manter a compatibilidade de códigos quando se altera um arquivo ".proto" se algumas regras forem respeitadas. Atributos podem serem inseridos e retirados. 

Para funcionar é necessário seguir algumas regras.
- Não altere as tags dos campos existentes
- Se remover campos, não reutilize as tags, colocando-as como obsoletas ou usando a tag reserved.
- É possível alterar o nome das variáveis, o protobuf só conhece o número da tag.

Regras:
- Ao adicionar novos campos, o código antigo que não os usa, irá ignorá-los.
- Ao remover um campo, o código que os usa. assumirá o valor padrão/default.

#### Tag reserved
Ao remover um atributo utilize a tag **reserved**, como abaixo, tanto para reservar a tag, quanto para reservar o nome do campo. Uma alternativa é renomear o campo, adicionando alguma indicação no início do atributo OBSOLETO_first_name. Nunca remove uma tag reserved.
`message MyMessage{`
	`reserved 2,15,9 to 12;`
	`reserved  "first_name","other";`
	`int32 id=1;`
`}`
#### Valores default
Interprete os valores padrões com cuidado, pois eles podem representar que o usuário o deixou em branco, ou que na verdade o valor não existe.

- Garanta que eles não tenham significado para o código.
- Use as mensagens do google (anotar mais adiante)
#### Enum
Podem evoluir também com as mesmas regras, adicionar, remover ou reservar. O valor padrão sempre será o com o a tag 0;

`enum DayOfWeek{`
	`DAY_OF_WEEK_UNSPECIFIED = 0;`
	`MONDAY=1;`
	`TUESDAY=2;`
	`...`	
`}`
### Convenção de nomes
São esses a convenção de nomes
- CamelCase para nome das mensagens
- userscore_separated_names para atributos
- CamelCase para nome de enum e CAPITAL_WITH_UNDERSCORE para atributos

## Importação e Pacotes
Para se ter classes em dois arquivos diferentes é necessário usar da importação. 
```
data.proto
	message Date{}

pessoa.proto
	syntax="proto3";
	import "caminho/data.proto"
	message Pessoa{
		Date data_aniversario = 1;
	}
```

Para se usar pacotes, se pode definir de forma completa o caminho de um arquivo / classe. Nesse momento o caminho ficará completamente definido.
```
data.proto
	package my.date;
	message Date{}

pessoa.proto
	syntax="proto3";
	package person;
	import "caminho/data.proto"
	message Pessoa{
		my.date.Date data_aniversario = 1;
	}	
```

## Serviços
São um grupo de endpoints que fornecem o acesso remoto a uma aplicação. O framework mais usado é o [[gRPC]], mas existem outros
![[Pasted image 20240929152827.png]]

## Geração de código

### Gerando código em Dart
Ver depois
https://protobuf.dev/reference/dart/dart-generated/

### Opções no momento de geração
Cada linguagem tem parâmetros específicos que fazem funções específicas
![[Pasted image 20240929151632.png]]



# Fonte
Capturar os tipos padrões do Goggle. 
https://github.com/googleapis/googleapis/tree/master/google/type
https://protobuf.dev/

