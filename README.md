# Sobre Blockchain e livros razão


---
#### Objetivos: 
```
1. Alguns conceitos sobre blockchain para serem discutidos em sala de aula. 
2. Exemplos que podem ser citados e comentados nas disciplinas que necessitam do apoio de uma banco de dados e projeto de sistemas. 
3. Este material é extremamente resumido e supõe que o leitor tem conhecimento básico de programação ou banco de dados. 
4. Este não é um guia definitivo, mas um pequeno tutorial compilado para auxiliar alunos e devs. 
5. Este material esta em construção.
```

---
#### Observações:
```
1. Este material pode ser usado como suporte às disciplinas de: banco de dados e projeto de sistemas.
2. Este material foi ou poderá ser usado em sala de aula/laboratório/EAD.
3. É um prerequisito conhecimentos básicos de, segurança da 
informação, programação e banco de dados.
4. Esta página poderá passar por atualizações sem aviso prévio.
```


---
# Sumário


- [Sobre Blockchain e livros razão](#sobre-blockchain-e-livros-razão)
      - [Objetivos:](#objetivos)
      - [Observações:](#observações)
- [Sumário](#sumário)
- [1 Conceitos](#1-conceitos)
  - [1.1. O problema de double spending](#11-o-problema-de-double-spending)
  - [1.2. Criptografia de chave privada](#12-criptografia-de-chave-privada)
  - [1.3. Critografia de chave pública](#13-critografia-de-chave-pública)
  - [1.4. Certificado digital](#14-certificado-digital)
  - [1.5. Tecnologias de livro razão](#15-tecnologias-de-livro-razão)
    - [1.5.1. Gráfos acíclicos dirigidos](#151-gráfos-acíclicos-dirigidos)
    - [1.5.2. Blockchain](#152-blockchain)
    - [1.5.3. Diferentes tipos de DLT](#153-diferentes-tipos-de-dlt)
    - [1.5.4. Alguns projetos de blockchain desde o surgimento até 2022](#154-alguns-projetos-de-blockchain-desde-o-surgimento-até-2022)
  - [1.6. Ethereum](#16-ethereum)
    - [1.6.1. EVM](#161-evm)
    - [1.6.2. Smart contracts](#162-smart-contracts)
    - [1.6.3 ETH](#163-eth)
    - [1.6.4. Gas fee](#164-gas-fee)
    - [1.6.5. IDE para programar com Ethereum](#165-ide-para-programar-com-ethereum)
  - [1.7. Wallets](#17-wallets)
    - [1.7.1. Carteiras, Contas, Chaves e Endereços](#171-carteiras-contas-chaves-e-endereços)
  - [1.8. Mining (mineração)](#18-mining-mineração)
  - [1.9. Consenso](#19-consenso)
  - [1.10. DeFi](#110-defi)
  - [1.11. Blockchain Oracle](#111-blockchain-oracle)
  - [1.12. Multhichain blockchain](#112-multhichain-blockchain)
  - [1.13. Hyperledger Fabric](#113-hyperledger-fabric)
  - [1.14. NFT](#114-nft)
  - [1.15. Stable Coin](#115-stable-coin)
- [2 Aplicabilidade](#2-aplicabilidade)
- [3 Tendências](#3-tendências)
- [4 Artigos interessantes](#4-artigos-interessantes)
- [5 Videos](#5-videos)
- [6 Reportagens](#6-reportagens)
- [7 Fontes](#7-fontes)
- [Avisos, licença](#avisos-licença)
  - [Aviso](#aviso)
  - [Licença](#licença)
- [Estatísticas desta página](#estatísticas-desta-página)







---
# 1 Conceitos


## 1.1. O problema de double spending

É um problema que surge ao transacionar moeda digital que envolve o mesmo gasto sendo gasto várias vezes. Múltiplas transações que compartilham a mesma informação transmitida na rede podem ser problemáticas e são uma falha exclusiva das moedas digitais. A principal razão para o gasto duplo é que a moeda digital pode ser facilmente reproduzida. <br>
Fonte: https://corporatefinanceinstitute.com/resources/cryptocurrency/double-spending/

Esta questão é particularmente preocupante nas transações digitais porque os ativos digitais, ao contrário do dinheiro físico, são facilmente replicáveis. Os sistemas financeiros tradicionais evitam a duplicação de gastos, confiando nas autoridades centrais, como os bancos, para verificar se uma pessoa possui fundos suficientes antes de processar uma transação. Sem uma autoridade central, como nos sistemas digitais descentralizados, torna-se um desafio impedir que alguém envie a mesma unidade monetária para várias partes simultaneamente.

A tecnologia Blockchain evita gastos duplos através da tecnologia de compartilhamento de arquivos peer-to-peer combinada com criptografia de chave pública. Blockchain resolve o problema do gasto duplo usando um livro-razão descentralizado, que todos podem acessar. Como todos os membros da rede podem examinar o histórico completo das transações, estes podem ter certeza de que nem suas cripto moedas nem quaisquer outras cripto moedas foram gastas mais de uma vez.

As transações são agrupadas em blocos e vinculadas em uma cadeia cronológica. Depois que uma transação é adicionada ao blockchain, ela recebe um carimbo de data e hora e é verificada pela rede, tornando praticamente impossível alterá-la. Este processo garante que cada unidade monetária possa ser gasta apenas uma vez, resolvendo o problema do gasto duplo sem a necessidade de uma autoridade centralizada.


[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

## 1.2. Criptografia de chave privada

A criptografia de chave privada, também conhecida como criptografia de chave simétrica, é um método em que a mesma chave é usada para criptografar e descriptografar dados. 
Neste sistema, o remetente e o destinatário devem partilhar uma chave secreta, que utilizam para proteger a sua comunicação. 
Quando um remetente deseja enviar informações confidenciais, ele criptografa os dados usando a chave privada compartilhada, transformando-os em um formato ilegível. 

O receptor, que também possui a chave, pode então descriptografar esses dados de volta à sua forma original. 
Este método é rápido e eficiente para criptografar grandes volumes de dados, mas depende muito do gerenciamento seguro da chave compartilhada.

Um desafio significativo com a criptografia de chave privada é a distribuição de chaves: ambas as partes devem ter a mesma chave, mas partilhá-la através de canais inseguros pode levar à intercepção por partes não autorizadas. Assim, os métodos seguros de troca de chaves são essenciais para que a criptografia de chave privada funcione de forma eficaz. Exemplos de algoritmos que usam criptografia de chave privada incluem AES (Advanced Encryption Standard) e DES (Data Encryption Standard). Apesar dos seus desafios, a criptografia de chave privada é amplamente utilizada em situações onde já existem canais seguros para partilha de chaves ou onde os dados devem ser encriptados e desencriptados rapidamente, como no armazenamento de ficheiros encriptados ou na encriptação de bases de dados locais.

## 1.3. Critografia de chave pública

Este tipo de criptografia envolve dois tipos de chaves, uma pública e uma privada. A chave pública pode ser compartilhada com terceiros. A chave privada deve ficar oculta. Dados são criptografos com a chave pública do destinatário,e pode ser decriptografa com a chave privada do destinatário. As chaves RSA pode ter vários tamanhos desde 1024 a 2048 bits. Criptografia de chave pública também é chamada de criptografia assimétrica. Neste sistema qualquer um com uma chave pública pode gerar mensagens criptografadas, mas somente aqueles que detem as chaves privadas correspondentes pode decifrá-las e obter a mensagem original.

Atualmente uma das implementações de critografia de chave pública mais utilizadas é baseada no algoritmos apresentados por Rivest-Shamir-Adelman (RSA) da Data Security. Outros algoritmos que implementam criptografia de chave pública: DSS, Elliptic curve, Paillier cryptosystem, Cramer-shoup, YAK, etc. Este tipo de criptografia também é muito utilizada no HTTPS com o TLS/SSL.

Programa que implementa criptografia e assinatura de mensagem: https://www.openpgp.org/.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

## 1.4. Certificado digital

Exemplos:
https://pt.wikipedia.org/wiki/Certificado_digital#/media/Ficheiro:Client_and_Server_Certificate.png

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

## 1.5. Tecnologias de livro razão

Tecnologias de livro razão distribuídas (ou "Distributed Ledger Technology (DLT)" do inglês) podem ser usadas para resolver problemas provocados pelo uso de uma terceira parte para autenticar transações, evitar cobranças de serviços, diminuir tempo de processamento, não se submeter a uma autoridade central e evitar um ponto de falha. Desta forma as DLT são interessantes para resolver uma série de problemas em um ambiente distribuído no qual vários participantes devem trocar dados, e geralmente estão a distâncias significativas e podem não ter os mesmos relacionamentos de confiança. 

DLT são implementações específica de uma categoria mais ampla de "livros razões compartilhados", que são simplesmente definidos como um registro compartilhado de dados em diferentes partes.  As DLT devem ser projetadas para trabalhar em ambientes que operam como máquinas de estados com múltiplos atores os quais compartilham registros entre si.

Um sistema de DLT deve: 

* A) permitir que seus participantes trabalhem de acordo com um determinado critério (ou consenso); 

* B) manter uma ordem de transações validada; 

* C) replicar os dados em vários nós; 

* D) manter um link entre as transações para evitar adulterações; 

* E) conter o livro razão (ou ledger) que é o resultado do processo de registro de transações (o qual relata a história das transações.

O registro em uma DLT pode ser realizado sob dois aspectos permissionless (na qual cada participantes pode escrever um registro na ledger) ou permissioned (na qual somente alguns participantes podem submeter envios). Quanto ao processamento e execução de tarefas ou programas na DLT, estas podem ser on-chain (execução interna), off-chain (execução externa) e side-chain (execução parcialmente interna com auxílio computacional externo). 

DLT podem ser divididas em duas classes: 

* A) grafos acíclicos dirigidos (ou directed acyclic graph (DAG) do inglês) e, 

* B) blockchain. Blockchain e DAG são sub tipos de DLTs.

![Exemplos de DLT](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig1.png "Exemplos de DLT")

Figura 1: As principais subdivisões e alguns exemplos.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

### 1.5.1. Gráfos acíclicos dirigidos

Uma forma de DLT é um grafo acíclico dirigido (DAG), o qual utiliza uma estrutura parecida com vértices e arestas; as arestas são posicionados em uma direção e o grafo é acíclico pois os vértices não se referenciam nem formam um loop para si mesmos.  Nos sistemas DAG não é necessário um minerador, pois cada usuário pode controlar sua própria sequência de blocos de forma assíncrona.  Sempre que uma transação é realizada, os participantes devem verificar duas outras transações de outros nós (PARK; KIM, 2022). 

Cada transação no DAG é um vértice, cada vértice tem uma ou mais arestas em direção a outros vértices, desta forma um vértice referencia outro vértice. Uma transação é registrada após a outra formando uma linearidade, porém o DAG não usa mineração ou custos de transação; pois um nó realiza validação simultânea de transações. Cada transação é registrada em vértices e não existe a necessidade de serem gravadas em bloco, formando uma cadeia de transações verificadas (LI et al., 2022). Com o DAG os participantes são mineradores e validadores de transações.
 
![Exemplos de DAG](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig2.png "Exemplos de DAG")

Figura 2: Nós em um sistema distribuído.

São alguns exemplos de projetos que utilizam DAG: IOTA4(é um DAG voltada para armazenar dados de IoT), NANO5(é uma criptomoeda e uma plataforma para transação de valores ponto-a-ponto), Obyte6(é uma DAG e criptomoeda), Hedera7(é uma rede pública baseada em DAG e uma criptomoeda) e IPFS8(é um sistema de arquivos distribuído, utilizado em uma rede ponto-a-ponto.). DAG é usada pelo IPFS onde cada identifcador tem um hash do conteúdo para um conteúdo, é usado para representar arquivos e diretórios, o IPFS quebra um arquivo em pedaços chamados de blocos, (IPFS, 2022).

Os blocos podem estar em vários lugares. Um arquivo é composto de vários blocos, cada bloco tem um identificador. Para localizar este arquivo composto por vários blocos o IPFS usa o que é chamado de tabela hash para localizar arquivos. Com esta tabela, um grupo de nós pode conter partes diferentes de um arquivo.  Nesta tabela, existem duas colunas uma com um hash inicia e final e a outra coluna com o conteúdo do arquivo. Dependendo qual o valor da chave hash o arquivo pode ser armazenado na tabela (no topo, por exemplo), para recuperar o arquivo é necessário percorrer a tabela, (PSARAS; SOARES; DIAS, 2022).

Um exemplo de implementação de DAG é o sistema de arquivos interplanetário, [IPFS](https://ipfs.tech/).

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

### 1.5.2. Blockchain


Blockchain é uma cadeia de blocos, na qual cada nó tem blocos de dados, um carimbo de data/hora e um hash de código que se refere ao nó anterior, reforçando a cadeia de dados de forma imutável. A tecnologia blockchain foi inicialmente projetada para oferecer suporte a moedas criptográficas, mas hoje, pode-se usá-la para outros fins, incluindo rastreamento da cadeia logística e contratos entre pessoas que não se conhecem.  Assim, a blockchain funciona salvando as transações de interesse para as quais foi projetada, onde cada uma pode implementar uma série de regras e também servir para transmitir dados. 

Em particular, as regras para a execução de transações ou operações são realizadas por meio de contratos inteligentes. Do ponto de vista do programador, elas podem ser vistas como um script (ou, simplificando, um programa que deve ser executado automaticamente quando uma transação é realizada). Assim, blockchain pode conter dados e código executável (MAESA; MORI, 2020), onde o último é visto como a lógica de programação para atualizar dados e disparar ações externas ao blockchain.


* "Bloco" são os dados armazenados de forma sequencial.<br>

* "Cadeia" é o termo usado porque um dos campos do bloco é um apontador para o seu bloco pai. Desta forma os bloco são serializados e unidos sequencialmente. 

![Cadeia de blocos](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig3.png "Cadeia de blocos")

Figura 3: Exemplos de encadeamento de blocos.

Artigo que iniciou com a ideia: [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf).


[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>


### 1.5.3. Diferentes tipos de DLT


| Propriedade   | Públicas   | Consórcios   | Privadas  |
|---|---|---|---|
| Acesso a leitura de dados  | Sem restrição  | Com ou sem restrição  | Com ou sem restrição  |  
| Acesso a escrita de dados  | Sem restrição  | Sem restrição ou somente com entidades pré-selecionadas  | Uma entidade única  | 
| Participa no processo de validação  | Sem restrição  | Somente com entidades pré-selecionadas  | Sem validação de dados  |
| Complexidade de validação| Consenso complexo de validação, envolve falha bizantina | Consenso de validação facilitado| Consenso não é necessário | 

[Voltar ao início](#sobre-blockchain-e-livros-razão)


### 1.5.4. Alguns projetos de blockchain desde o surgimento até 2022

Projetos de blockchain a partir do ano de criação até 2022: Hyperledger Fabric9, Multichain blockchain10, SAP blockchain11, Hyperledger Besu12, Oracle blockchain13, Hathor blockchain14, VMware VMBC15, Azure Confidential Ledger16, XO-DEX17, Nano18, Dragonchain19, Openchain20, GoQuorum21. Estes projetos de blockchain apresentam características de custo zero de transação (ou taxa zero), as quais podem ser explorada por blockchain privadas.

![Alguns projetos de blockchain até 2022](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig4.png)

Figura 4: Linha do tempo de alguns projetos de blockchain.


## 1.6. Ethereum 

Ethereum é uma rede de computadores em todo o mundo que segue um conjunto de regras do chamado protocolo Ethereum.


Definições pelo ChatGPT:
```
O Ethereum é uma plataforma de blockchain descentralizada, projetada para suportar contratos inteligentes e aplicativos descentralizados (dApps). 
Ele foi criado para expandir as funcionalidades das blockchains convencionais, permitindo que desenvolvedores criem e executem programas complexos diretamente na rede.
Em resumo, o Ethereum é uma plataforma blockchain versátil que permite que desenvolvedores criem, executem e interajam com uma ampla variedade de aplicativos descentralizados e contratos inteligentes.
```

**Pergunta para o ChatGPT:**

"*É possível afirmar que o Etherem é mais um ambiente de execução de apps distribuídas do que uma plataforma para criptomoedas* ?"

**Resposta:**


*Sim, é possível afirmar que o Ethereum é mais um ambiente de execução de aplicativos distribuídos (dApps) do que uma plataforma focada exclusivamente em criptomoedas. Embora o Ether (ETH) seja uma parte importante da rede e funcione como moeda digital para transações e pagamento de taxas, a principal inovação do Ethereum é sua capacidade de executar contratos inteligentes e aplicativos descentralizados.*

*Aqui estão alguns pontos que reforçam essa visão:*

*Contratos Inteligentes: A criação de contratos inteligentes é uma das maiores funcionalidades do Ethereum. Esses contratos são programas que operam de maneira autônoma, executando tarefas conforme condições pré-programadas, o que permite a criação de aplicativos que rodam sem intermediários, como marketplaces de NFTs, redes sociais e sistemas de votação.*

*Ethereum Virtual Machine (EVM): O Ethereum é equipado com a EVM, uma máquina virtual que permite executar código descentralizadamente em milhares de nós da rede. Isso transforma o Ethereum em uma plataforma de computação distribuída que pode hospedar e executar qualquer aplicativo programado para rodar na rede.*

*Ecossistema de dApps: Ethereum é um ecossistema completo para desenvolvimento de dApps, incluindo finanças descentralizadas (DeFi), jogos, redes sociais, e muito mais. A versatilidade do Ethereum para criar esses aplicativos mostra que seu propósito vai muito além de ser uma simples criptomoeda.*

*Mudança para Proof of Stake (PoS): Com a atualização para Ethereum 2.0 e a adoção do PoS, a rede tornou-se mais eficiente, escalável e segura, permitindo o crescimento de um ecossistema robusto de aplicativos descentralizados.*

*Portanto, embora o Ether (ETH) seja a criptomoeda nativa e essencial para o funcionamento da rede, o Ethereum é melhor descrito como uma plataforma de execução de aplicações distribuídas do que apenas uma plataforma de criptomoeda. Ele foi projetado para ser um "computador mundial" descentralizado, capaz de suportar uma ampla gama de aplicações em uma rede sem necessidade de confiança em intermediários.*


[Voltar ao início](#sobre-blockchain-e-livros-razão)


### 1.6.1. EVM

A Máquina Virtual Ethereum é o computador virtual global cujo estado todos os participantes (nós) da rede Ethereum armazenam (seu estado) e concordam. Qualquer participante pode solicitar a execução de código arbitrário na EVM; a execução do código (via smart contract) altera o estado do EVM. 

[Voltar ao início](#sobre-blockchain-e-livros-razão)


### 1.6.2. Smart contracts

Contratos inteligentes são programas de computador que estão e rodam na blockchain Ethereum. Transações acionam smart contracts. São acionados por aplicativos de usuários. Nick Szabo cunhou o termo "smart contract“, em 1994. Szabo idealizou um mercado virtual onde negócios automáticos e criptografados permitissem que transações ocorressem sem intermediários confiáveis.

```solidity
// SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.8.2 <0.9.0;

/**
 * @title Storage
 * @dev Store & retrieve value in a variable
 * @custom:dev-run-script ./scripts/deploy_with_ethers.ts
 */
contract Storage {

    uint256 number;

    /**
     * @dev Store value in variable
     * @param num value to store
     */
    function store(uint256 num) public {
        number = num;
    }

    /**
     * @dev Return value 
     * @return value of 'number'
     */
    function retrieve() public view returns (uint256){
        return number;
    }
}
```

Fonte: https://ethereum.org/en/smart-contracts/

[Voltar ao início](#sobre-blockchain-e-livros-razão)


### 1.6.3 ETH

ETH é uma criptomoeda (similar ao Bitcoin). Enviar ETH para outra pessoa você pagará uma taxa em ETH. Esse valor pago em ETH é a motivação para os validadores de bloco processar e verificar o que os usuários desejam fazer. Validadores são selecionados aleatóriamente para tratar um bloco de transações e posteriormente são recompensados com ETH.

Fonte: https://ethereum.org/en/eth/

[Voltar ao início](#sobre-blockchain-e-livros-razão)

### 1.6.4. Gas fee

Cada transação realizada no Ethereum consome "gas".
Enviar uma transação ou executar um smart contract gasta "gas".

Fonte: https://ethereum.org/en/wallets/

[Voltar ao início](#sobre-blockchain-e-livros-razão)


### 1.6.5. IDE para programar com Ethereum

Remix IDE:

![Remix IDE](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig5.png)

Figura 5: IDE Remix.


[Remix Ethereum](https://remix.ethereum.org/).

Exemplo da saída do log do Remix, no caso foi rodado o programa ilustrado na digura acima:

```solidity
[vm]from: 0x5B3...eddC4to: Storage.store(uint256) 0x7EF...8CB47value: 0 weidata: 0x605...0007blogs: 0hash: 0xbe4...3131b
status	true Transaction mined and execution succeed
transaction hash	0xbe4083338633379fd0ff81f2d81355da1c03cf74fc172e76133a78f939a3131b
block hash	0xbad12410685c870d6c931969de576a68ed22fa7fd6220a23b8a8a2166e2ee8ce
block number	8
from	0x5B38Da6a701c568545dCfcB03FcB875f56beddC4
to	Storage.store(uint256) 0x7EF2e0048f5bAeDe046f6BF797943daF4ED8CB47
gas	50283 gas
transaction cost	43724 gas 
execution cost	22520 gas 
input	0x605...0007b
decoded input	{
	"uint256 num": "123"
}
decoded output	{}
logs	[]
val	0 wei
```

Simulador local de Ethereum para desenvolvimento [Ganache](https://trufflesuite.com/ganache/).

[Voltar ao início](#sobre-blockchain-e-livros-razão)



## 1.7. Wallets

Uma carteira é uma forma de se controlar uma conta. Ela contém a identidade do usuário e seus ativos, além de informar saldos e enviar transações. A carteira é uma forma de interação com a rede Ethereum.

[Voltar ao início](#sobre-blockchain-e-livros-razão)


### 1.7.1. Carteiras, Contas, Chaves e Endereços

* Uma conta Ethereum é um par de chaves. Uma chave (pública) é usada para criar o endereço que pode ser compartilhado livremente e a outra chave (privada) é mantida em segredo porque é usada para assinar transações. Juntas, essas chaves permitem manter ativos e fazer transações.
* Uma conta Ethereum possui um endereço, assim como um email possui uma caixa de entrada. Isso é usado para identificar ativos digitais.
* Uma carteira é uma ferramenta (de software ou hardware) que permite interagir com uma conta, usando uma par de chaves. Ele permite que se visualize o saldo de uma conta, envie transações etc.
* A maioria dos produtos de carteira permite gerar uma conta Ethereum.

Fonte: https://ethereum.org/en/wallets

[Voltar ao início](#sobre-blockchain-e-livros-razão)



## 1.8. Mining (mineração)

A “mineração” de blockchain é uma metáfora para o trabalho computacional que os nós da rede realizam para validar as informações contidas nos blocos. Assim, na realidade, os mineiros estão essencialmente a ser pagos pelo seu trabalho como auditores.

Fonte: https://www.investopedia.com/tech/how-does-bitcoin-mining-work/#:~:text=Blockchain%20%22mining%22%20is%20a%20metaphor,for%20their%20work%20as%20auditors.


A mineração de Bitcoin é o processo de validação das informações em um bloco blockchain, gerando uma solução criptográfica que atende a critérios específicos. Quando uma solução correta é alcançada, uma recompensa na forma de bitcoin e taxas pelo trabalho realizado é dada ao(s) minerador(es) que alcançaram a solução primeiro.

Fonte: https://www.investopedia.com/terms/b/bitcoin-mining.asp


```
Como funciona a mineração de Bitcoin?
Aqui está um exemplo simplificado para explicar o processo. 
Digamos que você peça a amigos para adivinharem um número entre 1 e 100. 
Seus amigos não precisam adivinhar o número exato; eles só precisam ser 
os primeiros a adivinhar um número menor ou igual ao seu número. 
Se você pensar no número 19 e um amigo aparecer com 21, outro 55 e ainda outro 83, 
eles perdem porque todos adivinharam mais de 19. Mas se sobrarem três amigos
e o próximo acertar 16, eles ganham , e os outros não têm chance de adivinhar. 
Quem acertou 16 foi o primeiro a adivinhar um número menor ou igual a 19.
Fonte: https://www.investopedia.com/terms/b/bitcoin-mining.asp
```

[Voltar ao início](#sobre-blockchain-e-livros-razão)



## 1.9. Consenso

É um sistema que valida uma transação e a marca como autêntica. Este mecanismo lista todas as transações válidas de uma moeda em uma blockchain para construir confiança na moeda entre os comerciantes. Diversas moedas, como Bitcoin, Ethereum etc., utilizam este sistema.

* PoW (Proof of Work): ‘Prova’ refere-se à solução de um problema altamente complexo, e ‘trabalho’ refere-se ao processo de resolução do mesmo. Os mineradores de moedas criptográficas competem para resolver o problema e ganhar o direito de processar a transação. O solucionador mais rápido recebe uma taxa de mineração dos comerciantes dessas moedas.

* PoS (Proof of Stake): Este mecanismo escolhe aleatoriamente um proprietário máximo de moedas para validar uma transação. Também permite ao proprietário criar um bloco para a mesma moeda. Este mecanismo requer comparativamente menos energia, tempo de transação e uma taxa mais baixa. Moedas como Etherium 2.0

* PoA (Proof of Authority): Prova de autoridade (PoA) é um tipo de mecanismo de consenso usado em alguns blockchains para decidir qual participante adicionará o próximo bloco de transações. Ao contrário da Prova de Trabalho do Bitcoin, onde os mineiros competem para resolver quebra-cabeças complexos, ou da Prova de Participação, onde a chance de adicionar um bloco depende de quanta criptomoeda uma pessoa possui, o PoA tem tudo a ver com identidade e reputação.


| Característica                 | Proof of Work (PoW)                      | Proof of Stake (PoS)                         | Proof of Authority (PoA)                     |
|--------------------------------|------------------------------------------|----------------------------------------------|----------------------------------------------|
| **Conceito Principal**         | Competição para resolver puzzles criptográficos | Seleção baseada na quantidade de moedas em stake | Seleção baseada em autoridade de validadores confiáveis |
| **Participantes**              | Mineradores                              | Validadores (detentores de moedas)            | Validadores (indivíduos/entidades confiáveis) |
| **Consumo de Energia**         | Alto (exige muita computação)            | Baixo                                        | Muito baixo                                  |
| **Velocidade**                 | Mais lento devido ao processo de resolução de puzzles | Mais rápido que PoW                          | Muito rápido                                 |
| **Mecanismo de Segurança**     | Dificuldade computacional                | Moedas em stake (valor financeiro)           | Reputação dos validadores                    |
| **Descentralização**           | Alta, mas dependente do poder de mineração | Moderada a alta, dependendo da distribuição de moedas | Moderada, dependendo do número de validadores |
| **Exemplos de Redes**          | Bitcoin, Ethereum (pré-2.0)              | Ethereum 2.0, Cardano, Solana                | VeChain, POA Network, xDAI Chain             |
| **Risco de Centralização**     | Alto para pools de mineração             | Moderado, pois grandes detentores de moedas podem dominar | Alto se os validadores forem limitados       |
| **Casos de Uso**               | Redes públicas e abertas                 | Redes públicas ou semi-públicas              | Redes privadas, consórcios ou permissionadas |



Mais referências: https://cleartax.in/s/consensus-in-blockchain

[Voltar ao início](#sobre-blockchain-e-livros-razão)



## 1.10. DeFi

Significa Decentralized Finance (DeFi). É um conceito que visa trazer os serviços financeiros tradicionais para o universo das criptomoedas usando blockchains e "ledgers" distribuídas. Um atrativo para o uso de DeFi seria a não existência de taxas bancárias entre as transações.  O usuários destes serviços poderiam manter dinheiro digital em uma carteira (wallets) de forma segura (pelo uso de criptografia) e realizar transferências de fundos (cripto ativos) entre outros usuários deste ecossistema via Internet se unidades centrais de controle ou bancos tradicionais para intervir neste processo.

Redes ponto a ponto financeiras seriam os locais onde os serviços DeFi existiriam, os usuários destes serviços se conectariam via wallets, vendedores e compradores realizaram as transações dentro desta rede distribuída. Esta rede financeira estaria presente em qualquer lugar (desde que haja internet). É importante observar que DeFi não tem como objetivo fornecer serviço de anonimização, pelo contrário, espera-se que instituições financeiras tradicionais(CeFi - Centralizes Finance), comercios reais e pessoas físicas e jurídicas possam fazer uso dessa tecnologia da mesma forma como se usa os meios financeiros tradicionais centralizados. Inclusive as transações financeiras que se estabelecerão nas redes DeFi esperá-se que sejam todas rastreáveis.

A proposta DeFi pode ter surgido como uma ideia nas quais pessoas poderiam fazer transações entre si sem pagar taxas, mas é necessário uma infraestrutura para a computação e operação de redes de comptuadores custosa, instituições financeiras podem participar cobrando taxas bancárias muito baixas, mais atrativas que no sistema tradicional. 



[Voltar ao início](#sobre-blockchain-e-livros-razão)

## 1.11. Blockchain Oracle

São sistemas que conectam blockchains a sistemas externos, permitindo que os smart contracts possam de acordo com parâmetros externos. Desta forma sistema pré-existentes (ou legados) possam se conectar (via WEB3) com as blockchains. Os oracles podem receber dados do mundo externo (qualquer tipo de dados, por exemplo: dados de sensor de temperatura) e envia estes dados para a blockchain. Permite que ecossistemas decentralizados possam ter acessoa fontes de dados externas. 

[Voltar ao início](#sobre-blockchain-e-livros-razão)

## 1.12. Multhichain blockchain

Resumo sobre Multichain blockchain:

* Foi criada pela Coin Sciences, uma empresa britânica.
* É um fork do projeto bitcoin.
* O bitcoin foi usado como base(inspiração) para o desenvolvimento da multichain.
* Permite desenvolver blockchains privadas
* O que é uma blockchain privada? São as blockchains nas quais seus criados podem definir quem pode se conectar e permite gerenciar determinadas permissões de seus membros.
* Está disponível para download para os sistemas operacionais Windows e Linux
* A operação da multichain é via linha de comando
* Um computador pode rodar uma instancia (daemon) da multichain e conectar-se a mais de uma blockchain.
* Cada comando enviado para a blockchain é uma transação.
* Cada transação é armazenada em bloco.
* Cada transação tem um txid, que é o identificador desta.
* Um computador não necessita rodar uma instancia da multichain mas ele pode se conectar a uma instancia que está rodando em outro computador.
* Um computador pode descarregar a blockchain ele deverá ter também permissão para se conectar a ela. Quem fornece essa permissão é o criador da blockchain ou outro com permissão para tal.
* Permite um alto grau de privacidade por requer a autenticação com a devida permissão para acesso à blockchain.
* Suporta o algoritmo PoA (Proof of Authority).
* Toda transação é atômica.
* Toda transação é marcada por chaves públicas.
* Os mineradores são designados
* Pode ser instalada em servidores próprios
* Utiliza validation by consensus, criado pelos nós da rede.
* Suporta um ciclo de vida do ativo
* Não necessita de smart contracts
* É necessário ter que ser assinante de ativo para realizar consultas
* Cada nó pode escolher qual stream indexar
* As contas são identificadas por chaves públicas.
* Cada bloco é assinado pelo criador, outros só podem minerar com a devida permissão.
* As permissões da blockchain podem mudar durante o tempo.
* Utiliza JSON-RPC API para aplicações.
* A multichain pode ser acessada como serviço.
* Não possui limites de transações.
* Não possui limitações de nós por rede.
* O blocktime (é o tempo de bloqueio é o tempo que leva para criar um novo bloco ou arquivo em uma cadeia de criptomoeda) é menor que 2 segundos.

Streams:
* O streams é uma abstração para o armazenamento de dados, indexação e recuperação de dados.
* É possível ter vários streams.
* Cada stream pode estar aberto para escrita por todos ou apenas para alguns.
* Dados são publicados no formato json.
* Um dado pode ter a mesma chave.
* Para que um dados seja publicado na stream é necessário permissão de escrita na stream alvo.
* Uma consulta só pode ser feita em uma stream se foi feita uma assinatura (subscription) na referida stream.

Ativos: 
* Os ativos tem uma função semelhante ao conceito de moeda.
* Os ativos recebem uma quantidade inicial ao serem criados.
* Este ativo pode ser dividido em partes menores (fracionado).
* O ativo pode ser enviado a outros.
* O ativo pode ser recebido a partir de terceiros.
* Os ativos só podem ser transmitidos se o destinatário tem permissão para receber.
* Cada nó tem uma carteira (wallet) na qual ele pode armazenar os ativos.
* Os ativos na carteira podem ser visualizados com suas quantidades.
* Ativos podem ser reemitidos e destruidos.
* Blocos podem ser consultados na blockchain.
* Como os blocos são encadeados é possível saltá-los para consultar o bloco desejado.
* As consultas detalhadas de um bloco exigem que se use o hash do bloco.

Smart Filters: 
* Smart filters são códigos!
* Smart filters são funções que possibilitam verificações nas transações que são disparadas para a blockchain.
* Parecidos com triggers em bancos de dados.
* Filtram o que pode ser enviado para a blockchain.
* São funções em javascript
* Tipos:
A) Smart filters para transações  (usando o parâmetro txfilter) 
B)  Smart filters para objetos (usando o parâmetro streamfilter)
* Cada função obtém informações sobre uma transação ou objeto mediante callbacks.
* Callbaks: 
A) Se recebe um retorno vazio, a transação é rejeitada
B) Se recebe um valor diferente de vazio, a transação ou objeto é aceito.
C) Somente com permissões é possível criar smart filters
D) Streams podem ser ativadas ou desativadas.

Site da [Multichain blockchain](https://www.multichain.com/).

[Voltar ao início](#sobre-blockchain-e-livros-razão)

## 1.13. Hyperledger Fabric

Hyperledger é um projeto open source de blockchain mantido pela Linux Foundation (seu principal patrocinador é a IBM). É uma blockchain permissionada. 

Estrutura de uma rede Hyperledger Fabric:

<img src="https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig7.png" alt="drawing" width="500"/>

Figura 6: Exemplo de rede Hyperledger Fabric.

Fonte da figura: https://hyperledger-fabric.readthedocs.io/en/latest/network/network.html

* As organizações R0, R1 e R2 montaram uma rede e chegaram em um consenso sobre a infraestrutura e políticas de administração da rede. 
* As 3 organizações (R0, R1 e R2) são as proprietárias da rede, que utiliza como configuração CC1.
* No canal C1 estão os peers P1 e P2 das organizações R1 e R2.
* R0 é proprietária do peer O (que possui um serviço de ordenamento).
* Todos os nós contém uma cópia da blockchain (L1) (ou ledger).
* R1 e R2 também interagem com o canal usando as aplicações A1 e A2.
* Todas as 3 organizações possuem autoridades certificadoras CA0, CA1 e CA2.
* S5 é um chaincode (é um smart contract) instalado nos peers P1 e P2.

[Voltar ao início](#sobre-blockchain-e-livros-razão)

## 1.14. NFT

NFT significa Non-Fungible Token, são ativos que podem ser tokenizados por uma blockchain (ou seja, pode receber uma representação virtual como um objeto dentro de uma blockchain). Estes ativos podem representar qualquer coisa do mundo real como: obras de arte, carros, terrenos, etc. Recebem um código único de identificação e metadados que os descrevem (incluindo quantidade e valor). Os NFTs podem ser comprados e vendidos/trocados usando cripto moedas em determinadas plataformas. 

Exemplo de NFT são os Bored Ape Yacht Club Galeria dos [BAYC](https://boredapeyachtclub.com/#/gallery) NFT (notícias sobre: https://www.coindesk.com/web3/2023/07/03/bored-ape-yacht-club-nft-collection-floor-price-sinks-to-20-month-low/ e  https://www.theguardian.com/artanddesign/2022/jan/04/bored-ape-nft-art-eminem). Outro exemplo de market place de NFT é o site [Criptokitties](https://www.cryptokitties.co/).

[Voltar ao início](#sobre-blockchain-e-livros-razão)


## 1.15. Stable Coin

São um tipo de criptomoeda que possui um valor atrelado a um ativo de referência que pode ser uma commodities, bens materiais, ouro ou outra moeda física. A ideia é ter uma relação 1:1, no qual a criptomeda stable coin tem seu valor indexado por uma outra moeda. Desta forma seu valor tende a não ter tanda volatilidade. Esta opção é mais atrativa pois permite a conversibilidade da moeda em outros bens.

[Voltar ao início](#sobre-blockchain-e-livros-razão)


--- 
# 2 Aplicabilidade 


Desenvolvimento de criptomoedas

Comércio de ativos (NFT, tokens não fungíveis)

Rastreabilidade de transações, por exemplo em uma cadeia logística cada etapa (a cada saldo entre os players) pode ser feito um registro em uma blockchain, possibilitando a rastreabilidade dos ativos que estão em movimento:

![Cadeia logística](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig6.png)

Figura 7: Exemplo de cadeia logística.


Registro imutável de informações

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 3 Tendências

Google trends usado para mostrar tendências:

https://trends.google.com.br/trends/explore?date=today%205-y&q=blockchain,%2Fg%2F11g0g4sbp3,Ethereum&hl=pt-BR

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 4 Artigos

1. [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf)

Em desenvolvimento. 

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>



---
# 5 Videos

Em desenvolvimento.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 6 Reportagens

1. [Chegada do DREX e o fim do dinheiro em espécie](https://livecoins.com.br/chegada-do-drex-e-fim-do-dinheiro-em-especie-pode-virar-audiencia-publica-na-camara/).

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>



# 7 Fontes


Diversas fontes de pesquisa sobre blockchain:

AGI, M. A.; JHA, A. K. Blockchain technology in the supply chain: an integrated theoretical perspective of organizational adoption. International Journal of Production Economics, [S.l.], v. 247, p. 108458, 2022.
https://www.sciencedirect.com/science/article/pii/S0925527322000512



ANTONOPOULOS, P.; KAUSHIK, R.; KODAVALLA, H.; ROSALES ACEVES, S.; WONG, R.; ANDERSON, J.; SZYMASZEK, J. SQL Ledger: cryptographically verifiable data in azure sql database. In: INTERNATIONAL CONFERENCE ON MANAGEMENT OF DATA, 2021., 2021, New York, NY, USA Proceedings. Association for Computing Machinery, 2021. p. 2437–2449. (SIGMOD ’21).
https://dl.acm.org/doi/abs/10.1145/3448016.3457558

BASSILIOS, J. OECD adopts recommendations on blockchain and other DLT. Accessed: 2022-10-20.
https://www.oecd.org/daf/blockchain/oecd-recommendation-on-blockchain-and-other-dlt.htm


BERAWI, M. A.; REYES, G.; SARI, M.; SAROJI, G. Developing Public-Private Partnership Model with Blockchain-Based Crowdfunding Concept for Port City Project. In: ASSOCIATION FOR COMPUTING MACHINERY, 2021, New York, NY, USA. Anais. Association for Computing Machinery, 2021. (SPBPU IDE ’20).
https://dl.acm.org/doi/abs/10.1145/3444465.3444476


BROOKBANKS, M. M.; PARRY, G. The impact of a blockchain platform on trust in established relationships: a case study of wine supply chains. Supply Chain Management, [S.l.], 2022.
https://www.emerald.com/insight/content/doi/10.1108/SCM-05-2021-0227/full/html

BUSH, K. Blockchain: novel provenance applications. Washington, DC: Congressional Research Service, 2022. (R47064).
https://sgp.fas.org/crs/misc/R47064.pdf

BUSTAMANTE, P.; CAI, M.; GOMEZ, M.; HARRIS, C.; KRISHNAMURTHY, P.; LAW, W.; MADISON, M. J.; MURTAZASHVILI, I.; MURTAZASHVILI, J. B.; MYLOVANOV, T.; SHAPOVAL, N.; VEE, A.; WEISS, M. Government by Code? Blockchain Applications to Public Sector Governance. Frontiers in Blockchain, [S.l.], v. 5, 2022.
https://www.frontiersin.org/articles/10.3389/fbloc.2022.869665/full

CAGIGAS, D.; CLIFTON, J.; DIAZ-FUENTES, D.; FERNáNDEZ-GUTIéRREZ, M. Blockchain for Public Services: a systematic literature review. IEEE Access, [S.l.], v. 9, p. 13904–13921, 2021. CAI, Z.; YANG, G.; XU, S.; ZANG, C.; CHEN, J.; HANG, P.; YANG, B. RBaaS: a robust blockchain as a service paradigm in cloud-edge collaborative environment. IEEE Access, [S.l.], v. 10, p. 35437–35444, 2022.
https://ieeexplore.ieee.org/document/9326290

CHARLON, F. Overview of Openchain. 2017.
https://docs.openchain.org/_/downloads/en/latest/pdf/ e https://docs.openchain.org/en/latest/general/overview.html

CHARLON, F. Openchain modules Storage engines. 2015.
https://docs.openchain.org/en/latest/general/modules.html#storage-engines

CHEN, S.; ZHANG, J.; SHI, R.; YAN, J.; KE, Q. A Comparative Testing on Performance of Blockchain and Relational Database: foundation for applying smart technology into current business systems. In: _____. . [S.l.: s.n.], 2018. p. 21–34.
https://link.springer.com/chapter/10.1007/978-3-319-91125-0_2

DAS, S.; SARAF, C.; KHAIRNAR, D. P. A Hyperledger Fabric Based Organizational Decentralized Access Control Solution. In: IEEE 7TH INTERNATIONAL CONFERENCE ON ENGINEERING TECHNOLOGIES AND APPLIED SCIENCES (ICETAS), 2020., 2020. Anais. . . [S.l.: s.n.], 2020. p. 1–6.
https://ieeexplore.ieee.org/document/9484187

DIB, O.; BROUSMICHE, K.-L.; DURAND, A.; THEA, E.; BEN HAMIDA, E. Consortium blockchains: overview, applications and challenges. International Journal On Advances in Telecommunications, France, 2018.
https://hal.science/hal-02271063

EMBRAPA. Uso de blockchain para registro de dados de Cadeia de Suprimentos Verde da indústria sucroenergética. 2020.
https://www.alice.cnptia.embrapa.br/handle/doc/1126142

ESMAEILIAN, B.; SARKIS, J.; LEWIS, K.; BEHDAD, S. Blockchain for the future of sustainable supply chain management in Industry 4.0. Resources, Conservation and Recycling, [S.l.], v. 163, p. 105064, 2020.
https://www.sciencedirect.com/science/article/abs/pii/S0921344920303815

GAO, U. S. G. A. O. Blockchain Emerging Technology Offers Benefits for Some Applications but Faces Challenges. Washington, DC0: Government Accountability Office, 2022. GAO-22-104625.
https://www.gao.gov/products/gao-22-104625

GERAKOUDI-VENTOURI, K. Review of studies of blockchain technology effects on the shipping industry. Journal of Shipping and Trade, [S.l.], v. 7, n. 1, p. 2, Jan 2022.
https://jshippingandtrade.springeropen.com/articles/10.1186/s41072-021-00105-2


GUERPINAR, T.; GUADIANA, G.; ASTERIOS IOANNIDIS, P.; STRAUB, N.; HENKE, M. The Current State of Blockchain Applications in Supply Chain Management. In: THE 3RD INTERNATIONAL CONFERENCE ON BLOCKCHAIN TECHNOLOGY, 2021., 2021, New York, NY, USA. Anais. . . Association for Computing Machinery, 2021. p. 168–175. (ICBCT ’21).
https://dl.acm.org/doi/fullHtml/10.1145/3460537.3460568

HASAN, H.; ALHADHRAMI, E.; ALDHAHERI, A.; SALAH, K.; JAYARAMAN, R. Smart contract-based approach for efficient shipment management. Computers Industrial Engineering, [S.l.], v. 136, p. 149–159, 2019.
https://www.sciencedirect.com/science/article/abs/pii/S0360835219304140

HRGA, A.; CAPUDER, T.; ZARKO, I. Demystifying Distributed Ledger Technologies: limits, challenges and potentials in the energy sector. IEEE Access, [S.l.], v. PP, p. 1–1, 07 2020.
https://ieeexplore.ieee.org/document/9136665

IMERI, A.; AGOULMINE, N.; KHADRAOUI, D. Blockchain and IoT integrated approach for a trusted and secured process to manage the transportation of dangerous goods. Revista de sistemas e computação, Salvador, Brasil, v. 10, n. 1, p. 26–41, 2020.
https://revistas.unifacs.br/index.php/rsc/article/download/6444/4031

IPFS. How IPFS works. 2022.
https://docs.ipfs.tech/concepts/how-ipfs-works/

ITI. ITI apoia BNDES em projeto de Blockchain. 2022.
https://www.gov.br/iti/pt-br/assuntos/noticias/indice-de-noticias/iti-apoia-bndes-em-projeto-de-blockchain

ITU-T. Technical Specification FG DLT D3.1 Distributed ledger technology reference architecture. Geneva, Switzerland: ITU-T, 2019. (FG DLT D3.1).
https://www.itu.int/en/ITU-T/focusgroups/dlt/Documents/d31.pdf

JABBAR, A.; DANI, S. Investigating the link between transaction and computational costs in a blockchain environment. International Journal of Production Research, [S.l.], v. 58, n. 11, p. 3423–3436, 2020.
https://www.tandfonline.com/doi/full/10.1080/00207543.2020.1754487

KAPSOULIS, N.; PSYCHAS, A.; PALAIOKRASSAS, G.; MARINAKIS, A.; LITKE, A.; VARVARIGOU, T.; BOUCHLIS, C.; RAOUZAIOU, A.; CALVO, G.; ESCUDERO SUBIRANA, J. Consortium Blockchain Smart Contracts for Musical Rights Governance in a Collective Management Organizations (CMOs) Use Case. Future Internet, [S.l.], v. 12, n. 8, 2020.
https://www.mdpi.com/1999-5903/12/8/134

KERESZTES, R.; KOVáCS, I.; HORVáTH, A.; ZIMáNYI, K. Exploratory Analysis of Blockchain Platforms in Supply Chain Management. Economies, [S.l.], v. 10, n. 9, 2022.
https://www.mdpi.com/2227-7099/10/9/206

KHAN, D.; JUNG, L. T.; HASHMANI, M. A. Systematic Literature Review of Challenges in Blockchain Scalability. Applied Sciences, [S.l.], v. 11, n. 20, 2021.
https://www.mdpi.com/2076-3417/11/20/9372

KHAN, S.; SHAEL, M.; MAJDALAWIEH, M.; NIZAMUDDIN, N.; NICHO, M. Blockchain for Governments: the case of the dubai government. Sustainability, [S.l.], v. 14, n. 11, 2022.
https://www.mdpi.com/2071-1050/14/11/6576

KLEMENS, S. How long does a bitcoin transaction take? bitcoin unconfirmed transactions. [S.l.]: Exodus Crypto News amp; Insights, 2021.
https://coinmarketcap.com/academy/article/how-long-does-a-bitcoin-transaction-take

KOHLI, V.; CHAKRAVARTY, S.; CHAMOLA, V.; SANGWAN, K. S.; ZEADALLY, S. An analysis of energy consumption and carbon footprints of cryptocurrencies and possible solutions. Digital Communications and Networks, [S.l.], 2022.
https://www.sciencedirect.com/science/article/pii/S2352864822001390

KOMOLAFE, O. Solana faster than Algorand and TRON – The fastest blockchains in crypto space. [S.l.]: Crypto News Flash, 2022.
https://www.crypto-news-flash.com/solana-faster-than-algorand-and-tron-the-fastest-blockchains-in-crypto-space/

KOUSSEMA, R. A.; HAGA, H. Design and Implementation of Highly Secure Residents Management System Using Blockchain. Journal of Computer and Communications, [S.l.], v. 08No.09, p. 14, 2020.
https://www.scirp.org/journal/paperinformation.aspx?paperid=102949

KUO, T.-T.; ZAVALETA ROJAS, H.; OHNO, L. Comparison of blockchain platforms: a systematic review and healthcare examples. Journal of the American Medical Informatics Association, [S.l.], v. 26, n. 5, p. 462–478, 03 2019.
https://pubmed.ncbi.nlm.nih.gov/30907419/

LASMOLES, O.; T. DIALLO, M. Impacts of Blockchains on International Maritime Trade. Journal of Innovation Economics & Management, Louvain-la-Neuve, v. 37, n. 1, p. 91–116, 2022.
https://www.cairn.info/revue-journal-of-innovation-economics-2022-1-page-91.htm

LENGE, J.; MUSUMBU, K.; WANUKU, G.; SUNGU, P. Blockchain Technology as A Guarantee of Transparency in The Supply Chain of Commercial Enterprises. In: ASIA  SERVICE SCIENCES AND SOFTWARE ENGINEERING CONFERENCE, 2022., 2022, New York, NY, USA. Anais. Association for Computing Machinery, 2022. p. 1–7. (ASSE’22).
https://dl.acm.org/doi/fullHtml/10.1145/3523181.3523182

LI, N.; GUO, Y.; CHEN, Y.; CHAI, J. A Partitioned DAG Distributed Ledger with Local Consistency for Vehicular Reputation Management. Wireless Communications and Mobile Computing, [S.l.], v. 2022, p. 6833535, Mar 2022.
https://www.hindawi.com/journals/wcmc/2022/6833535/

MAESA, D. D. F.; MORI, P. Blockchain 3.0 applications survey. Journal of Parallel and Distributed Computing, [S.l.], v. 138, p. 99 – 114, 2020.
https://www.sciencedirect.com/science/article/abs/pii/S0743731519308664

MANEVICH, Y.; BARGER, A.; TOCK, Y. Endorsement in Hyperledger Fabric via service discovery. IBM Journal of Research and Development, [S.l.], v. 63, n. 2/3, p. 2:1–2:9, 2019.
https://dl.acm.org/doi/10.1147/JRD.2019.2900647

MASOOD, F.; FARIDI, A. An Overview of Distributed Ledger Technology and its Applications. International Journal of Computer Sciences and Engineering, [S.l.], v. 6, p. 422–427, 10 2018.
https://www.researchgate.net/publication/330139945_An_Overview_of_Distributed_Ledger_Technology_and_its_Applications

MONTEIRO, E. S.; MIGNONI, M. E.; RIGHI, R. d. R.; KUNST, R. Blockchain e inteligência artificial associada no controle de packs agrotóxicos. RICA Revista Ibero-Americana de Ciências Ambientais, [S.l.], v. 12, n. 12, 2021.

MONTEIRO, E. S.; ROSA RIGHI, R. da; BARBOSA, J. L. V.; ALBERTI, A. M. APTM: a model for pervasive traceability of agrochemicals. Applied Sciences, [S.l.], v. 11, n. 17, 2021.
https://www.mdpi.com/2076-3417/11/17/8149

NIE, Y.; HE, X.-W.; CAI, W.-L.; LIU, Z.-H. Improve the security of Hyperledger Fabric by dynamically selecting endorsing peers. In: INTERNATIONAL SYMPOSIUM ON COMPUTER AND INFORMATION PROCESSING TECHNOLOGY (ISCIPT), 2021., 2021. Anais. . . [S.l.: s.n.], 2021. p. 659–663.
https://ieeexplore.ieee.org/document/9644558

OCDE. Recommendation of the council on blockchain and other distributed ledger technologies. 2 Rue André Pascal, 75016 Paris, France: OCDE, 2022. Council at Ministerial.
https://www.oecd.org/mcm/Recommendation-on-Blockchain-and-other-Distributed-Ledger-Technologies.pdf

OGUNDARE, I. Cardano to scale to 1,000,000 tps with Hydra for micropayments on ADA blockchain. [S.l.]: Crypto News Flash, 2022.
https://cardanofeed.com/cardano-to-scale-to-1000000-tps-with-hydra-for-micropayments-on-ada-blockchain-139538

PARK, S.; KIM, H. DAGmap: multi-drone slam via a dag-based distributed ledger. Drones, [S.l.], v. 6, n. 2, 2022.
https://www.researchgate.net/publication/358001662_DAGmap_Multi-Drone_SLAM_via_a_DAG-Based_Distributed_Ledger

PENG, Y.; DU, M.; LI, F.; CHENG, R.; SONG, D. FalconDB: blockchain-based collaborative database. In: ACM SIGMOD INTERNATIONAL CONFERENCE ON MANAGEMENT OF DATA, 2020., 2020, New York, NY, USA. Proceedings. . . Association for Computing Machinery, 2020. p. 637–652. (SIGMOD ’20).
https://dl.acm.org/doi/10.1145/3318464.3380594

PEREZ, A. O.; DOMINGO-PALAOAG, T. Blockchain-based Model for Health Information Exchange: a case for simulated patient referrals using an electronic medical record. IOP Conference Series: Materials Science and Engineering, [S.l.], v. 1077, n. 1, p. 012059, feb 2021.
https://iopscience.iop.org/article/10.1088/1757-899X/1077/1/012059

PRASHAR, D.; JHA, N.; JHA, S.; LEE, Y.; JOSHI, G. P. Blockchain-Based Traceability and Visibility for Agricultural Products: a decentralized way of ensuring food safety in india. Sustainability, [S.l.], v. 12, n. 8, 2020.
https://www.mdpi.com/2071-1050/12/8/3497

PSARAS, Y.; SOARES, J. M.; DIAS, D. To the InterPlanetary File System–and Beyond!: peer-to-peer file sharing would make the internet far more efficient. IEEE Spectrum, [S.l.], v. 59, n. 11, p. 34–39, 2022.
https://ieeexplore.ieee.org/document/9941036

PURBO, O.; SRIYANTO, S.; SUHENDRO, S.; RZ, A.; HERWANTO, R. Benchmark and comparison between hyperledger and MySQL. TELKOMNIKA (Telecommunication Computing Electronics and Control), [S.l.], v. 18, p. 705, 04 2020.
https://pdfs.semanticscholar.org/fcd6/2761cfd48eb7974ae89b7953246d332f09a2.pdf

RAUCHS, M.; GLIDDEN, A.; GORDON, B.; PIETERS, G.; RECANATINI, M.; ROSTAND, F.; VAGNEUR, K.; ZHANG, B. Distributed Ledger Technology Systems: a conceptual framework. SSRN Electronic Journal, [S.l.], 01 2018.
https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3230013

SA, R.; MOREIRA, L.; MACHADO, J. A modular approach to Hybrid Blockchain-based and Relational Database Architectures. In: ESTENDIDOS DO XXXVII SIMPóSIO BRASILEIRO DE BANCOS DE DADOS, 2022, Porto Alegre, RS, Brasil. Anais. . . SBC, 2022. p. 154–160.
https://sol.sbc.org.br/index.php/sbbd_estendido/article/view/21858

SADEQ, M. J.; RAYHAN KABIR, S.; AKTER, M.; FORHAT, R.; HAQUE, R.; AKHTARUZZAMAN, M. Integration of Blockchain and Remote Database Access Protocol-Based Database. In: FIFTH INTERNATIONAL CONGRESS ON INFORMATION AND COMMUNICATION TECHNOLOGY, 2021, Singapore. Proceedings. . . Springer Singapore, 2021. p. 533–539.
https://www.researchgate.net/publication/344194318_Integration_of_Blockchain_and_Remote_Database_Access_Protocol-based_Database

SALAH, K.; REHMAN, M. H. U.; NIZAMUDDIN, N.; AL-FUQAHA, A. Blockchain for AI: review and open research challenges. IEEE Access, [S.l.], v. 7, p. 10127–10149, 2019.
https://ieeexplore.ieee.org/document/8598784

SILVA, J. O. D. da; SANTOS, D. R. dos. Study of Blockchain Application in the Logistics Industry. Theoretical Economics Letters, [S.l.], v. 12, n. 2, p. 321–342, 4 2022.
https://www.scirp.org/journal/paperinformation.aspx?paperid=115674

SINGH, A.; GUTUB, A.; NAYYAR, A.; KHAN, M. K. Redefining food safety traceability system through blockchain: findings, challenges and open issues. Multimedia Tools and Applications, [S.l.], Oct 2022.
https://link.springer.com/article/10.1007/s11042-022-14006-4

SINGH, N.; VARDHAN, M. Computing Optimal Block Size for Blockchain based Applications with Contradictory Objectives. Procedia Computer Science, [S.l.], v. 171, p. 1389–1398, 2020. Third International Conference on Computing and Network Communications (CoCoNet’19).
https://www.sciencedirect.com/science/article/pii/S1877050920311285

SOLVEJ, K.; NATARAJAN, K.; HARISH, G.; LUSKIN, H. Distributed Ledger Technology (DLT) and blockchain. Washington, D.C., 2017.
https://openknowledge.worldbank.org/entities/publication/563eb421-4449-5319-953b-2ace8da058c0

SULTAN, K.; RUHI, U.; LAKHANI, R. Conceptualizing Blockchains: characteristics & applications. CoRR, [S.l.], v. abs/1806.03693, 2018.
https://arxiv.org/abs/1806.03693

SYLIM, P. G.; LIU, F.; MARCELO, A. B.; FONTELO, P. A. Blockchain Technology for Detecting Falsified and Substandard Drugs in Distribution: pharmaceutical supply chain intervention. JMIR Research Protocols, [S.l.], v. 7, 2018.
https://pubmed.ncbi.nlm.nih.gov/30213780/

SYSRFID: GENERATION OF SYNTHETIC DATA IN SUPPLY CHAINS, 2011, Rome, Italy. Anais. . . itAIS, 2011. p. 6.
http://www.itais.org/proceedings/itais2011/pdf/25.pdf

TAN, E.; MAHULA, S.; CROMPVOETS, J. Blockchain governance in the public sector: a conceptual framework for public management. Government Information Quarterly, [S.l.], v. 39, p. 101625, 09 2021.
https://www.sciencedirect.com/science/article/pii/S0740624X21000617

TCU. TCU e BNDES lançam Rede Blockchain Brasil e definem próximos passos. 2022.
https://portal.tcu.gov.br/imprensa/noticias/tcu-e-bndes-lancam-rede-blockchain-brasil-e-definem-proximos-passos.htm#:~:text=O%20Tribunal%20de%20Contas%20da,aplica%C3%A7%C3%A3o%20descentralizada%20ocorra%20em%202023.

VIRIYASITAVAT, W.; HOONSOPON, D. Blockchain characteristics and consensus in modern business processes. Journal of Industrial Information Integration, [S.l.], v. 13, p. 32–39, 2019.
https://www.semanticscholar.org/paper/Blockchain-characteristics-and-consensus-in-modern-Viriyasitavat-Hoonsopon/cf58f0c53a2bd2c0a1ee7bec77920c3f80036ac2

WANG, Z.; WANG, T.; HU, H.; GONG, J.; REN, X.; XIAO, Q. Blockchain-based framework for improving supply chain traceability and information sharing in precast construction. Automation in Construction, [S.l.], v. 111, p. 103063, 2020.
https://www.sciencedirect.com/science/article/abs/pii/S0926580519305059

WORLDBANK. Blockchain & Distributed Ledger Technology (DLT). 2018. 1 p.
https://openknowledge.worldbank.org/server/api/core/bitstreams/5166f335-35db-57d7-9c7e-110f7d018f79/content

XU, S.; ZHAO, X.; LIU, Z. The impact of blockchain technology on the cost of food traceability supply chain. IOP Conference Series: Earth and Environmental Science, [S.l.], v. 615, n. 1, p. 012003, dec 2020.
https://iopscience.iop.org/article/10.1088/1755-1315/615/1/012003/pdf

XU, X.; LU, Q.; LIU, Y.; ZHU, L.; YAO, H.; VASILAKOS, A. V. Designing blockchain-based applications a case study for imported product traceability. Future Generation Computer Systems, [S.l.], v. 92, p. 399–406, 2019.
https://www.sciencedirect.com/science/article/abs/pii/S0167739X18314298

YADAV, J.; SHEVKAR, R. Performance-Based Analysis of Blockchain Scalability Metric. Tehnicki glasnik, [S.l.], v. 15, p. 133–142, 03 2021.
https://hrcak.srce.hr/file/367642

YUE, K.-B.; CHANDRASEKAR, K.; AND, H. G. Storing and Querying Bitcoin Blockchain Using SQL Databases. Information Systems Education Journal (ISEDJ), Texas, USA, v. 8, 8 2019.
https://files.eric.ed.gov/fulltext/EJ1219543.pdf

ZAKARI, N.; AL-RAZGAN, M.; ALSAADI, A.; ALSHAREEF, H.; SAIGH, H. A.; ALASHAIKH, L.; ALHARBI, M.; ALOMAR, R.; ALOTAIBI, S. Blockchain technology in the pharmaceutical industry: a systematic review. PeerJ Comput. Sci., [S.l.], p. 26, 3 2022.
https://peerj.com/articles/cs-840/

ZHAO, F.; GUO, X.; CHAN, W. K. V. Individual Green Certificates on Blockchain: a simulation approach. Sustainability, [S.l.], v. 12, n. 9, 2020.
https://www.mdpi.com/2071-1050/12/9/3942

ZHAO, W.; LV, J.; YAO, X.; ZHAO, J.; JIN, Z.; QIANG, Y.; CHE, Z.; WEI, C. Consortium Blockchain-Based Microgrid Market Transaction Research. Energies, [S.l.], v. 12, n. 20, 2019.
https://www.mdpi.com/1996-1073/12/20/3812

[Voltar ao início](#sobre-blockchain-e-livros-razão)


---
# Avisos & licença

## Aviso
```
Este material esta recebendo atualizações frequentes. 
As informações aqui contidas podem ser alteradas sem aviso prévio.
```

## Licença
```
Organizado e mantida pelo Prof. Dr. Monteiro, E. S.
Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0) 
https://creativecommons.org/licenses/by-nc-sa/4.0/
```


---
# Estatísticas desta página


[![GitHub Streak](https://streak-stats.demolab.com/?user=monteiro74&theme=dark)](https://git.io/streak-stats)


[![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=monteiro74)](https://github.com/monteiro74/github-readme-stats)

Histórico de atualizações nos repositórios do Prof. Monteiro:<br>
[![teste](https://github-readme-activity-graph.vercel.app/graph?username=monteiro74&theme=github-compact)](https://github.com/monteiro74/aulas_2023)


Pulse:<br>
https://github.com/monteiro74/aulas_2023/pulse<BR>

Contribuições de:<br>
<a href="https://github.com/monteiro74/tutorial_python/contributors">
  <img src="https://contrib.rocks/image?repo=monteiro74/tutorial_python" />
</a>

Histórico de frequência de código:<BR>
https://github.com/monteiro74/aulas_2023/graphs/code-frequency<BR>

Atividade de commits:<BR>
https://github.com/monteiro74/aulas_2023/graphs/commit-activity<BR>

Trafego:<BR>
https://github.com/monteiro74/aulas_2023/graphs/traffic<BR>


![stats](https://github-readme-stats.vercel.app/api?username=monteiro74&show=reviews,discussions_started,discussions_answered,prs_merged,prs_merged_percentage)

![stats](https://github-readme-stats.vercel.app/api?username=monteiro74&show_icons=true&theme=dark)

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=monteiro74)](https://github.com/monteiro74/github-readme-stats)

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=monteiro74&layout=donut-vertical)](https://github.com/monteiro74/github-readme-stats)

