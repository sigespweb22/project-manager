# Pendências semana entre 17-04 | 21-04

## Demandas time back
* sagep-nfse: Ajustar todos os endPoint que forem necessários para receber apenas o Id da nota fiscal, e os demais dados como tenant e etc o microservice obtém do bando de dados relacionado ao seu escopo de serviço. Exemplo: CancelNFSE requer codigoCancelamento, este código é regra de negócio relacionada ao microservice sagep-auth, portanto, ele deve ir atrás deste dado, o recurso que o quiser consumir, passa apenas a informação principal para que ele possa ir atrás do resto. 
Ajustar também os verbos destes métodos para get, afim de que recebam os ids na rota

Percebi que os métodos em geral não trabalham as informações relacionadas ao seu serviço, apenas esperam tudo da chamada de api

* sagep-nfse: Ajustar EndPoint para receber apenas o ID da NFS-e. Com base neste ID o microservice deve recuperar os dados da NFS-e e seguir com o processo de importação dos dados.

* exportação NFS-e: Se a exportação é em lote, pq ter o numero da nota fiscal para exportar uma nota fiscal? Já não tem esta funcionalidade individualmente em cada nota?
adequar o tipo FilterNFSE

* Código da empresa e código do convênio não são os mesmos códigos? Código da empresa não seria código do fornecedor?

* sagep-nfse: Tirar tenantId de todos os filtros e parâmetros de endpoint e extrair este dado de dentro do token.

* exportar: Ao abrir modal o tipo pdf está marcado, contudo, não está setado no objeto filtros. Sendo assim quando clica em exportar sem antes selecionar o tipo xml e depois voltar para pdf o tipo fica undefined.

* sagep-nfse: exportar xml: Não está retornando XML adequado, verificar o que está havendo? O tipo de chamada para geração do xml parece ser assincrono porque tem que ir na api para assinar, portanto, demora para vir o retorno e quando vem retorna 406.

* MAIRA: Testar todo sistema, e levantar os erros para os devidos ajustes. Criar os tickets com os problemas e vincular aos responsáveis