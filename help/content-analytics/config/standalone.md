---
title: Configurar o Content Analytics (independente)
description: Orienta você pelas etapas necessárias para configurar o Content Analytics (independente)
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 81e7488a91a99456cd950d367d9ff16ec7c1cb5a
workflow-type: tm+mt
source-wordcount: '1810'
ht-degree: 8%

---


# Configuração independente

>[!IMPORTANT]
>
>Este guia de configuração é para clientes que licenciaram o pacote independente do Adobe Content Analytics. O guia presume que você não usou ou planejou usar o Customer Journey Analytics ou qualquer outro aplicativo do Experience Platform além dos recursos e das funções do Content Analytics. Consulte [Configurar Content Analytics](configuration.md) se desejar configurar e usar o Content Analytics como parte de uma implementação existente do Customer Journey Analytics.
>

Esta configuração orienta você na administração, configuração e instalação de todos os aplicativos necessários para uma implementação **independente** do Content Analytics em funcionamento. Essas etapas consistem em:

1. **Configurar o controle de acesso e as permissões** para oferecer suporte à configuração e à implementação do Content Analytics.
1. **Configure um esquema e um conjunto de dados** para definir o modelo (esquema) dos dados dos quais você deseja coletar insights de análise de conteúdo e de onde coletar esses dados (conjunto de dados).
1. **Configure uma sequência de dados** para configurar como seus dados coletados serão roteados para o conjunto de dados.
1. **Use marcas de site** para configurar regras e elementos de dados em relação aos dados na camada de dados do site e garantir que os dados sejam enviados para a sequência de dados configurada.
1. **Implante** em um ambiente de teste **e valide** a coleta de dados antes de publicar em um ambiente de produção.
1. **Configure uma conexão** com seu conjunto de dados.
1. **Configurar uma visualização de dados** para definir métricas e dimensões.
1. **Configurar e implementar o Content Analytics**.
1. **Configure um projeto** para criar relatórios e visualizações do Content Analytics.

## Configurar controle de acesso e permissões

Esta seção documenta qual acesso é necessário ao produto, perfis de produto e quais permissões são necessárias para configurar e configurar o Content Analytics independente. Embora você só esteja interessado na funcionalidade do Content Analytics, para que essa funcionalidade funcione corretamente, ainda são necessários acesso e permissões para outros produtos da Experience Platform.

### Controle de acesso

O controle de acesso determina se você tem acesso a um produto da Experience Platform.

