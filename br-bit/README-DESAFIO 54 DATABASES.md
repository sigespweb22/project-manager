## A nova aplicação de DASHBOARD deverá consumir dados de 54 bancos de dados diferentes (são unidades prisionais diferentes)

# São duas possíveis abordagens
* 1) Criar uma camada de serviço que agrupa os dados de todos os bancos de dados e expõe uma única API para sua dashboard. Dessa forma, a dashboard só precisaria se comunicar com um único serviço, e o serviço seria responsável por gerenciar todas as conexões aos bancos de dados.
Esta camada poderia ser em Python ou Node, para aproveitar os recursos específicos dessas linguagens no processamento de dados em lotes.

* 2) Elasticsearch | Banco de dados de indexação: Iríamos indexar e pesquisar dados em diferentes bancos de dados em tempo real.

A princípio a abordagem que me parece mais adequada é com elasticsearch.
