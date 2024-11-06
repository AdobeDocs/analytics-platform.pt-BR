---
title: Usar tags para implementar o SDK da Web para Customer Journey Analytics
description: Saiba como usar tags para implementar o SDK da Web para Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '1320'
ht-degree: 76%

---

# Usar tags para implementar o SDK da Web para Customer Journey Analytics

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

Você pode usar o recurso Tags na Adobe Experience Platform para implementar o código em seu site para coletar dados. Esta solução de gerenciamento de tags permite implantar o código do junto com outros requisitos de marcação. As tags oferecem integração perfeita com a Adobe Experience Platform usando a extensão do SDK da Web da Adobe Experience Platform.

## Criar sua tag

1. Na interface do usuário da Adobe Experience Platform, no painel esquerdo, selecione **[!UICONTROL Tags]** em [!UICONTROL COLEÇÃO DE DADOS].

2. Selecione **[!UICONTROL Nova propriedade]**.

   Nomeie a tag, selecione **[!UICONTROL Web]** e insira um nome de domínio. Selecione **[!UICONTROL Salvar]** para continuar.

   ![Criar uma propriedade da ](assets/create-property.png)

## Configurar sua tag

Depois de criar a tag, você deve configurá-la com as extensões corretas e configurar os elementos de dados e as regras de acordo com como deseja rastrear seu site e enviar dados para a Adobe Experience Platform.

Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.


### **Extensões**

Para garantir que você possa enviar dados para a Adobe Experience Platform (por meio de sua sequência de dados), adicione a extensão SDK da Web da Plataforma Adobe à sua tag.

Para criar e configurar a extensão do SDK da Web da Adobe Experience Platform:

1. Selecione **[!UICONTROL Extensões]** no painel esquerdo.

1. Selecione **[!UICONTROL Catálogo]** na barra superior.

1. Procure ou role a tela até a extensão do SDK da Web da Adobe Experience Platform e selecione **[!UICONTROL Instalar]** para instalá-la.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Selecione a sandbox e a sequência de dados criadas anteriormente para o [!UICONTROL Ambiente de produção], o [!UICONTROL Ambiente de preparo] (opcional) e o [!UICONTROL Ambiente de desenvolvimento].

   ![Configuração da extensão do SDK da Web da AEP](assets/aepwebsk-extension-datastreams.png)

   Selecione **[!UICONTROL Salvar]**.

Consulte [Configurar a extensão do SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html) para obter mais informações.

O SDK da Web inclui o [!UICONTROL Serviço da Adobe Experience Cloud ID] nativamente, portanto, não é necessário adicionar a extensão do serviço de ID à sua marca.

### **Elementos de dados**

Os elementos de dados são os blocos fundamentais do seu dicionário de dados (ou mapa de dados). Use elementos de dados para coletar, organizar e entregar dados em toda a tecnologia de marketing e anúncios. Você configura elementos de dados na tag que são lidos a partir da camada de dados e podem ser usados para fornecer dados à Adobe Experience Platform.

Há diferentes tipos de elementos de dados. Primeiro, configure um elemento de dados para capturar o nome da página que as pessoas estão visualizando no site.

Para definir um elemento de dados de nome de página:

1. Selecione **[!UICONTROL Elementos de dados]** no painel esquerdo.

2. Selecione **[!UICONTROL Adicionar elemento de dados]**.

3. Na caixa de diálogo [!UICONTROL Criar elemento de dados]:

   - Nomeie seu elemento de dados, por exemplo `Page Name`.

   - Selecione **[!UICONTROL Núcleo]** na lista [!UICONTROL Extensão].

   - Selecione **[!UICONTROL Informações da página]** na lista [!UICONTROL Tipo de elemento de dados].

   - Selecione **[!UICONTROL Título]** na lista [!UICONTROL Atributo].

     ![Criar elemento de data usando informações da página](assets/create-dataelement-1.png)

     Como alternativa, você pode usar o valor de uma variável da camada de dados, por exemplo `pageName` e o tipo de elemento de dados da [!UICONTROL Variável JavaScript] para definir o elemento de dados.

     ![Criar elemento de dados usando a variável Javascript](assets/create-dataelement-2.png)

   - Selecione **[!UICONTROL Salvar]**.

