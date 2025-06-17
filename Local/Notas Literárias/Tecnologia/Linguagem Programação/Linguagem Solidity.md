---
tags:
  - tecnologia/linguagem
revisões: -1
criado: ""
título_alternativo:
---
Uma linguagem para a [[Blockchain]]. Permite a criação de variáveis, métodos e emissão de eventos, para quem estiver escutando na blockchain possa ouvir. 

Os tipos de dados são os abaixo:
 
```
uint8 a = 1; // 8-bit inteiro sem sinal (0 a 255)
uint16 b = 65535; // 16-bit inteiro sem sinal (0 a 65535)
uint256 c = 1000000000; // 256-bit inteiro sem sinal (0 a 2^256-1)
int8 d = -128; // 8-bit inteiro com sinal (-128 a 127)
int16 e = 23767; //8-bit inteiro com sinal (-32768 a 32767)
int256 f = -1000000000; // 256-bit inteiro com sinal (-2^255 a 2^255-1)
bool isReady = true;
bool hasBalance = false;
address owner = 0x1234567890123456789012345678901234567890;
address payable payableOwner = payable(owner);
string greeting = "Hello,World!";
string name = "Alice";
enum State {
	Created,
	Locked,
	Inactive
}
State public state;
```

Os métodos são como o abaixo:
```
function getGreeting() public pure returns (string memory) {
	return "Hello, World!";
}
```

Os métodos são declarados com os seguintes modificadores:
De visibilidade:
- public (acessível fora do contrato e dentro do contrato)
- internal (acessível dentro do contrato, mas também dos contratos que herdarem esse contrato  herança),
- external (somente acessível externamente, não é acessível dentro do contrato.)
- private (somente acessível dentro do seu contrato)

De eficiência:
- pure (não consulta ou altera a blockchain)
- view  (consulta a blockchain em algum momento)

Os eventos são criados da seguinte forma:
```
event Added(uint value);
```

E são emitidos da seguinte forma:
```
emit Added(_c);
```

É permitido criar modificadores para uma função, para que ele seja executado antes ou depois dessa função.
```
modifier onlyOnwer() {
	// Cria um modifier para validar a mensagem antes de executar a função.
	require(msg.sender == owner, "Not the contract owner");
	_;
}
```

Assim, a validação acima será chamada antes de se executar a função abaixo
```
function getNameViewOnlyOwner() public view onlyOnwer returns (string memory){
	return name;
}
```

## Trabalhando com herança
É possível trabalhar com herança em solidity. Abaixo o exemplo de duas classes que trabalham com herança.

Classe Base
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.24;

// Exemplo de classe base para ser herdada
contract Base {
    uint private data;
    event DataUpdated(uint oldValue, uint newValue);

    constructor(uint _initialData) {
        data = _initialData;
    }

    function setData(uint _data) public virtual {
        emit DataUpdated(data, _data);
        data = _data;
    }

    function getData() public view returns (uint) {
        return data;
    }
}
```

Classe que herda a classe base
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.24;

import "./Base.sol";

contract Derived is Base {
    bool public isDataUpdated;

    constructor(uint _initialData) Base(_initialData) {
        isDataUpdated = false;
    }
    function setData(uint _data) public override {
        super.setData(_data);
        isDataUpdated = true;
    }
    function resetUpdateStatus() public {
        isDataUpdated = false;
    }
}
```

# Fonte
Treinamento Alura, Solidity - Criando Smart Contracts e Tokens