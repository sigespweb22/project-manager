# Pendências semana entre 24-04 | 28-04

## Ajustes finais para entrega módulo NFS-e
* sagep-nfse: Método sendEmail > Parâmtros title, doorSMTP e serverSMTP devem ser fixos na aplicação, contudo, criar um ticket para criar uma configuração por tenant e setor para obtenção destes dados sempre que for necessário o envio de um e-mail sistêmico.

* sagep-nfse: ajustar deserealização do token para obter apenas a string da propriedade tenantId. Caso o microservice precise de mais algum dado do tenant, pode portanto fazer uma chamada para o auth e solicitar o tenant com base no seu id.
