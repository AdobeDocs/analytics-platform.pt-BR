---
title: Criar uma exibição de dados no Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 45%

---

# Criar uma exibição de dados no Customer Journey Analytics {#upgrade-create-dataview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataview"
>title="Criar uma exibição de dados no Customer Journey Analytics"
>abstract="Uma exibição de dados é um container específico do Customer Journey Analytics que permite determinar como interpretar dados de uma conexão. <br><br>Embora a criação inicial da exibição de dados leve apenas alguns minutos, configurar cada dimensão e métrica com as definições de componente desejadas pode levar vários dias. O ajuste dessas configurações é retroativo para que sua organização possa refiná-los ao longo do tempo."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

A criação de uma visualização de dados envolve criar métricas e dimensões com base em elementos de esquema ou utilizar componentes padrão. A maioria dos elementos do esquema pode ser uma dimensão ou uma métrica, dependendo das necessidades da sua empresa. Depois de arrastar um elemento do esquema para uma visualização de dados, algumas opções serão exibidas à direita, onde você poderá ajustar como a dimensão ou métrica opera no Customer Journey Analytics.

Para criar uma visualização de dados:

1. Faça logon no [Customer Journey Analytics](https://analytics.adobe.com) e acesse a guia **[!UICONTROL Visualizações de dados]**.

1. Selecione **[!UICONTROL Criar nova visualização de dados]**. Como alternativa, selecione uma visualização de dados existente na lista de visualizações de dados para editá-la.

1. Na guia [!UICONTROL **Configurar**], especifique um nome para a visualização de dados e defina suas configurações básicas, componentes e opções de calendário.

   Para obter informações detalhadas sobre cada campo, consulte [Configurar](/help/data-views/create-dataview.md#configure) em [Criar ou editar uma visualização de dados](/help/data-views/create-dataview.md).

   ![Configurar visualização de dados](assets/dataview-configure.png)

1. Selecione a guia [!UICONTROL **Componentes**].

   A guia [!UICONTROL **Componentes**] é onde você define os componentes de uma visualização de dados, o que significa que é possível criar métricas e dimensões com base em elementos de esquema. Você também pode usar os componentes padrão.

   ![Guia Componentes](assets/dataview-components.png)

1. Na guia [!UICONTROL **Componentes**], arraste os elementos do esquema do painel esquerdo para a seção [!UICONTROL **Métricas**] ou para a seção [!UICONTROL **Dimensões**]. Os elementos do esquema adicionados se tornam métricas ou dimensões na visualização de dados.

   Para obter informações detalhadas sobre as opções disponíveis ao adicionar componentes a uma visualização de dados, consulte [Componentes](/help/data-views/create-dataview.md#components) em [Criar ou editar uma visualização de dados](/help/data-views/create-dataview.md).

1. Selecione a guia [!UICONTROL **Configurações**]. Aqui, você pode configurar filtros para aplicar a toda a sua visualização de dados e configurar o tempo limite da sessão e as métricas.

   Para obter informações detalhadas sobre as opções disponíveis ao definir configurações para uma visualização de dados, consulte [Configurações](/help/data-views/create-dataview.md#settings) em [Criar ou editar uma visualização de dados](/help/data-views/create-dataview.md).

1. Selecione **[!UICONTROL Salvar]** para salvar a configuração da sua visualização de dados.

1. Após especificar todas as configurações desejadas, selecione **[!UICONTROL Salvar e concluir]**.

{{upgrade-final-step}}
