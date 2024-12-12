---
title: Adicionar a lógica da coleção de dados XDM à tag
description: Saiba como adicionar a lógica da coleção de dados XDM à sua tag
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc6c7568-8bd2-4ee1-ab1b-9fa1f6138811
source-git-commit: 9849d686e886426124842ce210b423ac6c74fb89
workflow-type: tm+mt
source-wordcount: '1224'
ht-degree: 49%

---

# Adicionar a lógica da coleção de dados XDM à tag

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

Depois de [criar a marca e adicionar a extensão Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), você deve configurá-la com elementos de dados e regras, de acordo com a maneira como deseja rastrear o site e enviar dados para a Adobe Experience Platform. Depois de configurar elementos de dados e regras para a tag, você pode criá-la e publicá-la.

## Configurar elementos de dados

Os elementos de dados são os blocos fundamentais do seu dicionário de dados (ou mapa de dados). Use elementos de dados para coletar, organizar e entregar dados em toda a tecnologia de marketing e anúncios. Você configura elementos de dados na tag que são lidos a partir da camada de dados e podem ser usados para fornecer dados à Adobe Experience Platform.

Há diferentes tipos de elementos de dados. Primeiro, configure um elemento de dados para capturar o nome da página que as pessoas estão visualizando no site. Em seguida, configure um elemento de dados que faça referência à ID do Experience Cloud. Por fim, defina um elemento de dados de objeto XDM.

### Elemento de dados do nome da página

Para definir um elemento de dados de nome de página:

1. Faça logon em experience.adobe.com usando suas credenciais da Adobe ID.

1. No Adobe Experience Platform, vá para **[!UICONTROL Coleção de Dados]** > **[!UICONTROL Marcas]**.

1. Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.

1. Selecione **[!UICONTROL Elementos de dados]** no painel esquerdo.

1. Selecione **[!UICONTROL Adicionar elemento de dados]**.

1. Na caixa de diálogo [!UICONTROL Criar Elemento de Dados], especifique as seguintes informações:

   * **[!UICONTROL Nome]**: o nome do seu elemento de dados. Por exemplo, `Page Name`.

   * **[!UICONTROL Extensão]**: selecione **[!UICONTROL Núcleo]** na lista.

   * **[!UICONTROL Tipo de Elemento de Dados]**: Selecione **[!UICONTROL Informações da Página]** na lista.

   * **[!UICONTROL Atributo]**: selecione **[!UICONTROL Título]** na lista.

     ![Criar elemento de data usando informações da página](assets/create-dataelement-1.png)

     Como alternativa, você pode usar o valor de uma variável da camada de dados, por exemplo `pageName` e o tipo de elemento de dados da [!UICONTROL Variável JavaScript] para definir o elemento de dados.

     ![Criar elemento de dados usando a variável Javascript](assets/create-dataelement-2.png)

1. Selecione **[!UICONTROL Salvar]**.

   Agora você deseja configurar um elemento de dados que faça referência à ID da Experience Cloud, fornecida automaticamente pelo SDK da Web da Adobe Experience Platform e disponível por meio da extensão do Serviço da Experience Cloud ID.

