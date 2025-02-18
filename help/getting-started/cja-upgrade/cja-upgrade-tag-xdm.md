---
title: Adicionar a lógica da coleção de dados XDM à tag
description: Saiba como adicionar a lógica da coleção de dados XDM à sua tag
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc6c7568-8bd2-4ee1-ab1b-9fa1f6138811
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '1697'
ht-degree: 35%

---

# Adicionar a lógica da coleção de dados XDM à tag {#upgrade-tag-xdm}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-xdm"
>title="Adicionar a lógica da coleção de dados XDM à tag"
>abstract="Com a tag de carregamento instalada no site, é possível adicionar regras e elementos de dados para preencher um objeto XDM que será enviado para a Adobe. A Adobe recomenda manter um documento de design da solução para monitorar como as tags são configuradas.<br><br>Esta etapa exige muito trabalho, pois é necessário configurar toda a lógica de análise para sua propriedade. Estabelecer as regras de tags corretas, testá-las e implantá-las no site pode levar um mês ou mais."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

Depois de [criar a marca e adicionar a extensão Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), você deve configurá-la com elementos de dados e regras, de acordo com a maneira como deseja rastrear o site e enviar dados para a Adobe Experience Platform. Depois de configurar elementos de dados e regras para a tag, você pode criá-la e publicá-la.

## Configurar elementos de dados

Os elementos de dados são os blocos fundamentais do seu dicionário de dados (ou mapa de dados). Use elementos de dados para coletar, organizar e entregar dados em toda a tecnologia de marketing e anúncios. Você configura elementos de dados na tag que leem a partir da camada de dados e podem ser usados para fornecer dados à Adobe Experience Platform. (Para obter mais informações sobre elementos de dados, consulte [Elementos de dados](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/data-elements) na Documentação de tags.)

As seções a seguir descrevem elementos de dados sugeridos e outros elementos de dados comuns que você pode configurar.

Há vários tipos de elementos de dados. Dois elementos de dados comuns que você pode querer configurar são: um que captura o nome da página que as pessoas estão visualizando no site e outro que captura a Experience Cloud ID de cada pessoa que visita o site.

Após configurar esses dois elementos de dados, você pode configurar elementos de dados adicionais para os dados específicos que deseja capturar.

Finalmente, após definir todos os elementos de dados desejados, é necessário atribuir os elementos de dados ao [esquema criado](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) anteriormente. Para fazer isso, defina um elemento de dados XDM, que fornece uma representação do esquema XDM.

<!-- Assigning data elements to an XDM object. All of the available XDM objects are based on the schema -->

### Criar elementos de dados sugeridos

As seções a seguir descrevem como criar elementos de dados comuns que se aplicam à maioria das organizações.

#### Elemento de dados do nome da página

Um elemento de dados comum que se aplica à maioria das organizações é um elemento de dados que captura o nome da página que as pessoas estão visualizando.

Para criar um elemento de dados de nome de página:

1. Faça logon em experience.adobe.com usando suas credenciais da Adobe ID.

1. No Adobe Experience Platform, vá para **[!UICONTROL Coleção de Dados]** > **[!UICONTROL Marcas]**.

1. Na página **[!UICONTROL Propriedades da Marca]**, selecione a marca recém-criada na lista de propriedades para abri-la.

1. Selecione **[!UICONTROL Elementos de dados]** no painel esquerdo.

1. Selecione **[!UICONTROL Adicionar elemento de dados]**.

1. Na caixa de diálogo **[!UICONTROL Criar Elemento de Dados]**, especifique as seguintes informações:

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

#### Elemento de dados ECID

Um elemento de dados comum que se aplica à maioria das organizações é um elemento de dados que captura a Experience Cloud ID de cada pessoa que visita seu site.

Para criar um elemento de dados ECID:

1. Faça logon em experience.adobe.com usando suas credenciais da Adobe ID.