Agora você deseja configurar um elemento de dados que faça referência à ID da Experience Cloud, fornecida automaticamente pelo SDK da Web da Adobe Experience Platform e disponível por meio da extensão do Serviço da Experience Cloud ID.

Para definir um elemento de dados da ECID:

1. Selecione **[!UICONTROL Elementos de dados]** no painel esquerdo.

2. Selecione **[!UICONTROL Adicionar elemento de dados]**.

3. Na caixa de diálogo [!UICONTROL Criar elemento de dados]:

   - Nomeie seu elemento de dados, por exemplo `ECID`.

   - Selecione **[!UICONTROL Serviço da Experience Cloud ID]** da lista [!UICONTROL Extensão].

   - Selecione **[!UICONTROL ECID]** na lista [!UICONTROL Tipo de elemento de dados].

     ![Elemento de dados da ECID](assets/ecid-dataelement.png)

   - Selecione **[!UICONTROL Salvar]**.

Por fim, agora é possível mapear qualquer um dos elementos de dados específicos para o esquema definido anteriormente. Você define outro elemento de dados que fornece uma representação do esquema XDM.

Para definir um elemento de dados de objeto XDM:

1. Selecione **[!UICONTROL Elementos de dados]** no painel esquerdo.

2. Selecione **[!UICONTROL Adicionar elemento de dados]**.

3. Na caixa de diálogo [!UICONTROL Criar elemento de dados]:

   - Nomeie seu elemento de dados, por exemplo `XDM - Page View`.

   - Selecione **[!UICONTROL SDK da Web da Adobe Experience Platform]** na lista [!UICONTROL Extensão].

   - Selecione **[!UICONTROL Objeto XDM]** na lista [!UICONTROL Tipo de elemento de dados].

   - Selecione a sandbox na lista [!UICONTROL Sandbox].

   - Selecione o esquema na lista [!UICONTROL Esquema].

   - Mapeie o atributo `identification > core > ecid`, definido no esquema, no elemento de dados da ECID. Selecione o ícone de cilindro para escolher facilmente o elemento de dados da ECID na lista de elementos de dados.

     ![Selecionar elemento de dados da ECID](assets/pick-ecid-dataelement.png)

     ![Mapear elemento de dados da ECID](assets/map-ecid.png)


   - Mapeie o atributo `web > webPageDetails > name`, definido no esquema, para o elemento de dados Nome da página.

     ![Mapear elemento de dados do nome da página](assets/map-pagename.png)

   - Selecione **[!UICONTROL Salvar]**.


### **Regras**

As tags na Adobe Experience Platform seguem um sistema baseado em regras. Elas buscam a interação do usuário e dados associados. Quando os critérios definidos nas regras são cumpridos, a regra aciona a extensão, o script ou o código do lado do cliente identificado. Você pode usar regras para enviar dados (como um objeto XDM) para a Adobe Experience Platform usando a extensão do SDK da Web da Adobe Experience Platform.

Para definir uma regra:

1. Selecione **[!UICONTROL Regras]** no painel esquerdo.

1. Selecione **[!UICONTROL Criar nova regra]**.

