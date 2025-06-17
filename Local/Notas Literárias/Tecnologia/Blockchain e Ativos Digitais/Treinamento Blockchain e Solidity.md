---
tags: 
revisões: -1
criado: ""
título_alternativo:
---
É um treinamento que tem como objetivo dar uma visão completa sobre blockchain a linguagem de programação Solidity e fazer um projeto de exemplo.
Pré-requisitos
- Instalação do GIT, CURL no Linux
- Instalação do ASDF e Node
- Instalação do Foundry
Ele inicia o treinamento instalando o pacote ASDF e também o node, curl e git
## Ativos Digitais
A nossa vida está baseada no on-line, nosso cpf é digital, a compra de um ingresso é digital, um livro e etc. No mundo digital se banalizou a propriedade do que é digital, diferente do físico que se tinha a propriedade física do ativo (livro, fotografia). A cópia de livros eram mais difíceis e hoje são mais fáceis.  Com a mudança do digital, houve o declínio do valor. 

Desafios para esses ativos:
- Cópias infinitas
	Pode-se ter cópias infinitas do ativo com a mesma qualidade. 
	O dono do ativo não sabe quem o têm
- Propriedade 
	Se pode copiar um documento e repassar para outra pessoa, como você fosse o dono.
- Dependência sobre validade
	Somos dependentes de alguma entidade para saber se o documento digital é valido. Por exemplo, uma CNH, dependemos do DETRAN para que nos diga se ainda está valida.
		
E para os dinheiros, como podemos  digitalizar o dinheiro da mesma forma que enviamos um PDF. Trocar da mesma forma que trocamos o dinheiro.
## Blockchains
É uma infraestrutura de validação de dados que ficou popularizada com o Bitcoin em 2008, porém, ela é bem mais antiga do que isso. Para maiores detalhes acesse: [[Blockchain]].

Como aplicação, é  uma forma de transferir algo pela internet sem intermediário, como um dinheiro. Garante a autenticidade e envia a cópia não autorizada de ativos digitais. 

Uma implementação da Blockchain é o bitcoin. Outra é o Etherium que traz novas funcionalidades
### Bitcoin
A [[Bitcoin]] foi a primeira implementação da Blockchain a ser bem sucedida.
### Etherium
A [[Etherium]] é  uma implementação da blockchain que estende as suas funcionalidades permitindo que se escrevam programas. Portanto se pode submeter aplicações que estejam disponíveis nessa infraestrutura. 
## Tokens
É um padrão de contrato que utilizamos para criar os meios de troca digitais. Representam a propriedade de ativos e são usados para facilitar a emissão e e negociação 

Os ativos digitais são armazenados em um "container" ou **tokens**. Qualquer item pode ser armazenado nesse rede. Os containers são transferidos facilmente. Portanto, um fotógrafo pode criar um token que representa a imagem dele. Quem tem a propriedade da foto é àquela registrada.  Serve como um cartório digital.

Existem dois padrões para se criar um contrato:
### Padrão ERC-20
Utilizado para tokens fungíveis que possuem um valor associado, como pontos de fidelidade ou uma moeda. Pode-se criar moedas digitais dentro da Etherium. Existem algumas regras para:
- Como os token se movem entre endereços
- Permitem que terceiros usem seus tokens com permissões
- Define como verificar o saldo de um endereço
https://ethereum.org/en/developers/docs/standards/tokens/erc-20/

O exercício feito abaixo segue esse padrão. 
### Padrão ERC-721
Utilizado para identificar ativos únicos como os NFTs. Eles têm uma identificação única e por isso são indivisíveis. 
- Somente uma pessoa é dona da propriedade.
- Permite associar metadados com informações adicionais (imagem, descrição)
- Define como são comprados, vendidos e gerenciados.