1. No Adobe Experience Platform, vá para **[!UICONTROL Coleção de Dados]** > **[!UICONTROL Marcas]**.

1. Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.

1. (Condicional) Instale a extensão do Serviço da Experience Cloud ID se ela ainda não estiver instalada:

   1. Selecione **[!UICONTROL Extensões]** no painel esquerdo.

   1. A guia **[!UICONTROL Instalado]** é selecionada por padrão. Se o bloco **[!UICONTROL Serviço da Experience Cloud ID]** estiver listado, pule para a Etapa 5.

   1. Se o bloco **[!UICONTROL Serviço da Experience Cloud ID]** não estiver listado, selecione a guia **[!UICONTROL Catálogo]**.

   1. No campo de pesquisa, pesquise por **[!UICONTROL Serviço da Experience Cloud ID]** e selecione o bloco quando ele aparecer

   1. Selecione **[!UICONTROL Instalar]** > **[!UICONTROL Salvar]**.

1. Selecione **[!UICONTROL Elementos de dados]** no painel esquerdo.

1. Selecione **[!UICONTROL Adicionar elemento de dados]**.

1. Na caixa de diálogo **[!UICONTROL Criar Elemento de Dados]**, especifique as seguintes informações:

   * **[!UICONTROL Nome]**: o nome do seu elemento de dados. Por exemplo, `ECID`.

   * **[!UICONTROL Extensão]**: selecione **[!UICONTROL Serviço da Experience Cloud ID]** na lista.

   * **[!UICONTROL Tipo de Elemento de Dados]**: Selecione **[!UICONTROL ECID]** na lista.

     ![Elemento de dados da ECID](assets/ecid-dataelement.png)

1. Selecione **[!UICONTROL Salvar]**.

