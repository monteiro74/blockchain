# Sobre Blockchain e livros razão



[1 Conceitos](#1-Conceitos) <br>
[1.1. O problema de double spending](#11-o-problema-de-double-spending)<br>
[1.2. Criptografia de chave pública](#12-critografia-de-chave-pública)<br>
[1.3. Certificado digital](#13-certificado-digital)<br>
[1.4. Tecnologias de livro razao](#14-tecnologias-de-livro-razao)<br>
[2 Aplicabilidade](#2-Aplicabilidade)<br>
[3 Tendências](#3-Tendências)<br>
[4 Artigos interessantes](#4-Artigos-interessantes)<br>
[5 Fontes](#4-Fontes)<br>



---
# 1 Conceitos


## 1.1. O problema de double spending

## 1.2. Critografia de chave pública

## 1.3. Certificado digital

## 1.4. Tecnologias de livro razao

Tecnologias de livro razão distribuídas (ou "Distributed Ledger Technology (DLT)"do inglês) podem ser usadas para resolver problemas provocados pelo uso de uma terceira parte para autenticar transações, evitar cobranças de serviços, diminuir tempo de processamento, não se submeter a uma autoridade central e evitar um ponto de falha. 

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



### 1.4.2. Blockchain


Blockchain é uma cadeia de blocos, na qual cada nó tem blocos de dados, um carimbo de
data/hora e um hash de código que se refere ao nó anterior, reforçando a cadeia de dados de
forma imutável (SULTAN; RUHI; LAKHANI, 2018a). 

A tecnologia blockchain foi inicialmente projetada para oferecer suporte a moedas criptográficas (MAESA; MORI, 2020), mas
hoje, pode-se usá-la para outros fins, incluindo rastreamento da cadeia logística e contratos
entre pessoas que não se conhecem. 

Assim, a blockchain funciona salvando as transações de
interesse para as quais foi projetada, onde cada uma pode implementar uma série de regras e
também servir para transmitir dados. 

Em particular, as regras para a execução de transações
ou operações são realizadas por meio de contratos inteligentes (SALAH et al., 2019; SULTAN;
RUHI; LAKHANI, 2018a). 

Do ponto de vista do programador, elas podem ser vistas como
um script (ou, simplificando, um programa que deve ser executado automaticamente quando
uma transação é realizada). 

Assim, blockchain pode conter dados e código executável (MAESA; MORI, 2020), onde o último é visto como a lógica de programação para atualizar dados e disparar ações externas ao blockchain, Figura 7.




Artigo que iniciou com a ideia: [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf).

--- 
# 2 Aplicabilidade 


Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec nec orci dui. Pellentesque ultricies auctor faucibus. Se

---
# 3 Tendências


Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec nec orci dui. Pellentesque ultricies auctor faucibus. Sed tempor sem id diam molestie tempus. Duis id aliquam dolor. 

---
# 4 Artigos interessantes

1. [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf)


Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec nec orci dui. Pellentesque ultricies auctor faucibus. Sed tempor sem id diam molestie tempus. Duis id aliquam dolor. 

---
# 5 Fontes


Duis id aliquam dolor. Sed posuere ut nulla non dictum. Fusce dignissim, nisl sit amet mattis venenatis, urna justo consequat ex, sit amet semper sapien turpis id leo. Phasellus mollis dignissim tincidunt. 

---
# 6 Videos

---
# 7 Reportagens