# Sobre Blockchain e livros razão



[1 Conceitos](#1-Conceitos) <br>
[1.1. O problema de double spending](#11-o-problema-de-double-spending)<br>
[1.2. Criptografia de chave pública](#12-critografia-de-chave-pública)<br>
[1.3. Certificado digital](#13-certificado-digital)<br>
[1.4. Tecnologias de livro razao](#14-tecnologias-de-livro-razao)<br>
[2. Aplicabilidade](#2-Aplicabilidade)<br>
[3. Tendências](#3-Tendências)<br>
[4. Artigos interessantes](#4-Artigos-interessantes)<br>
[5. Fontes](#5-fontes)<br>
[6. Videos](#6-videos)<br>
[7. Reportagens](#7-reportagens)<br>



---
# 1 Conceitos


## 1.1. O problema de double spending

É um problema que surge ao transacionar moeda digital que envolve o mesmo gasto sendo gasto várias vezes. Múltiplas transações que compartilham a mesma informação transmitida na rede podem ser problemáticas e são uma falha exclusiva das moedas digitais. A principal razão para o gasto duplo é que a moeda digital pode ser facilmente reproduzida. <br>
Fonte: https://corporatefinanceinstitute.com/resources/cryptocurrency/double-spending/


A tecnologia Blockchain evita gastos duplos através da tecnologia de compartilhamento de arquivos peer-to-peer combinada com criptografia de chave pública.

Blockchain resolve o problema do gasto duplo usando um livro-razão descentralizado, que todos podem acessar. Como todos os membros da rede podem examinar o histórico completo das transações, estes podem ter certeza de que nem suas cripto moedas nem quaisquer outras cripto moedas foram gastas mais de uma vez.



[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

## 1.2. Critografia de chave pública

Este tipo de criptografia envolve dois tipos de chaves, uma pública e uma privada. A chave pública pode ser compartilhada com terceiros. A chave privada deve ficar oculta. Dados são criptografos com a chave pública do destinatário,e pode ser decriptografa com a chave privada do destinatário. As chaves RSA pode ter vários tamanhos desde 1024 a 2048 bits. 



Criptografia de chave pública também é chamada de criptografia assimétrica. Neste sistema qualquer um com uma chave pública pode gerar mensagens criptografadas, mas somente aqueles que detem as chaves privadas correspondentes pode decifrá-las e obter a mensagem original.

Atualmente uma das implementações de critografia de chave pública mais utilizadas é baseada no algoritmos apresentados por Rivest-Shamir-Adelman (RSA) da Data Security. Outros algoritmos que implementam criptografia de chave pública: DSS, Elliptic curve, Paillier cryptosystem, Cramer-shoup, YAK, etc. Este tipo de criptografia também é muito utilizada no HTTPS com o TLS/SSL.

Programa que implementa criptografia e assinatura de mensagem: https://www.openpgp.org/.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

## 1.3. Certificado digital

Exemplos:
https://pt.wikipedia.org/wiki/Certificado_digital#/media/Ficheiro:Client_and_Server_Certificate.png

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

## 1.4. Tecnologias de livro razao

Tecnologias de livro razão distribuídas (ou "Distributed Ledger Technology (DLT)" do inglês) podem ser usadas para resolver problemas provocados pelo uso de uma terceira parte para autenticar transações, evitar cobranças de serviços, diminuir tempo de processamento, não se submeter a uma autoridade central e evitar um ponto de falha. 

Desta forma as DLT são interessantes para resolver uma série de problemas em um ambiente distribuído no qual vários participantes devem trocar dados, e geralmente estão
a distâncias significativas e podem não ter os mesmos relacionamentos de confiança. 

DLT são implementações específica de uma categoria mais ampla de "livros razões compartilhados", que são simplesmente definidos como um registro compartilhado de dados em diferentes partes. 

As DLT devem ser projetadas para trabalhar em ambientes que operam como máquinas de estados com múltiplos atores os quais compartilham registros entre si.

Um sistema de DLT deve: 

A) permitir que seus participantes trabalhem de acordo com um determinado critério (ou consenso); 

B) manter uma ordem de transações validada; 

C) replicar os dados em vários nós; 

D) manter um link entre as transações para evitar adulterações; 

E) conter o livro razão (ou ledger) que é o resultado do processo de registro de transações (o qual relata a história das transações. 

O registro em uma DLT pode ser realizado sob dois aspectos permissionless (na qual cada participantes pode escrever um registro na ledger) ou permissioned (na qual somente alguns participantes podem submeter envios). 

Quanto ao processamento e execução de tarefas ou programas na DLT, estas podem ser on-chain (execução interna), off-chain (execução externa) e side-chain (execução parcialmente interna com auxílio computacional externo). 

DLT podem ser divididas em duas classes: 

A) grafos acíclicos dirigidos (ou directed acyclic graph (DAG) do inglês) e, 

B) blockchain. Blockchain e DAG são sub tipos de DLTs.

As principais subdivisões e alguns exemplos são:

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

### 1.4.1. Gráfos acíclicos dirigidos


Uma forma de DLT é um grafo acíclico dirigido (DAG), o qual utiliza uma estrutura parecida com vértices e arestas; as arestas são posicionados em uma direção e o grafo é acíclico pois
os vértices não se referenciam nem formam um loop para si mesmos. 

Nos sistemas DAG não é
necessário um minerador, pois cada usuário pode controlar sua própria sequência de blocos de
forma assíncrona. 

Sempre que uma transação é realizada, os participantes devem verificar duas
outras transações de outros nós (PARK; KIM, 2022). 

Cada transação no DAG é um vértice,
cada vértice tem uma ou mais arestas em direção a outros vértices, desta forma um vértice referencia outro vértice. 

Uma transação é registrada após a outra formando uma linearidade, porém
o DAG não usa mineração ou custos de transação; pois um nó realiza validação simultânea de
transações. 

Cada transação é registrada em vértices e não existe a necessidade de serem gravadas em bloco, formando uma cadeia de transações verificadas (LI et al., 2022). Com o DAG os
participantes são mineradores e validadores de transações.

Um exemplo da estrutura DAG é apresentada na Figura 6. 

São alguns exemplos de projetos
que utilizam DAG: IOTA4(é um DAG voltada para armazenar dados de IoT), NANO5(é uma
criptomoeda e uma plataforma para transação de valores ponto-a-ponto), Obyte6(é uma DAG e
criptomoeda), Hedera7(é uma rede pública baseada em DAG e uma criptomoeda) e IPFS8(é um
sistema de arquivos distribuído, utilizado em uma rede ponto-a-ponto.). 

DAG é usada pelo IPFS
onde cada identifcador tem um hash do conteúdo para um conteúdo, é usado para representar
arquivos e diretórios, o IPFS quebra um arquivo em pedaços chamados de blocos, (IPFS, 2022).

Os blocos podem estar em vários lugares. 

Um arquivo é composto de vários blocos, cada bloco
tem um identificador. 

Para localizar este arquivo composto por vários blocos o IPFS usa o que é
chamado de tabela hash para localizar arquivos. 

Com esta tabela, um grupo de nós pode conter
partes diferentes de um arquivo. 

Nesta tabela, existem duas colunas uma com um hash inicia
e final e a outra coluna com o conteúdo do arquivo. 

Dependendo qual o valor da chave hash
o arquivo pode ser armazenado na tabela (no topo, por exemplo), para recuperar o arquivo é
necessário percorrer a tabela, (PSARAS; SOARES; DIAS, 2022).

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

### 1.4.2. Blockchain


Blockchain é uma cadeia de blocos, na qual cada nó tem blocos de dados, um carimbo de data/hora e um hash de código que se refere ao nó anterior, reforçando a cadeia de dados de forma imutável. 

A tecnologia blockchain foi inicialmente projetada para oferecer suporte a moedas criptográficas, mas hoje, pode-se usá-la para outros fins, incluindo rastreamento da cadeia logística e contratos entre pessoas que não se conhecem. 

Assim, a blockchain funciona salvando as transações de interesse para as quais foi projetada, onde cada uma pode implementar uma série de regras e também servir para transmitir dados. 

Em particular, as regras para a execução de transações ou operações são realizadas por meio de contratos inteligentes. 

Do ponto de vista do programador, elas podem ser vistas como um script (ou, simplificando, um programa que deve ser executado automaticamente quando uma transação é realizada). 

Assim, blockchain pode conter dados e código executável (MAESA; MORI, 2020), onde o último é visto como a lógica de programação para atualizar dados e disparar ações externas ao blockchain.


* "Bloco" são os dados armazenados de forma sequencial.<br>

* "Cadeia" é o termo usado porque um dos campos do bloco é um apontador para o seu bloco pai. Desta forma os bloco são serializados e unidos sequencialmente. 


Artigo que iniciou com a ideia: [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf).


[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

### 1.5. Ethereum 

Ethereum é uma rede de computadores em todo o mundo que segue um conjunto de regras do chamado protocolo Ethereum.

### 1.6. EVM

A Máquina Virtual Ethereum é o computador virtual global cujo estado todos os participantes (nós) da rede Ethereum armazenam (seu estado) e concordam. Qualquer participante pode solicitar a execução de código arbitrário na EVM; a execução do código (via smart contract) altera o estado do EVM. 


### 1.7. Smart contracts

Contratos inteligentes são programas de computador que estão e rodam na blockchain Ethereum. Transações acionam smart contracts. São acionados por aplicativos de usuários. Nick Szabo cunhou o termo "smart contract“, em 1994. Szabo idealizou um mercado virtual onde negócios automáticos e criptografados permitissem que transações ocorressem sem intermediários confiáveis.

Fonte: https://ethereum.org/en/smart-contracts/

### 1.8. ETH

ETH é uma criptomoeda (similar ao Bitcoin). Enviar ETH para outra pessoa você pagará uma taxa em ETH. Esse valor pago em ETH é a motivação para os validadores de bloco processar e verificar o que os usuários desejam fazer. Validadores são selecionados aleatóriamente para tratar um bloco de transações e posteriormente são recompensados com ETH.

Fonte: https://ethereum.org/en/eth/

### 1.9. Wallets

Uma carteira é uma forma de se controlar uma conta. Ela contém a identidade do usuário e seus ativos, além de informar saldos e enviar transações. A carteira é uma forma de interação com a rede Ethereum.

#### 1.9.1. Carteiras, Contas, Chaves e Endereços

* Uma conta Ethereum é um par de chaves. Uma chave (pública) é usada para criar o endereço que pode ser compartilhado livremente e a outra chave (privada) é mantida em segredo porque é usada para assinar transações. Juntas, essas chaves permitem manter ativos e fazer transações.
* Uma conta Ethereum possui um endereço, assim como um email possui uma caixa de entrada. Isso é usado para identificar ativos digitais.
* Uma carteira é uma ferramenta (de software ou hardware) que permite interagir com uma conta, usando uma par de chaves. Ele permite que se visualize o saldo de uma conta, envie transações etc.
* A maioria dos produtos de carteira permite gerar uma conta Ethereum.

Fonte: https://ethereum.org/en/wallets

### 1.10. Gas fee

Cada transação realizada no Ethereum consome "gas".
Enviar uma transação ou executar um smart contract gasta "gas".

Fonte: https://ethereum.org/en/wallets/

### 1.11. Mining (mineração)

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

### 1.12. Consenso

É um sistema que valida uma transação e a marca como autêntica. Este mecanismo lista todas as transações válidas de uma moeda em uma blockchain para construir confiança na moeda entre os comerciantes. Diversas moedas, como Bitcoin, Ethereum etc., utilizam este sistema.

PoW (Proof of Work): ‘Prova’ refere-se à solução de um problema altamente complexo, e ‘trabalho’ refere-se ao processo de resolução do mesmo. Os mineradores de moedas criptográficas competem para resolver o problema e ganhar o direito de processar a transação. O solucionador mais rápido recebe uma taxa de mineração dos comerciantes dessas moedas.

Fonte https://cleartax.in/s/consensus-in-blockchain

### 1.13. IDE para programar com Ethereum

Remis Ethereum https://remix.ethereum.org/

Simulador local de Ethereum para desenvolvimento: Ganache



--- 
# 2 Aplicabilidade 


Em desenvolvimento.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 3 Tendências


Em desenvolvimento.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 4 Artigos interessantes

1. [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf)


Em desenvolvimento. 

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 5 Fontes


Em desenvolvimento.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 6 Videos


[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 7 Reportagens

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>