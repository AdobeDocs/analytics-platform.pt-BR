---
title: Estimar e gerenciar o uso do CJA
description: Mostra dois métodos de estimativa de uso e um método de gerenciamento.
role: Admin
feature: CJA Basics
source-git-commit: 2bcf1f805a54581f13f7d08b9ef034535d7959b1
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 42%

---


# Estimar e gerenciar o uso do CJA

Para entender o uso do CJA, você pode usar dois métodos:

* Adicione as linhas de dados do evento para cada conexão. (Consulte **Estime o tamanho da conexão** abaixo)
* Use o Analysis Workspace para relatar os eventos do mês passado. (Consulte **Criar um projeto do Workspace usando todos os dados do evento** abaixo.)

Para gerenciar o uso do CJA:

* Use a API do CJA. (Consulte **Criar um relatório na API do CJA** abaixo.)

## Estimar tamanho da conexão {#estimate-size}

Talvez seja necessário saber quantas linhas de dados de evento você tem atualmente em [!UICONTROL Customer Journey Analytics]. Para obter uma conta precisa do uso dos registros de dados de evento (linhas de dados) de sua organização, faça o seguinte **para cada uma das conexões criadas pela organização**.

>[!NOTE]
>
>Faça isso na primeira sexta-feira de cada mês, já que o Adobe executa seu relatório de uso mais recente naquele dia.

1. No [!UICONTROL Customer Journey Analytics], clique na guia **[!UICONTROL Conexões]**.

   Agora você pode ver uma lista de todas as conexões atuais.

1. Clique em cada nome de conexão para acessar o Gerenciador de conexões.

1. Adicione o **[!UICONTROL Registros dos dados do evento disponíveis]** para cada conexão criada pela organização. (Dependendo do tamanho da conexão, o número pode levar algum tempo para ser exibido.)

   ![dados do evento](assets/event-data.png)

   >[!CAUTION]
   >
   >   Essa contagem se aplica somente aos dados do evento, não aos dados do perfil ou da pesquisa. Se você tiver dados de perfil e pesquisa, a contagem será um pouco maior. No entanto, atualmente não há como criar relatórios sobre o uso de dados de perfil e pesquisa na interface do usuário. Essa funcionalidade está programada para 2023.

1. Depois de ter uma soma de todas as linhas de dados do evento, procure o direito de “Linhas de dados” no contrato do Customer Journey Analytics que sua empresa assinou com a Adobe.

   Isso fornece o número máximo de linhas de dados autorizadas na Ordem de venda. Se o número de linhas de dados resultante da Etapa 3 for maior que esse número, você está incorrendo em um excedente.

1. Para corrigir essa situação, você tem várias opções:

   * Alterar as [configurações de retenção de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=pt-BR#set-rolling-window-for-connection-data-retention).
   * [Excluir todas as conexões não usadas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=pt-BR#implications-of-deleting-data-components).
   * [Excluir um conjunto de dados na AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=pt-BR#implications-of-deleting-data-components).
   * Entre em contato com o Gerente de conta da Adobe para obter licença de capacidade adicional.

## Criar um projeto do Workspace usando todos os dados do evento {#workspace-event-data}

1. Antes de criar o projeto no Workspace, [criar uma visualização de dados](/help/data-views/create-dataview.md) que extrai dados de TODAS as suas conexões e não tem filtros aplicados. Em outras palavras, inclui todos os seus dados.

1. No Workspace, crie um novo projeto e extraia todos os eventos (da variável **[!UICONTROL Métricas]** ) para o mês anterior.

   ![Eventos](assets/events-usage.png)

1. faça isso

## Criar um relatório na API do CJA {#api-report}

Use o [API de relatórios CJA](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) para executar um relatório em todos os dados do evento.