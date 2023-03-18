# MINHAS PENDÊNCIAS
* Verificar com o Denner e Maira se a TorreServe possui algum serviço de ElasticSearch para indexarmos as 54 bases de dados das vps

## FRONT
* LIMPAR ESTRUTURA DO PROJETO - DEIXAR APENAS AS ENTIDADE RELACIONADAS AO LOGIN, E A NOVA TELA DETENTOS E A NF.

## BACK
* IMPLEMENTAR FUNCIONALIDADE NOVA DE MENU;
* 

## CROSS
* Reuniões tecnologia com o time de BackEnd - Fazer um simuladão sobre dotnet core - Partir do zero com uma entidade

## PRODUTIVIDA TIME
* Desenvolver SCAFFOLDING para criação automatizada dos principais componentes de front e back dos principais projetos 

## DECISÕES PARA O FUTURO DOS PROJETOS
* Golande - https://go.dev/solutions/#case-studies
* Julia
* Arquitetura Lambda - Go ou C#
* gRPC | AMQP - Implementar estes protocolos de comunicação entre microservices

## EVOLUÇÃO DO TIME
https://blog.cronapp.io/5-boas-praticas-para-monitorar-e-gerenciar-o-desenvolvimento-de-softwares/
https://uds.com.br/blog/boas-praticas-de-desenvolvimento-de-software/

## CULTURA DE PROJETO E SEGURANÇA
Abordagem proativa para área de segurança das aplicações.
https://www.syhunt.com/pt/?n=Products.SyhuntCode

## ARQUITETURA WEB

# Estratégia de DB | MULTI-ESQUEMA
* A decisão pela estratégia multi-esquemas levou em consideração 3 fatores:

a) RECURSOS e CUSTOS: Manter bancos de dados separados pode exigir maior custo em infraestrutura, maior custo de manutenibilidade pelo time, principalmente nas correções e evolução das tabelas em comum entre os bancos. Bem como impactar diretamente no conceito de entrega contínua de software, ao passo que para cada melhoria que envolva ajustes banco, requer uma atualização de todos os bancos de dados, impactando na cultura de continuidade das entregas.
Outro ponto importante são os recursos superestimados ao concentrar toda operação de apenas uma unidade prisional em um único banco. Por exemplo, manter um banco exclusivo para receber um fluxo não muito grande de requisições simultâneas, bem como também por exemplo uma tabela exclusiva de detentos em um banco exclusivo para manter apenas em média 800 a 1500 registros ativos de detentos.

Esta decisão não é a mais fácil, sendo a mais desafiadora, contudo, é a que melhor oferece custo benefício 

* Vantagens do banco de dados separado:
> POUCA RELEVÂNCIA | Flexibilidade para escalar horizontalmente, uma vez que é mais fácil clusterizar e distribuir instâncias de um mesmo banco de dados em caso de gargalo.  em geral por tabela isso também pode ser feito na estratégia de multi-esquemas, embora tenhamos uma camada a mais de complexidade para manter os dados sincronizados estre as instâncias.
> Contudo, isso não me parece ser tão importante, uma vez que não há grandes surpresas quanto a quantidade de dados
>

* Desvantagens do banco de dados separado:
> 

Estas vantangens considerando o nosso negócio não são vantagens 

* Vantagens do Multi-Esquemas
> Entrega contínua de correções, pequenos ajustes até novas funcionalidades: Nem sempre as funcionalidades novas serão entregues em produção antes das mesmas serem vendidas ao estado. Portanto, MULTI-ESQUEMAS como argumento de facilidade na e

> Alcançamos o nível necessário de isolamento, sem a necessidade da separação dos dados em cada tabela pelo tenantId

* Desvantagens

* Como lidar com as desvantagens:
> Federated Database System: Vamos dividir as unidades prisionais em grupos de bancos de dados, onde cada estado terá um banco de dados único, com multiplos esquemas ao qual cada um representa os dados de uma unidade prisional.

# Porque não usuar DB's separadas:

* Não há necessidades emergenciais de escala 

* Benefícios da tenant via multi-scheme


## Dados estatísticos sobre o sistema prisional no Brasil
TOTAL UNIDADE PRISIONAIS NO BRASIL: 1381
TOTAL DETENTOS NO BRASIL: 811k
https://www.cnmp.mp.br/portal/relatoriosbi/sistema-prisional-em-numeros



