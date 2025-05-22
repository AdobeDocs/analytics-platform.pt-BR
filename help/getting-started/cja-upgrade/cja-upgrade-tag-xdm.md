---
title: Adicionar lógica de coleção de dados XDM à tag
description: Saiba como adicionar a lógica de coleção de dados XDM à tag
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc6c7568-8bd2-4ee1-ab1b-9fa1f6138811
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '1631'
ht-degree: 100%

---

# Adicionar lógica de coleção de dados XDM à tag {#upgrade-tag-xdm}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-xdm"
>title="Adicionar lógica de coleção de dados XDM à tag"
>abstract="Com a tag de carregamento instalada no site, é possível adicionar regras e elementos de dados para preencher um objeto XDM que será enviado para a Adobe. A Adobe recomenda manter um documento de design da solução para monitorar como as tags são configuradas.<br><br>Esta etapa exige muito trabalho, pois é necessário configurar toda a lógica de análise para sua propriedade. Estabelecer as regras de tags corretas, testá-las e implantá-las no site pode levar um mês ou mais."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Depois de [criar a tag e adicionar a extensão do SDK da web](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), você deve configurá-la com elementos de dados e regras, de acordo com a forma como deseja rastrear seu site e enviar dados para a Adobe Experience Platform. Depois de configurar elementos de dados e regras para a tag, você pode criá-la e publicá-la.

## Configurar elementos de dados

Os elementos de dados são os blocos fundamentais do seu dicionário de dados (ou mapa de dados). Use elementos de dados para coletar, organizar e entregar dados em toda a tecnologia de marketing e anúncios. Você configura elementos de dados na tag que são lidos a partir da camada de dados e podem ser usados para fornecer dados à Adobe Experience Platform. (Para obter mais informações sobre elementos de dados, consulte [Elementos de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/ui/data-elements) na Documentação de tags.)

As seções a seguir descrevem elementos de dados sugeridos e outros elementos de dados comuns que você pode configurar.

Há diferentes tipos de elementos de dados. Dois elementos de dados comuns que você pode querer configurar são: um que captura o nome da página que as pessoas estão visualizando no seu site e outro que captura a ID da Experience Cloud de cada pessoa que visita seu site.

Depois de configurar esses dois elementos de dados, você pode configurar elementos de dados adicionais para os dados específicos que deseja capturar.

Por fim, depois de definir todos os elementos de dados desejados, você precisa atribuir os elementos de dados ao [esquema que você criou](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) anteriormente. Para fazer isso, defina um elemento de dados XDM, que fornece uma representação do seu esquema XDM.

<!-- Assigning data elements to an XDM object. All of the available XDM objects are based on the schema -->

### Criar elementos de dados sugeridos

As seções a seguir descrevem como criar elementos de dados comuns que se aplicam à maioria das organizações.

#### Elemento de dados do nome da página

Um elemento de dados comum que se aplica à maioria das organizações é um elemento de dados que captura o nome da página que as pessoas estão visualizando.

Para criar um elemento de dados de nome de página:

1. Faça logon em experiencecloud.adobe.com com as suas credenciais do Adobe ID.

1. No Adobe Experience Platform, acesse **[!UICONTROL Coleção de dados]** > **[!UICONTROL Tags]**.

1. Na página **[!UICONTROL Propriedades da tag]**, selecione a tag recém-criada na lista de propriedades para abri-la.

1. Selecione **[!UICONTROL Elementos de dados]** no painel esquerdo.

1. Selecione **[!UICONTROL Adicionar elemento de dados]**.

1. Na caixa de diálogo **[!UICONTROL Criar elemento de dados]**, especifique as seguintes informações:

   * **[!UICONTROL Nome]**: o nome do seu elemento de dados. Por exemplo, `Page Name`.

   * **[!UICONTROL Extensão]**: selecione **[!UICONTROL Núcleo]** na lista.

   * **[!UICONTROL Tipo de elemento de dados]**: selecione **[!UICONTROL Informações da página]** na lista.

   * **[!UICONTROL Atributo]**: selecione **[!UICONTROL Título]** na lista.

     ![Criar elemento de data usando informações da página](assets/create-dataelement-1.png)

     Como alternativa, você pode usar o valor de uma variável da camada de dados, por exemplo `pageName` e o tipo de elemento de dados da [!UICONTROL Variável JavaScript] para definir o elemento de dados.

     ![Criar elemento de dados usando a variável Javascript](assets/create-dataelement-2.png)

1. Selecione **[!UICONTROL Salvar]**.

   Agora você deseja configurar um elemento de dados que faça referência à ID da Experience Cloud, fornecida automaticamente pelo SDK da Web da Adobe Experience Platform e disponível por meio da extensão do Serviço da Experience Cloud ID.

