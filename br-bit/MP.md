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

Primeiro ponto a ser levantado são os benefícios em cada uma das estratégias;

1) MULTI-ESQUEMAS:
    Benefícios:
    a) Isolamento de dados o que fornece mais segurança em caso de vasamentos de dados;
    b) Em

* Porque não multi-bancos?
> Basicamente quando o assunto é multi-bancos de imediato nos vem em mente 3 grandes benefícios: Isolamento de dados, Personalização e Desempenho nas consultas. Contudo, considerando o nosso negócio este tipo de necessidade não é latente bem como recorrente. Ao passo que o que no que nos é mais relevante como Desempenho temos uma gama imensa de soluções que atendem o modelo escolhido, sem super estimar infraestrutura. Dose certa, para o problema certo.

* A decisão pela estratégia multi-esquemas levou em consideração 3 fatores:

a) RECURSOS e CUSTOS: Manter bancos de dados separados pode exigir maior custo em infraestrutura, maior custo de manutenibilidade pelo time, principalmente nas correções e evolução das tabelas em comum entre os bancos. Bem como impactar diretamente no conceito de entrega contínua de software, ao passo que para cada melhoria que envolva ajustes banco, requer uma atualização de todos os bancos de dados, impactando na cultura de continuidade das entregas.
Outro ponto importante são os recursos superestimados ao concentrar toda operação de apenas uma unidade prisional em um único banco. Por exemplo, manter um banco exclusivo para receber um fluxo não muito grande de requisições simultâneas, bem como também por exemplo uma tabela exclusiva de detentos em um banco exclusivo para manter apenas em média 800 a 1500 registros ativos de detentos.
É o mesmo que usar um canhão pra matar uma barata!

Esta decisão não é a mais fácil de manter, sendo portanto a mais desafiadora.
Vai exigir com o passar do tempo maior conhecimento em tecnologias afins e dedicação do time para superar os desafios de segurança, escalabilidade e performance que irão surgirão com o passar do tempo.

b) GERENCIAMENTO SIMPLIFICADO | CONDIÇÕES MELHORES PARA ESCALAR E INTEGRAR INFORMAÇÕES: Um único banco com multiplos esquemas centraliza a lógica de escala nas atualizações, migrações e monitoramento, o que por sua vez facilita o gerenciamento como um todo, mesmo quando aplicado outras estratégias para prover performance para a aplicação.
Aplicar atualizações em bancos multi-esquemas garante o versionamento preciso e consistência na relação entre as tabelas comuns, tabelas relacionadas, bem como a integridade entre elas no que diz respeito as tabelas idênticas e suas propriedades. Dados em um mesmo banco de dados, separados apenas por esquemas, facilita o relacionamento de informações entre diferentes clientes.

c) ESCALA HORIZONTAL: A medida que o número de clientes aumentam e, consequentemente, o número de bancos de dados aumenta, o gerenciamento e a manutenção de todos estes bancos podem se tornar mais complexos nas necessidades de backups, atualizações e migrações.

* ATENÇÕES IMEDIATOS
> SEGURANÇA: Em casos de vazamento de dados, a extensão do dano é maior, ao passo que tudo está centralizado em apenas um banco central e suas instâncias ou clusters, contudo, uma cultura de segurança forte aliada a estratégias de observability (rastreamento e monitoramento de logs) vão mitigar estes riscos significativamente.
> BACKUPS: Testar os backups pode ser mais desafiador, devido ao volume dos dados, bem como o tamanho dos arquivos de backups gerados.


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



