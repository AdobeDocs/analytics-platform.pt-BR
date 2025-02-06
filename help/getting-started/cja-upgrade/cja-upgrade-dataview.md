---
title: Criar uma visualização de dados no Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 20%

---

# Criar uma visualização de dados no Customer Journey Analytics {#upgrade-create-dataview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataview"
>title="Criar uma visualização de dados no Customer Journey Analytics"
>abstract="Uma visualização de dados é um container específico do Customer Journey Analytics que permite determinar como interpretar dados de uma conexão.<br><br>Enquanto a criação inicial da visualização de dados leva alguns minutos, a configuração de cada dimensão e métrica com as configurações de componente desejadas pode levar vários dias. Ajustar essas configurações se aplica retroativamente, para que sua organização possa refiná-las ao longo do tempo."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

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

1. Na guia [!UICONTROL **Componentes**], arraste os elementos do esquema do painel esquerdo para a seção [!UICONTROL **Métricas**] ou para a seção [!UICONTROL **Dimension**]. Os elementos do esquema adicionados se tornam métricas ou dimensões na visualização de dados.

   Para obter informações detalhadas sobre as opções disponíveis ao adicionar componentes a uma visualização de dados, consulte [Componentes](/help/data-views/create-dataview.md#components) em [Criar ou editar uma visualização de dados](/help/data-views/create-dataview.md).

1. Selecione a guia [!UICONTROL **Configurações**]. Aqui, você pode configurar filtros para aplicar a toda a sua visualização de dados e configurar o tempo limite da sessão e as métricas.

   Para obter informações detalhadas sobre as opções disponíveis ao definir configurações para uma visualização de dados, consulte [Configurações](/help/data-views/create-dataview.md#settings) em [Criar ou editar uma visualização de dados](/help/data-views/create-dataview.md).

1. Selecione **[!UICONTROL Salvar]** para salvar a configuração da sua visualização de dados.

1. Após especificar todas as configurações desejadas, selecione **[!UICONTROL Salvar e concluir]**.

1. Continue seguindo as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou as [etapas de atualização geradas dinamicamente](https://gigazelle.github.io/cja-ttv/).