1. Continuar com [elemento de dados ECID](#ecid-data-element).

### Elemento de dados ECID

Para definir um elemento de dados da ECID:

1. Faça logon em experience.adobe.com usando suas credenciais da Adobe ID.

1. No Adobe Experience Platform, vá para **[!UICONTROL Coleção de Dados]** > **[!UICONTROL Marcas]**.

1. Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.

1. Selecione **[!UICONTROL Elementos de dados]** no painel esquerdo.

1. Selecione **[!UICONTROL Adicionar elemento de dados]**.

1. Na caixa de diálogo [!UICONTROL Criar Elemento de Dados], especifique as seguintes informações:

   * **[!UICONTROL Nome]**: o nome do seu elemento de dados. Por exemplo, `ECID`.

   * **[!UICONTROL Extensão]**: selecione **[!UICONTROL Serviço de ID de Experience Cloud]** na lista.

   * **[!UICONTROL Tipo de Elemento de Dados]**: Selecione **[!UICONTROL ECID]** na lista.

     ![Elemento de dados da ECID](assets/ecid-dataelement.png)

1. Selecione **[!UICONTROL Salvar]**.

1. Continuar com [elemento de dados do objeto XDM](#xdm-object-data-element).

### Elemento de dados do objeto XDM

Por fim, agora é possível mapear qualquer um dos elementos de dados específicos para o esquema definido anteriormente. Você define outro elemento de dados que fornece uma representação do esquema XDM.

Para definir um elemento de dados de objeto XDM:

1. Faça logon em experience.adobe.com usando suas credenciais da Adobe ID.

1. No Adobe Experience Platform, vá para **[!UICONTROL Coleção de Dados]** > **[!UICONTROL Marcas]**.

1. Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.

1. Selecione **[!UICONTROL Elementos de dados]** no painel esquerdo.

1. Selecione **[!UICONTROL Adicionar elemento de dados]**.

1. Na caixa de diálogo [!UICONTROL Criar Elemento de Dados], especifique as seguintes informações:

   * **[!UICONTROL Nome]**: o nome do seu elemento de dados. Por exemplo, `XDM - Page View`.

   * **[!UICONTROL Extensão]**: selecione **[!UICONTROL Adobe Experience Platform Web SDK]** na lista.

   * **[!UICONTROL Tipo de Elemento de Dados]**: Selecione **[!UICONTROL Objeto XDM]** na lista.

   * **[!UICONTROL Sandbox]**: selecione sua sandbox na lista.

   * **[!UICONTROL Esquema]**: selecione seu esquema na lista.

1. Mapeie o atributo `identification > core > ecid`, definido no esquema, no elemento de dados da ECID. Selecione o ícone de cilindro para escolher facilmente o elemento de dados da ECID na lista de elementos de dados.

   ![Selecionar elemento de dados da ECID](assets/pick-ecid-dataelement.png)

   ![Mapear elemento de dados da ECID](assets/map-ecid.png)


1. Mapeie o atributo `web > webPageDetails > name`, definido no esquema, para o elemento de dados Nome da página.

   ![Mapear elemento de dados do nome da página](assets/map-pagename.png)

1. Selecione **[!UICONTROL Salvar]**.

1. Continuar com [Configurar regras](#configure-rules).

## **Configurar regras**

As tags na Adobe Experience Platform seguem um sistema baseado em regras. Elas buscam a interação do usuário e dados associados. Quando os critérios definidos nas regras são cumpridos, a regra aciona a extensão, o script ou o código do lado do cliente identificado. Você pode usar regras para enviar dados (como um objeto XDM) para a Adobe Experience Platform usando a extensão do SDK da Web da Adobe Experience Platform.

Para definir uma regra:

>[!NOTE]
>
>As etapas a seguir são um exemplo de definição de uma regra que envia dados XDM, contendo valores de outros elementos de dados, para o Adobe Experience Platform.
>
>Você pode usar as regras de várias maneiras na tag para manipular variáveis (usando os elementos de dados).
>
>Consulte [Regras de](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=pt-BR) para obter mais informações.

1. Faça logon em experience.adobe.com usando suas credenciais da Adobe ID.

1. No Adobe Experience Platform, vá para **[!UICONTROL Coleção de Dados]** > **[!UICONTROL Marcas]**.

1. Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.

1. Selecione **[!UICONTROL Regras]** no painel esquerdo.

1. Selecione **[!UICONTROL Criar nova regra]**.

1. Na caixa de diálogo [!UICONTROL Criar Regra], especifique as seguintes informações:

   * **[!UICONTROL Nome]**: o nome da regra. Por exemplo, `Page View`.

   * **[!UICONTROL Eventos]**: Selecione **[!UICONTROL + Adicionar]**. Em seguida, na caixa de diálogo [!UICONTROL Configuração de evento], especifique as informações a seguir. Quando terminar, selecione **[!UICONTROL Manter alterações]**.

      * **[!UICONTROL Extensão]**: selecione **[!UICONTROL Núcleo]** na lista.

      * **[!UICONTROL Tipo de Evento]**: Selecione **[!UICONTROL Janela Carregada]** na lista.

        ![Regra - Configuração de evento](assets/event-windowloaded-pageview.png)

   * **[!UICONTROL Ações]**: Selecione **[!UICONTROL + Adicionar]**. Em seguida, na caixa de diálogo [!UICONTROL Configuração da ação], especifique as informações a seguir. Quando terminar, selecione **[!UICONTROL Manter alterações]**.

      * **[!UICONTROL Extensão]**: selecione **[!UICONTROL Adobe Experience Platform Web SDK]** na lista.

      * **[!UICONTROL Tipo de ação]**: selecionar **[!UICONTROL Enviar Evento]** da lista.

      * **[!UICONTROL Tipo]**: selecione **[!UICONTROL web.webpagedetails.pageViews]** da lista.

      * **[!UICONTROL Dados XDM]**: selecione o ícone do cilindro e selecione **[!UICONTROL XDM - Exibição de página]** na lista de elementos de dados.

        ![Regra - Configuração de ação](assets/action-pageview-xdm.png)

        Sua regra deve ter a seguinte aparência:

        ![Criar regra](assets/rule-pageview.png)

1. Selecione **[!UICONTROL Salvar]**.

## Criar e publicar sua tag

Depois de definir elementos de dados e regras, você deve criar e publicar sua tag. Ao criar um build de biblioteca, você deve atribuí-lo a um ambiente. As extensões, regras e elementos de dados da build são compilados e colocados no ambiente atribuído. Cada ambiente fornece um código integrado exclusivo que permite integrar a build atribuída ao site.

As tags do Adobe Experience Platform são compatíveis com fluxos de trabalho de publicação simples a complexos que devem acomodar a implantação do Adobe Experience Platform Web SDK. Consulte [Visão geral de publicação](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=pt-BR) para obter mais informações.

Para criar e publicar a tag:

1. Faça logon em experience.adobe.com usando suas credenciais da Adobe ID.

1. No Adobe Experience Platform, vá para **[!UICONTROL Coleção de Dados]** > **[!UICONTROL Marcas]**.

1. Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.

1. Selecione **[!UICONTROL Fluxo de publicação]** no painel esquerdo.

1. Selecione **[!UICONTROL Selecionar uma biblioteca de trabalho]**, seguida de **[!UICONTROL Adicionar biblioteca...]**.

1. Na caixa de diálogo [!UICONTROL Criar Biblioteca], especifique as seguintes informações:

   * **[!UICONTROL Nome]**: o nome da biblioteca.

   * **[!UICONTROL Ambiente]**: selecione **[!UICONTROL Desenvolvimento (desenvolvimento)]** na lista.

1. Clique em **[!UICONTROL + Adicionar todos os recursos alterados]**.

   ![Publicar - Criar biblioteca](assets/create-library-aep.png)

1. Selecione **[!UICONTROL Salvar e criar no desenvolvimento]**.

   Sua tag é salva e é criada para o ambiente de desenvolvimento. Um ponto verde indica uma criação bem-sucedida da tag no ambiente de desenvolvimento.

1. Você pode selecionar **[!UICONTROL ...]** para recriar a biblioteca ou mover a biblioteca para um ambiente de preparo ou produção.

   ![Publicar - Criar biblioteca](assets/build-library.png)
