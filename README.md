# Sobre Blockchain e livros razão

Objetivos: 
Alguns conceitos sobre blockchain para serem discutidos em sala de aula. Exemplos que podem ser citados e comentados nas disciplinas que necessitam do apoio de uma banco de dados e projeto de sistemas. Este material é extremamente resumido e supõe que o leitor tem conhecimento básico de programação ou banco de dados. Este não é um guia definitivo, mas um pequeno tutorial compilado para auxiliar alunos e devs. Este material esta em construção.

---
Observações:
```
1. Este material pode ser usado como suporte às disciplinas de: banco de dados e projeto de sistemas.
2. Este material foi ou poderá ser usado em sala de aula/laboratório/EAD.
3. É um prerequisito conhecimentos básicos de, segurança da 
informação, programação e banco de dados.
4. Esta página poderá passar por atualizações sem aviso prévio.
```


---

[1 Conceitos](#1-Conceitos) <br>
[1.1. O problema de double spending](#11-o-problema-de-double-spending)<br>
[1.2. Criptografia de chave pública](#12-critografia-de-chave-pública)<br>
[1.3. Certificado digital](#13-certificado-digital)<br>
[1.4. Tecnologias de livro razao](#14-tecnologias-de-livro-razao)<br>
[1.4.1. Gráfos acíclicos dirigidos](#141-gráfos-acíclicos-dirigidos)<br>
[1.4.2. Blockchain](#142-blockchain)<br>
[1.4.3. Diferentes tipos de DLT](#143-diferentes-tipos-de-dlt)<br>
[1.4.4. Alguns projetos desde o surgimento até 2022](#144-alguns-projetos-de-blockchain-desde-o-surgimento-até-2022)<br>
[1.5. Ethereum](#15-ethereum)<br>
[1.6. EVM](#16-evm)<br>
[1.7. Smart Contract](#17-smart-contracts)<br>
[1.8. ETH](#18-eth)<br>
[1.9. Wallets](#19-wallets)<br>
[1.10. Gas fee](#110-gas-fee)<br>
[1.11. Mining](#111-mining-mineração)<br>
[1.12. Consenso](#112-consenso)<br>
[1.13. IDE para programar com Ethereum](#113-ide-para-programar-com-ethereum)<br>
[2. Aplicabilidade](#2-Aplicabilidade)<br>
[3. Tendências](#3-tendências)<br>
[4. Artigos interessantes](#4-Artigos-interessantes)<br>
[5. Fontes](#5-fontes)<br>
[6. Videos](#6-videos)<br>
[7. Reportagens](#7-reportagens)<br>



---
# 1 Conceitos


## 1.1. O problema de double spending

É um problema que surge ao transacionar moeda digital que envolve o mesmo gasto sendo gasto várias vezes. Múltiplas transações que compartilham a mesma informação transmitida na rede podem ser problemáticas e são uma falha exclusiva das moedas digitais. A principal razão para o gasto duplo é que a moeda digital pode ser facilmente reproduzida. <br>
Fonte: https://corporatefinanceinstitute.com/resources/cryptocurrency/double-spending/


A tecnologia Blockchain evita gastos duplos através da tecnologia de compartilhamento de arquivos peer-to-peer combinada com criptografia de chave pública. Blockchain resolve o problema do gasto duplo usando um livro-razão descentralizado, que todos podem acessar. Como todos os membros da rede podem examinar o histórico completo das transações, estes podem ter certeza de que nem suas cripto moedas nem quaisquer outras cripto moedas foram gastas mais de uma vez.



[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

## 1.2. Critografia de chave pública

Este tipo de criptografia envolve dois tipos de chaves, uma pública e uma privada. A chave pública pode ser compartilhada com terceiros. A chave privada deve ficar oculta. Dados são criptografos com a chave pública do destinatário,e pode ser decriptografa com a chave privada do destinatário. As chaves RSA pode ter vários tamanhos desde 1024 a 2048 bits. Criptografia de chave pública também é chamada de criptografia assimétrica. Neste sistema qualquer um com uma chave pública pode gerar mensagens criptografadas, mas somente aqueles que detem as chaves privadas correspondentes pode decifrá-las e obter a mensagem original.

Atualmente uma das implementações de critografia de chave pública mais utilizadas é baseada no algoritmos apresentados por Rivest-Shamir-Adelman (RSA) da Data Security. Outros algoritmos que implementam criptografia de chave pública: DSS, Elliptic curve, Paillier cryptosystem, Cramer-shoup, YAK, etc. Este tipo de criptografia também é muito utilizada no HTTPS com o TLS/SSL.

Programa que implementa criptografia e assinatura de mensagem: https://www.openpgp.org/.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

## 1.3. Certificado digital

Exemplos:
https://pt.wikipedia.org/wiki/Certificado_digital#/media/Ficheiro:Client_and_Server_Certificate.png

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

## 1.4. Tecnologias de livro razao

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



As principais subdivisões e alguns exemplos são:

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

### 1.4.1. Gráfos acíclicos dirigidos

Uma forma de DLT é um grafo acíclico dirigido (DAG), o qual utiliza uma estrutura parecida com vértices e arestas; as arestas são posicionados em uma direção e o grafo é acíclico pois
os vértices não se referenciam nem formam um loop para si mesmos.  Nos sistemas DAG não é necessário um minerador, pois cada usuário pode controlar sua própria sequência de blocos de forma assíncrona.  Sempre que uma transação é realizada, os participantes devem verificar duas outras transações de outros nós (PARK; KIM, 2022). 

Cada transação no DAG é um vértice, cada vértice tem uma ou mais arestas em direção a outros vértices, desta forma um vértice referencia outro vértice. Uma transação é registrada após a outra formando uma linearidade, porém o DAG não usa mineração ou custos de transação; pois um nó realiza validação simultânea de transações. Cada transação é registrada em vértices e não existe a necessidade de serem gravadas em bloco, formando uma cadeia de transações verificadas (LI et al., 2022). Com o DAG os participantes são mineradores e validadores de transações.
 
![Exemplos de DAG](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig2.png "Exemplos de DAG")


São alguns exemplos de projetos que utilizam DAG: IOTA4(é um DAG voltada para armazenar dados de IoT), NANO5(é uma criptomoeda e uma plataforma para transação de valores ponto-a-ponto), Obyte6(é uma DAG e criptomoeda), Hedera7(é uma rede pública baseada em DAG e uma criptomoeda) e IPFS8(é um sistema de arquivos distribuído, utilizado em uma rede ponto-a-ponto.). DAG é usada pelo IPFS onde cada identifcador tem um hash do conteúdo para um conteúdo, é usado para representar arquivos e diretórios, o IPFS quebra um arquivo em pedaços chamados de blocos, (IPFS, 2022).

Os blocos podem estar em vários lugares. Um arquivo é composto de vários blocos, cada bloco tem um identificador. Para localizar este arquivo composto por vários blocos o IPFS usa o que é chamado de tabela hash para localizar arquivos. Com esta tabela, um grupo de nós pode conter partes diferentes de um arquivo.  Nesta tabela, existem duas colunas uma com um hash inicia e final e a outra coluna com o conteúdo do arquivo. Dependendo qual o valor da chave hash o arquivo pode ser armazenado na tabela (no topo, por exemplo), para recuperar o arquivo é necessário percorrer a tabela, (PSARAS; SOARES; DIAS, 2022).

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

### 1.4.2. Blockchain


Blockchain é uma cadeia de blocos, na qual cada nó tem blocos de dados, um carimbo de data/hora e um hash de código que se refere ao nó anterior, reforçando a cadeia de dados de forma imutável. A tecnologia blockchain foi inicialmente projetada para oferecer suporte a moedas criptográficas, mas hoje, pode-se usá-la para outros fins, incluindo rastreamento da cadeia logística e contratos entre pessoas que não se conhecem.  Assim, a blockchain funciona salvando as transações de interesse para as quais foi projetada, onde cada uma pode implementar uma série de regras e também servir para transmitir dados. 

Em particular, as regras para a execução de transações ou operações são realizadas por meio de contratos inteligentes. Do ponto de vista do programador, elas podem ser vistas como um script (ou, simplificando, um programa que deve ser executado automaticamente quando uma transação é realizada). Assim, blockchain pode conter dados e código executável (MAESA; MORI, 2020), onde o último é visto como a lógica de programação para atualizar dados e disparar ações externas ao blockchain.


* "Bloco" são os dados armazenados de forma sequencial.<br>

* "Cadeia" é o termo usado porque um dos campos do bloco é um apontador para o seu bloco pai. Desta forma os bloco são serializados e unidos sequencialmente. 

![Cadeia de blocos](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig3.png "Cadeia de blocos")

Artigo que iniciou com a ideia: [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf).


[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>


### 1.4.3. Diferentes tipos de DLT


| Propriedade   | Públicas   | Consórcios   | Privadas  |
|---|---|---|---|
| Acesso a leitura de dados  | Sem restrição  | Com ou sem restrição  | Com ou sem restrição  |  
| Acesso a escrita de dados  | Sem restrição  | Sem restrição ou somente com entidades pré-selecionadas  | Uma entidade única  | 
| Participa no processo de validação  | Sem restrição  | Somente com entidades pré-selecionadas  | Sem validação de dados  |
| Complexidade de validação| Consenso complexo de validação, envolve falha bizantina | Consenso de validação facilitado| Consenso não é necessário | 

### 1.4.4. Alguns projetos de blockchain desde o surgimento até 2022

Projetos de blockchain a partir do ano de criação até 2022: Hyperledger Fabric9, Multichain blockchain10, SAP blockchain11, Hyperledger Besu12, Oracle blockchain13, Hathor blockchain14, VMware VMBC15, Azure Confidential Ledger16, XO-DEX17, Nano18, Dragonchain19, Openchain20, GoQuorum21. Estes projetos de blockchain apresentam características de custo zero de transação (ou taxa zero), as quais podem ser explorada por blockchain privadas.

![Alguns projetos de blockchain até 2022](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig4.png)

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

* PoW (Proof of Work): ‘Prova’ refere-se à solução de um problema altamente complexo, e ‘trabalho’ refere-se ao processo de resolução do mesmo. Os mineradores de moedas criptográficas competem para resolver o problema e ganhar o direito de processar a transação. O solucionador mais rápido recebe uma taxa de mineração dos comerciantes dessas moedas.

* PoS (Proof of Stake): Este mecanismo escolhe aleatoriamente um proprietário máximo de moedas para validar uma transação. Também permite ao proprietário criar um bloco para a mesma moeda. Este mecanismo requer comparativamente menos energia, tempo de transação e uma taxa mais baixa. Moedas como Etherium 2.0


Fonte https://cleartax.in/s/consensus-in-blockchain

### 1.13. IDE para programar com Ethereum

Remix IDE:

![Remix IDE](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig5.png)

[Remix Ethereum](https://remix.ethereum.org/).

Simulador local de Ethereum para desenvolvimento [Ganache](https://trufflesuite.com/ganache/).


--- 
# 2 Aplicabilidade 


Desenvolvimento de criptomoedas

Comércio de ativos (NFT, tokens não fungíveis)

Rastreabilidade de transações

Registro imutável de informações

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 3 Tendências

Google trends usado para mostrar tendências:

https://trends.google.com.br/trends/explore?date=today%205-y&q=blockchain,%2Fg%2F11g0g4sbp3,Ethereum&hl=pt-BR

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 4 Artigos interessantes

1. [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf)


Em desenvolvimento. 

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 5 Fontes


Diversas fontes de pesquisa sobre blockchain:

AGI, M. A.; JHA, A. K. Blockchain technology in the supply chain: an integrated theoretical perspective of organizational adoption. International Journal of Production Economics, [S.l.], v. 247, p. 108458, 2022.

AHMED, S.; KALSOOM, T.; RAMZAN, N.; PERVEZ, Z.; AZMAT, M.; ZEB, B.; UR REHMAN, M. Towards Supply Chain Visibility Using Internet of Things: a dyadic analysis review. Sensors, [S.l.], v. 21, n. 12, 2021. AL-SAID AHMAD, A.; ANDRAS, P. Scalability analysis comparisons of cloud-based software services. Journal of Cloud Computing, [S.l.], v. 8, n. 1, p. 10 Jul 2019.

ANTONOPOULOS, P.; KAUSHIK, R.; KODAVALLA, H.; ROSALES ACEVES, S.; WONG,
R.; ANDERSON, J.; SZYMASZEK, J. SQL Ledger: cryptographically verifiable data in azure sql database. In: INTERNATIONAL CONFERENCE ON MANAGEMENT OF DATA, 2021., 2021, New York, NY, USA. Proceedings. . . Association for Computing Machinery, 2021. p. 2437–2449. (SIGMOD ’21).

BASSILIOS, J. OECD adopts recommendations on blockchain and other DLT. Accessed:
2022-10-20.

BERAWI, M. A.; REYES, G.; SARI, M.; SAROJI, G. Developing Public-Private Partnership
Model with Blockchain-Based Crowdfunding Concept for Port City Project. In:
ASSOCIATION FOR COMPUTING MACHINERY, 2021, New York, NY, USA. Anais. . .
Association for Computing Machinery, 2021. (SPBPU IDE ’20).

BROOKBANKS, M. M.; PARRY, G. The impact of a blockchain platform on trust in
established relationships: a case study of wine supply chains. Supply Chain Management,
[S.l.], 2022.

BUSH, K. Blockchain: novel provenance applications. Washington, DC: Congressional
Research Service, 2022. (R47064).

BUSTAMANTE, P.; CAI, M.; GOMEZ, M.; HARRIS, C.; KRISHNAMURTHY, P.; LAW, W.;
MADISON, M. J.; MURTAZASHVILI, I.; MURTAZASHVILI, J. B.; MYLOVANOV, T.;
SHAPOVAL, N.; VEE, A.; WEISS, M. Government by Code? Blockchain Applications to
Public Sector Governance. Frontiers in Blockchain, [S.l.], v. 5, 2022.

CAGIGAS, D.; CLIFTON, J.; DIAZ-FUENTES, D.; FERNáNDEZ-GUTIéRREZ, M.
Blockchain for Public Services: a systematic literature review. IEEE Access, [S.l.], v. 9,
p. 13904–13921, 2021.
CAI, Z.; YANG, G.; XU, S.; ZANG, C.; CHEN, J.; HANG, P.; YANG, B. RBaaS: a robust
blockchain as a service paradigm in cloud-edge collaborative environment. IEEE Access,
[S.l.], v. 10, p. 35437–35444, 2022.

CHARLON, F. Overview of Openchain. 2015.

CHARLON, F. Openchain modules Storage engines. 2015.

CHEN, S.; ZHANG, J.; SHI, R.; YAN, J.; KE, Q. A Comparative Testing on Performance of
Blockchain and Relational Database: foundation for applying smart technology into current
business systems. In: _____. . [S.l.: s.n.], 2018. p. 21–34.

DAS, S.; SARAF, C.; KHAIRNAR, D. P. A Hyperledger Fabric Based Organizational
Decentralized Access Control Solution. In: IEEE 7TH INTERNATIONAL CONFERENCE
ON ENGINEERING TECHNOLOGIES AND APPLIED SCIENCES (ICETAS), 2020., 2020.
Anais. . . [S.l.: s.n.], 2020. p. 1–6.

DIB, O.; BROUSMICHE, K.-L.; DURAND, A.; THEA, E.; BEN HAMIDA, E. Consortium
blockchains: overview, applications and challenges. International Journal On Advances in
Telecommunications, France, 2018.

EMBRAPA. Uso de blockchain para registro de dados de Cadeia de Suprimentos Verde
da indústria sucroenergética. 2020.

ESMAEILIAN, B.; SARKIS, J.; LEWIS, K.; BEHDAD, S. Blockchain for the future of
sustainable supply chain management in Industry 4.0. Resources, Conservation and
Recycling, [S.l.], v. 163, p. 105064, 2020.

GAO, U. S. G. A. O. Blockchain Emerging Technology Offers Benefits for Some
Applications but Faces Challenges. Washington, DC0: Government Accountability Office,
2022. GAO-22-104625.

GERAKOUDI-VENTOURI, K. Review of studies of blockchain technology effects on the
shipping industry. Journal of Shipping and Trade, [S.l.], v. 7, n. 1, p. 2, Jan 2022.

GUERPINAR, T.; GUADIANA, G.; ASTERIOS IOANNIDIS, P.; STRAUB, N.; HENKE, M.
The Current State of Blockchain Applications in Supply Chain Management. In: THE 3RD
INTERNATIONAL CONFERENCE ON BLOCKCHAIN TECHNOLOGY, 2021., 2021, New
York, NY, USA. Anais. . . Association for Computing Machinery, 2021. p. 168–175. (ICBCT
’21).

HASAN, H.; ALHADHRAMI, E.; ALDHAHERI, A.; SALAH, K.; JAYARAMAN, R. Smart
contract-based approach for efficient shipment management. Computers Industrial
Engineering, [S.l.], v. 136, p. 149–159, 2019.

HRGA, A.; CAPUDER, T.; ZARKO, I. Demystifying Distributed Ledger Technologies:
limits, challenges and potentials in the energy sector. IEEE Access, [S.l.], v. PP, p. 1–1,
07 2020.

IMERI, A.; AGOULMINE, N.; KHADRAOUI, D. Blockchain and IoT integrated approach
for a trusted and secured process to manage the transportation of dangerous goods. Revista de
sistemas e computação, Salvador, Brasil, v. 10, n. 1, p. 26–41, 2020.

IPFS. How IPFS works. 2022.

ITI. ITI apoia BNDES em projeto de Blockchain. 2022.

ITU-T. Technical Specification FG DLT D3.1 Distributed ledger technology reference
architecture. Geneva, Switzerland: ITU-T, 2019. (FG DLT D3.1).

JABBAR, A.; DANI, S. Investigating the link between transaction and computational costs in
a blockchain environment. International Journal of Production Research, [S.l.], v. 58,
n. 11, p. 3423–3436, 2020.

KAPSOULIS, N.; PSYCHAS, A.; PALAIOKRASSAS, G.; MARINAKIS, A.; LITKE, A.;
VARVARIGOU, T.; BOUCHLIS, C.; RAOUZAIOU, A.; CALVO, G.;
ESCUDERO SUBIRANA, J. Consortium Blockchain Smart Contracts for Musical Rights
Governance in a Collective Management Organizations (CMOs) Use Case. Future Internet,
[S.l.], v. 12, n. 8, 2020.

KERESZTES, R.; KOVáCS, I.; HORVáTH, A.; ZIMáNYI, K. Exploratory Analysis of
Blockchain Platforms in Supply Chain Management. Economies, [S.l.], v. 10, n. 9, 2022.

KHAN, D.; JUNG, L. T.; HASHMANI, M. A. Systematic Literature Review of Challenges in
Blockchain Scalability. Applied Sciences, [S.l.], v. 11, n. 20, 2021.

KHAN, S.; SHAEL, M.; MAJDALAWIEH, M.; NIZAMUDDIN, N.; NICHO, M. Blockchain
for Governments: the case of the dubai government. Sustainability, [S.l.], v. 14, n. 11, 2022.

KLEMENS, S. How long does a bitcoin transaction take? bitcoin unconfirmed
transactions. [S.l.]: Exodus Crypto News amp; Insights, 2021.

KOHLI, V.; CHAKRAVARTY, S.; CHAMOLA, V.; SANGWAN, K. S.; ZEADALLY, S. An
analysis of energy consumption and carbon footprints of cryptocurrencies and possible
solutions. Digital Communications and Networks, [S.l.], 2022.

KOMOLAFE, O. Solana faster than Algorand and TRON – The fastest blockchains in
crypto space. [S.l.]: Crypto News Flash, 2022.

KOUSSEMA, R. A.; HAGA, H. Design and Implementation of Highly Secure Residents
Management System Using Blockchain. Journal of Computer and Communications, [S.l.],
v. 08No.09, p. 14, 2020.

KUO, T.-T.; ZAVALETA ROJAS, H.; OHNO, L. Comparison of blockchain platforms: a
systematic review and healthcare examples. Journal of the American Medical Informatics
Association, [S.l.], v. 26, n. 5, p. 462–478, 03 2019.

LASMOLES, O.; T. DIALLO, M. Impacts of Blockchains on International Maritime Trade.
Journal of Innovation Economics & Management, Louvain-la-Neuve, v. 37, n. 1,
p. 91–116, 2022.

LENGE, J.; MUSUMBU, K.; WANUKU, G.; SUNGU, P. Blockchain Technology as A
Guarantee of Transparency in The Supply Chain of Commercial Enterprises. In: ASIA
SERVICE SCIENCES AND SOFTWARE ENGINEERING CONFERENCE, 2022., 2022,
New York, NY, USA. Anais. . . Association for Computing Machinery, 2022. p. 1–7. (ASSE’
22).

LI, N.; GUO, Y.; CHEN, Y.; CHAI, J. A Partitioned DAG Distributed Ledger with Local
Consistency for Vehicular Reputation Management. Wireless Communications and Mobile
Computing, [S.l.], v. 2022, p. 6833535, Mar 2022.

MAESA, D. D. F.; MORI, P. Blockchain 3.0 applications survey. Journal of Parallel and
Distributed Computing, [S.l.], v. 138, p. 99 – 114, 2020.

MANEVICH, Y.; BARGER, A.; TOCK, Y. Endorsement in Hyperledger Fabric via service
discovery. IBM Journal of Research and Development, [S.l.], v. 63, n. 2/3, p. 2:1–2:9, 2019.

MASOOD, F.; FARIDI, A. An Overview of Distributed Ledger Technology and its
Applications. International Journal of Computer Sciences and Engineering, [S.l.], v. 6,
p. 422–427, 10 2018.

MONTEIRO, E. S.; MIGNONI, M. E.; RIGHI, R. d. R.; KUNST, R. Blockchain e inteligência
artificial associada no controle de packs agrotóxicos. RICA Revista Ibero-Americana de
Ciências Ambientais, [S.l.], v. 12, n. 12, 2021.


MONTEIRO, E. S.; ROSA RIGHI, R. da; BARBOSA, J. L. V.; ALBERTI, A. M. APTM: a
model for pervasive traceability of agrochemicals. Applied Sciences, [S.l.], v. 11, n. 17, 2021.


NIE, Y.; HE, X.-W.; CAI, W.-L.; LIU, Z.-H. Improve the security of Hyperledger Fabric by
dynamically selecting endorsing peers. In: INTERNATIONAL SYMPOSIUM ON
COMPUTER AND INFORMATION PROCESSING TECHNOLOGY (ISCIPT), 2021., 2021.
Anais. . . [S.l.: s.n.], 2021. p. 659–663.



OCDE. recommendation of the council on blockchain and other distributed ledger
technologies. 2 Rue André Pascal, 75016 Paris, France: OCDE, 2022. Council at Ministerial.

OGUNDARE, I. Cardano to scale to 1,000,000 tps with Hydra for micropayments on
ADA blockchain. [S.l.]: Crypto News Flash, 2022.

PARK, S.; KIM, H. DAGmap: multi-drone slam via a dag-based distributed ledger. Drones,
[S.l.], v. 6, n. 2, 2022.


PENG, Y.; DU, M.; LI, F.; CHENG, R.; SONG, D. FalconDB: blockchain-based collaborative
database. In: ACM SIGMOD INTERNATIONAL CONFERENCE ON MANAGEMENT OF
DATA, 2020., 2020, New York, NY, USA. Proceedings. . . Association for Computing
Machinery, 2020. p. 637–652. (SIGMOD ’20).


PEREZ, A. O.; DOMINGO-PALAOAG, T. Blockchain-based Model for Health Information
Exchange: a case for simulated patient referrals using an electronic medical record. IOP
Conference Series: Materials Science and Engineering, [S.l.], v. 1077, n. 1, p. 012059,
feb 2021.


PRASHAR, D.; JHA, N.; JHA, S.; LEE, Y.; JOSHI, G. P. Blockchain-Based Traceability and
Visibility for Agricultural Products: a decentralized way of ensuring food safety in india.
Sustainability, [S.l.], v. 12, n. 8, 2020.

PSARAS, Y.; SOARES, J. M.; DIAS, D. To the InterPlanetary File System–and Beyond!:
peer-to-peer file sharing would make the internet far more efficient. IEEE Spectrum, [S.l.],
v. 59, n. 11, p. 34–39, 2022.

PURBO, O.; SRIYANTO, S.; SUHENDRO, S.; RZ, A.; HERWANTO, R. Benchmark and
comparison between hyperledger and MySQL. TELKOMNIKA (Telecommunication
Computing Electronics and Control), [S.l.], v. 18, p. 705, 04 2020.
[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

RAUCHS, M.; GLIDDEN, A.; GORDON, B.; PIETERS, G.; RECANATINI, M.; ROSTAND,
F.; VAGNEUR, K.; ZHANG, B. Distributed Ledger Technology Systems: a conceptual
framework. SSRN Electronic Journal, [S.l.], 01 2018.

SA, R.; MOREIRA, L.; MACHADO, J. A modular approach to Hybrid Blockchain-based and
Relational Database Architectures. In: ESTENDIDOS DO XXXVII SIMPóSIO
BRASILEIRO DE BANCOS DE DADOS, 2022, Porto Alegre, RS, Brasil. Anais. . . SBC,
2022. p. 154–160.

SADEQ, M. J.; RAYHAN KABIR, S.; AKTER, M.; FORHAT, R.; HAQUE, R.;
AKHTARUZZAMAN, M. Integration of Blockchain and Remote Database Access
Protocol-Based Database. In: FIFTH INTERNATIONAL CONGRESS ON INFORMATION
AND COMMUNICATION TECHNOLOGY, 2021, Singapore. Proceedings. . . Springer
Singapore, 2021. p. 533–539.


SALAH, K.; REHMAN, M. H. U.; NIZAMUDDIN, N.; AL-FUQAHA, A. Blockchain for AI:
review and open research challenges. IEEE Access, [S.l.], v. 7, p. 10127–10149, 2019.

SILVA, J. O. D. da; SANTOS, D. R. dos. Study of Blockchain Application in the Logistics
Industry. Theoretical Economics Letters, [S.l.], v. 12, n. 2, p. 321–342, 4 2022.

SINGH, A.; GUTUB, A.; NAYYAR, A.; KHAN, M. K. Redefining food safety traceability
system through blockchain: findings, challenges and open issues. Multimedia Tools and
Applications, [S.l.], Oct 2022.


SINGH, N.; VARDHAN, M. Computing Optimal Block Size for Blockchain based
Applications with Contradictory Objectives. Procedia Computer Science, [S.l.], v. 171,
p. 1389–1398, 2020. Third International Conference on Computing and Network
Communications (CoCoNet’19).

SOLVEJ, K.; NATARAJAN, K.; HARISH, G.; LUSKIN, H. Distributed Ledger Technology
(DLT) and blockchain. Washington, D.C., 2017.

SULTAN, K.; RUHI, U.; LAKHANI, R. Conceptualizing Blockchains: characteristics &
applications. CoRR, [S.l.], v. abs/1806.03693, 2018.


SYLIM, P. G.; LIU, F.; MARCELO, A. B.; FONTELO, P. A. Blockchain Technology for
Detecting Falsified and Substandard Drugs in Distribution: pharmaceutical supply chain
intervention. JMIR Research Protocols, [S.l.], v. 7, 2018.

SYSRFID: GENERATION OF SYNTHETIC DATA IN SUPPLY CHAINS, 2011, Rome,
Italy. Anais. . . itAIS, 2011. p. 6.

TAN, E.; MAHULA, S.; CROMPVOETS, J. Blockchain governance in the public sector: a
conceptual framework for public management. Government Information Quarterly, [S.l.],
v. 39, p. 101625, 09 2021.

TCU. TCU e BNDES lançam Rede Blockchain Brasil e definem próximos passos. 2022.

VIRIYASITAVAT, W.; HOONSOPON, D. Blockchain characteristics and consensus in
modern business processes. Journal of Industrial Information Integration, [S.l.], v. 13,
p. 32–39, 2019.

WANG, Z.; WANG, T.; HU, H.; GONG, J.; REN, X.; XIAO, Q. Blockchain-based framework
for improving supply chain traceability and information sharing in precast construction.
Automation in Construction, [S.l.], v. 111, p. 103063, 2020.

WORLDBANK. Blockchain & Distributed Ledger Technology (DLT). 2018. 1 p.

XU, S.; ZHAO, X.; LIU, Z. The impact of blockchain technology on the cost of food
traceability supply chain. IOP Conference Series: Earth and Environmental Science, [S.l.],
v. 615, n. 1, p. 012003, dec 2020.

XU, X.; LU, Q.; LIU, Y.; ZHU, L.; YAO, H.; VASILAKOS, A. V. Designing
blockchain-based applications a case study for imported product traceability. Future
Generation Computer Systems, [S.l.], v. 92, p. 399–406, 2019.

YADAV, J.; SHEVKAR, R. Performance-Based Analysis of Blockchain Scalability Metric.
Tehnicki glasnik ˇ , [S.l.], v. 15, p. 133–142, 03 2021.

YUE, K.-B.; CHANDRASEKAR, K.; AND, H. G. Storing and Querying Bitcoin Blockchain
Using SQL Databases. Information Systems Education Journal (ISEDJ), Texas, USA, v. 8,
8 2019.

ZAKARI, N.; AL-RAZGAN, M.; ALSAADI, A.; ALSHAREEF, H.; SAIGH, H. A.;
ALASHAIKH, L.; ALHARBI, M.; ALOMAR, R.; ALOTAIBI, S. Blockchain technology in
the pharmaceutical industry: a systematic review. PeerJ Comput. Sci., [S.l.], p. 26, 3 2022.

ZHAO, F.; GUO, X.; CHAN, W. K. V. Individual Green Certificates on Blockchain: a
simulation approach. Sustainability, [S.l.], v. 12, n. 9, 2020.

ZHAO, W.; LV, J.; YAO, X.; ZHAO, J.; JIN, Z.; QIANG, Y.; CHE, Z.; WEI, C. Consortium
Blockchain-Based Microgrid Market Transaction Research. Energies, [S.l.], v. 12, n. 20, 2019.

---
# 6 Videos

Em desenvolvimento.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 7 Reportagens

Em desenvolvimento.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>


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
