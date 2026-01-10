---
title: Criar um esquema personalizado no Customer Journey Analytics
description: Saiba como criar um esquema personalizado para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 902e5890-f970-4f1a-b091-9c3e51a987db
source-git-commit: 3dc53d6955eab3048ebf8a7c9d232b4b5739c6bd
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 100%

---

# Criar um esquema personalizado para usar com o Customer Journey Analytics {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create"
>title="Criar o esquema personalizado desejado na Adobe Experience Platform"
>abstract="Use a interface da Adobe Experience Platform para criar um esquema que permita que a Adobe saiba o formato correto para armazenar seus dados.<br><br>Esta etapa envolve a criação real do esquema aceito pela sua organização. O tempo estimado para criar seu esquema na interface da Adobe Experience Platform é de aproximadamente uma semana, dependendo do número de dimensões e métricas que precisam ser criadas."

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create-default-aa"
>title="Criar um esquema usando o grupo de campos ExperienceEvent do Adobe Analytics"
>abstract="Use o grupo de campos “ExperienceEvent do Adobe Analytics” para criar um esquema na Adobe Experience Platform que contenha todos os campos usados pelo Adobe Analytics.<br><br>Criar um esquema com base no grupo de campos ExperienceEvent do Adobe Analytics é simples e leva apenas alguns minutos."

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-profile"
>title="Habilitar o esquema do perfil"
>abstract="Habilite o perfil no esquema para uso na Adobe Real-time CDP.  Essa etapa aparece porque você selecionou a opção de integração com a Adobe Real-time CDP.<br><br>Como esta etapa envolve clicar em uma única caixa, ela leva apenas alguns minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

