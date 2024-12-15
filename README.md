# Sobre Blockchain e livros razão


---
#### Objetivos: 
```
1. Alguns conceitos sobre blockchain para serem discutidos em sala de aula. 
2. Exemplos que podem ser citados e comentados nas disciplinas que necessitam do apoio
 de uma banco de dados e projeto de sistemas. 
3. Este material é extremamente resumido e supõe que o leitor tem conhecimento básico
 de programação, sistemas distribuídos e banco de dados. 
4. Este não é um guia definitivo, mas um pequeno tutorial compilado para auxiliar
 alunos e devs. 
```

---
#### Observações:
```
1. Este material pode ser usado como suporte às disciplinas de: banco de dados, 
engenharia de software e projeto de sistemas.
2. Este material foi ou poderá ser usado em sala de aula/laboratório/EAD.
3. É um prerequisito conhecimentos básicos de, segurança da 
informação, programação e banco de dados.
4. Esta página poderá passar por atualizações sem aviso prévio.
5. Este material não tem foco em criptomoedas nem em inidicações de investimentos.
6. Este material visa abordar aspectos tecnológicos sobre DLT, não tem intenção de 
abordar criptmoedas, apesar as blockchains suportarem esse tipo de desenvolvimento, 
eventualmente poderão ser mencionadas aqui.
7. Este material esta em construção.
```


---
# Sumário


