---
title: Criar uma visualização de dados no Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
TQID: https://experienceleague.adobe.com/rQL8R2D1JeIabt-iQSyYGY74N5JkP3hTN-x2kj-swXU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 402
ht-degree: 95%

---

# Criar uma visualização de dados no Customer Journey Analytics {#upgrade-create-dataview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataview"
>title="Criar uma visualização de dados no Customer Journey Analytics"
>abstract="Uma exibição de dados é um container específico do Customer Journey Analytics que permite determinar como interpretar dados de uma conexão.<br><br>Embora a criação inicial da exibição de dados leve apenas alguns minutos, configurar cada dimensão e métrica com as definições de componente desejadas pode levar vários dias. O ajuste dessas configurações é retroativo para que sua organização possa refiná-los ao longo do tempo."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

A criação de uma visualização de dados envolve criar métricas e dimensões com base em elementos de esquema ou utilizar componentes padrão. A maioria dos elementos do esquema pode ser uma dimensão ou uma métrica, dependendo dos requisitos da sua empresa. Depois de arrastar um elemento do esquema para uma visualização de dados, algumas opções serão exibidas à direita, onde você poderá ajustar como a dimensão ou métrica opera no Customer Journey Analytics.

Para criar uma visualização de dados:

1. Faça logon no [Customer Journey Analytics](https://analytics.adobe.com) e selecione **[!UICONTROL Visualizações de dados]** ou use a seção **[!UICONTROL Gerenciamento de dados]** no menu superior.

1. Selecione **[!UICONTROL Criar nova visualização de dados]**. Como alternativa, selecione uma visualização de dados existente na lista de visualizações de dados para editá-la.

1. Na guia [!UICONTROL **Configurar**], especifique um nome para a visualização de dados e defina suas configurações básicas, componentes e opções de calendário.

   Para obter informações detalhadas sobre cada campo, consulte [Configurar](/help/data-views/create-dataview.md#configure) em [Criar ou editar uma visualização de dados](/help/data-views/create-dataview.md).

   ![Configurar visualização de dados](assets/dataview-configure.png)

1. Selecione a guia [!UICONTROL **Componentes**].

   Na guia [!UICONTROL **Componentes**], é possível definir os componentes da visualização de dados,  o que significa que você pode criar métricas e dimensões com base em elementos do esquema. Você também pode usar os componentes padrão.

   ![Guia Componentes](assets/dataview-components.png)

1. Na guia [!UICONTROL **Componentes**], arraste os elementos do esquema do painel esquerdo para a seção [!UICONTROL **Métricas**] ou para a seção [!UICONTROL **Dimensões**]. Os elementos do esquema adicionados se tornam métricas ou dimensões na visualização de dados.

   Para obter informações detalhadas sobre as opções disponíveis ao adicionar componentes a uma visualização de dados, consulte [Componentes](/help/data-views/create-dataview.md#components) em [Criar ou editar uma visualização de dados](/help/data-views/create-dataview.md).

1. Selecione a guia [!UICONTROL **Configurações**]. Aqui, você pode configurar segmentos para aplicar a toda a sua visualização de dados e configurar o tempo limite da sessão e as métricas.

   Para obter informações detalhadas sobre as opções disponíveis ao definir configurações em uma visualização de dados, consulte [Configurações](/help/data-views/create-dataview.md#settings) em [Criar ou editar uma visualização de dados](/help/data-views/create-dataview.md).

1. Selecione **[!UICONTROL Salvar]** para salvar a configuração da visualização de dados existente.

1. Depois que todas as configurações desejadas forem especificadas, clique em **[!UICONTROL Salvar e concluir]**.

{{upgrade-final-step}}
