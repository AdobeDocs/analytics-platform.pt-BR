---
title: Criar um campo derivado de canal de marketing para o Customer Journey Analytics
description: Saiba como criar um campo derivado de canal de marketing para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 25%

---

# Criar um campo derivado de canal de marketing para o Customer Journey Analytics {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="Criar um campo derivado de canal de marketing"
>abstract="Campos derivados são criados em uma exibição de dados.<br><br>O uso de uma configuração de canal de marketing padrão leva apenas alguns minutos, mas criar uma configuração de canal de marketing altamente personalizada pode levar várias horas."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Ao usar o conector de origem do Analytics, os dados de canais de marketing fluem para o Customer Journey Analytics por meio desse conector. As regras do canal de marketing são configuradas no Adobe Analytics tradicional e algumas regras não são compatíveis. Para obter mais informações, consulte [Usar dimensões do canal de marketing](/help/use-cases/aa-data/marketing-channels.md).

Para usar canais de marketing no Customer Journey Analytics ao usar o Experience Platform Web SDK, você pode usar campos derivados em uma visualização de dados para recriar os mesmos canais de marketing e regras de processamento para o Customer Journey Analytics.

1. No Customer Journey Analytics, selecione a visualização de dados à qual deseja adicionar canais de marketing.

1. Na visualização de dados, selecione a guia **[!UICONTROL Componentes]**.

1. Selecione **[!UICONTROL Criar campo derivado]** no painel esquerdo.

1. Na caixa de diálogo **[!UICONTROL Criar campo derivado]**, selecione **[!UICONTROL Modelos de função]** no menu suspenso.

   ![Criar modelos de função de campo derivados](assets/derived-field-create.png)

1. Arraste o modelo **[!UICONTROL Canais de marketing]** para a tela em branco.

1. Personalize a lógica de cada canal de marketing para garantir que corresponda à lógica usada para identificar cada canal no ambiente do Adobe Analytics.

   Você pode modificar os nomes dos canais de saída ou adicionar lógica para identificar outros canais específicos da organização.

1. Na coluna à direita, especifique um nome e uma descrição para o canal de marketing.

1. Selecione **[!UICONTROL Salvar]**.

   O novo campo derivado é adicionado ao container Campos derivados > como parte dos Campos de esquema no painel esquerdo da visualização de dados.

{{upgrade-final-step}}
