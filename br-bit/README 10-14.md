# Pendências semana entre 10-04 | 14-04

## Avisa Maisa das issues no gitlab

## CI/CD - GitLab RoadMap | Roteiros
* Implementar Gráfico de Gantt - A ideia é implementar uma ferramenta visual para controlar os cronogramas dos projetos. No sentido de ajudar a avaliar os prazos de entrega e os recursos crítico
 
# Ajuste sagep-nfse

* Formato de xml retornado na chamada de export, está correto? Validar com Maira...
* O que a route import faz? | Implementei o serviço e preciso ajustar de acordo com as especificações corretas...
* Implementar o método de busca inicialmente pelo número dela (Esta busca deve ocorrer dentro do microservice e não na prefeitura) - Consultar documentação de api do sagep-auth para implementar no mesmo modelo;
* O que seria a entidade tenantFornecedor?
* Excluir entidade notaFiscalStatus e substituir este campo por uma enumeração
* No arquivo ts excluir as propriedades de status (notaFiscalStatusId e notaFiscalStatus), substitui pela propriedade que é do tipo enumeração
* Padronizar os dados da tenancy com base nas propriedades do sagep-auth
* O Tipo ImportNFSE como parametro no endpoint ImportNFSEApplication tem a propriedade serviço, esta propriedade são os serviços da NFSe? Caso sim, deveria ser no plurall
export interface ImportNFSE {
    tenant: Tenant;
    fornecedor: Fornecedor;
    notaFiscal: NotaFiscal;
    servico: Servico & notaFiscalServico;
}

## Padrões de nomenclatura
* Trocar o nome Discriminacao por Descrição
* Manter um padrão apenas: Ou PascalCase ou Undercore
export interface FilterNFSE extends ExportType {

    tenantId: string;
    competencia_from?: string
    competencia_to?: string
    notaFiscalStatusId?: string
    numeroNotaFiscal?: number   
    codigoChamada?: string
    mesChamada?: string
    codigoEmpresa?: number
    codigoConvenio?: number
    notaFiscalStatus?: string,
    razaoSocial?: string
}

## Ajustes JWT
* A rota deverá estar protegida e o middleare deve verificar se o token do usuário possui as permissões a seguir para acessar a rota.
O tenantId deverá ser extraido do token, conforme padrão abaixo.

# Padrões | Implementar regras no SonarCube ou GitLab - Não permitir o merge request?!?
* Criar regras para padronizar nomes de entidade (PascalCase ou Undercore), sonarcube ou gitlab?