1. Continue com [Elemento de dados da ECID](#ecid-data-element).

#### Elemento de dados da ECID

Um elemento de dados comum que se aplica à maioria das organizações é um elemento de dados que captura a ID da Experience Cloud de cada pessoa que visita seu site.

Para criar um elemento de dados da ECID:

1. Faça logon em experiencecloud.adobe.com com as suas credenciais do Adobe ID.

1. Na Adobe Experience Platform, acesse **[!UICONTROL Coleção de dados]** > **[!UICONTROL Tags]**.

1. Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.

1. (Condicional) Instale a extensão de ID de serviço da Experience Cloud se ela ainda não estiver instalada:

   1. Selecione **[!UICONTROL Extensões]** no painel esquerdo.

   1. A guia **[!UICONTROL Instalado]** é selecionada por padrão. Se o bloco **[!UICONTROL ID de serviço da Experience Cloud]** estiver listado, pule para a Etapa 5.

   1. Se o bloco **[!UICONTROL ID de serviço da Experience Cloud]** não estiver listado, selecione a guia **[!UICONTROL Catálogo]**.

   1. No campo de pesquisa, pesquise por **[!UICONTROL ID de serviço da Experience Cloud]** e selecione o bloco quando ele aparecer

   1. Selecione **[!UICONTROL Instalar]** > **[!UICONTROL Salvar]**.

1. Selecione **[!UICONTROL Elementos de dados]** no painel esquerdo.

1. Selecione **[!UICONTROL Adicionar elemento de dados]**.

1. Na caixa de diálogo **[!UICONTROL Criar elemento de dados]**, especifique as seguintes informações:

   * **[!UICONTROL Nome]**: o nome do seu elemento de dados. Por exemplo, `ECID`.

   * **[!UICONTROL Extensão]**: selecione **[!UICONTROL ID de serviço da Experience Cloud]** na lista.

   * **[!UICONTROL Tipo de elemento de dados]**: selecione **[!UICONTROL ECID]** na lista.

     ![Elemento de dados da ECID](assets/ecid-dataelement.png)

1. Selecione **[!UICONTROL Salvar]**.

1. Continue com [Criar elementos de dados adicionais](#create-additional-data-elements).

### Criar elementos de dados adicionais

Crie um elemento de dados para cada tipo de dados que deseja coletar. Use o mesmo processo descrito em [Elemento de dados do nome da página](#page-name-data-element) e [Elemento de dados da ECID](#ecid-data-element) para criar cada elemento de dados adicional.

Os elementos de dados que você cria devem ter um campo correlacionado no seu esquema.

Os elementos de dados comuns variam dependendo do setor e dos requisitos comerciais. Considere os seguintes elementos de dados comuns, organizados por setor:

**Elementos de dados de varejo**

* Produtos

* Adições ao carrinho

* Check-outs

**Elementos de dados financeiros**

* ID da transação

* Data da transação

* Tipo de serviço

**Elementos de dados de saúde**

* ID do provedor

* Data da visita

* Tipo de tratamento

Depois de criar todos os elementos de dados necessários para sua organização para a implementação, continue com [Elemento de dados do objeto XDM](#xdm-object-data-element).

### Elemento de dados do objeto XDM

Por fim, agora é possível mapear qualquer elemento de dados criado para o [esquema que você criou](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) anteriormente. Para fazer isso, defina um elemento de dados de objeto XDM que forneça uma representação do seu esquema XDM.

Para definir um elemento de dados de objeto XDM:

1. Faça logon em experiencecloud.adobe.com com as suas credenciais do Adobe ID.

1. Na Adobe Experience Platform, acesse **[!UICONTROL Coleção de dados]** > **[!UICONTROL Tags]**.

1. Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.

1. Selecione **[!UICONTROL Elementos de dados]** no painel esquerdo.

1. Selecione **[!UICONTROL Adicionar elemento de dados]**.

1. Na caixa de diálogo **[!UICONTROL Criar elemento de dados]**, especifique as seguintes informações:

   * **[!UICONTROL Nome]**: o nome do seu elemento de dados. Por exemplo, `XDM - Page View`.

   * **[!UICONTROL Extensão]**: selecione **[!UICONTROL SDK da web da Adobe Experience Platform]** na lista.

   * **[!UICONTROL Tipo de elemento de dados]**: selecione **[!UICONTROL Objeto XDM]** na lista.

   * **[!UICONTROL Sandbox]**: selecione a sandbox na lista.

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
>As etapas a seguir são um exemplo de definição de uma regra que envia dados XDM, contendo valores de outros elementos de dados, para a Adobe Experience Platform.
>
>Você pode usar as regras de várias maneiras na tag para manipular variáveis (usando os elementos de dados).
>
>Consulte [Regras de](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=pt-BR) para obter mais informações.

1. Faça logon em experiencecloud.adobe.com com as suas credenciais do Adobe ID.

1. Na Adobe Experience Platform, acesse **[!UICONTROL Coleção de dados]** > **[!UICONTROL Tags]**.

1. Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.

1. Selecione **[!UICONTROL Regras]** no painel esquerdo.

1. Selecione **[!UICONTROL Adicionar regra]**.

1. Na caixa de diálogo **[!UICONTROL Criar regra]**, especifique as seguintes informações:

   * **[!UICONTROL Nome]**: o nome da regra. Por exemplo, `Page View`.

   * **[!UICONTROL Eventos]**: selecione **[!UICONTROL + Adicionar]**. Em seguida, na caixa de diálogo **[!UICONTROL Configuração de evento]**, especifique as seguintes informações. Quando terminar, selecione **[!UICONTROL Manter alterações]**.

      * **[!UICONTROL Extensão]**: selecione **[!UICONTROL Núcleo]** na lista.

      * **[!UICONTROL Tipo de evento]**: selecione **[!UICONTROL Janela carregada]** na lista.

        ![Regra - Configuração de evento](assets/event-windowloaded-pageview.png)

   * **[!UICONTROL Ações]**: selecione **[!UICONTROL + Adicionar]**. Em seguida, na caixa de diálogo [!UICONTROL Configuração de ação], especifique as seguintes informações. Quando terminar, selecione **[!UICONTROL Manter alterações]**.

      * **[!UICONTROL Extensão]**: selecione **[!UICONTROL SDK da web da Adobe Experience Platform]** na lista.

      * **[!UICONTROL Tipo de ação]**: selecione **[!UICONTROL Enviar evento]** na lista.

      * **[!UICONTROL Tipo]**: selecione **[!UICONTROL Exibições de página da web]** na lista.

      * **[!UICONTROL Dados XDM]**: clique no ícone do cilindro e selecione **[!UICONTROL XDM: exibição de página]** na lista de elementos de dados.

        ![Regra - Configuração de ação](assets/action-pageview-xdm.png)

        Sua regra deve ter a seguinte aparência:

        ![Criar regra](assets/rule-pageview.png)

1. Selecione **[!UICONTROL Salvar]**.

1. Repita esse processo para cada regra que você deseja adicionar ao site.

   Para obter mais informações sobre regras, consulte [Regras](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/ui/rules) na Documentação de tags.

1. Continue com [Criar e publicar a tag](#build-and-publish-your-tag).

## Criar e publicar a tag

Após definir elementos de dados e regras, é necessário criar e publicar a tag. Ao criar um build de biblioteca, você deve atribuí-lo a um ambiente. As extensões, regras e elementos de dados da build são compilados e colocados no ambiente atribuído. Cada ambiente fornece um código incorporado exclusivo que permite integrar a build atribuída ao site.

As tags da Adobe Experience Platform oferecem suporte a fluxos de trabalho de publicação simples e complexos que devem se ajustar à implantação do SDK da web da Adobe Experience Platform. Consulte [Visão geral de publicação](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=pt-BR) para obter mais informações.

Para criar e publicar a tag:

1. Faça logon em experiencecloud.adobe.com com as suas credenciais do Adobe ID.

1. Na Adobe Experience Platform, acesse **[!UICONTROL Coleção de dados]** > **[!UICONTROL Tags]**.

1. Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.

1. Selecione **[!UICONTROL Fluxo de publicação]** no painel esquerdo.

1. Selecione **[!UICONTROL Adicionar biblioteca]**.

1. Na caixa de diálogo **[!UICONTROL Criar biblioteca]**, especifique as seguintes informações:

   * **[!UICONTROL Nome]**: o nome da biblioteca.

   * **[!UICONTROL Ambiente]**: selecione **[!UICONTROL Desenvolvimento (development)]** na lista.

1. Clique em **[!UICONTROL + Adicionar todos os recursos alterados]**.

   ![Publicar - Criar biblioteca](assets/create-library-aep.png)

1. Selecione **[!UICONTROL Salvar e criar no desenvolvimento]**.

   A tag é salva e é criada para o ambiente de desenvolvimento. Um ponto verde indica uma criação bem-sucedida da tag no ambiente de desenvolvimento.

1. Você pode selecionar **[!UICONTROL ...]** para recriar a biblioteca ou mover a biblioteca para um ambiente de preparo ou produção.

   ![Publicar - Criar biblioteca](assets/build-library.png)

{{upgrade-final-step}}