>[!IMPORTANT]
>
>Antes de começar a criar o esquema personalizado, trabalhe com sua equipe de dados e outras partes interessadas em sua organização para identificar o design de esquema ideal do Customer Journey Analytics e de outros aplicativos da Adobe Experience Platform que você usa. Para obter mais informações, consulte [Projete seu esquema para uso com o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

As seções a seguir descrevem como criar um esquema que pode ser usado com o Customer Journey Analytics. As seguintes opções de esquema estão disponíveis:

* **Esquema XDM personalizado:** (recomendado) possibilita um esquema simplificado e adaptado às necessidades da organização e aos aplicativos específicos da Platform que você usa. As alterações necessárias no futuro são simplificadas.

* **O esquema do Adobe Analytics que usa o grupo de campos ExperienceEvent do Adobe Analytics:** requer a adição de milhares de campos desnecessários. As alterações necessárias no futuro são mais difíceis.

Para obter mais informações sobre essas opções de esquema, consulte [Escolha o esquema para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

## Criar o esquema

O esquema personalizado definido para a implementação do SDK da web representa o modelo dos dados coletados na Adobe Experience Platform.

Para criar um esquema personalizado:

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. Na Adobe Experience Platform, no painel esquerdo, selecione **[!UICONTROL Esquemas]** em [!UICONTROL GERENCIAMENTO DE DADOS].

1. Selecione **[!UICONTROL Criar esquema]**. 

1. Na etapa **[!UICONTROL Selecionar uma classe]** do assistente Criar esquema:

   1. Selecione **[!UICONTROL Evento de experiência]**.

      ![Criar um esquema destacando o evento de experiência](assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Um esquema de evento de experiência é usado para modelar o _comportamento_ de um perfil (como nome do cenário, pressione o botão para adicionar ao carrinho). Um esquema de Perfil individual é usado para modelar os _atributos_ de perfil (como nome, email, gênero).

   1. Selecione **[!UICONTROL Próximo]**.


1. No [!UICONTROL Nome e etapa de revisão] do assistente [!UICONTROL Criar esquema]:

   1. Insira um **[!UICONTROL nome de exibição]** para o esquema e uma **[!UICONTROL descrição]** (opcional).

      ![Janela Criar esquema mostrando os campos Nomear seu esquema](assets/create-ee-schema-wizard-step-2.png)

   1. Selecione **[!UICONTROL Concluir]**.

1. Adicione todos os grupos de campos que contêm quaisquer campos que você deseja incluir no esquema.

   Grupos de campos são coleções reutilizáveis de objetos e atributos que permitem estender facilmente o esquema.

   1. Na seção **[!UICONTROL Grupos de campos]**, selecione **[!UICONTROL + Adicionar]**.

      ![Adicione um grupo de campos](assets/add-field-group-button.png)

   1. Na caixa de diálogo [!UICONTROL Adicionar grupos de campos], selecione o grupo de campos **[!UICONTROL SDK da Web ExperienceEvent da AEP]** na lista.

      ![Grupo de campos ExperienceEvent do SDK da Web da AEP](assets/select-aepwebsdk-experienceevent.png)

      É possível selecionar o botão de visualização para visualizar os campos que fazem parte desse grupo de campos, como `web > webPageDetails > name`.

      ![Visualização do campo de grupos ExperienceEvent do SDK da Web da AEP](assets/aepwebsdk-experiencevent-preview.png)

      Selecione **[!UICONTROL Voltar]** para fechar a visualização.

   1. (Opcional) Selecione qualquer grupo de campos adicional que deseja incluir.

      Se você optar por usar o esquema padrão do Adobe Analytics em vez de criar um esquema XDM personalizado, é possível adicionar o grupo de campos do ExperienceEvent do Adobe Analytics agora. No entanto, a Adobe recomenda criar um esquema XDM personalizado em vez de adicionar esse grupo de campos.

      Para obter mais informações sobre essas opções de esquema, consulte [Escolher esquema para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

   1. Selecione **[!UICONTROL Adicionar grupos de campos]**.

1. (Opcional) Se você tiver campos personalizados que deseja incluir no esquema, crie um grupo de campos personalizados e adicione-os ao grupo de campos.

   1. Na seção **[!UICONTROL Grupos de campos]**, selecione **[!UICONTROL + Adicionar]**.

      ![Adicione um grupo de campos](assets/add-field-group-button.png)

   1. Na caixa de diálogo [!UICONTROL Adicionar grupos de campos], selecione **[!UICONTROL Criar novo grupo de campos]**.

   1. Especifique um nome de exibição e uma descrição opcional e selecione **[!UICONTROL Adicionar grupos de campos]**.

1. Selecione **[!UICONTROL +]** ao lado do nome do esquema no painel [!UICONTROL Estrutura].

   ![Botão Adicionar campo de esquema de exemplo](assets/example-schema-plus.png)

1. No painel [!UICONTROL Propriedades do campo], digite `Identification` como nome, **[!UICONTROL Identificação]** como [!UICONTROL Nome de exibição], selecione **[!UICONTROL Objeto]** como [!UICONTROL Tipo] e selecione **[!UICONTROL ExperienceEvent Core v2.1]** como [!UICONTROL Grupo de campos].

   >[!NOTE]
   >
   >Se esse grupo de campos não estiver disponível, procure outro grupo de campos que contenha campos de identidade. Ou [crie um novo grupo de campos](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=pt-BR) e [adicione novos campos de identidade](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html?lang=pt-BR#define-a-identity-field) (como `ecid`, `crmId` e outros que você precise) ao grupo de campos e selecione esse novo grupo de campos.

   ![Objeto de identificação](assets/identification-field.png)

   O objeto de identificação adiciona recursos de identificação ao esquema. No seu caso, você deseja identificar os perfis que visitam seu site usando a Experience Cloud ID e o endereço de email. Há muitos outros atributos disponíveis para rastrear a identificação da pessoa (por exemplo, ID do cliente, ID de fidelidade).

   Selecione **[!UICONTROL Aplicar]** para adicionar esse objeto ao esquema.

1. Selecione o campo **[!UICONTROL ecid]** no objeto de identificação que você acabou de adicionar e selecione **[!UICONTROL Identidade]** e **[!UICONTROL Identidade principal]** e **[!UICONTROL ECID]** do [!UICONTROL Namespace de identidade] no painel direito.

   ![Especificar ECID como identidade](./assets/specify-identity.png)

   Você está especificando a Experience Cloud Identity como a identidade principal que o serviço Adobe Experience Platform Identity pode usar para combinar (compilar) o comportamento dos perfis com a mesma ECID.

   Selecione **[!UICONTROL Aplicar]**. Você verá um ícone de impressão digital no atributo ecid.

1. Selecione o **[!UICONTROL email]** no objeto de identificação que você acabou de adicionar e selecione **[!UICONTROL Identidade]** e **[!UICONTROL Email]** na lista [!UICONTROL Namespace de identidade] no painel [!UICONTROL Propriedades do campo].

   ![Especificar email como identidade](./assets/specify-email-identity.png)

   Você está especificando o endereço de email como outra identidade que o serviço Adobe Experience Platform Identity pode usar para combinar (compilar) o comportamento dos perfis.

   Selecione **[!UICONTROL Aplicar]**. Você vê que um ícone de impressão digital aparece no atributo de email.

   Selecione **[!UICONTROL Salvar]**.

1. (Opcional) Se quiser integrar o Customer Journey Analytics à RTCDP, selecione o elemento raiz do esquema que exibe o nome do esquema e selecione a opção **[!UICONTROL Perfil]**.

   Você deve habilitar o esquema para o perfil. Depois de habilitados, quando os dados são assimilados em conjuntos de dados com base nesse esquema, esses dados são mesclados ao Perfil do cliente em tempo real.

   Consulte [Habilitar o esquema para usar no Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=pt-BR#profile) para obter mais informações.

   >[!IMPORTANT]
   >
   >Após habilitar um esquema para perfil, ele não pode ser desabilitado para perfil.

   ![Habilitar esquema para perfil](./assets/enable-for-profile.png)

1. Selecione **[!UICONTROL Salvar]** para salvar o esquema.

   Você criou um esquema mínimo que modela os dados que pode capturar de seu site. O esquema permite que os perfis sejam identificados usando a Experience Cloud Identity e o endereço de email. Ao habilitar o esquema para o perfil, você garante que os dados capturados de seu site sejam adicionados ao Perfil do cliente em tempo real.

   Ao lado dos dados de comportamento, você também pode capturar os dados do atributo de perfil do site (por exemplo, detalhes de perfis que assinam um boletim informativo).

   Para capturar esses dados de perfil, você deve:

   * Criar um esquema com base na classe Perfil individual XDM.

   * Adicionar o grupo de campos Profile Core v2 ao esquema.

   * Adicionar um objeto de identificação com base no grupo de campos Profile Core v2.

   * Defina a Experience Cloud ID como identificador principal e o email como identificador.

   * Habilitar o esquema do perfil

   Consulte [Criar e editar esquemas na interface do usuário](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=pt-BR) para obter mais informações sobre a adição e remoção de grupos de campos e campos individuais a um esquema.

{{upgrade-final-step}}
