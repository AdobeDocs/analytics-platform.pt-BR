---
title: Um exemplo de projeto B2B
description: Saiba como definir, configurar e relatar dados B2B
solution: Customer Journey Analytics
feature: Use Cases
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: d1097ca5f981623283a7d02200d5023548046429
workflow-type: tm+mt
source-wordcount: '1373'
ht-degree: 6%

---

# Um exemplo de projeto B2B baseado em pessoas

Este artigo ilustra um caso de uso em que você deseja relatar corretamente no Customer Journey Analytics os dados pessoais no contexto de uma configuração B2B típica com base em pessoas. Essa configuração é facilitada pela [Real-Time CDP B2B edition](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/intro/rtcdpb2b-intro/b2b-overview).  O caso de uso explica como definir, configurar e relatar dados B2B baseados em nível de perfil (pessoa) no Customer Journey Analytics.

[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Uma seção separada para casos de uso de relatórios baseados em conta foi publicada com a versão do [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md).

## Conexão

Defina sua conexão para incluir todos os conjuntos de dados B2B relevantes da Experience Platform. Conjuntos de dados que você pode considerar adicionar à conexão:

| Conjunto de dados (opcional) | Esquema | Tipo de esquema | Classe base | Descrição |
|---|---|---|---|---|
| Conjunto de dados da atividade B2B | Esquema de atividade B2B | Evento | XDM ExperienceEvent | Um ExperienceEvent é um registro de fato do que ocorreu, incluindo o momento e a identidade do indivíduo envolvido. ExperienceEvents podem ser explícitos (ações humanas diretamente observáveis) ou implícitos (gerados sem uma ação humana direta) e são registrados sem agregação ou interpretação. Os eventos de experiência são essenciais para a análise no domínio do tempo, pois permitem a observação e a análise das alterações que ocorrem em uma determinada janela de tempo e a comparação entre várias janelas de tempo para rastrear tendências. |
| Conjunto de dados de pessoa B2B | Esquema de pessoa B2B | Perfil | Perfil individual XDM | Um Perfil individual XDM forma uma representação singular dos atributos e interesses de indivíduos identificados e parcialmente identificados. Os perfis menos identificados podem conter apenas sinais comportamentais anônimos, como cookies de navegador, enquanto os perfis altamente identificados podem conter informações pessoais detalhadas, como nome, data de nascimento, localização e endereço de email. À medida que um perfil cresce, ele se torna um repositório robusto de informações pessoais, informações de identificação, detalhes de contato e preferências de comunicação de um indivíduo. |
| Conjunto de dados da conta B2B | Esquema de conta B2B | Pesquisa | Conta de negócios XDM | Uma Conta comercial XDM é uma classe padrão do Experience Data Model (XDM) que captura as propriedades mínimas necessárias de uma conta comercial. Essa classe XDM só pode ser incluída no perfil de clientes com o B2B ou B2P Edition. |
| Conjunto de dados de oportunidade B2B | Esquema de oportunidade B2B | Pesquisa | Oportunidade de negócios XDM | A Oportunidade de negócios XDM é uma classe padrão do Experience Data Model (XDM) que captura as propriedades mínimas necessárias de uma oportunidade de negócios. Essa classe XDM só pode ser incluída no perfil de clientes com o B2B ou B2P Edition. |
| Conjunto de dados da campanha B2B | Esquema de campanha B2B | Pesquisa | Campanha de negócios XDM | Campanha Comercial XDM é uma classe padrão do Experience Data Model (XDM) que captura as propriedades mínimas necessárias de uma campanha comercial. Essa classe XDM só pode ser incluída no perfil de clientes com o B2B ou B2P Edition. |
| Conjunto de dados da lista de marketing B2B | Esquema de lista de marketing B2B | Pesquisa | Lista de marketing de negócios XDM | A Lista de marketing de negócios XDM é uma classe padrão do Experience Data Model (XDM) que captura as propriedades mínimas necessárias de uma lista de marketing. As listas de marketing permitem que você priorize os clientes em potencial com maior probabilidade de comprar seu produto. Essa classe XDM só pode ser incluída no perfil de clientes com o B2B ou B2P Edition. |
| Conjunto de dados de relação pessoal da conta B2B | Esquema de relação pessoal da conta B2B | Pesquisa | Relação pessoal da conta de negócios XDM | A relação pessoal da conta comercial XDM é uma classe padrão do Experience Data Model (XDM) que captura as propriedades mínimas necessárias de uma pessoa associada a uma conta comercial. |
| Conjunto de dados de relação pessoal da oportunidade B2B | Esquema de relação pessoal de oportunidade B2B | Pesquisa | Relação pessoal de oportunidade de negócios XDM | A relação da pessoa com a oportunidade de negócios XDM é uma classe padrão do Experience Data Model (XDM) que captura as propriedades mínimas necessárias de uma pessoa associada a uma oportunidade de negócios. |
| Conjunto de dados do membro da Lista de marketing B2B | Esquema de membro da Lista de marketing B2B | Pesquisa | Membros da lista de marketing XDM | Membros da Lista de marketing comercial XDM é uma classe padrão do Experience Data Model (XDM) que descreve membros, pessoas ou contatos associados a uma lista de marketing. |
| Conjunto de dados de membro da campanha B2B | Esquema de membro da campanha B2B | Pesquisa | Membros da campanha de negócios XDM | Membros da campanha de negócios XDM é uma classe padrão do Experience Data Model (XDM) que descreve um contato ou um cliente potencial associado a uma campanha de negócios. |

<!--
| B2B Account Dataset | B2B Account Schema | Lookup | XDM Business Account | XDM Business Account is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business account.  |
| B2B Opportunity Dataset | B2B Opportunity Schema | Lookup | XDM Business Opportunity | XDM Business Opportunity is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business opportunity.  |
| B2B Campaign Dataset | B2B Campaign Schema | Lookup | XDM Business Campaign | XDM Business Campaign is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business campaign.  |
| B2B Marketing List Dataset | B2B Marketing List Schema | Lookup | XDM Marketing List | XDM Business Marketing List is a standard Experience Data Model (XDM) class that captures the minimum required properties of a marketing list. Marketing lists allow you to prioritize on prospect clients who are most likely to buy your product.  |
-->


A relação entre os esquemas de pesquisa B2B, o esquema de perfil e o esquema de evento é definida na configuração B2B no Experience Platform. Consulte Esquemas no [Real-Time Customer Data Platform B2B edition](https://experienceleague.adobe.com/pt-br/docs/experience-platform/rtcdp/schemas/b2b) e [Definir uma relação muitos para um entre dois esquemas no Real-Time Customer Data Platform B2B edition](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/relationship-b2b).


Para garantir uma configuração adequada de uma conexão que suporte pesquisas baseadas em pessoas de seus dados B2B, use a seguinte ilustração para obter uma visão geral e siga estas etapas:

![Esquemas B2B anotados](assets/b2b-schemas-annotated.svg)

1. Adicione conjuntos de dados da tabela acima à conexão.
1. Para cada conjunto de dados de pesquisa adicionado à sua conexão, defina explicitamente a relação com um conjunto de dados de evento usando a **[!UICONTROL Chave]** e a **[!UICONTROL Chave correspondente]** na caixa de diálogo **[!UICONTROL Editar conjunto de dados]**.
1. Para cada conjunto de dados de pesquisa que você deseja transformar para pesquisas B2B baseadas em pessoas, habilite **[!UICONTROL Transformar conjunto de dados]** para garantir que os dados sejam transformados para pesquisas baseadas em pessoas. Consulte [Transformar conjuntos de dados para pesquisas B2B](/help/connections/transform-datasets-b2b-lookups.md) para obter informações adicionais.

   ![Chave - Chave correspondente](assets/key-matchingkey.png)

   A tabela abaixo fornece um exemplo de visão geral dos valores de exemplo de [!UICONTROL ID de Pessoa], [!UICONTROL Chave] e [!UICONTROL Chave correspondente] para cada um dos conjuntos de dados.

   >[!IMPORTANT]
   >
   >Os valores de **ID de Pessoa**, **Chave** e **Chave Correspondente** na tabela abaixo são **valores de exemplo** e podem ser diferentes em seu ambiente específico.
   >


   | Conjunto de dados (opcional) | ID da pessoa | Chave<br/> | Chave correspondente<br/>(no conjunto de dados do evento)<br/> |
   |---|---|---|---| 
   | Conjunto de dados da atividade B2B | SourceKey <br/>**personKey.sourceKey** | | |
   | Conjunto de dados de pessoa B2B | SourceKey <br/>**b2b.personKey.sourceKey** | | |
   | Conjunto de dados da conta B2B | | SourceKey <br/>**accountKey.sourceKey**❶ | SourceKey<br>(Conjunto de Dados de Pessoa B2B)<br/>**b2b.accountKey.sourceKey**❶ |
   | Conjunto de dados de oportunidade B2B | | Chave do Source <br/>**opportunityKey.sourceKey**❷ | SourceKey<br/>(Conjunto de Dados de Relação de Oportunidade B2B)<br/>**opportunityKey.sourceKey**❷ |
   | Conjunto de dados da campanha B2B | | SourceKey <br/>**campaignKey.sourceKey**❸ | SourceKey<br/>(Conjunto de Dados de Membro da Campanha B2B)<br/>**campaignKey.sourceKey**❸<br/> |
   | Conjunto de dados da lista de marketing B2B | | SourceKey <br/>**marketingListKey.sourceKey**❹ | SourceKey<br/>(Conjunto de Dados de Membro da Lista de Marketing B2B)<br/>**marketingListKey.sourceKey**❹ |
   | Conjunto de dados de relação pessoal da conta B2B | | SourceKey <br/>**personKey.sourceKey**❺ | Chave do Source<br/>(Conjuntos de dados de eventos)<br/>**personKey.sourceKey**❺ |
   | Conjunto de dados de relação pessoal da oportunidade B2B | | SourceKey <br/>**personKey.sourceKey** y❻ | Chave do Source<br/>(Conjuntos de dados de eventos)<br/>**personKey.sourceKey**❻ |
   | Conjunto de dados de membro da campanha B2B | | SourceKey <br/>**personKey.sourceKey**❼ | Chave do Source<br/>(Conjuntos de dados de eventos)<br/>**personKey.sourceKey**❼ |
   | Conjunto de dados do membro da Lista de marketing B2B | | SourceKey <br/>**personKey.sourceKey**❽ | Chave do Source<br/>(Conjuntos de dados de eventos)<br/>**personKey.sourceKey**❽ |

{style="table-layout:auto"}

Consulte [Adicionar e configurar conjuntos de dados](../../connections/create-connection.md) para obter mais informações sobre como definir configurações para um conjunto de dados.


## Visualização de dados

Para ter acesso a dimensões e métricas B2B relevantes ao criar seu projeto do Workspace, você deve definir sua visualização de dados de acordo.

Você pode, por exemplo, adicionar os seguintes componentes à visualização de dados para garantir que possa relatar o nível com base em pessoas nos seus dados B2B. Os nomes dos componentes às vezes são modificados para maior clareza em relação aos nomes do esquema original.

+++Métricas 

>[!IMPORTANT]
>
>As métricas e seus valores (**Nome do componente**, **Conjunto de Dados**, **Tipo de conjunto de dados** e **[!UICONTROL Caminho do esquema])** na tabela abaixo são **exemplos**. Defina métricas B2B relevantes (Nome do componente, Conjunto de dados, Tipo de dados e Caminho do esquema) para sua situação específica.
>

| Nome do componente | Conjunto de dados | Tipo de dados | Caminho do esquema |
|---|---|---|---|
| Receita anual da conta | Conjunto de dados da conta B2B | Duplo | accountOrganization.annualRevenue.amount |
| Número de funcionários | Conjunto de dados da conta B2B | Número inteiro | accountOrganization.numberOfEmployees |
| Custo Efetivo da Campanha | Conjunto de dados da campanha B2B | Duplo | actualCost.amount |
| Custo orçado da campanha | Conjunto de dados da campanha B2B | Duplo | budgetedCost.amount |
| Receita de oportunidade esperada | Conjunto de dados de oportunidade B2B | Duplo | expectedRevenue.amount |
| Receita esperada da campanha | Conjunto de dados da campanha B2B | Duplo | expectedRevenue.amount |
| Valor da oportunidade | Conjunto de dados de oportunidade B2B | Duplo | opportunityAmount.amount |

+++

+++Dimensões

>[!IMPORTANT]
>
>As dimensões e seus valores (**Nome do componente**, **Conjunto de Dados**, **Tipo de conjunto de dados** e **[!UICONTROL Caminho do esquema])** na tabela abaixo são **exemplos**. Defina dimensões B2B relevantes (Nome do componente, Conjunto de dados, Tipo de dados e Caminho do esquema) para sua situação específica.
>

| Nome do componente | Conjunto de dados | Tipo de dados | Caminho do esquema |
|---|---|---|---|
| Nome da conta | Conjunto de dados da conta B2B | String | accountName |
| Nome da campanha | Conjunto de dados da campanha B2B | String | campaignName |
| Nome do canal | Conjunto de dados da campanha B2B | String | channelName |
| País | Conjunto de dados da conta B2B | String | accountBillingAddress.country |
| Nome da Categoria de Previsão | Conjunto de dados de oportunidade B2B | String | forecastCategoryName |
| Setor | Conjunto de dados da conta B2B | String | accountOrganization.industry |
| Sobrenome | Conjunto de dados de pessoa B2B | String | person.name.lastName |
| Nome da lista de marketing | Conjunto de dados da lista de marketing B2B | String | marketingListName |
| Nome da oportunidade | Conjunto de dados de oportunidade B2B | String | opportunityName |
| Estágio da oportunidade | Conjunto de dados de oportunidade B2B | String | opportunityStage |
| Tipo de oportunidade | Conjunto de dados do tipo de oportunidade B2B | String | opportunityType |
| Nome da sessão do webinário | Conjunto de dados da campanha B2B | String | webinarSessionName |

+++

## Workspace

Com seus componentes definidos corretamente na visualização de dados, agora é possível criar relatórios e visualizações B2B específicos no projeto do Workspace.

Abaixo está uma captura de tela de um projeto de exemplo que depende da conexão e da visualização de dados descritas acima. As descrições da visualização explicam qual da visualização da tabela de forma livre depende dos dados de pesquisa B2B transformados.

![Projeto de exemplo](assets/sample-workspace-project.png)