1. Na caixa de diálogo [!UICONTROL Criar regra]:

   - Nomeie a regra, por exemplo `Page View`.

   - Selecione **[!UICONTROL + Adicionar]** abaixo de [!UICONTROL Eventos].

   - Na caixa de diálogo [!UICONTROL Configuração de evento]:

      - Selecione **[!UICONTROL Núcleo]** na lista [!UICONTROL Extensão].

      - Selecione **[!UICONTROL Janela carregada]** na lista [!UICONTROL Tipo de evento].

        ![Regra - Configuração de evento](assets/event-windowloaded-pageview.png)

      - Selecione **[!UICONTROL Manter alterações]**.



   - Selecione **[!UICONTROL + Adicionar]** abaixo de [!UICONTROL Ações].

   - Na caixa de diálogo [!UICONTROL Configuração de ação]:

      - Selecione **[!UICONTROL SDK da Web da Adobe Experience Platform]** na lista [!UICONTROL Extensão].

      - Selecione **[!UICONTROL Enviar evento]** na lista [!UICONTROL Tipo de ação].

      - Selecione **[!UICONTROL web.webpagedetails.pageViews]** na lista [!UICONTROL Tipo].

      - Selecione o ícone do cilindro ao lado de [!UICONTROL Dados XDM] e Selecione **[!UICONTROL XDM - Exibição de página]** na lista de elementos de dados.

     ![Regra - Configuração de ação](assets/action-pageview-xdm.png)

      - Selecione **[!UICONTROL Manter alterações]**.

   - Sua regra deve ter a seguinte aparência:

     ![Criar regra](assets/rule-pageview.png)

1. Selecione **[!UICONTROL Salvar]**.

O exposto acima é apenas um exemplo de definição de uma regra que envia dados XDM, contendo valores de outros elementos de dados, para o Adobe Experience Platform.

Você pode usar as regras de várias maneiras na tag para manipular variáveis (usando os elementos de dados).

Consulte [Regras de](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=pt-BR) para obter mais informações.

## Criar e publicar a tag

Depois de definir elementos de dados e regras, você deve criar e publicar sua tag. Ao criar um build de biblioteca, você deve atribuí-lo a um ambiente. As extensões, regras e elementos de dados da build são compilados e colocados no ambiente atribuído. Cada ambiente fornece um código integrado exclusivo que permite integrar a build atribuída ao site.

Para criar e publicar a tag:

1. Selecione **[!UICONTROL Fluxo de publicação]** no painel esquerdo.

2. Selecione **[!UICONTROL Selecionar uma biblioteca de trabalho]**, seguida de **[!UICONTROL Adicionar biblioteca...]**.

3. Na caixa de diálogo [!UICONTROL Criar biblioteca]:

   - Dê um nome para a biblioteca.

   - Selecione **[!UICONTROL Desenvolvimento]** na lista suspensa [!UICONTROL Ambiente].

   - Clique em **[!UICONTROL + Adicionar todos os recursos alterados]**.

     ![Publicar - Criar biblioteca](assets/create-library-aep.png)

   - Selecione **[!UICONTROL Salvar e criar no desenvolvimento]**.

   A tag é salva e é criada para o ambiente de desenvolvimento. Um ponto verde indica uma criação bem-sucedida da tag no ambiente de desenvolvimento.

4. Você pode selecionar **[!UICONTROL ...]** para recriar a biblioteca ou mover a biblioteca para um ambiente de preparo ou produção.

   ![Publicar - Criar biblioteca](assets/build-library.png)

As tags da Adobe Experience Platform são compatíveis com fluxos de trabalho de publicação simples e complexos, que devem acomodar a implantação do SDK da Web da Adobe Experience Platform.

Consulte [Visão geral de publicação](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=pt-BR) para obter mais informações.


## Recuperar o código da tag

Por fim, você deve instalar sua tag no site que deseja rastrear, o que implica colocar o código na tag de cabeçalho do modelo do site.

Para obter o código que faz referência à sua tag:

1. Selecione **[!UICONTROL Ambientes]** no painel esquerdo.

1. Na lista de ambientes, selecione o botão de instalação correto (caixa).

   Na caixa de diálogo [!UICONTROL Instruções de instalação da Web] clique no botão copiar ao lado do código de script que deve ser lido como:

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![Ambiente](assets/environment.png)

1. Selecione **[!UICONTROL Fechar]**.

   Em vez do código para o ambiente de desenvolvimento, você pode ter selecionado outro ambiente (armazenamento temporário, produção) com base em onde você está no processo de implantação do SDK da Web da Adobe Experience Platform.

   Consulte [Ambientes](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=pt-BR) para obter mais informações.

1. Continue seguindo as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou as [etapas de atualização geradas dinamicamente](https://gigazelle.github.io/cja-ttv/).