1. Continue com [Criar elementos de dados adicionais](#create-additional-data-elements).

### Criar elementos de dados adicionais

Crie um elemento de dados para cada tipo de dados que deseja coletar. Use o mesmo processo descrito no [Elemento de dados de nome da página](#page-name-data-element) e no [Elemento de dados ECID](#ecid-data-element) para criar cada elemento de dados adicional.

Os elementos de dados criados devem ter um campo de correlação no esquema.

Os elementos de dados comuns variam de acordo com os requisitos do setor e da empresa. Considere os seguintes elementos de dados comuns, organizados por setor:

**Elementos de dados de varejo**

* Produtos

* Adições ao carrinho

* Check-outs

**Elementos de dados financeiros**

* ID da transação

* Data da transação

* Tipo de serviço

**Elementos de dados da área de saúde**

* ID do provedor

* Data da visita

* Tipo de tratamento

Depois de criar todos os elementos de dados necessários à sua organização para a implementação, continue com o [elemento de dados do objeto XDM](#xdm-object-data-element).

### Elemento de dados do objeto XDM

Finalmente, agora você deseja mapear qualquer elemento de dados criado para o [esquema criado](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) anteriormente. Para fazer isso, defina um elemento de dados de objeto XDM que forneça uma representação do esquema XDM.

Para definir um elemento de dados de objeto XDM:

1. Faça logon em experience.adobe.com usando suas credenciais da Adobe ID.

1. No Adobe Experience Platform, vá para **[!UICONTROL Coleção de Dados]** > **[!UICONTROL Marcas]**.

1. Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.

1. Selecione **[!UICONTROL Elementos de dados]** no painel esquerdo.

1. Selecione **[!UICONTROL Adicionar elemento de dados]**.

1. Na caixa de diálogo **[!UICONTROL Criar Elemento de Dados]**, especifique as seguintes informações:

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

1. Selecione **[!UICONTROL Adicionar Regra]**.

1. Na caixa de diálogo **[!UICONTROL Criar Regra]**, especifique as seguintes informações:

   * **[!UICONTROL Nome]**: o nome da regra. Por exemplo, `Page View`.

   * **[!UICONTROL Eventos]**: Selecione **[!UICONTROL + Adicionar]**. Em seguida, na caixa de diálogo **[!UICONTROL Configuração de evento]**, especifique as informações a seguir. Quando terminar, selecione **[!UICONTROL Manter alterações]**.

      * **[!UICONTROL Extensão]**: selecione **[!UICONTROL Núcleo]** na lista.

      * **[!UICONTROL Tipo de Evento]**: Selecione **[!UICONTROL Janela Carregada]** na lista.

        ![Regra - Configuração de evento](assets/event-windowloaded-pageview.png)

   * **[!UICONTROL Ações]**: Selecione **[!UICONTROL + Adicionar]**. Em seguida, na caixa de diálogo [!UICONTROL Configuração da ação], especifique as informações a seguir. Quando terminar, selecione **[!UICONTROL Manter alterações]**.

      * **[!UICONTROL Extensão]**: selecione **[!UICONTROL Adobe Experience Platform Web SDK]** na lista.

      * **[!UICONTROL Tipo de ação]**: selecionar **[!UICONTROL Enviar evento]** da lista.

      * **[!UICONTROL Tipo]**: selecione **[!UICONTROL Exibições de Página de Detalhes da Página da Web]** na lista.

      * **[!UICONTROL Dados XDM]**: selecione o ícone do cilindro e selecione **[!UICONTROL XDM - Exibição de página]** na lista de elementos de dados.

        ![Regra - Configuração de ação](assets/action-pageview-xdm.png)

        Sua regra deve ter a seguinte aparência:

        ![Criar regra](assets/rule-pageview.png)

1. Selecione **[!UICONTROL Salvar]**.

1. Repita esse processo para cada regra que você deseja adicionar ao site.

   Para obter mais informações sobre regras, consulte [Regras](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/rules) na Documentação de marcas.

1. Continue com [Crie e publique sua marca](#build-and-publish-your-tag).

## Criar e publicar sua tag

Depois de definir elementos de dados e regras, você deve criar e publicar sua tag. Ao criar um build de biblioteca, você deve atribuí-lo a um ambiente. As extensões, regras e elementos de dados da build são compilados e colocados no ambiente atribuído. Cada ambiente fornece um código integrado exclusivo que permite integrar a build atribuída ao site.

As tags do Adobe Experience Platform são compatíveis com fluxos de trabalho de publicação simples a complexos que devem acomodar a implantação do Adobe Experience Platform Web SDK. Consulte [Visão geral de publicação](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=pt-BR) para obter mais informações.

Para criar e publicar a tag:

1. Faça logon em experience.adobe.com usando suas credenciais da Adobe ID.

1. No Adobe Experience Platform, vá para **[!UICONTROL Coleção de Dados]** > **[!UICONTROL Marcas]**.

1. Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.

1. Selecione **[!UICONTROL Fluxo de publicação]** no painel esquerdo.

1. Selecione **[!UICONTROL Adicionar Biblioteca]**.

1. Na caixa de diálogo **[!UICONTROL Criar Biblioteca]**, especifique as seguintes informações:

   * **[!UICONTROL Nome]**: o nome da biblioteca.

   * **[!UICONTROL Ambiente]**: selecione **[!UICONTROL Desenvolvimento (desenvolvimento)]** na lista.

1. Clique em **[!UICONTROL + Adicionar todos os recursos alterados]**.

   ![Publicar - Criar biblioteca](assets/create-library-aep.png)

1. Selecione **[!UICONTROL Salvar e criar no desenvolvimento]**.

   Sua tag é salva e é criada para o ambiente de desenvolvimento. Um ponto verde indica uma criação bem-sucedida da tag no ambiente de desenvolvimento.

1. Você pode selecionar **[!UICONTROL ...]** para recriar a biblioteca ou mover a biblioteca para um ambiente de preparo ou produção.

   ![Publicar - Criar biblioteca](assets/build-library.png)