Você precisa de um administrador de sistema ou de um administrador de produto para adicioná-lo como administrador de um produto ou de um perfil de produto. Um administrador de produto só pode adicioná-lo como administrador do produto administrado (perfil), um administrador de sistema pode adicionar administradores de produto a qualquer produto (perfil).

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Gerenciar usuários para um perfil de produto](https://video.tv.adobe.com/v/333860/?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.


>[!ENDSHADEBOX]

Você precisa ser um administrador de produto dos seguintes produtos e perfis de produto para o Content Analytics independente:

* Adobe Experience Platform
   * AEP-Padrão-Todos-os-Usuários (o perfil padrão para acessar a sandbox de produção)

* Coleção de dados da Adobe Experience Platform
   * Acesso a Todos os Dados da Coleção de Dados Padrão

* Adobe Experience Platform Privacy Service

* Customer Journey Analytics (Personalizado)
   * Customer Journey Analytics (ou qualquer outro perfil de produto provisionado padrão)

Você define o acesso de administrador de produto por meio da Admin Console:

1. Acessar [Admin Console](https://adminconsole.adobe.com).
1. Selecione **[!UICONTROL Produtos]**.
1. Selecione o produto específico.
1. Selecione a guia **[!UICONTROL Administradores]**.
1. Selecione **[!UICONTROL Adicionar administrador]** para adicionar um administrador ao produto.
1. Digite um ou mais nomes de email ou usuário na caixa de diálogo **[!UICONTROL Adicionar administradores de produtos]**. Selecione **[!UICONTROL Salvar]** para salvar.


Você define o acesso do administrador de perfil de produto por meio da Admin Console:

1. Acessar [Admin Console](https://adminconsole.adobe.com).
1. Selecione **[!UICONTROL Produtos]**.
1. Selecione o produto específico. Verifique se você já tem acesso de administrador de produto.
1. Selecione **[!UICONTROL Perfis de produto]**.
1. Selecione o perfil de produto específico.
1. Selecione a guia **[!UICONTROL Administradores]**.
1. Selecione **[!UICONTROL Adicionar administrador]** para adicionar um administrador ao perfil do produto.
1. Insira um ou mais nomes de email ou usuário na caixa de diálogo **[!UICONTROL Adicionar administradores de perfil de produto]**. Selecione **[!UICONTROL Salvar]** para salvar.


### Permissões

As permissões definem o que você pode fazer em um produto depois de ter acesso a ele.

Você define permissões para o Experience Platform na interface [!UICONTROL Permissões] e usa o controle de acesso baseado em atributos. Para o Customer Journey Analytics, você define permissões por meio da [!UICONTROL Admin Console].

#### Experience Platform

A interface [!UICONTROL Permissões] no Experience Platform é baseada na definição de uma função. Uma função é uma coleção de permissões baseadas em recursos. Em um novo ambiente provisionado, duas funções padrão estão disponíveis: **[!UICONTROL Todo o acesso à produção padrão]** e **[!UICONTROL Administradores de sandbox]**.

Para o Content Analytics, é necessário verificar se os seguintes recursos e permissões associadas são adicionados a essas funções:

* Função de Produção padrão de acesso integral

   * Coleta de dados
      * Exibir fluxos de dados
      * Gerenciar fluxos de dados

   * Gerenciamento de dados
      * Visualizar conjuntos de dados
      * Gerenciar conjuntos de dados

   * Modelagem de dados
      * Visualizar esquemas
      * Gerenciar esquemas
      * Gerenciar metadados de identidade


* Função Administradores de sandbox

   * Sandboxes
      * Prod
      * (qualquer outra sandbox que você deseja usar para o Content Analytics)

   * Administração de sandbox
      * Gerenciar pacotes
      * Gerenciar sandboxes
      * Redefinir sandbox
      * Exibir sandbox


Na interface de Permissões, é possível verificar as funções e as permissões associadas. E quais usuários pertencem à função.

1. Acesse o Experience Platform para sua organização.
1. Na tela de boas-vindas, em **[!UICONTROL Acesso rápido]**, selecione **[!UICONTROL Exibir todos]**.
1. Habilite o pino ![PinOn](/help/assets/icons/PinOn.svg) para **[!UICONTROL Permissões]**, para que **[!UICONTROL Permissões]** fique disponível no **[!UICONTROL Acesso Rápido]** para uso futuro.
1. Selecione **[!UICONTROL Permissões]**.
1. Selecione ![Usuário](/help/assets/icons/User.svg) **[!UICONTROL Funções]**.
1. Selecione a função específica que deseja verificar (por exemplo, **[!UICONTROL Acesso integral à Produção Padrão]**). Selecione **[!UICONTROL Exibir tudo]** para ver todas as permissões.
1. Na tela **[!UICONTROL Detalhes]**:
   1. Verifique os **[!UICONTROL Recursos]** listados em **[!UICONTROL Permissões]**.
   1. Verifique os nomes das sandboxes em **[!UICONTROL Sandboxes]**.

   Para fazer atualizações, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]**.
   1. Para adicionar um recurso ausente, selecione **[!UICONTROL Nome do recurso]** ![Adicionar](/help/assets/icons/Add.svg) no painel esquerdo **[!UICONTROL Recursos]** > **[!UICONTROL Adobe Experience Platform]**.
   1. Para adicionar uma permissão ausente, selecione ![DivisaInativa](/help/assets/icons/ChevronDown.svg) no recurso que não tem a permissão no painel principal e selecione a permissão ausente.

      ![Interface de permissões](/help/content-analytics/assets/aep-permissions-ui.png)

   Selecione **[!UICONTROL Salvar]** para salvar qualquer atualização.

1. Na tela Users or Users groups (Usuários ou grupos de usuários):
   1. Verifique se os usuários individuais ou grupos de usuários corretos fazem parte dessa função.
      1. Selecione ![UserAdd](/help/assets/icons/UserAdd.svg) Adicionar usuários aos usuários para adicionar usuários individuais que você definiu no Admin Console.
      1. Selecione ![Adicionar](/help/assets/icons/Add.svg) Adicionar grupos em grupos de usuários para adicionar grupos de usuários definidos no Admin Console.


#### Customer Journey Analytics

O Customer Journey Analytics não oferece suporte ao controle de acesso baseado em atributos. Para especificar permissões, use o Admin Console.

Para o Content Analytics, é necessário verificar se as seguintes permissões de perfil de produto do Customer Journey Analytics estão incluídas:

* Visualizações de dados
   * Todas as visualizações de dados disponíveis.

* Ferramentas de relatório
   * Acesso guiado à análise?
   * Criação de métricas calculadas
   * Criação de segmentos
   * Acesso ao Labs?
   * Criação de anotação
   * Criação de público-alvo?
   * Visualização de público?
   * Acesso aos logs de auditoria
   * Compartilhar links do projeto com qualquer pessoa
   * Previsão
   * Assistente de IA: conhecimento do produto
   * Data Insights Agent
   * Legendas inteligentes
   * Contar histórias de dados?

* Ferramentas de visualização de dados
   * Exportar Tabela Completa?
   * Extensão do CJA BI?

Para verificar e atualizar essas permissões para o Customer Journey Analytics:

1. Acessar [Admin Console](https://adminconsole.adobe.com).
1. Selecione **[!UICONTROL Produtos]**.
1. Selecione o produto **[!UICONTROL Customer Journey Analytics]**.
1. Selecione **[!UICONTROL Perfis de produto]**.
1. Selecione o perfil de produto padrão provisionado disponível para o Customer Journey Analytics. Por exemplo: **[!UICONTROL Customer Journey Analytics]**.
1. Na tela do perfil do produto, selecione **[!UICONTROL Permissões]**.
1. Selecione qualquer um dos botões ![Editar](/help/assets/icons/Edit.svg) para editar as permissões. Na caixa de diálogo **[!UICONTROL Editar permissões para Customer Journey Analytics]**:

   ![Interface de Permissões do CJA](../assets/cja-permissions-ui.png)

   1. Selecione **[!UICONTROL Visualizações de Dados]** e habilite **[!UICONTROL Inclusão automática: Em]**. Essa alternância garante que todas as visualizações de dados façam parte automaticamente dos **[!UICONTROL itens de permissão incluídos]**.
   1. Selecione **[!UICONTROL Ferramentas de relatório]** e verifique se todas as permissões listadas acima fazem parte dos **[!UICONTROL itens de permissão incluídos]**.
   1. Selecione **[!UICONTROL Ferramentas de Visualização de Dados]** e verifique se todas as permissões listadas acima fazem parte dos **[!UICONTROL itens de permissão incluídos]**.

   Selecione **[!UICONTROL Salvar]**.


## Configurar esquema e conjunto de dados

Para coletar dados do seu site, sujeito aos insights do Content Analytics, primeiro é necessário definir que tipo de dados deseja coletar. E também como esses dados são armazenados. Ambos os conceitos são explicados em [Configurar um esquema e um conjunto de dados](/help/data-ingestion/aepwebsdk.md#set-up-a-schema-and-dataset) no [Guia de início rápido do Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


## Configurar um fluxo de dados

Você definiu quais dados coletar e como armazená-los. A próxima etapa é garantir que os dados coletados do seu site sejam roteados para o conjunto de dados. Você precisa configurar uma sequência de dados, o que é explicado em [Configurar uma sequência de dados](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream) no [Guia de início rápido do Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


## Usar tags

Você definiu quais dados coletar (esquema), como armazenar esses dados (conjunto de dados) e como os dados coletados do seu site são roteados para o conjunto de dados (fluxo de dados). Como próxima etapa, é necessário marcar o site para configurar regras e elementos de dados em relação aos dados na camada de dados do site. Marcar seu site garante que os dados sejam enviados para o fluxo de dados configurado. A marcação do seu site com a ajuda de Marcas é explicada em [Usar Marcas](/help/data-ingestion/aepwebsdk.md#use-tags) no [Guia de início rápido de Assimilar dados por meio do Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


## Implantar e validar

Agora você pode implantar o código na versão de desenvolvimento do seu site dentro da tag `<head>`. Quando implantado, seu site começa a coletar dados na Adobe Experience Platform. Esses dados são então sujeitos ao Content Analytics.

Valide sua implementação, corrija-a conforme necessário e, depois de correta, implante-a no ambiente de preparo e produção usando o recurso de fluxo de trabalho de publicação de tags


## Configure uma conexão com seu conjunto de dados.

Para criar relatórios sobre os dados coletados e configurá-los para o Content Analytics, é necessário configurar uma conexão no Customer Journey Analytics. A conexão se conecta ao conjunto de dados que contém os dados coletados. Como configurar uma conexão é explicado em [Configurar uma conexão](../../data-ingestion/aepwebsdk.md#set-up-a-connection) no [Guia de início rápido do Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


## Configurar uma visualização de dados

A etapa final antes de configurar o Content Analytics é definir uma visualização de dados. Uma visualização de dados é um container específico do Customer Journey Analytics que permite determinar como interpretar dados de uma conexão. Uma visualização de dados permite definir métricas e dimensões com base nos dados de um ou mais conjuntos de dados aos quais o Customer Journey Analytics está conectado. Como configurar uma visualização de dados é explicado em [Configurar uma visualização de dados](/help/data-ingestion/aepwebsdk.md#set-up-a-data-view) no [Guia de início rápido do Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md).


## Configure o Content Analytics

Agora você tem tudo em vigor para configurar o Content Analytics.

### Configuração guiada

Use o [assistente de configuração guiada](guided.md) e selecione a exibição de dados criada como parte da etapa [Configurar uma exibição de dados](#set-up-a-data-view). Essa seleção garante que o Content Analytics seja configurado e implementado com base nos dados coletados do seu site.

Esteja ciente de que o assistente de configuração guiado configura os seguintes objetos específicos adicionais do Content Analytics:

* **Conjunto de dados**, que é configurado automaticamente para eventos do Content Analytics. Esse conjunto de dados usa um esquema Content Analytics específico que já foi criado e está disponível.
* **Datastream**, que é configurado automaticamente para transmitir eventos do Content Analytics para o conjunto de dados do Content Analytics.
* **Propriedade de marcas**, que é configurada automaticamente e configurada com a extensão do Content Analytics. Essa propriedade Tags garante que seu site envie dados do Content Analytics para a sequência de dados da Content Analytics e o conjunto de dados da Content Analytics.

  >[!IMPORTANT]
  >
  >Selecione a opção para criar uma propriedade de Novas Marcas como parte da etapa [Coleção de dados](guided.md#new-configuration-1) do assistente.
  >



### Configuração manual

Para implementar o Content Analytics para o seu site, você precisa publicar a propriedade de Tags do Content Analytics [manualmente](manual.md).


## Configurar um projeto

Configure um projeto no Customer Journey Analytics para criar seus [relatórios e visualizações do Content Analytics](/help/content-analytics/report/report.md). Como alternativa, você pode usar um [modelo do Content Analytics](/help/content-analytics/report/report.md#template) para começar.