https://ethereum.org/en/developers/docs/standards/tokens/erc-721/
### Bibliotecas de padrões / OpenZepellin
Para facilitar a implementação existem bibliotecas de que são baseados nos padrões da indústria como ERC-20 e outros. Essas bibliotecas passaram por auditoria e validações.  Uma delas é o [OpenZeppelin](https://www.openzeppelin.com/).  
Ela é uma biblioteca de código aberto para contratos inteligentes. 

Veja um exemplo:
![[Pasted image 20241029095203.png]]
## Smart Contracts
São programas que são implantadas na blockchain e executam determinadas ações. São os aplicativos descentralizados **dApps**. Eles são desenvolvidos com o Solidity, que é uma linguagem de programação.
- Linguagem de programação: Solidity
- As duas ferramentas são: Hardhat e Foundry
- Biblioteca de integração: Web3.js e Ethers.js (Integrar o sistema com a blockchain)

É um conceito que veio lá dos anos 90 proposto por Nick Szabo, que propôs um contrato que seria auto executado, uma vez que as condições propostas fossem atendidas. Uma analogia é o de máquinas de refrigerante que uma vez que se paga, o contrato foi atendido e o refrigerante cai para ser consumido.
### Ferramentas

- Linguagem de Programação: [[Solidity]]
- IDE: Existe a RemixIDE da própria Etherium. Tem um compilador solidity integrado e uma simulação da blockchain. https://remix.etherium.org

# Exercícios
### Subindo um token para a blockchain
- Acessei o metamask e adicionei a rede "Polygon Amoy Testnet". 
- Acessei um faucet https://faucet.polygon.technology/ para me dar crédito para poder executar a transação de adicionar um token na rede blockchain.
- Acesso o VSCode e o projeto 3876-blockchain-projeto_incial
- Dentro da pasta "src" colei o seguinte comando
	
```
forge create --rpc-url https://rpc.ankr.com/polygon_amoy --private-key minhachaveprivada src/MeuPrimeiroToken.sol:MeuToken --constructor-args 10000000
```

- Copiei o recibo da transação e os detalhes:
```
Deployer: 0xf8C5CdE966591176722df080a520B98dbBCB3812
Deployed to: 0x4DD9b81Fc3cA295860E241a6ce6755881B447803
Transaction hash: 0xb94b8814a7d27c17ad27198c03b90e78d3bdef48026c0540b4976ff39b18a89d
```
- Com o recibo da transação recebido acessei o site http://amoy.polygonscan.com para verificar o conteúdo da transação
	Esse site Amoy é um local onde se pode consultar tudo o que está dentro da blockchain da Polygon. 
### Compilando para o bitecode
Nesse exercício vamos compilar a aplicação para o bitecode que a blockchain da Etherium compreende e é o que faz com que essa infraestrutura de blockchain permita a execução de código fonte. 

```
bco@Pessoal-Vostro:~/github/alura/3876-blockchain-projeto_incial/src$ npx solc --bin MeuPrimeiroToken.sol
```

Ao término se tem um binário que é enviado para a blockchain de forma que a máquina virtual da blockchain possa compreender, quando chamarmos uma função ou consultarmos uma variável. 
### Explorando a linguagem Solidity
Nesse exercício foi explorado a [[Linguagem Solidity]]

O seguinte contrato foi criado:
```
pragma solidity ^0.8.0;
contract Variables {
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

    event Added(uint value);

    // As visibilidades das funções são como segue
    // public (acessível fora do contrato e dentro do contrato)
    // internal (acessível dentro do contrato, mas também dos contratos que herdarem esse contrato - henrança),
    // external (somente acessível externamente, não é acessível dentro do contrato.)
    // private (somente acessível dentro do seu contrato)
    function getGreeting() public pure returns (string memory) {
        return "Hello, World!";
    }

    // Os comportamentos das funções
    // pure (não consulta ou altera a blockchain)
    // view  (consulta a blockchain em algum momento)
    function getGreetingPure() public pure returns (string memory) {
        return "Hello World!";
    }

    function add(uint _a, uint _b) public pure returns (uint) {
        return _a + _b;
    }

    function addWithEvent(uint _a, uint _b) public returns (uint) {
        uint _c = _a + _b;
        // Toda ver que tiver uma soma vai ser publicada na blockchain
        emit Added(_c);
        return _c;
    }

    function getNameView() public view returns (string memory) {
        return name;
    }

    modifier onlyOnwer() {
        // Cria um modifier para validar a mensagem antes de executar a função.
        require(msg.sender == owner, "Not the contract owner");
        _;
    }

    function getNameViewOnlyOwner()
        public
        view
        onlyOnwer
        returns (string memory)
    {
        return name;
    }
}
```

### IDE Remix
Foi explicado como utilizar a IDE REMIX para executar e Debugar os Códigos em Solidity.
https://remix.ethereum.org/#lang=en&optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.26+commit.8a97fa7a.js

### Criando um contrato no padrão ERC20
Nessa aula foi criado um contrato no padrão ERC20, conforme abaixo:
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.24;

// Padrão de funções de ERC20.
contract TokenERC20 {
    // Variáveis
    // Quantidade de tokens que vai existir no total
    uint256 public totalSupply;
    // Chave valor (endereço para inteiro), quando buscar um endereço vai retornar um inteiro.
    // Representa o saldo da carteira
    mapping(address => uint256) public balanceOf;
    // Um usuário autoriza que a transferência de seu saldo para outra pessoa
    mapping(address => mapping(address => uint256)) public allowance;
    // Nome do Contrato
    string public name;
    // Símbolo
    string public symbol;
    // Quantidade de decimais trabalhadas. 1 Milhão de tokens com 6 casas decimais
    uint8 public decimals;

    // Definição dos eventos
    // indexed, antes de variável, significa que pode ser utilizada para filtro de buscas futuras
    // Realiza a transferência
    event Transfer(address indexed from, address indexed to, uint256 value);
    // Autoriza alguém a transferir para você
    event Approval(
        address indexed owner,
        address indexed spender,
        uint256 value
    );

    // Classe construtora
    constructor(string memory _name, string memory _symbol, uint8 _decimals) {
        name = _name;
        symbol = _symbol;
        decimals = _decimals;
    }

    // Função chamada fora do contrato e que realiza a transferência
    function transfer(
        address recipient,
        uint256 amount
    ) external returns (bool) {
        // Se ele não tiver saldo suficiente, vai lançar um erro e a execução não será completada.
        balanceOf[msg.sender] -= amount;
        balanceOf[recipient] += amount;
        emit Transfer(msg.sender, recipient, amount);
        return true;
    }

    // Permite que alguém faça a transferência em seu nome
    // spender é alguem que vai gastar por você
    function approve(address spender, uint256 amount) external returns (bool) {
        allowance[msg.sender][spender] = amount;
        emit Approval(msg.sender, spender, amount);
        return true;
    }

    // É uma transação sendo feito por outra pessoa
    function transferFrom(
        address sender,
        address recipient,
        uint256 amount
    ) external returns (bool) {
        allowance[sender][msg.sender] -= amount;
        balanceOf[sender] -= amount;
        balanceOf[recipient] += amount;
        emit Transfer(sender, recipient, amount);
        return true;
    }

    // Cria novos tokens
    // Internal = só pode ser chamada dentro do contrato e daqueles que herdarem.
    function _mint(address to, uint256 amount) internal {
        balanceOf[to] += amount;
        totalSupply += amount;
        // Padrão para criação e destruição de token.
        emit Transfer(address(0), to, amount);
    }

    // Queima os tokens, por qualquer motivo que seja
    function _burn(address from, uint256 amount) internal {
        balanceOf[from] -= amount;
        totalSupply -= amount;
        emit Transfer(from, address(0), amount);
    }

    // Padrão se quiser expor para o mundo exterior
    function burn(address from, uint256 amount) external{
        _burn(from, amount);
    }
}
```

### Trabalhando com herança
A [[Linguagem Solidity]] permite trabalhar com herança. No link da linguagem há um exemplo para tal. A herança é importante porque é possível trabalhar com os padrões das industrias apenas herdando os seus contratos bases. 

Para isso existem algumas bibliotecas que se pode usar. 

# Fonte
Treinamento da Alura sobre Blockchain e Solidity

Outras documentações:
https://ethereum.org/en/developers/docs/standards/tokens/erc-20/
https://ethereum.org/en/developers/docs/standards/tokens/erc-721/