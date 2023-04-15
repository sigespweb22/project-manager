# project-manager
Repositório para documentação de gestão de projetos da Br-Bit Sistemas

## Cross
* Multitenacy

## BackEnd
* Entidades comuns entre serviços como DETENTOS, como vamos separa-la? | Vamos ter que separar os serviços.

## FrontEnd
* Campos insentivo fiscal e optante pelo simples é uma pergunta? Então, o ideal seria HasIncentivoFiscal

# Detalhes RoadMap de Abril

# Prioridade Alta

# Prioridade média
* Módulo Saúde em PHP | Definir os passos para reescrita do microservice para dotnet ou node, no intuito de entregá-lo implementado junto do escopo de projetos do supersagep

# Prioridade baixa
* SIAPA - Java / JSF / PrimeNG | Iniciar transição de transferência de tecnologia para o time biters web
* Regime aberto - Facial | Iniciar transição de transferência de tecnologia para o time biters web

## CI/CD - GitLab
* https://about.gitlab.com/pricing/premium/?step=2
* https://about.gitlab.com/pricing/

* Pendências para ver com Mauro
  > Falar sobre o versionamento semântico;
  > Padrão linguagem projeto (Portugês | Inglês);

-------------------------------------------------------------------------------------------------------
ENTREGA ATÉ ABRIL/2023
Educação
Saúde
Meu Reforço
Penal
SIAPA - Java / JSF / PrimeNG
Regime aberto - Facial
Dashboard - DOTNET 7.0
NFS-e - Distrito Federal - NODEJS/EXPRESS

-------------------------------------------------------------------------------------------------------
ENTREGA ATÉ ABRIL/2023
Dashboard - DOTNET 7.0
NFS-e - Distrito Federal - NODEJS/EXPRESS

ESTAS DUAS FEATURES SERÃO DOIS NOVOS MICROSERVICES
-------------------------------------------------------------------------------------------------------
ENTREGA ATÉ DEZEMBRO/2023
SuperSagepWeb
Dashboard - DOTNET 7.0
NFS-e - Distrito Federal - NODEJS/EXPRESS
Laboral/Pecúlio

REUNIÃO 15/03/2023
-------------------------------------------------------------------------------------------------------
* Implantação SAÚDE

REUNIÃO 24/03/2023
-------------------------------------------------------------------------------------------------------
* NFS-e (Assinatura | Travada, Plugar Front com o Back, Envio pro município);
  > Ajustar nome do menu para Nota Fiscal de Serviço;
  > Exportação PDF
  > Exportação de lista de PDF | XML - (Modelo PDF solicitado ao LEONILDO ao qual já solicito para o DF, mas faremos um modelo qualquer depois ajustamos);
  > Sincronização -> Consulta e salvar os dados no banco - 50%
  > Cancelamento -> Consulta e salvar os dados no banco - Quase pronto
  > Listagem -> Concluída - Plugar com o front e listar as notas;
  > Listagem -> Filtros - Está sendo implementado;
  > View -> Concluída;
  > Exportação invidual por NFS-e - PDF (Modelo PDF);
  > Envio de e-mail - Pronto, mas sem anexo do xml e pdf da nota.
  
* Saúde - Implantação
  > Até quarta feira a base em homologação estará pronta
  > Até 15 e 20 de Abril ambiente de homologação
  > Até 15 e 20 de Maio ambiente de produção
* Devs novos (2) - A partir de segunda feira a tarde | Criação do ambiente e o encaminhamento dos treinamento já com foco na transição para produto dentro do projeto.
* Educação | Features para entrega em Abril
* Entrega contínua | 
* Dashboard |


# Assuntos para tratar com o TIME
## Padrãoes de projeto: 
* Porque estão colocando nos métodos de endpoints objetos gigantescos como parâmetros, exemplo é o método ImportNFSERepository
* Porque criaram entidade Tenant no microservice nfse? Não ficou claro a composição dos microservices?
* Porque o tomio criou um seed com os dados todos iguais? Guid pode dar conflito na hora de obter um registro pelo seu ID. Exemplo foi o seed da nota fiscal
* Mensagens de erro devem todas seguir as regras que compõe a nossa lingua. Exemplo: Ponto final no final das mensagens de erro, gramática, e etc...
* Filtros para exportação NFS-e, porque foi colocado os campos Cód. Empresa e convênio como opção para usuário decidir sobre os filtros que vai utilizar para exportar as nfs-es? O adequado seria listar as empresas e convênios permitindo ao usuário buscar pelo nome ou cnpj para efetuar o filtro.
* Entidade NotaFiscal: Campo mesChamada, porque foi utilizado o mês do tipo text? Este dado é do tipo int dentro do tipo DateTime, fica mais fácil para validação, ocupa menos espaço na memória. Se é só o mÊs pq guardo o ano?