- [Sobre Blockchain e livros razão](#sobre-blockchain-e-livros-razão)
      - [Objetivos:](#objetivos)
      - [Observações:](#observações)
- [Sumário](#sumário)
- [1. Conceitos](#1-conceitos)
  - [1.1. O problema de double spending](#11-o-problema-de-double-spending)
  - [1.2. Criptografia de chave privada](#12-criptografia-de-chave-privada)
  - [1.3. Critografia de chave pública](#13-critografia-de-chave-pública)
  - [1.4. Certificado digital](#14-certificado-digital)
  - [1.4.1. ICP Brasil](#141-icp-brasil)
  - [1.5. Tecnologias de livro razão](#15-tecnologias-de-livro-razão)
    - [1.5.1. Gráfos acíclicos dirigidos](#151-gráfos-acíclicos-dirigidos)
      - [1.5.1.1. IOTA](#1511-iota)
      - [1.5.1.2. Hedera](#1512-hedera)
      - [1.5.1.3. Obyte](#1513-obyte)
      - [1.5.1.4. IPFS](#1514-ipfs)
      - [1.5.1.5 Projeto Swarm](#1515-projeto-swarm)
    - [1.5.2. Blockchain](#152-blockchain)
      - [1.5.2.1. Exemplos de Blockchain](#1521-exemplos-de-blockchain)
      - [1.5.2.2. Exemplo em Python](#1522-exemplo-em-python)
    - [1.5.3. Diferentes tipos de DLT](#153-diferentes-tipos-de-dlt)
    - [1.5.4. Alguns projetos de blockchain desde o surgimento até 2022](#154-alguns-projetos-de-blockchain-desde-o-surgimento-até-2022)
  - [1.6. Ethereum blockchain](#16-ethereum-blockchain)
    - [1.6.1. EVM](#161-evm)
      - [1.6.2 Ethereum nodes](#162-ethereum-nodes)
      - [1.6.2.1. Full nodes](#1621-full-nodes)
      - [1.6.2.2. Archive nodes](#1622-archive-nodes)
      - [1.6.2.3. Light nodes](#1623-light-nodes)
    - [1.6.2. Smart contracts](#162-smart-contracts)
    - [1.6.3. ETH](#163-eth)
    - [1.6.4. Gas fee](#164-gas-fee)
    - [1.6.5. IDE para programar com Ethereum](#165-ide-para-programar-com-ethereum)
      - [1.6.5.1. dApps](#1651-dapps)
      - [1.6.5.2. Arquitetura de uma aplicação Web3 (dapp)](#1652-arquitetura-de-uma-aplicação-web3-dapp)
  - [1.7. Wallets](#17-wallets)
    - [1.7.1. Carteiras, Contas, Chaves e Endereços no Ethereum](#171-carteiras-contas-chaves-e-endereços-no-ethereum)
    - [1.7.2. Metamask](#172-metamask)
    - [1.7.3. Carteira em hardware](#173-carteira-em-hardware)
  - [1.8. Mining (mineração)](#18-mining-mineração)
  - [1.9. Nonce](#19-nonce)
  - [1.10. Consenso](#110-consenso)
    - [1.10.1. PoW](#1101-pow)
    - [1.10.2. PoS](#1102-pos)
    - [1.10.3. PoA](#1103-poa)
    - [1.10.4. Comparações PoW, PoS e PoA](#1104-comparações-pow-pos-e-poa)
  - [1.11. DeFi](#111-defi)
    - [1.11.1. DAO](#1111-dao)
  - [1.12. Blockchain Oracle](#112-blockchain-oracle)
  - [1.13. NFT](#113-nft)
  - [1.14. Stable Coin](#114-stable-coin)
  - [1.15. Block explorers](#115-block-explorers)
  - [1.16. Dapps](#116-dapps)
  - [1.17. Soluções de 2º camada x Sidechains](#117-soluções-de-2º-camada-x-sidechains)
- [2. Blockchains privadas](#2-blockchains-privadas)
  - [2.1. Multhichain blockchain](#21-multhichain-blockchain)
    - [2.1.1. Resumo sobre Multichain blockchain:](#211-resumo-sobre-multichain-blockchain)
    - [2.1.2. Multichain streams](#212-multichain-streams)
    - [2.1.3. Multichain ativos](#213-multichain-ativos)
    - [2.1.4. Multichain smart filters](#214-multichain-smart-filters)
    - [2.1.5. Multichain outras referências](#215-multichain-outras-referências)
  - [2.2. Hyperledger](#22-hyperledger)
    - [2.2.1. Hyperledger Fabric](#221-hyperledger-fabric)
    - [2.2.2. Hyperledger Besu](#222-hyperledger-besu)
    - [2.2.3. Solução b-cadastro](#223-solução-b-cadastro)
  - [2.3. Corda](#23-corda)
  - [2.4. DLT (distributed ledger technology) em bancos de dados](#24-dlt-distributed-ledger-technology-em-bancos-de-dados)
    - [2.4.1. Oracle blockchain](#241-oracle-blockchain)
    - [2.4.2. SQL Server Ledger table](#242-sql-server-ledger-table)
    - [2.4.3. Outros bancos de dados + Blockchain](#243-outros-bancos-de-dados--blockchain)
- [3. Escalabilidade e performance em blockchains](#3-escalabilidade-e-performance-em-blockchains)
  - [3.1 Soluções como sharding, rollups e canais de estado.](#31-soluções-como-sharding-rollups-e-canais-de-estado)
  - [3.2. Comparação de soluções Layer 1 e Layer 2.](#32-comparação-de-soluções-layer-1-e-layer-2)
- [4. Interoperabilidade entre blockchains](#4-interoperabilidade-entre-blockchains)
  - [4.1. Protocolos como Polkadot e Cosmos.](#41-protocolos-como-polkadot-e-cosmos)
  - [4.2. Pontes (bridges) e desafios de interoperabilidade.](#42-pontes-bridges-e-desafios-de-interoperabilidade)
- [5. Impactos ambientais do blockchain](#5-impactos-ambientais-do-blockchain)
  - [5.1. Consumo energético do Proof of Work (PoW).](#51-consumo-energético-do-proof-of-work-pow)
  - [5.2. Alternativas sustentáveis como Proof of Stake (PoS).](#52-alternativas-sustentáveis-como-proof-of-stake-pos)
  - [5.3. Propostas de blockchain verdes e projetos relacionados.](#53-propostas-de-blockchain-verdes-e-projetos-relacionados)
- [6. Segurança em blockchain](#6-segurança-em-blockchain)
  - [6.1. Ataques conhecidos (51%, Sybil, Re-entrancy).](#61-ataques-conhecidos-51-sybil-re-entrancy)
  - [6.2. Análise de vulnerabilidades em contratos inteligentes.](#62-análise-de-vulnerabilidades-em-contratos-inteligentes)
  - [6.3. Ferramentas de auditoria de contratos (ex.: MythX, Slither).](#63-ferramentas-de-auditoria-de-contratos-ex-mythx-slither)
- [7. Aplicabilidade](#7-aplicabilidade)
  - [7.1. Aplicações em identidade digital e verificação de credenciais (SSI - Self-Sovereign Identity).](#71-aplicações-em-identidade-digital-e-verificação-de-credenciais-ssi---self-sovereign-identity)
  - [7.2. Blockchain no setor público (governo, saúde, votações).](#72-blockchain-no-setor-público-governo-saúde-votações)
  - [7.3. Aplicações em logística e rastreamento de cadeias de suprimento.](#73-aplicações-em-logística-e-rastreamento-de-cadeias-de-suprimento)
- [8. Tokenomics (Economia de Tokens)](#8-tokenomics-economia-de-tokens)
  - [8.1. Modelagem econômica de criptoativos.](#81-modelagem-econômica-de-criptoativos)
  - [8.2. Diferenças entre utility tokens, security tokens e governance tokens.](#82-diferenças-entre-utility-tokens-security-tokens-e-governance-tokens)
- [9. Blockchain e inteligência artificial](#9-blockchain-e-inteligência-artificial)
  - [9.1. Usos de blockchain na validação de dados para IA.](#91-usos-de-blockchain-na-validação-de-dados-para-ia)
  - [9.2. Propostas de descentralização de modelos de IA (ex.: Ocean Protocol).](#92-propostas-de-descentralização-de-modelos-de-ia-ex-ocean-protocol)
- [10. Blockchain em metaversos](#10-blockchain-em-metaversos)
  - [10.1. Tokens não fungíveis (NFTs) e a economia do metaverso.](#101-tokens-não-fungíveis-nfts-e-a-economia-do-metaverso)
  - [10.2. Interação entre Web3 e mundos virtuais.](#102-interação-entre-web3-e-mundos-virtuais)
- [11. Evolução técnica e novos paradigmas](#11-evolução-técnica-e-novos-paradigmas)
  - [11.1 Arquiteturas emergentes como blockchain modular.](#111-arquiteturas-emergentes-como-blockchain-modular)
  - [11.2. Tendências em zero-knowledge proofs (ZKPs) e privacidade.](#112-tendências-em-zero-knowledge-proofs-zkps-e-privacidade)
- [12. Regulamentação e desafios legais](#12-regulamentação-e-desafios-legais)
  - [12.1. Regulamentação de criptomoedas e blockchain no mundo.](#121-regulamentação-de-criptomoedas-e-blockchain-no-mundo)
  - [12.2. Governança de DAOs e implicações legais.](#122-governança-de-daos-e-implicações-legais)
  - [12.3. Proteção ao consumidor e segurança de dados em blockchains públicas.](#123-proteção-ao-consumidor-e-segurança-de-dados-em-blockchains-públicas)
- [4. Tendências](#4-tendências)
  - [4.1. Situação de alguns projetos](#41-situação-de-alguns-projetos)
- [5. Videos](#5-videos)
- [6. Treinamentos](#6-treinamentos)
- [7. Reportagens e artigos](#7-reportagens-e-artigos)
  - [7.1. Sobre blockchain](#71-sobre-blockchain)
  - [7.2. Artigos sobre criptomoedas, mineração e outros](#72-artigos-sobre-criptomoedas-mineração-e-outros)
- [8. Fontes e referências diversas](#8-fontes-e-referências-diversas)
- [Avisos \& licença](#avisos--licença)
  - [Aviso](#aviso)
  - [Licença](#licença)
- [Estatísticas desta página](#estatísticas-desta-página)





---
# 1. Conceitos


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

É um documento eletrônico usado para comprovar a validade de uma chave pública. O certificado inclui a chave pública e informações sobre ela, informações sobre a identidade de seu proprietário (chamado de sujeito) e a assinatura digital de uma entidade que verificou o conteúdo do certificado (chamado de emissor). Fonte: https://en.wikipedia.org/wiki/Public_key_certificate

![https://upload.wikimedia.org/wikipedia/commons/0/01/Client_and_Server_Certificate.png](https://upload.wikimedia.org/wikipedia/commons/0/01/Client_and_Server_Certificate.png)

Figura 1: Certificado digital do site Wikipedia. Fonte:
https://pt.wikipedia.org/wiki/Certificado_digital#/media/Ficheiro:Client_and_Server_Certificate.png


## 1.4.1. ICP Brasil

A Infraestrutura de Chaves Públicas Brasileira (ICP-Brasil) é uma cadeia hierárquica de confiança que viabiliza a emissão de certificados digitais para identificação virtual do cidadão.

Observa-se que o modelo adotado pelo Brasil foi o de certificação com raiz única, sendo que o ITI, além de desempenhar o papel de Autoridade Certificadora Raiz (AC-Raiz), também tem o papel de credenciar e descredenciar os demais participantes da cadeia, supervisionar e fazer auditoria dos processos.

Infra Estrutura de Chaves Pública Brasil https://www.gov.br/iti/pt-br/assuntos/icp-brasil

Estrutura da ICP Brasil:

![https://www.gov.br/iti/pt-br/assuntos/icp-brasil/EcossistemaICPBrasil_2408221.png](https://www.gov.br/iti/pt-br/assuntos/icp-brasil/EcossistemaICPBrasil_2408221.png)

Figura 2: Ecossistema da ICP-Brasil. Fonte: https://www.gov.br/iti/pt-br/assuntos/icp-brasil/ecossistema-icp-brasil).

[Navegação na Estrutura](https://estrutura.iti.gov.br/).

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

* B) Blockchain. Blockchain e DAG são sub tipos de DLTs.

![Exemplos de DLT](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig1.png "Exemplos de DLT")

Figura 3: As principais subdivisões e alguns exemplos.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

### 1.5.1. Gráfos acíclicos dirigidos

Uma forma de DLT é um grafo acíclico dirigido (DAG), o qual utiliza uma estrutura parecida com vértices e arestas; as arestas são posicionados em uma direção e o grafo é acíclico pois os vértices não se referenciam nem formam um loop para si mesmos.  Nos sistemas DAG não é necessário um minerador, pois cada usuário pode controlar sua própria sequência de blocos de forma assíncrona.  Sempre que uma transação é realizada, os participantes devem verificar duas outras transações de outros nós (PARK; KIM, 2022). 

Cada transação no DAG é um vértice, cada vértice tem uma ou mais arestas em direção a outros vértices, desta forma um vértice referencia outro vértice. Uma transação é registrada após a outra formando uma linearidade, porém o DAG não usa mineração ou custos de transação; pois um nó realiza validação simultânea de transações. Cada transação é registrada em vértices e não existe a necessidade de serem gravadas em bloco, formando uma cadeia de transações verificadas (LI et al., 2022). Com o DAG os participantes são mineradores e validadores de transações.
 
![Exemplos de DAG](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig2.png "Exemplos de DAG")

Figura 4: Nós em um sistema distribuído.

São alguns exemplos de projetos que utilizam DAG: IOTA(é um DAG voltada para armazenar dados de IoT), NANO(é uma criptomoeda e uma plataforma para transação de valores ponto-a-ponto), Obyte(é uma DAG e criptomoeda), Hedera(é uma rede pública baseada em DAG e uma criptomoeda) e IPFS(é um sistema de arquivos distribuído, utilizado em uma rede ponto-a-ponto.). DAG é usada pelo IPFS onde cada identifcador tem um hash do conteúdo para um conteúdo, é usado para representar arquivos e diretórios, o IPFS quebra um arquivo em pedaços chamados de blocos, (IPFS, 2022).

Os blocos podem estar em vários lugares. Um arquivo é composto de vários blocos, cada bloco tem um identificador. Para localizar este arquivo composto por vários blocos o IPFS usa o que é chamado de tabela hash para localizar arquivos. Com esta tabela, um grupo de nós pode conter partes diferentes de um arquivo.  Nesta tabela, existem duas colunas uma com um hash inicia e final e a outra coluna com o conteúdo do arquivo. Dependendo qual o valor da chave hash o arquivo pode ser armazenado na tabela (no topo, por exemplo), para recuperar o arquivo é necessário percorrer a tabela, (PSARAS; SOARES; DIAS, 2022).

Um exemplo de implementação de DAG é o sistema de arquivos interplanetário, [IPFS](https://ipfs.tech/).

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

#### 1.5.1.1. IOTA

IOTA foi criada especificamente para a Internet das Coisas (IoT) e se diferencia das blockchains tradicionais por usar uma estrutura chamada Tangle em vez de blocos encadeados. O Tangle é um gráfico acíclico direcionado (DAG) que permite transações paralelas, eliminando a necessidade de mineradores e taxas de transação, tornando as operações rápidas e leves, ideais para dispositivos IoT com recursos limitados. Cada nova transação valida outras duas, promovendo a escalabilidade e evitando gargalos comuns em blockchains tradicionais. Essa arquitetura torna a IOTA uma solução promissora para ambientes de IoT, onde se espera uma grande quantidade de transações entre dispositivos conectados.

![https://upload.wikimedia.org/wikipedia/commons/thumb/8/8f/Tangleimage.jpg/600px-Tangleimage.jpg](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8f/Tangleimage.jpg/600px-Tangleimage.jpg)

Figura 5: Rede Tangle do IOTA.

https://www.iota.org/ e https://wiki.iota.org/

#### 1.5.1.2. Hedera

A Hedera Hashgraph é uma rede distribuída que usa uma estrutura de gráfico acíclico direcionado (DAG) chamada Hashgraph, que se diferencia das blockchains convencionais por não organizar os dados em blocos sequenciais. Com o Hashgraph, as transações são processadas em paralelo e registradas por meio de um mecanismo de consenso assíncrono baseado em “gossip” (troca rápida de informações entre nós) e votação virtual. Esse modelo torna a Hedera altamente eficiente, com velocidade e capacidade de escalabilidade superiores à maioria das blockchains tradicionais, além de alcançar um consenso rápido e final sem a necessidade de mineração. Essas características fazem da Hedera uma plataforma robusta para aplicações que exigem alta taxa de transações, como pagamentos, tokenização de ativos, e autenticação de identidade.

https://hedera.com/ e https://hedera.com/hh_whitepaper_v2.1-20200815.pdf

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

#### 1.5.1.3. Obyte

Obyte é uma plataforma descentralizada que utiliza uma estrutura de gráfico acíclico direcionado (DAG), permitindo transações sem a necessidade de blocos e mineradores, como ocorre em blockchains tradicionais. Nela, cada transação é um ponto no DAG que verifica duas transações anteriores, promovendo um modelo que elimina taxas de transação e facilita micropagamentos. Obyte também integra funcionalidades avançadas como contratos inteligentes, chamados de smart contracts, e oferece suporte para transações de dados confidenciais, mantendo a privacidade dos usuários. Sua arquitetura única a torna adequada para uma ampla gama de casos de uso, incluindo pagamentos, armazenamento seguro de dados e autenticação descentralizada, além de proporcionar uma rede eficiente e escalável sem depender de mineradores.

https://obyte.org/technology e https://wiki.obyte.org/Overview

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

#### 1.5.1.4. IPFS

O IPFS (InterPlanetary File System) é uma rede de armazenamento e compartilhamento de arquivos descentralizada que utiliza uma estrutura de gráfico acíclico direcionado (DAG) para organizar e distribuir dados. Em vez de depender de um servidor central, o IPFS permite que arquivos sejam divididos em pequenos blocos e armazenados de forma distribuída, onde cada bloco é identificado por uma “hash” exclusiva. Esse sistema facilita a recuperação de arquivos por meio de uma rede peer-to-peer, permitindo que o conteúdo seja acessado por sua identificação de hash, garantindo que ele permaneça imutável. Com o IPFS, é possível compartilhar e armazenar dados de forma segura, eficiente e resistente à censura, o que o torna útil para aplicações como o armazenamento de dados para blockchains, backup de arquivos e hospedagem de sites descentralizados.

![https://camo.githubusercontent.com/cd3b6a61e698bd1169dfca6ae4ea353908f4a0045fb5fd4739151085d46ad84d/68747470733a2f2f676174657761792e697066732e696f2f697066732f516d6156624259734542623334484d503159576545727253375833544236593974316951347342526e5476537761](https://camo.githubusercontent.com/cd3b6a61e698bd1169dfca6ae4ea353908f4a0045fb5fd4739151085d46ad84d/68747470733a2f2f676174657761792e697066732e696f2f697066732f516d6156624259734542623334484d503159576545727253375833544236593974316951347342526e5476537761)

Figura 6: IPFS desktop. Fonte: https://github.com/ipfs/ipfs-desktop.

![https://camo.githubusercontent.com/d8fed8dcec620e69690c5378d13507be3605206890cb0373202203371460ed0b/68747470733a2f2f676174657761792e697066732e696f2f697066732f516d594875586974584d663578546a6951586d586471737a764d54414476724d357a413745716f446a3364335248](https://camo.githubusercontent.com/d8fed8dcec620e69690c5378d13507be3605206890cb0373202203371460ed0b/68747470733a2f2f676174657761792e697066732e696f2f697066732f516d594875586974584d663578546a6951586d586471737a764d54414476724d357a413745716f446a3364335248)

Figura 7: IPFS desktop. Fonte: https://github.com/ipfs/ipfs-desktop.

https://ipfs.tech/

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

#### 1.5.1.5 Projeto Swarm

O projeto Swarm, da Ethereum, não é exatamente uma blockchain nem uma DAG. Ele é uma rede descentralizada de armazenamento e distribuição de dados que funciona como um sistema de arquivos distribuído. Swarm é projetado para ser uma plataforma de infraestrutura Web3, permitindo que dados e conteúdos sejam armazenados e distribuídos sem depender de servidores centralizados. Embora utilize uma arquitetura que permite que os nós compartilhem e repliquem dados de forma distribuída, Swarm se integra à blockchain da Ethereum para contratos inteligentes e tokens, mas não usa diretamente uma estrutura de blockchain ou DAG para organizar suas transações de dados.

https://www.ethswarm.org/

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

### 1.5.2. Blockchain


Blockchain é uma cadeia de blocos, na qual cada nó tem blocos de dados, um carimbo de data/hora e um hash de código que se refere ao nó anterior, reforçando a cadeia de dados de forma imutável. A tecnologia blockchain foi inicialmente projetada para oferecer suporte a moedas criptográficas, mas hoje, pode-se usá-la para outros fins, incluindo rastreamento da cadeia logística e contratos entre pessoas que não se conhecem.  Assim, a blockchain funciona salvando as transações de interesse para as quais foi projetada, onde cada uma pode implementar uma série de regras e também servir para transmitir dados. 

Em particular, as regras para a execução de transações ou operações são realizadas por meio de contratos inteligentes. Do ponto de vista do programador, elas podem ser vistas como um script (ou, simplificando, um programa que deve ser executado automaticamente quando uma transação é realizada). Assim, blockchain pode conter dados e código executável (MAESA; MORI, 2020), onde o último é visto como a lógica de programação para atualizar dados e disparar ações externas ao blockchain.


* "Bloco" são os dados armazenados de forma sequencial.<br>

* "Cadeia" é o termo usado porque um dos campos do bloco é um apontador para o seu bloco pai. Desta forma os bloco são serializados e unidos sequencialmente. 

![Cadeia de blocos](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig3.png "Cadeia de blocos")

Figura 8: Exemplos de encadeamento de blocos.

Artigo que iniciou com a ideia: [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf).


[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

#### 1.5.2.1. Exemplos de Blockchain


[Solana](https://solana.com/pt)

[Stellar](https://stellar.org/)

[Cardano](https://cardano.org/)

[Hathor](https://hathor.network/)



#### 1.5.2.2. Exemplo em Python 

```
import hashlib
import time

class Block:
    def __init__(self, index, previous_hash, data, timestamp=None):
        self.index = index
        self.previous_hash = previous_hash
        self.data = data
        self.timestamp = timestamp or time.time()
        self.hash = self.calculate_hash()

    def calculate_hash(self):
        block_content = str(self.index) + str(self.previous_hash) + str(self.data) + str(self.timestamp)
        return hashlib.sha256(block_content.encode()).hexdigest()

# Function to create the genesis block (first block)
def create_genesis_block():
    return Block(index=0, previous_hash="0", data="Genesis Block")

# Function to create a new block in the chain
def create_new_block(previous_block, data):
    new_index = previous_block.index + 1
    new_block = Block(index=new_index, previous_hash=previous_block.hash, data=data)
    return new_block

# Initialize the blockchain with the genesis block
blockchain = [create_genesis_block()]

# Adding new blocks to the blockchain
blockchain.append(create_new_block(blockchain[-1], "Block 1 Data"))
blockchain.append(create_new_block(blockchain[-1], "Block 2 Data"))
blockchain.append(create_new_block(blockchain[-1], "Block 3 Data"))

# Display the blockchain
for block in blockchain:
    print(f"Block {block.index} [Hash: {block.hash}]")
    print(f"Previous Hash: {block.previous_hash}")
    print(f"Data: {block.data}")
    print(f"Timestamp: {block.timestamp}")
    print("\n")
```

O exemplo acima rodando na IDE Spyder:

![https://raw.githubusercontent.com/monteiro74/blockchain/refs/heads/main/figuras/blockchain_python.png](https://raw.githubusercontent.com/monteiro74/blockchain/refs/heads/main/figuras/blockchain_python.png)

Figura 9: Exemplo simplificado de conceitos em python.

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

Projetos de blockchain a partir do ano de criação até 2022: Hyperledger Fabric, Multichain blockchain, SAP blockchain, Hyperledger Besu, Oracle blockchain, [Hathor](https://hathor.network/), VMware VMBC, Azure Confidential Ledger, XO-DEX, Nano, Dragonchain, [Openchain](https://github.com/openchain), GoQuorum. Estes projetos de blockchain apresentam características de custo zero de transação (ou taxa zero), as quais podem ser explorada por blockchain privadas.

![Alguns projetos de blockchain até 2022](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig4.png)

Figura 10: Linha do tempo de alguns projetos de blockchain.

[Voltar ao início](#sobre-blockchain-e-livros-razão)

## 1.6. Ethereum blockchain

Ethereum é uma rede de computadores em todo o mundo que segue um conjunto de regras do chamado protocolo Ethereum.


Definições pelo ChatGPT:
```
O Ethereum é uma plataforma de blockchain descentralizada, projetada para suportar
 contratos inteligentes e aplicativos descentralizados (dApps). 
Ele foi criado para expandir as funcionalidades das blockchains convencionais, 
permitindo que desenvolvedores criem e executem programas complexos diretamente
 na rede.
Em resumo, o Ethereum é uma plataforma blockchain versátil que permite que
 desenvolvedores criem, executem e interajam com uma ampla variedade de 
 aplicativos descentralizados e contratos inteligentes.
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

![https://ethereum.org/content/developers/docs/evm/evm.png](https://ethereum.org/content/developers/docs/evm/evm.png)

Figura 11: Máquina virtual Etehreum, fonte da figura: https://ethereum.org/en/developers/docs/evm/

https://ethereum.org/en/developers/docs/evm/

[Voltar ao início](#sobre-blockchain-e-livros-razão)

#### 1.6.2 Ethereum nodes

São 3 tipos:

#### 1.6.2.1. Full nodes

```
Os nós completos fazem uma validação bloco por bloco do blockchain, incluindo o download
e a verificação do corpo do bloco e dos dados de estado de cada bloco. Existem diferentes
classes de full node – alguns começam no bloco gênese e verificam cada bloco em toda a
história do blockchain. Outros iniciam sua verificação em um bloco mais recente que eles
confiam ser válido (por exemplo, 'snap sync' de Geth). Independentemente de onde a 
verificação começa, os nós completos mantêm apenas uma cópia local dos dados relativamente
recentes (normalmente os 128 blocos mais recentes), permitindo que os dados mais antigos 
sejam excluídos para economizar espaço em disco. Dados mais antigos podem ser regenerados
quando necessário.

Armazena dados completos do blockchain (embora isso seja periodicamente removido para que 
um nó completo não armazene todos os dados de estado desde a gênese)

Participa da validação de blocos, verifica todos os blocos e estados.

Todos os estados podem ser recuperados do armazenamento local ou regenerados a partir 
de 'instantâneos' por um nó completo.

Atende a rede e fornece dados mediante solicitação.
```

Fonte: https://ethereum.org/en/developers/docs/nodes-and-clients/

#### 1.6.2.2. Archive nodes

```
Os nós de arquivo são nós completos que verificam cada bloco desde o genesis e nunca 
excluem nenhum dos dados baixados.

Armazena tudo o que é mantido no nó completo e cria um arquivo de estados históricos
```

Fonte: https://ethereum.org/en/developers/docs/nodes-and-clients/

#### 1.6.2.3. Light nodes

```
Em vez de baixar cada bloco, os nós leves baixam apenas os cabeçalhos dos blocos. 
Esses cabeçalhos contêm informações resumidas sobre o conteúdo dos blocos. Qualquer outra 
informação que o nó leve exija é solicitada de um nó completo. O nó leve pode então verificar 
independentemente os dados que recebe em relação às raízes de estado nos cabeçalhos do bloco. 
Os nós leves permitem que os usuários participem da rede Ethereum sem o hardware poderoso 
ou a alta largura de banda necessária para executar nós completos.
```

Fonte: https://ethereum.org/en/developers/docs/nodes-and-clients/

Maiores detalhes sobre a arquitetura dos nós: https://ethereum.org/en/developers/docs/nodes-and-clients/node-architecture/

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


### 1.6.3. ETH

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

Figura 12: IDE Remix.


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

#### 1.6.5.1. dApps

Um aplicativo descentralizado (dapp) é um aplicativo construído em uma rede descentralizada que combina um contrato inteligente e uma interface de usuário frontend. No Ethereum, os contratos inteligentes são acessíveis e transparentes – como APIs abertas – então seu dapp pode até incluir um contrato inteligente escrito por outra pessoa.

#### 1.6.5.2. Arquitetura de uma aplicação Web3 (dapp)

![https://raw.githubusercontent.com/monteiro74/trab_tecnicas_prog/refs/heads/main/arquitetura.jpg](https://raw.githubusercontent.com/monteiro74/trab_tecnicas_prog/refs/heads/main/arquitetura.jpg)

Figura 13: Arquetura de uma dapp.

![https://raw.githubusercontent.com/monteiro74/trab_tecnicas_prog/refs/heads/main/tela6.jpg](https://raw.githubusercontent.com/monteiro74/trab_tecnicas_prog/refs/heads/main/tela6.jpg)

Figura 14: Exemplo da app rodando e o log console.

Um exemplo simples aqui: https://github.com/monteiro74/trab_tecnicas_prog

Mais info aqui: https://www.preethikasireddy.com/post/the-architecture-of-a-web-3-0-application

## 1.7. Wallets

Uma carteira é uma forma de se controlar uma conta. Ela contém a identidade do usuário e seus ativos, além de informar saldos e enviar transações. A carteira é uma forma de interação com a rede Ethereum.

[Voltar ao início](#sobre-blockchain-e-livros-razão)


### 1.7.1. Carteiras, Contas, Chaves e Endereços no Ethereum

* Uma conta Ethereum é um par de chaves. Uma chave (pública) é usada para criar o endereço que pode ser compartilhado livremente e a outra chave (privada) é mantida em segredo porque é usada para assinar transações. Juntas, essas chaves permitem manter ativos e fazer transações.
* Uma conta Ethereum possui um endereço, assim como um email possui uma caixa de entrada. Isso é usado para identificar ativos digitais.
* Uma carteira é uma ferramenta (de software ou hardware) que permite interagir com uma conta, usando uma par de chaves. Ele permite que se visualize o saldo de uma conta, envie transações etc.
* A maioria dos produtos de carteira permite gerar uma conta Ethereum.

Fonte: https://ethereum.org/en/wallets

[Voltar ao início](#sobre-blockchain-e-livros-razão)

### 1.7.2. Metamask

Carteira em software:

* Metamask

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/36/MetaMask_Fox.svg/512px-MetaMask_Fox.svg.png" alt="drawing" width="150"/>

Figura 15: Logo do projeto Metamask, fonte da imagem: https://en.wikipedia.org/wiki/File:MetaMask_Fox.svg

Artigos sobre problemas com o Metamask:

https://www.tokenmetrics.com/blog/is-metamask-safe

https://slowmist.medium.com/demonic-vulnerability-analysis-of-metamasks-wallet-browser-extension-8de529a70caf

https://slowmist.medium.com/metamask-clickjacking-vulnerability-analysis-f3e7c22ff4d9

https://bitcoinist.com/metamask-vulnerability-could-endanger-your-funds/

### 1.7.3. Carteira em hardware

Exemplos de carteiras em hardware:

* Safepal S1
* Tangem
* Keystone
* Nano X Crypto Hardware Wallet
* Trezor One + Billfodl
* KleverSafe Hardware Wallet
* OneKey Classic


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


## 1.9. Nonce 


Definição de [Investopédia](https://www.investopedia.com/terms/n/nonce.asp#:~:text=%E2%80%9CNonce%E2%80%9D%20combines%20the%20phrase%20%E2%80%9C,value%20when%20mining%20a%20block.):
```
“Nonce” combina a frase “número usado uma vez”. Ele é usado pelo blockchain Bitcoin 
para ajudar a gerar um valor hash ao minerar um bloco.
```

Definição de [Geeksforgeeks](https://www.geeksforgeeks.org/what-is-a-nonce-in-blockchain/)
```
é um número aleatório ou semi-aleatório gerado pelos mineiros quando criam um novo bloco na blockchain.

A palavra “nonce” deriva do latim e significa “número usado uma vez”. Isto quer dizer que este número 
deve ser usado apenas uma vez neste caso específico.
Os nonces são de importância central para o modelo do mecanismo de consenso de prova de trabalho, que 
é uma forma bem conhecida de operar em muitos blockchains, como Bitcoin e Ethereum.
Os Nonces fornecem a capacidade de provar o envolvimento no processo de mineração de um problema 
matemático complexo e a exigência de adicionar um novo bloco ao blockchain
```

Definição de [Cointelegraph](https://cointelegraph.com/explained/what-is-a-nonce-in-blockchain-explained):
```
Um nonce, abreviação de “número usado uma vez”, é um número especial atribuído a um bloco em uma 
blockchain durante o processo de mineração. É uma parte essencial do mecanismo de consenso de prova 
de trabalho (PoW). 

O nonce, servindo como um quebra-cabeça criptográfico, é uma variável que os mineradores manipulam 
para produzir um valor hash que satisfaça requisitos específicos. Os mineradores continuam alterando 
o nonce até encontrarem um hash que possua as propriedades necessárias, que geralmente são um 
determinado número de zeros à esquerda. Este processo iterativo, conhecido como mineração, 
garante a segurança do blockchain.

O nonce correto é essencial para validar a legitimidade de um bloco e desempenha um papel 
fundamental na criação de um bloco. Ele evita que atores mal-intencionados adulterem os dados, 
tornando proibitivamente alto o esforço computacional necessário para tais alterações.
```


## 1.10. Consenso

É um sistema que valida uma transação e a marca como autêntica. Este mecanismo lista todas as transações válidas de uma moeda em uma blockchain para construir confiança na moeda entre os comerciantes. Diversas moedas, como Bitcoin, Ethereum etc, utilizam este sistema (também chamado de "protocolo de consenso").

### 1.10.1. PoW

* PoW (Proof of Work): ‘Prova’ refere-se à solução de um problema altamente complexo, e ‘trabalho’ refere-se ao processo de resolução do mesmo. Os mineradores de moedas criptográficas competem para resolver o problema e ganhar o direito de processar a transação. O solucionador mais rápido recebe uma taxa de mineração dos comerciantes dessas moedas.

### 1.10.2. PoS

* PoS (Proof of Stake): Este mecanismo escolhe aleatoriamente um proprietário máximo de moedas para validar uma transação. Também permite ao proprietário criar um bloco para a mesma moeda. Este mecanismo requer comparativamente menos energia, tempo de transação e uma taxa mais baixa. Moedas como Etherium 2.0

### 1.10.3. PoA

* PoA (Proof of Authority): Prova de autoridade (PoA) é um tipo de mecanismo de consenso usado em alguns blockchains para decidir qual participante adicionará o próximo bloco de transações. Ao contrário da Prova de Trabalho do Bitcoin, onde os mineiros competem para resolver quebra-cabeças complexos, ou da Prova de Participação, onde a chance de adicionar um bloco depende de quanta criptomoeda uma pessoa possui, o PoA tem tudo a ver com identidade e reputação.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

### 1.10.4. Comparações PoW, PoS e PoA


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



Mais info... https://cleartax.in/s/consensus-in-blockchain

[Voltar ao início](#sobre-blockchain-e-livros-razão)



## 1.11. DeFi

Significa **Decentralized Finance** (DeFi). É um conceito que visa trazer os serviços financeiros tradicionais para o universo das criptomoedas usando blockchains e "ledgers" distribuídas. Um atrativo para o uso de DeFi seria a não existência de taxas bancárias entre as transações.  O usuários destes serviços poderiam manter dinheiro digital em uma carteira (wallets) de forma segura (pelo uso de criptografia) e realizar transferências de fundos (cripto ativos) entre outros usuários deste ecossistema via Internet se unidades centrais de controle ou bancos tradicionais para intervir neste processo.

Redes ponto a ponto financeiras seriam os locais onde os serviços DeFi existiriam, os usuários destes serviços se conectariam via wallets, vendedores e compradores realizaram as transações dentro desta rede distribuída. Esta rede financeira estaria presente em qualquer lugar (desde que haja internet). É importante observar que DeFi não tem como objetivo fornecer serviço de anonimização, pelo contrário, espera-se que instituições financeiras tradicionais(CeFi - Centralizes Finance), comercios reais e pessoas físicas e jurídicas possam fazer uso dessa tecnologia da mesma forma como se usa os meios financeiros tradicionais centralizados. Inclusive as transações financeiras que se estabelecerão nas redes DeFi esperá-se que sejam todas rastreáveis.

A proposta DeFi pode ter surgido como uma ideia nas quais pessoas poderiam fazer transações entre si sem pagar taxas, mas é necessário uma infraestrutura para a computação e operação de redes de comptuadores custosa, instituições financeiras podem participar cobrando taxas bancárias muito baixas, mais atrativas que no sistema tradicional. 

> :warning: Projetos de DeFi em muitos paises não são regulamentadas pelos respectivos governos. É importante que se entenda quais são as garantias de transferências de cada plataforma, muitas DeFi ainda não são projetos consolidados. Sobre o uso de cripto nos sistemas de pagamentos [Why Crypto Will Never Fix Payments (feat. Patrick McKenzie) - Episode 143](https://www.youtube.com/watch?v=tEJ-7dAquwg).

[Voltar ao início](#sobre-blockchain-e-livros-razão)

### 1.11.1. DAO 

Uma DAO (Organização Autônoma Descentralizada) é uma **organização governada por regras codificadas em contratos inteligentes**, permitindo que membros tomem decisões coletivas sem a necessidade de uma estrutura hierárquica tradicional. Em uma DAO, as regras e operações são transparentes e imutáveis, pois ficam registradas em uma blockchain. Geralmente, os membros de uma DAO possuem tokens de governança que lhes conferem poder de voto sobre decisões, como alocação de fundos, desenvolvimento de projetos, ou atualização das regras. O objetivo de uma DAO é promover uma gestão transparente e democrática, onde os membros participam de forma direta e colaborativa. 

> :warning: Projetos de DeFi inclusive de DAO, como comentado anteriormente ainda não tem respaldo legal nos seus países de origem, alguns projetos é difícil achar o pais sede do projeto, DAO e DeFi ainda tem uma estrada longa para se provarem práticos como meios de pagamento. Sobre o uso de cripto nos sistemas de pagamentos [Why Crypto Will Never Fix Payments (feat. Patrick McKenzie) - Episode 143](https://www.youtube.com/watch?v=tEJ-7dAquwg).

[Voltar ao início](#sobre-blockchain-e-livros-razão)

## 1.12. Blockchain Oracle

São **sistemas que conectam blockchains a sistemas externos**, permitindo que os smart contracts possam de acordo com parâmetros externos. Desta forma sistema pré-existentes (ou legados) possam se conectar (via WEB3) com as blockchains. Os oracles podem receber dados do mundo externo (qualquer tipo de dados, por exemplo: dados de sensor de temperatura) e envia estes dados para a blockchain. Permite que ecossistemas decentralizados possam ter acessoa fontes de dados externas. 


:warning: **Atenção**: Não confundir os dois termos abaixo!


| Termo   | Descrição   | Exemplo                         |
|-----|---|-------------|
| **Blockchain Oracle** | Tecnologia ou serviço que conecta blockchains com dados externos, permitindo que contratos inteligentes usem informações do mundo real.              | [Chainlink](https://chain.link/education/blockchain-oracles)                       |
| **Oracle Blockchain** | Plataforma de blockchain oferecida pela empresa Oracle, focada em soluções empresariais para criar e gerenciar redes blockchain privadas e seguras. | [Oracle Blockchain Platform](https://www.oracle.com/br/blockchain/)      |




[Voltar ao início](#sobre-blockchain-e-livros-razão)


## 1.13. NFT

NFT significa Non-Fungible Token, **são ativos que podem ser tokenizados por uma blockchain** (ou seja, podem receber uma *representação virtual como um objeto dentro de uma blockchain*). Estes ativos podem representar qualquer coisa do mundo real como: obras de arte, carros, terrenos, etc. Recebem um código único de identificação e metadados que os descrevem (incluindo quantidade e valor). Os NFTs podem ser comprados e vendidos/trocados usando cripto moedas em determinadas plataformas. 

Exemplo de NFT são os Bored Ape Yacht Club Galeria dos [BAYC](https://boredapeyachtclub.com/#/gallery) NFT (notícias sobre: https://www.coindesk.com/web3/2023/07/03/bored-ape-yacht-club-nft-collection-floor-price-sinks-to-20-month-low/ e  https://www.theguardian.com/artanddesign/2022/jan/04/bored-ape-nft-art-eminem). 

[Voltar ao início](#sobre-blockchain-e-livros-razão)


## 1.14. Stable Coin

São um tipo de criptomoeda que possui um valor atrelado a um ativo de referência que pode ser uma commodities, bens materiais, ouro ou outra moeda física. A ideia é ter uma **relação 1:1**, no qual a criptomeda stable coin tem seu valor indexado por uma outra moeda. Desta forma seu valor tende a não ter tanda volatilidade. Esta opção é mais atrativa pois permite a conversibilidade da moeda em outros bens.

Um exemplo de stablecoin é o Tether USDT. Ela é projetada para manter seu valor atrelado ao dólar americano, sendo respaldada por reservas em dólares ou ativos equivalentes, o que ajuda a manter a estabilidade de seu preço. Stablecoins como o Tether são amplamente utilizadas para facilitar transações em exchanges de criptomoedas, oferecendo uma opção menos volátil em comparação com outras criptomoedas como Bitcoin ou Ethereum.

> :warning: **Investigação** sobre Tether... Exposing Tether - Bitcoin's Biggest Secret. Outros problemas com as Stable Coins comentados neste vídeo: [Which Stablecoins Are Safe to Use? (USDC, USDT, DAI, etc.)](https://www.youtube.com/watch?v=6OqvW-XbRPI).

[Voltar ao início](#sobre-blockchain-e-livros-razão)


## 1.15. Block explorers

Os exploradores (explorers) de blocos são o seu portal para os dados do Ethereum. Você pode usá-los para ver dados em tempo real sobre blocos, transações, validadores, contas e outras atividades na rede.

Alguns exemplos:

* [Etherscan](https://etherscan.io/)

* [Blockchair](https://blockchair.com/ethereum)

* [Ethernow](https://www.ethernow.xyz/)

* [Ethplorer](https://ethplorer.io/)


[Voltar ao início](#sobre-blockchain-e-livros-razão)


## 1.16. Dapps 

Um aplicativo descentralizado (dapp) é um aplicativo construído em uma rede descentralizada que combina um contrato inteligente e uma interface de usuário frontend. No Ethereum, os contratos inteligentes são acessíveis e transparentes, assim um Dapp pode até incluir um contrato inteligente escrito por outra pessoa.

Video sobre Dapps [What is a dApp? Decentralized Application on the Blockchain](https://www.youtube.com/watch?v=F50OrwV6Uk8&t).

[Voltar ao início](#sobre-blockchain-e-livros-razão)

## 1.17. Soluções de 2º camada x Sidechains

| Critério                | Soluções de Segunda Camada                                       | Sidechains                                               |
|-------------------------|------------------------------------------------------------------|----------------------------------------------------------|
| **Estrutura**           | Construídas como uma camada extra sobre a blockchain principal, processando transações fora da primeira camada. | Blockchains independentes que operam em paralelo à  blockchain principal, conectadas a ela por um “peg” bidirecional.      |
| **Exemplos**            | Lightning Network roda sobre Bitcoin, Plasma roda sobre Ethereum                 | Liquid Network roda sobre Bitcoin, Polygon roda sobre Ethereum |
| **Mecanismo de Segurança** | Usa a segurança da blockchain principal,com validação periódica das transações.                    | Possui seu próprio mecanismo de consenso e segurança, podendo ter regras e parâmetros específicos.   |
| **Tipo de Transação**   | Focada em transações rápidas e de baixo valor, omo micropagamentos ou trocas frequentes de ativos.                  | Permite transações variadas, incluindo operações complexas, com suporte a contratos inteligentes e tokens.         |
| **Interdependência**    | Altamente dependente da blockchain principal para segurança e integridade das transações.  | Menos dependente da blockchain principal, funcionando de forma independente, embora conectada a ela. |
| **Flexibilidade de Uso**| Menos flexível, pois herda as restrições da blockchain principal e é específica para determinados tipos de transações. | Mais flexível, com regras, taxas e funcionalidades  customizáveis para atender diferentes necessidades.      |
| **Ideal Para**          | Reduzir congestionamento na blockchain principal, aumentando a escalabilidade e velocidade.              | Aplicações complexas que exigem transações diversificadas ou customizações, como operações de maior valor.|


> :warning: Um "peg" bidirecional é um mecanismo que permite a transferência de ativos (como criptomoedas) entre a blockchain principal e uma sidechain de forma segura. Esse sistema vincula o ativo na blockchain principal, "bloqueando-o" para que ele não seja usado enquanto uma versão equivalente é "desbloqueada" na sidechain, e vice-versa. O "peg" inicial refere-se ao primeiro processo de transferência, onde ativos da blockchain principal são transferidos pela primeira vez para a sidechain, criando o vínculo entre ambas.


Dica: [O que são sidechains e como funcionam?](https://www.bity.com.br/blog/o-que-sao-sidechains-e-como-funcionam/#:~:text=A%20intera%C3%A7%C3%A3o%20entre%20a%20blockchain,ativos%20entre%20ambas%20as%20redes.).

> :warning: Críticas: [Lightning Network has Failed](https://www.youtube.com/watch?v=5Cq0C0SpbkY).

[Bitcoin Lightning Network Explained: How it Actually Works](https://www.youtube.com/watch?v=yKdK-7AtAMQ)


[Voltar ao início](#sobre-blockchain-e-livros-razão)

# 2. Blockchains privadas

## 2.1. Multhichain blockchain

### 2.1.1. Resumo sobre [Multichain blockchain](https://www.multichain.com/):

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

### 2.1.2. Multichain streams

* O streams é uma abstração para o armazenamento de dados, indexação e recuperação de dados.
* É possível ter vários streams.
* Cada stream pode estar aberto para escrita por todos ou apenas para alguns.
* Dados são publicados no formato json.
* Um dado pode ter a mesma chave.
* Para que um dados seja publicado na stream é necessário permissão de escrita na stream alvo.
* Uma consulta só pode ser feita em uma stream se foi feita uma assinatura (subscription) na referida stream.

### 2.1.3. Multichain ativos

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

### 2.1.4. Multichain smart filters

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

### 2.1.5. Multichain outras referências

* Site principal da [Multichain blockchain](https://www.multichain.com/).
* [Documentação da MultiChain](https://www.multichain.com/developers/).
* [Tutorial para iniciantes](https://www.multichain.com/getting-started/).

[Voltar ao início](#sobre-blockchain-e-livros-razão)

## 2.2. Hyperledger

Hyperledger foi absorvida por https://www.lfdecentralizedtrust.org/about

Lista de todos os projetos Hyperledger: https://www.lfdecentralizedtrust.org/project-matrix

### 2.2.1. Hyperledger Fabric

Hyperledger é um projeto open source de blockchain mantido pela Linux Foundation (seu principal patrocinador é a IBM). É uma blockchain permissionada. 

Estrutura de uma rede Hyperledger Fabric:

<img src="https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig7.png" alt="drawing" width="500"/>

Figura 19: Exemplo de rede Hyperledger Fabric.

Fonte da figura: https://hyperledger-fabric.readthedocs.io/en/latest/network/network.html

* As organizações R0, R1 e R2 montaram uma rede e chegaram em um consenso sobre a infraestrutura e políticas de administração da rede. 
* As 3 organizações (R0, R1 e R2) são as proprietárias da rede, que utiliza como configuração CC1.
* No canal C1 estão os peers P1 e P2 das organizações R1 e R2.
* R0 é proprietária do peer O (que possui um serviço de ordenamento).
* Todos os nós contém uma cópia da blockchain (L1) (ou ledger).
* R1 e R2 também interagem com o canal usando as aplicações A1 e A2.
* Todas as 3 organizações possuem autoridades certificadoras CA0, CA1 e CA2.
* S5 é um chaincode (é um smart contract) instalado nos peers P1 e P2.

**Pergunta para o ChatGPT**: "*Hyperledger é uma cripto moeda ou um ambiente para execução de app distribuídas ?*"

**Resposta**:

*O Hyperledger não é uma criptomoeda. Em vez disso, é um ambiente para o desenvolvimento de aplicações distribuídas e ferramentas para blockchains empresariais. É um projeto de código aberto mantido pela Linux Foundation, com o objetivo de fornecer uma estrutura modular para construir redes blockchain e soluções distribuídas, especialmente para empresas e organizações.*

*Aqui estão alguns pontos importantes sobre o Hyperledger:*

*Plataforma para Aplicações Distribuídas e Blockchains Empresariais: O Hyperledger oferece uma variedade de frameworks e ferramentas para criar blockchains privadas e permissionadas (com controle de acesso), voltadas para ambientes corporativos e consórcios.*

*Foco em Aplicações Empresariais: Ao contrário de blockchains públicas como Ethereum e Bitcoin, que são abertas e descentralizadas, as redes Hyperledger são projetadas para ambientes corporativos onde é necessário um controle de acesso restrito e uma maior privacidade das transações.*

*Diversos Frameworks: O Hyperledger inclui diferentes projetos, como o Hyperledger Fabric, que é uma das plataformas mais usadas para criar blockchains empresariais com suporte a contratos inteligentes; o Hyperledger Sawtooth, que é voltado para modularidade; e o Hyperledger Besu, que é compatível com a rede Ethereum e permite interoperabilidade com ela.*

*Sem Criptomoeda Própria: Diferentemente de plataformas como Ethereum, o Hyperledger não possui uma moeda nativa. Seus frameworks são projetados para permitir transações e contratos inteligentes sem a necessidade de uma criptomoeda.*

*Portanto, o Hyperledger é essencialmente um ambiente para criação de aplicações distribuídas e blockchains empresariais, e não uma criptomoeda. Ele atende a empresas que precisam de soluções blockchain com controle de acesso e privacidade, mas sem a necessidade de tokens públicos.*

Outras referências:

* [Tutorial de Fabric para a rede de testes](https://hyperledger-fabric.readthedocs.io/en/latest/tutorials.html).

* [Tutorial para escrita de chaincode (smartcode)](https://hyperledger-fabric.readthedocs.io/en/release-1.3/tutorials.html)


[Voltar ao início](#sobre-blockchain-e-livros-razão)

### 2.2.2. Hyperledger Besu

Besu é um DLT para que possam ser criadas blockchains privadas.

Documentação https://besu.hyperledger.org/private-networks

[Voltar ao início](#sobre-blockchain-e-livros-razão)

### 2.2.3. Solução b-cadastro

O b-cadastro é um produto do Serpro para órgãos públics realizarem consultas de CPF e CNPJ, utiliza a rede [Hyperledger fabric](https://www.lfdecentralizedtrust.org/projects/fabric).

[Voltar ao início](#sobre-blockchain-e-livros-razão)

## 2.3. Corda 

Corda é uma plataforma de blockchain desenvolvida especialmente para ambientes empresariais, focada em fornecer soluções descentralizadas para empresas que precisam de privacidade e segurança em transações. Diferente de blockchains públicas, onde todos os dados são visíveis para todos os participantes, a Corda usa um modelo de transação onde apenas as partes diretamente envolvidas têm acesso aos dados, o que é crucial para setores como finanças, saúde e supply chain. A Corda adota uma abordagem de consenso flexível, permitindo que as empresas escolham como e quando validar transações, o que aumenta a eficiência sem comprometer a segurança. Suas funcionalidades incluem contratos inteligentes personalizados e suporte a tokens, oferecendo uma estrutura robusta e escalável para a automação e otimização de processos interorganizacionais.

https://corda.net/

[Voltar ao início](#sobre-blockchain-e-livros-razão)

## 2.4. DLT (distributed ledger technology) em bancos de dados

### 2.4.1. Oracle blockchain

[Oracle Database native Blockchain and Immutable Tables](https://blogs.oracle.com/coretec/post/blockchain-or-immutable-tables)

Citado da documentação oficial:

Tabelas imutáveis:
```
Tabelas imutáveis ​​são tabelas somente leitura que evitam modificações não autorizadas de dados 
por pessoas internas e modificações acidentais de dados resultantes de erros humanos.
```

Tabelas blockchain:
```
As tabelas Blockchain são tabelas somente de inserção que organizam as linhas em várias cadeias. 
Cada linha de uma cadeia, exceto a primeira linha, é encadeada à linha anterior da cadeia. 
cadeia usando um hash criptográfico.
```

Comparativo:


| **Aspecto**                              | **Immutable Tables**                                                              | **Blockchain Tables**                                                                                  |
|------------------------------------------|----------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| **Prevenção de alterações não autorizadas** | Prevenção de alterações por insiders mal-intencionados com acesso a credenciais.   | Além da prevenção de alterações por insiders mal-intencionados, detecta alterações não autorizadas feitas fora do Oracle Database. |
| **Impersonação de usuários**             | Não mencionado.                                                                  | Detecta a inserção de dados em nome de um usuário sem sua autorização.                                |
| **Garantia de integridade dos dados**    | Não mencionado.                                                                  | Previne adulteração e garante que os dados foram realmente inseridos na tabela.                      |
| **Encadeamento de linhas**               | Linhas não são encadeadas.                                                       | Cada linha (exceto a primeira) é encadeada à anterior usando um hash criptográfico.                   |
| **Quebra do encadeamento**               | Não aplicável.                                                                   | Modificações em uma linha quebram o encadeamento, indicando adulteração.                              |
| **Processamento adicional no commit**    | Não requer processamento adicional no momento do commit.                         | Requer processamento adicional no momento do commit para encadear as linhas.                          |


Fonte: https://docs.oracle.com/en/database/oracle/oracle-database/19/admin/managing-tables.html#GUID-F537DD20-58ED-450A-837C-372E3BDA12F9

[Voltar ao início](#sobre-blockchain-e-livros-razão)

### 2.4.2. SQL Server Ledger table


[Ledger overview](https://learn.microsoft.com/en-us/sql/relational-databases/security/ledger/ledger-overview?view=sql-server-ver16)

![https://learn.microsoft.com/en-us/sql/relational-databases/security/ledger/media/ledger/ledger-table-architecture.png?view=sql-server-ver16](https://learn.microsoft.com/en-us/sql/relational-databases/security/ledger/media/ledger/ledger-table-architecture.png?view=sql-server-ver16)

### 2.4.3. Outros bancos de dados + Blockchain

1. [Blockchain baseadas em bancos de dados](https://blog.logrocket.com/top-7-blockchain-based-databases/)
 
2. [OurSQL — tool to replicate MySQL databases using blockchain](https://medium.com/@gelembjuk/oursql-tool-to-replicate-mysql-databases-using-blockchain-5ae509636435)

3. [Bitcoin Blockchain SQL Schema for MySQL](https://crypto.bi/schema/)

4. [RBaaS: A Robust Blockchain as a Service Paradigm in Cloud-Edge Collaborative Environment](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9740132)

5. [Integration of Blockchain and Remote Database Access Protocol-based Database](https://www.researchgate.net/publication/344194318_Integration_of_Blockchain_and_Remote_Database_Access_Protocol-based_Database)

6. [Blockchain Based Charity System Using PHP/MySQL](https://www.irjet.net/archives/V9/i5/IRJET-V9I555.pdf)

7. [Building a Blockchain Inside PostgreSQL](https://postgresconf.org/conferences/2021_Postgres_Conference_Webinars/program/proposals/building-a-blockchain-inside-postgresql)

8. [PostgreSQL and Blockchain: Storing Blockchain Data](https://reintech.io/blog/postgresql-and-blockchain-storing-data)

9. [Blockchain PG: Enabling Authenticated Query and Trace Query in Database](https://link.springer.com/chapter/10.1007/978-3-030-60290-1_41)

10. [Blockchain Database: A Comprehensive Guide](https://www.mongodb.com/resources/basics/databases/blockchain-database)

11. [Blockchain-based Database to Ensure Data Integrity in Cloud Computing Environments](https://ceur-ws.org/Vol-1816/paper-15.pdf)

[Voltar ao início](#sobre-blockchain-e-livros-razão)

# 3. Escalabilidade e performance em blockchains

## 3.1 Soluções como sharding, rollups e canais de estado.

> :warning: Aviso: Material em construção.


## 3.2. Comparação de soluções Layer 1 e Layer 2.

> :warning: Aviso: Material em construção.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

# 4. Interoperabilidade entre blockchains

## 4.1. Protocolos como Polkadot e Cosmos.

> :warning: Aviso: Material em construção.

## 4.2. Pontes (bridges) e desafios de interoperabilidade.

> :warning: Aviso: Material em construção.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

# 5. Impactos ambientais do blockchain

## 5.1. Consumo energético do Proof of Work (PoW).

> :warning: Aviso: Material em construção.

## 5.2. Alternativas sustentáveis como Proof of Stake (PoS).

> :warning: Aviso: Material em construção.

## 5.3. Propostas de blockchain verdes e projetos relacionados.

> :warning: Aviso: Material em construção.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

# 6. Segurança em blockchain

## 6.1. Ataques conhecidos (51%, Sybil, Re-entrancy).

> :warning: Aviso: Material em construção.

## 6.2. Análise de vulnerabilidades em contratos inteligentes.

> :warning: Aviso: Material em construção.

## 6.3. Ferramentas de auditoria de contratos (ex.: MythX, Slither).

> :warning: Aviso: Material em construção.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

--- 
# 7. Aplicabilidade 


1. Desenvolvimento de criptomoedas

2. Comércio de ativos (NFT, tokens não fungíveis)

3. Rastreabilidade de transações, por exemplo em uma cadeia logística cada etapa (a cada saldo entre os players) pode ser feito um registro em uma blockchain, possibilitando a rastreabilidade dos ativos que estão em movimento:

![Cadeia logística](https://raw.githubusercontent.com/monteiro74/blockchain/main/figuras/fig6.png)

Figura 20: Exemplo de cadeia logística.

4. Registro imutável de informações

5. Ecônomia baseada em tokens

6. Regulação em complience via blockchain.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

## 7.1. Aplicações em identidade digital e verificação de credenciais (SSI - Self-Sovereign Identity).

> :warning: Aviso: Material em construção.

## 7.2. Blockchain no setor público (governo, saúde, votações).

> :warning: Aviso: Material em construção.

## 7.3. Aplicações em logística e rastreamento de cadeias de suprimento.

> :warning: Aviso: Material em construção.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

# 8. Tokenomics (Economia de Tokens)

## 8.1. Modelagem econômica de criptoativos.

> :warning: Aviso: Material em construção.

## 8.2. Diferenças entre utility tokens, security tokens e governance tokens.

> :warning: Aviso: Material em construção.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

# 9. Blockchain e inteligência artificial

## 9.1. Usos de blockchain na validação de dados para IA.

> :warning: Aviso: Material em construção.

## 9.2. Propostas de descentralização de modelos de IA (ex.: Ocean Protocol).

> :warning: Aviso: Material em construção.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

# 10. Blockchain em metaversos

## 10.1. Tokens não fungíveis (NFTs) e a economia do metaverso.

> :warning: Aviso: Material em construção.

## 10.2. Interação entre Web3 e mundos virtuais.

> :warning: Aviso: Material em construção.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

# 11. Evolução técnica e novos paradigmas

## 11.1 Arquiteturas emergentes como blockchain modular.

> :warning: Aviso: Material em construção.

## 11.2. Tendências em zero-knowledge proofs (ZKPs) e privacidade.

> :warning: Aviso: Material em construção.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>


# 12. Regulamentação e desafios legais


## 12.1. Regulamentação de criptomoedas e blockchain no mundo.

> :warning: Aviso: Material em construção.

## 12.2. Governança de DAOs e implicações legais.

> :warning: Aviso: Material em construção.

## 12.3. Proteção ao consumidor e segurança de dados em blockchains públicas.

> :warning: Aviso: Material em construção.

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 4. Tendências

Google trends usado para mostrar tendências:

https://trends.google.com.br/trends/explore?date=today%205-y&q=blockchain,%2Fg%2F11g0g4sbp3,Ethereum&hl=pt-BR

outro gráfico de tendência:

https://trends.google.com.br/trends/explore?date=2020-04-10%202024-11-04&q=%2Fg%2F11g0g4sbp3,%2Fm%2F054_cb,NFT,blockchain,%2Fm%2F0vpj4_b&hl=pt-BR



> :warning: Aviso: Se a página do Google Trends apresentar um erro é só recarregá-la novamente!


![https://raw.githubusercontent.com/monteiro74/blockchain/refs/heads/main/figuras/tendencias.png](https://raw.githubusercontent.com/monteiro74/blockchain/refs/heads/main/figuras/tendencias.png)

Figura 21: Google trends, mundo, 2020-2024, todas as categorias, pesquisa na web. Captura em Novembro/2024.


## 4.1. Situação de alguns projetos

> [!WARNING]  
> https://www.web3isgoinggreat.com/


[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 5. Videos

[Lançamento da Rede Blockchain Brasil (RBB)](https://www.youtube.com/watch?v=Mhm8buV3lVs)

[Entre desilusão e esperança, bitcoin completa um ano em El Salvador | AFP](https://www.youtube.com/watch?v=rcmLhDYK3lg)

[What is a dApp? Decentralized Application on the Blockchain](https://www.youtube.com/watch?v=F50OrwV6Uk8&t).

[How I hacked a hardware crypto wallet and recovered $2 million](https://www.youtube.com/watch?v=dT9y-KQbqi4)

[Ethereum Has A MAJOR Problem...](https://www.youtube.com/watch?v=UF6W4fo5D4o)

[Binance Now Controls 80% of Bitcoin's Volume](https://www.youtube.com/watch?v=Mu9u1KFigEU)

[Bolsa Desiste de Blockchain e Investe em COBOL](https://www.youtube.com/watch?v=j89GXwU0E6A)

[The Embarrassing DOWNFALL of the Bored Ape Yacht Club](https://www.youtube.com/watch?v=IYS_uuUjQbY)

[The "Web3" Metaverse: One Year Later](https://www.youtube.com/watch?v=cWcJejr3Fl4)

[Line Goes Up – The Problem With NFTs](https://www.youtube.com/watch?v=YQ_xWvX1n9g)

[A look inside the sadest NFT metaverse yet, "VEVEVerse" Crypto, Blockchain fails](https://www.youtube.com/watch?v=MIuh6DNv9OY)

[how the FTX collapse ACTUALLY happened...](https://www.youtube.com/watch?v=hl-6GpwoTfA)

[The FTX Collapse Explained in 99 Seconds](https://www.youtube.com/watch?v=Ow-MN7qJnIY)

[FTX Collapsed…Here’s Why](https://www.youtube.com/watch?v=l3HfrRjWilQ)

[Justiça determina que ‘Faraó dos Bitcoins’ pague R$ 19 bilhões para ressarcir vítimas](https://www.youtube.com/watch?v=C-4S4gFLyx0)

[Mulher do "Faraó dos Bitcoins" é presa nos Estados Unidos | SBT Brasil (26/01/24)](https://www.youtube.com/watch?v=Rhk4sWnymxQ)

[Mulher do "Faraó dos Bitcoins" é presa nos Estados Unidos | SBT Brasil (26/01/24)](https://www.youtube.com/watch?v=Rhk4sWnymxQ)

[Golpe Financeiro: 'faraó dos bitcoins' pode ter enganado quase 70 mil pessoas](https://www.youtube.com/watch?v=umgqsLvbKGk)

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>


---
# 6. Treinamentos

[Get started with blockchain development](https://learn.microsoft.com/en-us/training/paths/ethereum-blockchain-development/)

[Learn Blockchain Solidity Smart Contract for Beginners](https://www.udemy.com/course/blockchain-solidity-smart-contract-tutorial/)

[Learn Ethereum and Solidity](https://www.udemy.com/course/learn-ethereum-and-solidity/)

[Blockchain Theory 101](https://www.udemy.com/course/blockchain-theory-101/)

[Como aprender Blockchain e Smart Contract em 1 dia!](https://www.udemy.com/course/como-aprender-blockchain-e-smart-contracts-em-1-dia/)

[Do zero ao blockchain](https://www.udemy.com/course/do-zero-ao-blockchain/)

[Blockchain Free learning and resources](https://skillsbuild.org/students/course-catalog/blockchain)

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

---
# 7. Reportagens e artigos

Referências em blogs e revistas comerciais com reportagens diversas para o público em geral.
Algunas referências desta seção não revistas científicas.

## 7.1. Sobre blockchain

[Blockchain by Example in SQL Server](https://benjaminsky.medium.com/blockchain-by-example-in-sql-server-8376b410128)

[Storing and Querying Bitcoin Blockchain Using SQL Databases](https://sceweb.sce.uhcl.edu/big/papers/ISEDJv17n4-Yue.pdf)

[Programming Smart Contracts in C#](https://learn.microsoft.com/en-us/archive/msdn-magazine/2019/november/blockchain-programming-smart-contracts-in-csharp)

[Azure SQL Database ledger PART 1 by Jason M. Anderson](https://www.sqlservergeeks.com/azure-sql-database-ledger-part-1-by-jason-m-anderson/)

[Azure SQL Database Ledger Getting Started and Examples](https://www.mssqltips.com/sqlservertip/6890/azure-sql-database-ledger-getting-started-and-examples/)

[Ledger overview](https://learn.microsoft.com/en-us/sql/relational-databases/security/ledger/ledger-overview?view=sql-server-ver16)

[SQL Server meet Blockchain!](https://medium.com/provendb/sql-server-meet-blockchain-555b0a137c71)

[Introduction to ProvenDB for SQLServer](https://provendb.readme.io/docs/introduction-1)

[O que é Blockchain?](https://www.oracle.com/br/blockchain/what-is-blockchain/)

[Blockchain Platform Service](https://www.oracle.com/blockchain/cloud-platform/)

[Blockchain Oracle](https://oracle-base.com/articles/21c/blockchain-tables-21c)

[Advancing Enterprise Blockchain with the Latest Generation of Oracle Blockchain Platform](https://blogs.oracle.com/blockchain/post/advancing-enterprise-blockchain-with-the-latest-generation-of-oracle-blockchain-platform)

[Announcing Azure SQL Database ledger](https://techcommunity.microsoft.com/t5/azure-sql-blog/announcing-azure-sql-database-ledger/ba-p/2200401)

[Distributed storage](https://fisco-bcos-documentation.readthedocs.io/en/latest/docs/manual/distributed_storage.html)

[Lightning Network has Failed](https://www.youtube.com/watch?v=5Cq0C0SpbkY).

[Bitcoin Lightning Network Explained: How it Actually Works](https://www.youtube.com/watch?v=yKdK-7AtAMQ)

[Crypto: The World’s Greatest Scam.](https://www.youtube.com/watch?v=ORdWE_ffirg)

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>

## 7.2. Artigos sobre criptomoedas, mineração e outros

[Chegada do DREX e o fim do dinheiro em espécie](https://livecoins.com.br/chegada-do-drex-e-fim-do-dinheiro-em-especie-pode-virar-audiencia-publica-na-camara/).

[BC divulga as diretrizes do projeto-piloto do Real Digital](https://www.bcb.gov.br/detalhenoticia/667/noticia)

[“Criptomoedas não valem nada”, afirma presidente do Banco Central Europeu](https://portaldobitcoin.uol.com.br/criptomoedas-nao-valem-nada-afirma-presidente-do-banco-central-europeu/)

[“Faraó do Bitcoin” tem 72 horas para depositar R$ 19 bi em conta judicial](https://bmcnews.com.br/2022/09/20/farao-do-bitcoin-tem-72-horas-para-depositar-r-19-bi-em-conta-judicial-0022/)

[“Cripto é um investimento em nada”, diz Charlie Munger, parceiro de Warren Buffett](https://istoedinheiro.com.br/cripto-e-um-investimento-em-nada-diz-charlie-munger-parceiro-de-warren-buffett/)

[Comprar criptomoedas ‘é investir em nada’, afirma braço direito de Warren Buffett](https://www.moneytimes.com.br/comprar-criptomoedas-e-investir-em-nada-afirma-braco-direito-de-warren-buffett/)

[Binance vai travar saques de 21 criptomoedas na próxima quinta, veja quais](https://livecoins.com.br/binance-vai-travar-saques-de-21-criptomoedas-na-proxima-quinta-veja-quais/)

[Bitcoin Maximalist Michael Saylor Makes the Case Against Ethereum](https://www.coindesk.com/business/2022/07/27/bitcoin-maximalist-michael-saylor-makes-the-case-against-ethereum/)


[Crypto Exchange Zipmex Seeks Bankruptcy Protection In Singapore As Crypto Crisis Spreads](https://www.forbes.com/sites/zinnialee/2022/07/29/crypto-exchange-zipmex-seeks-bankruptcy-protection-in-singapore-as-crypto-crisis-spreads/?sh=752881b44233)

[Ethereum’s Merge already causing more problems than it’s solving](https://coingeek.com/ethereum-merge-already-causing-more-problems-than-its-solving/)

[Solana, USDC Drained From Wallets in Attack](https://decrypt.co/106590/multiple-wallets-including-sol-and-usdc-drained-in-unfolding-attack)

[Empresa de criptomoedas promovida por artistas do SBT desaparece com dinheiro dos clientes](https://livecoins.com.br/bm4-financas-sbt-desaparece-dinheiro-dos-clientes/)

[“NFT que comprei por R$ 3,2 milhões vale R$ 50 hoje”, lamenta o youtuber Logan Paul](https://portaldobitcoin.uol.com.br/nft-que-comprei-por-r-32-milhoes-vale-r-50-hoje-lamenta-o-youtuber-logan-paul/)

[Logan Paul afirma que seu NFT de R$ 3,2 milhões agora vale R$ 50](https://www.tecmundo.com.br/mercado/252618-logan-paul-afirma-nft-r-3-2-milhoes-vale-r-50.htm)

[Países da UE precisam estar prontos para bloquear a mineração de criptomoedas, diz Comissão Europeia](https://www.infomoney.com.br/mercados/paises-da-ue-precisam-estar-prontos-para-bloquear-a-mineracao-de-criptomoedas-diz-comissao-europeia/)

[FTX sofre hack bilionário e pede que usuários não acessem site](https://livecoins.com.br/ftx-sofre-hack-bilionario/)

[Third Crypto Boss Dies in Helicopter Crash](https://www.thegatewaypundit.com/2022/11/third-crypto-boss-dies-helicopter-crash/)

[Vencedor do Nobel, Paul Krugman decreta o 'fim do Bitcoin'](https://g1.globo.com/economia/noticia/2022/12/05/vencedor-do-nobel-paul-krugman-decreta-o-fim-do-bitcoin.ghtml)

[China to roll out first national ‘digital asset’ marketplace – media](https://www.rt.com/business/569124-china-digital-asset-marketplace/)

[1 ano depois de virar moeda oficial em El Salvador, bitcoin está 'esquecido' no país](https://exame.com/future-of-money/1-ano-depois-de-virar-moeda-oficial-em-el-salvador-bitcoin-esta-esquecido-no-pais/)

[Más de 1.300 cajeros automáticos de bitcoin fueron desconectados en enero y febrero](https://www.criptonoticias.com/comunidad/adopcion/mas-1300-cajeros-automaticos-bitcoin-fueron-desconectados-enero-febrero/)

[Retiran más de 1,300 cajeros automáticos de Bitcoin](https://www.hoycripto.com/criptomonedas/2023/03/02/Retiran-mas-de-1300-cajeros-automaticos-de-Bitcoin/)

[El Salvador perde R$ 370 milhões com bitcoin, mas presidente defende criptomoeda](https://exame.com/future-of-money/el-salvador-perde-r-370-milhoes-com-bitcoin-mas-presidente-defende-criptomoeda/)

[74% da população de El Salvador não usou bitcoin desde que moeda foi oficializada](https://www.cnnbrasil.com.br/economia/financas/74-da-populacao-de-el-salvador-nao-usou-bitcoin-desde-que-moeda-foi-oficializada/)

[Binance faces scrutiny in Brazil, exec summoned to testify before Congress](https://cointelegraph.com/news/binance-scrutiny-in-brazil-as-government-demands-executive-testimony)

[BlackRock está promovendo o maior Ponzi da história”, diz professor da Unicamp](https://livecoins.com.br/blackrock-esta-promovendo-o-maior-ponzi-da-historia/#amp_tf=De%20%251%24s&aoh=16887242600313&csi=0&referrer=https%3A%2F%2Fwww.google.com&ampshare=https%3A%2F%2Flivecoins.com.br%2Fblackrock-esta-promovendo-o-maior-ponzi-da-historia%2F)

[Remember when NFTs sold for millions of dollars? 95% of the digital collectibles may now be worthless.](https://markets.businessinsider.com/news/currencies/nft-market-crypto-digital-assets-investors-messari-mainnet-currency-tokens-2023-9)

[Bored Ape Yacht Club Prices Crash to Two-Year Low, Down 88% From Peak](https://decrypt.co/147201/bored-ape-yacht-club-prices-crash-two-year-low-down-88-peak)

[Bitcoin mining manufacturer can’t pay staff – report](https://www.rt.com/business/584561-crypto-mining-bitmain-stop-pay/)

[Bitmain suspends employee pay amid financial turmoil](https://cryptoslate.com/bitmain-suspends-employee-pay-amid-financial-turmoil/)

[Binance and CEO Plead Guilty to Federal Charges in $4B Resolution](https://www.justice.gov/opa/pr/binance-and-ceo-plead-guilty-federal-charges-4b-resolution)

[Inside Binance’s Guilty Plea and the Biggest Fine in Crypto History](https://www.wsj.com/finance/inside-binances-guilty-plea-and-the-biggest-fine-in-crypto-history-e959fca0)

[Governo de Honduras fecha cidade bitcoin privada de Próspera](https://livecoins.com.br/governo-de-honduras-fecha-cidade-bitcoin-privada-de-prospera/)

[Chegada do Drex e fim do dinheiro em espécie pode virar audiência pública na Câmara](https://livecoins.com.br/chegada-do-drex-e-fim-do-dinheiro-em-especie-pode-virar-audiencia-publica-na-camara/)

[Dead Coins: Over 50% of Cryptocurrencies Have Failed](https://www.coingecko.com/research/publications/how-many-cryptocurrencies-failed)

[Squid Game But It's a Crypto Scam](https://www.youtube.com/watch?v=YoFQcU3_-p4)

[Lista de blockchains](https://en.wikipedia.org/wiki/List_of_blockchains)

[Voltar ao início](#sobre-blockchain-e-livros-razão)<br>


---
# 8. Fontes e referências diversas

Diversas fontes de pesquisa sobre blockchain, principalmente revistas científicas:

[Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf)

[The Collapse Of Silvergate Bank](https://www.researchgate.net/publication/371701475_The_Collapse_of_Silvergate_Bank)

AGI, M. A.; JHA, A. K. **Blockchain technology in the supply chain: an integrated theoretical perspective of organizational adoption**. International Journal of Production Economics, [S.l.], v. 247, p. 108458, 2022.
https://www.sciencedirect.com/science/article/pii/S0925527322000512


ANTONOPOULOS, P.; KAUSHIK, R.; KODAVALLA, H.; ROSALES ACEVES, S.; WONG, R.; ANDERSON, J.; SZYMASZEK, J. **SQL Ledger: cryptographically verifiable data in azure sql database**. In: INTERNATIONAL CONFERENCE ON MANAGEMENT OF DATA, 2021., 2021, New York, NY, USA Proceedings. Association for Computing Machinery, 2021. p. 2437–2449. (SIGMOD ’21).
https://dl.acm.org/doi/abs/10.1145/3448016.3457558

BASSILIOS, J. **OECD adopts recommendations on blockchain and other DLT**. Accessed: 2022-10-20.
https://www.oecd.org/daf/blockchain/oecd-recommendation-on-blockchain-and-other-dlt.htm


BERAWI, M. A.; REYES, G.; SARI, M.; SAROJI, G. **Developing Public-Private Partnership Model with Blockchain-Based Crowdfunding Concept for Port City Project**. In: ASSOCIATION FOR COMPUTING MACHINERY, 2021, New York, NY, USA. Anais. Association for Computing Machinery, 2021. (SPBPU IDE ’20).
https://dl.acm.org/doi/abs/10.1145/3444465.3444476

BROOKBANKS, M. M.; PARRY, G. **The impact of a blockchain platform on trust in established relationships: a case study of wine supply chains**. Supply Chain Management, [S.l.], 2022.
https://www.emerald.com/insight/content/doi/10.1108/SCM-05-2021-0227/full/html

BUSH, K. **Blockchain: novel provenance applications**. Washington, DC: Congressional Research Service, 2022. (R47064).
https://sgp.fas.org/crs/misc/R47064.pdf

BUSTAMANTE, P.; CAI, M.; GOMEZ, M.; HARRIS, C.; KRISHNAMURTHY, P.; LAW, W.; MADISON, M. J.; MURTAZASHVILI, I.; MURTAZASHVILI, J. B.; MYLOVANOV, T.; SHAPOVAL, N.; VEE, A.; WEISS, M. **Government by Code? Blockchain Applications to Public Sector Governance**. Frontiers in Blockchain, [S.l.], v. 5, 2022.
https://www.frontiersin.org/articles/10.3389/fbloc.2022.869665/full

CAGIGAS, D.; CLIFTON, J.; DIAZ-FUENTES, D.; FERNáNDEZ-GUTIéRREZ, M. **Blockchain for Public Services: a systematic literature review**. IEEE Access, [S.l.], v. 9, p. 13904–13921, 2021. CAI, Z.; YANG, G.; XU, S.; ZANG, C.; CHEN, J.; HANG, P.; YANG, B. RBaaS: a robust blockchain as a service paradigm in cloud-edge collaborative environment. IEEE Access, [S.l.], v. 10, p. 35437–35444, 2022.
https://ieeexplore.ieee.org/document/9326290

CHARLON, F. **Overview of Openchain**. 2017.
https://docs.openchain.org/_/downloads/en/latest/pdf/ e https://docs.openchain.org/en/latest/general/overview.html

CHARLON, F. **Openchain modules Storage engines**. 2015.
https://docs.openchain.org/en/latest/general/modules.html#storage-engines

CHEN, S.; ZHANG, J.; SHI, R.; YAN, J.; KE, Q. **A Comparative Testing on Performance of Blockchain and Relational Database: foundation for applying smart technology into current business systems**. In: _____. . [S.l.: s.n.], 2018. p. 21–34.
https://link.springer.com/chapter/10.1007/978-3-319-91125-0_2

DAS, S.; SARAF, C.; KHAIRNAR, D. P. **A Hyperledger Fabric Based Organizational Decentralized Access Control Solution**. In: IEEE 7TH INTERNATIONAL CONFERENCE ON ENGINEERING TECHNOLOGIES AND APPLIED SCIENCES (ICETAS), 2020., 2020. Anais. . . [S.l.: s.n.], 2020. p. 1–6.
https://ieeexplore.ieee.org/document/9484187

DIB, O.; BROUSMICHE, K.-L.; DURAND, A.; THEA, E.; BEN HAMIDA, E. **Consortium blockchains: overview, applications and challenges**. International Journal On Advances in Telecommunications, France, 2018.
https://hal.science/hal-02271063

EMBRAPA. **Uso de blockchain para registro de dados de Cadeia de Suprimentos Verde da indústria sucroenergética**. 2020.
https://www.alice.cnptia.embrapa.br/handle/doc/1126142

ESMAEILIAN, B.; SARKIS, J.; LEWIS, K.; BEHDAD, S. **Blockchain for the future of sustainable supply chain management in Industry 4.0**. Resources, Conservation and Recycling, [S.l.], v. 163, p. 105064, 2020.
https://www.sciencedirect.com/science/article/abs/pii/S0921344920303815

GAO, U. S. G. A. O. **Blockchain Emerging Technology Offers Benefits for Some Applications but Faces Challenges**. Washington, DC0: Government Accountability Office, 2022. GAO-22-104625.
https://www.gao.gov/products/gao-22-104625

GERAKOUDI-VENTOURI, K. **Review of studies of blockchain technology effects on the shipping industry**. Journal of Shipping and Trade, [S.l.], v. 7, n. 1, p. 2, Jan 2022.
https://jshippingandtrade.springeropen.com/articles/10.1186/s41072-021-00105-2

GUERPINAR, T.; GUADIANA, G.; ASTERIOS IOANNIDIS, P.; STRAUB, N.; HENKE, M. **The Current State of Blockchain Applications in Supply Chain Management**. In: THE 3RD INTERNATIONAL CONFERENCE ON BLOCKCHAIN TECHNOLOGY, 2021., 2021, New York, NY, USA. Anais. . . Association for Computing Machinery, 2021. p. 168–175. (ICBCT ’21).
https://dl.acm.org/doi/fullHtml/10.1145/3460537.3460568

HASAN, H.; ALHADHRAMI, E.; ALDHAHERI, A.; SALAH, K.; JAYARAMAN, R. **Smart contract-based approach for efficient shipment management**. Computers Industrial Engineering, [S.l.], v. 136, p. 149–159, 2019.
https://www.sciencedirect.com/science/article/abs/pii/S0360835219304140

HRGA, A.; CAPUDER, T.; ZARKO, I. **Demystifying Distributed Ledger Technologies: limits, challenges and potentials in the energy sector**. IEEE Access, [S.l.], v. PP, p. 1–1, 07 2020.
https://ieeexplore.ieee.org/document/9136665

IMERI, A.; AGOULMINE, N.; KHADRAOUI, D. **Blockchain and IoT integrated approach for a trusted and secured process to manage the transportation of dangerous goods**. Revista de sistemas e computação, Salvador, Brasil, v. 10, n. 1, p. 26–41, 2020.
https://revistas.unifacs.br/index.php/rsc/article/download/6444/4031

IPFS. **How IPFS works**. 2022.
https://docs.ipfs.tech/concepts/how-ipfs-works/

ITI. **ITI apoia BNDES em projeto de Blockchain**. 2022.
https://www.gov.br/iti/pt-br/assuntos/noticias/indice-de-noticias/iti-apoia-bndes-em-projeto-de-blockchain

ITU-T. **Technical Specification FG DLT D3.1 Distributed ledger technology reference architecture. Geneva, Switzerland: ITU-T, 2019**. (FG DLT D3.1).
https://www.itu.int/en/ITU-T/focusgroups/dlt/Documents/d31.pdf

JABBAR, A.; DANI, S. **Investigating the link between transaction and computational costs in a blockchain environment**. International Journal of Production Research, [S.l.], v. 58, n. 11, p. 3423–3436, 2020.
https://www.tandfonline.com/doi/full/10.1080/00207543.2020.1754487

KAPSOULIS, N.; PSYCHAS, A.; PALAIOKRASSAS, G.; MARINAKIS, A.; LITKE, A.; VARVARIGOU, T.; BOUCHLIS, C.; RAOUZAIOU, A.; CALVO, G.; ESCUDERO SUBIRANA, J. **Consortium Blockchain Smart Contracts for Musical Rights Governance in a Collective Management Organizations (CMOs) Use Case**. Future Internet, [S.l.], v. 12, n. 8, 2020.
https://www.mdpi.com/1999-5903/12/8/134

KERESZTES, R.; KOVáCS, I.; HORVáTH, A.; ZIMáNYI, K. **Exploratory Analysis of Blockchain Platforms in Supply Chain Management**. Economies, [S.l.], v. 10, n. 9, 2022.
https://www.mdpi.com/2227-7099/10/9/206

KHAN, D.; JUNG, L. T.; HASHMANI, M. A. **Systematic Literature Review of Challenges in Blockchain Scalability**. Applied Sciences, [S.l.], v. 11, n. 20, 2021.
https://www.mdpi.com/2076-3417/11/20/9372

KHAN, S.; SHAEL, M.; MAJDALAWIEH, M.; NIZAMUDDIN, N.; NICHO, M. **Blockchain for Governments: the case of the dubai government**. Sustainability, [S.l.], v. 14, n. 11, 2022.
https://www.mdpi.com/2071-1050/14/11/6576

KLEMENS, S. **How long does a bitcoin transaction take? bitcoin unconfirmed transactions**. [S.l.]: Exodus Crypto News amp; Insights, 2021.
https://coinmarketcap.com/academy/article/how-long-does-a-bitcoin-transaction-take

KOHLI, V.; CHAKRAVARTY, S.; CHAMOLA, V.; SANGWAN, K. S.; ZEADALLY, S. **An analysis of energy consumption and carbon footprints of cryptocurrencies and possible solutions**. Digital Communications and Networks, [S.l.], 2022.
https://www.sciencedirect.com/science/article/pii/S2352864822001390

KOMOLAFE, O. **Solana faster than Algorand and TRON – The fastest blockchains in crypto space**. [S.l.]: Crypto News Flash, 2022.
https://www.crypto-news-flash.com/solana-faster-than-algorand-and-tron-the-fastest-blockchains-in-crypto-space/

KOUSSEMA, R. A.; HAGA, H. **Design and Implementation of Highly Secure Residents Management System Using Blockchain**. Journal of Computer and Communications, [S.l.], v. 08No.09, p. 14, 2020.
https://www.scirp.org/journal/paperinformation.aspx?paperid=102949

KUO, T.-T.; ZAVALETA ROJAS, H.; OHNO, L. **Comparison of blockchain platforms: a systematic review and healthcare examples**. Journal of the American Medical Informatics Association, [S.l.], v. 26, n. 5, p. 462–478, 03 2019.
https://pubmed.ncbi.nlm.nih.gov/30907419/

LASMOLES, O.; T. DIALLO, M. **Impacts of Blockchains on International Maritime Trade**. Journal of Innovation Economics & Management, Louvain-la-Neuve, v. 37, n. 1, p. 91–116, 2022.
https://www.cairn.info/revue-journal-of-innovation-economics-2022-1-page-91.htm

LENGE, J.; MUSUMBU, K.; WANUKU, G.; SUNGU, P. **Blockchain Technology as A Guarantee of Transparency in The Supply Chain of Commercial Enterprises**. In: ASIA  SERVICE SCIENCES AND SOFTWARE ENGINEERING CONFERENCE, 2022., 2022, New York, NY, USA. Anais. Association for Computing Machinery, 2022. p. 1–7. (ASSE’22).
https://dl.acm.org/doi/fullHtml/10.1145/3523181.3523182

LI, N.; GUO, Y.; CHEN, Y.; CHAI, J. **A Partitioned DAG Distributed Ledger with Local Consistency for Vehicular Reputation Management**. Wireless Communications and Mobile Computing, [S.l.], v. 2022, p. 6833535, Mar 2022.
https://www.hindawi.com/journals/wcmc/2022/6833535/

MAESA, D. D. F.; MORI, P. **Blockchain 3.0 applications survey**. Journal of Parallel and Distributed Computing, [S.l.], v. 138, p. 99 – 114, 2020.
https://www.sciencedirect.com/science/article/abs/pii/S0743731519308664

MANEVICH, Y.; BARGER, A.; TOCK, Y. **Endorsement in Hyperledger Fabric via service discovery**. IBM Journal of Research and Development, [S.l.], v. 63, n. 2/3, p. 2:1–2:9, 2019.
https://dl.acm.org/doi/10.1147/JRD.2019.2900647

MASOOD, F.; FARIDI, A. **An Overview of Distributed Ledger Technology and its Applications. International Journal of Computer Sciences and Engineering**, [S.l.], v. 6, p. 422–427, 10 2018.
https://www.researchgate.net/publication/330139945_An_Overview_of_Distributed_Ledger_Technology_and_its_Applications

MONTEIRO, E. S.; MIGNONI, M. E.; RIGHI, R. d. R.; KUNST, R. **Blockchain e inteligência artificial associada no controle de packs agrotóxicos**. RICA Revista Ibero-Americana de Ciências Ambientais, [S.l.], v. 12, n. 12, 2021. https://sustenere.inf.br/index.php/rica/article/view/6312

MONTEIRO, E. S.; ROSA RIGHI, R. da; BARBOSA, J. L. V.; ALBERTI, A. M. **APTM: a model for pervasive traceability of agrochemicals**. Applied Sciences, [S.l.], v. 11, n. 17, 2021.
https://www.mdpi.com/2076-3417/11/17/8149


NIE, Y.; HE, X.-W.; CAI, W.-L.; LIU, Z.-H. **Improve the security of Hyperledger Fabric by dynamically selecting endorsing peers**. In: INTERNATIONAL SYMPOSIUM ON COMPUTER AND INFORMATION PROCESSING TECHNOLOGY (ISCIPT), 2021., 2021. Anais. . . [S.l.: s.n.], 2021. p. 659–663.
https://ieeexplore.ieee.org/document/9644558

OCDE. **Recommendation of the council on blockchain and other distributed ledger technologies**. 2 Rue André Pascal, 75016 Paris, France: OCDE, 2022. Council at Ministerial.
https://www.oecd.org/mcm/Recommendation-on-Blockchain-and-other-Distributed-Ledger-Technologies.pdf

OGUNDARE, I. **Cardano to scale to 1,000,000 tps with Hydra for micropayments on ADA blockchain**. [S.l.]: Crypto News Flash, 2022.
https://cardanofeed.com/cardano-to-scale-to-1000000-tps-with-hydra-for-micropayments-on-ada-blockchain-139538

PARK, S.; KIM, H. **DAGmap: multi-drone slam via a dag-based distributed ledger**. Drones, [S.l.], v. 6, n. 2, 2022.
https://www.researchgate.net/publication/358001662_DAGmap_Multi-Drone_SLAM_via_a_DAG-Based_Distributed_Ledger

PENG, Y.; DU, M.; LI, F.; CHENG, R.; SONG, D. **FalconDB: blockchain-based collaborative database**. In: ACM SIGMOD INTERNATIONAL CONFERENCE ON MANAGEMENT OF DATA, 2020., 2020, New York, NY, USA. Proceedings. . . Association for Computing Machinery, 2020. p. 637–652. (SIGMOD ’20).
https://dl.acm.org/doi/10.1145/3318464.3380594

PEREZ, A. O.; DOMINGO-PALAOAG, T. **Blockchain-based Model for Health Information Exchange: a case for simulated patient referrals using an electronic medical record**. IOP Conference Series: Materials Science and Engineering, [S.l.], v. 1077, n. 1, p. 012059, feb 2021.
https://iopscience.iop.org/article/10.1088/1757-899X/1077/1/012059

PRASHAR, D.; JHA, N.; JHA, S.; LEE, Y.; JOSHI, G. P. **Blockchain-Based Traceability and Visibility for Agricultural Products: a decentralized way of ensuring food safety in india**. Sustainability, [S.l.], v. 12, n. 8, 2020.
https://www.mdpi.com/2071-1050/12/8/3497

PSARAS, Y.; SOARES, J. M.; DIAS, D. **To the InterPlanetary File System–and Beyond!: peer-to-peer file sharing would make the internet far more efficient**. IEEE Spectrum, [S.l.], v. 59, n. 11, p. 34–39, 2022.
https://ieeexplore.ieee.org/document/9941036

PURBO, O.; SRIYANTO, S.; SUHENDRO, S.; RZ, A.; HERWANTO, R. **Benchmark and comparison between hyperledger and MySQL**. TELKOMNIKA (Telecommunication Computing Electronics and Control), [S.l.], v. 18, p. 705, 04 2020.
https://pdfs.semanticscholar.org/fcd6/2761cfd48eb7974ae89b7953246d332f09a2.pdf

RAUCHS, M.; GLIDDEN, A.; GORDON, B.; PIETERS, G.; RECANATINI, M.; ROSTAND, F.; VAGNEUR, K.; ZHANG, B. **Distributed Ledger Technology Systems: a conceptual framework**. SSRN Electronic Journal, [S.l.], 01 2018.
https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3230013

SA, R.; MOREIRA, L.; MACHADO, J. **A modular approach to Hybrid Blockchain-based and Relational Database Architectures**. In: ESTENDIDOS DO XXXVII SIMPóSIO BRASILEIRO DE BANCOS DE DADOS, 2022, Porto Alegre, RS, Brasil. Anais. . . SBC, 2022. p. 154–160.
https://sol.sbc.org.br/index.php/sbbd_estendido/article/view/21858

SADEQ, M. J.; RAYHAN KABIR, S.; AKTER, M.; FORHAT, R.; HAQUE, R.; AKHTARUZZAMAN, M. **Integration of Blockchain and Remote Database Access Protocol-Based Database**. In: FIFTH INTERNATIONAL CONGRESS ON INFORMATION AND COMMUNICATION TECHNOLOGY, 2021, Singapore. Proceedings. . . Springer Singapore, 2021. p. 533–539.
https://www.researchgate.net/publication/344194318_Integration_of_Blockchain_and_Remote_Database_Access_Protocol-based_Database

SALAH, K.; REHMAN, M. H. U.; NIZAMUDDIN, N.; AL-FUQAHA, A. **Blockchain for AI: review and open research challenges**. IEEE Access, [S.l.], v. 7, p. 10127–10149, 2019.
https://ieeexplore.ieee.org/document/8598784

SILVA, J. O. D. da; SANTOS, D. R. dos. **Study of Blockchain Application in the Logistics Industry**. Theoretical Economics Letters, [S.l.], v. 12, n. 2, p. 321–342, 4 2022.
https://www.scirp.org/journal/paperinformation.aspx?paperid=115674

SINGH, A.; GUTUB, A.; NAYYAR, A.; KHAN, M. K. **Redefining food safety traceability system through blockchain: findings, challenges and open issues**. Multimedia Tools and Applications, [S.l.], Oct 2022.
https://link.springer.com/article/10.1007/s11042-022-14006-4

SINGH, N.; VARDHAN, M. **Computing Optimal Block Size for Blockchain based Applications with Contradictory Objectives**. Procedia Computer Science, [S.l.], v. 171, p. 1389–1398, 2020. Third International Conference on Computing and Network Communications (CoCoNet’19).
https://www.sciencedirect.com/science/article/pii/S1877050920311285

SOLVEJ, K.; NATARAJAN, K.; HARISH, G.; LUSKIN, H. **Distributed Ledger Technology (DLT) and blockchain**. Washington, D.C., 2017.
https://openknowledge.worldbank.org/entities/publication/563eb421-4449-5319-953b-2ace8da058c0

SULTAN, K.; RUHI, U.; LAKHANI, R. *Conceptualizing Blockchains: characteristics & applications*. CoRR, [S.l.], v. abs/1806.03693, 2018.
https://arxiv.org/abs/1806.03693

SYLIM, P. G.; LIU, F.; MARCELO, A. B.; FONTELO, P. A. **Blockchain Technology for Detecting Falsified and Substandard Drugs in Distribution: pharmaceutical supply chain intervention**. JMIR Research Protocols, [S.l.], v. 7, 2018.
https://pubmed.ncbi.nlm.nih.gov/30213780/

**SYSRFID: GENERATION OF SYNTHETIC DATA IN SUPPLY CHAINS**, 2011, Rome, Italy. Anais. . . itAIS, 2011. p. 6.
http://www.itais.org/proceedings/itais2011/pdf/25.pdf

TAN, E.; MAHULA, S.; CROMPVOETS, J. **Blockchain governance in the public sector: a conceptual framework for public management**. Government Information Quarterly, [S.l.], v. 39, p. 101625, 09 2021.
https://www.sciencedirect.com/science/article/pii/S0740624X21000617

TCU. **TCU e BNDES lançam Rede Blockchain Brasil e definem próximos passos**. 2022.
https://portal.tcu.gov.br/imprensa/noticias/tcu-e-bndes-lancam-rede-blockchain-brasil-e-definem-proximos-passos.htm#:~:text=O%20Tribunal%20de%20Contas%20da,aplica%C3%A7%C3%A3o%20descentralizada%20ocorra%20em%202023.

VIRIYASITAVAT, W.; HOONSOPON, D. **Blockchain characteristics and consensus in modern business processes**. Journal of Industrial Information Integration, [S.l.], v. 13, p. 32–39, 2019.
https://www.semanticscholar.org/paper/Blockchain-characteristics-and-consensus-in-modern-Viriyasitavat-Hoonsopon/cf58f0c53a2bd2c0a1ee7bec77920c3f80036ac2

WANG, Z.; WANG, T.; HU, H.; GONG, J.; REN, X.; XIAO, Q. **Blockchain-based framework for improving supply chain traceability and information sharing in precast construction**. Automation in Construction, [S.l.], v. 111, p. 103063, 2020.
https://www.sciencedirect.com/science/article/abs/pii/S0926580519305059

WORLDBANK. **Blockchain & Distributed Ledger Technology (DLT)**. 2018. 1 p.
https://openknowledge.worldbank.org/server/api/core/bitstreams/5166f335-35db-57d7-9c7e-110f7d018f79/content

XU, S.; ZHAO, X.; LIU, Z. **The impact of blockchain technology on the cost of food traceability supply chain**. IOP Conference Series: Earth and Environmental Science, [S.l.], v. 615, n. 1, p. 012003, dec 2020.
https://iopscience.iop.org/article/10.1088/1755-1315/615/1/012003/pdf

XU, X.; LU, Q.; LIU, Y.; ZHU, L.; YAO, H.; VASILAKOS, A. V. **Designing blockchain-based applications a case study for imported product traceability**. Future Generation Computer Systems, [S.l.], v. 92, p. 399–406, 2019.
https://www.sciencedirect.com/science/article/abs/pii/S0167739X18314298

YADAV, J.; SHEVKAR, R. **Performance-Based Analysis of Blockchain Scalability Metric**. Tehnicki glasnik, [S.l.], v. 15, p. 133–142, 03 2021.
https://hrcak.srce.hr/file/367642

YUE, K.-B.; CHANDRASEKAR, K.; AND, H. G. **Storing and Querying Bitcoin Blockchain Using SQL Databases**. Information Systems Education Journal (ISEDJ), Texas, USA, v. 8, 8 2019.
https://files.eric.ed.gov/fulltext/EJ1219543.pdf

ZAKARI, N.; AL-RAZGAN, M.; ALSAADI, A.; ALSHAREEF, H.; SAIGH, H. A.; ALASHAIKH, L.; ALHARBI, M.; ALOMAR, R.; ALOTAIBI, S. **Blockchain technology in the pharmaceutical industry: a systematic review**. PeerJ Comput. Sci., [S.l.], p. 26, 3 2022.
https://peerj.com/articles/cs-840/

ZHAO, F.; GUO, X.; CHAN, W. K. V. **Individual Green Certificates on Blockchain: a simulation approach**. Sustainability, [S.l.], v. 12, n. 9, 2020.
https://www.mdpi.com/2071-1050/12/9/3942

ZHAO, W.; LV, J.; YAO, X.; ZHAO, J.; JIN, Z.; QIANG, Y.; CHE, Z.; WEI, C. **Consortium Blockchain-Based Microgrid Market Transaction Research**. Energies, [S.l.], v. 12, n. 20, 2019.
https://www.mdpi.com/1996-1073/12/20/3812

Szabo, Nick. **The Idea of Smart Contracts**. 1997. https://www.fon.hum.uva.nl/rob/Courses/InformationInSpeech/CDROM/Literature/LOTwinterschool2006/szabo.best.vwh.net/idea.html

Szabo, Nick. **Smart Contracts**. 1994. https://www.fon.hum.uva.nl/rob/Courses/InformationInSpeech/CDROM/Literature/LOTwinterschool2006/szabo.best.vwh.net/smart.contracts.html

Szabo, Nick. **Smart Contracts: Building Blocks for Digital Markets**. 1996. https://www.truevaluemetrics.org/DBpdfs/BlockChain/Nick-Szabo-Smart-Contracts-Building-Blocks-for-Digital-Markets-1996-14591.pdf



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

