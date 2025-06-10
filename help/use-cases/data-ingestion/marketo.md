---
title: Relatórios de dados do Marketo Engage
description: Saiba como criar relatórios sobre dados do Marketo Engage no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
role: Admin
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 51%

---

# Relatórios de dados do Marketo Engage

Você pode aproveitar os conjuntos de dados do Marketo Engage recém-disponíveis no Adobe Experience Platform (Adobe Experience Platform) para fornecer análises e soluções de relatórios valiosas para profissionais de marketing B2B. Em seguida, relate esses conjuntos de dados na Adobe Customer Journey Analytics.

## Etapa 1: Mapear campos de dados de origem do Marketo para seus públicos-alvo XDM

Mapeie os objetos [Pessoas](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html#persons) e [Atividades](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html#activities) aos respectivos campos de público-alvo do esquema XDM.

## Etapa 2: Assimilar dados do Marketo na Adobe Experience Platform

Use o [conector do Marketo Engage](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html) para trazer os dados do Marketo para a Experience Platform e manter esses dados atualizados usando aplicativos conectados à Platform.

## Etapa 3: configurar uma conexão com esse conjunto de dados no Customer Journey Analytics

Para criar relatórios sobre conjuntos de dados do Experience Platform, primeiro é necessário estabelecer uma conexão entre os conjuntos de dados na Experience Platform e no Customer Journey Analytics. Consulte para obter mais informações [Criar ou editar uma conexão](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR).

## Etapa 4: Criar uma ou mais visualizações de dados

Uma [visualização de dados](/help/data-views/data-views.md) é um container específico do Customer Journey Analytics que permite determinar como interpretar dados de uma conexão. Especifica todas as dimensões e métricas disponíveis no Analysis Workspace, neste caso, métricas e dimensões específicas do Marketo. Também especifica a partir de quais colunas essas dimensões e métricas obtêm os dados. As visualizações de dados são definidas na preparação de relatórios no Analysis Workspace.

## Etapa 5: Relatório no Analysis Workspace

Um caso de uso que você pode explorar é: Quantas visitas de páginas da Web por clientes potenciais tivemos em abril-junho de 2020?

1. Abrir [Espaço de trabalho do Analytics](/help/analysis-workspace/home.md) e criar um novo projeto.
Clientes com CDP B2B/B2P podem realizar análise no estilo B2C no Customer Journey Analytics. Os objetos B2B ainda não estão disponíveis.

1. Crie um [segmento](/help/components/segments/seg-create.md) para exibições de página da Web da seguinte maneira - Tipo de evento = web.webpagedetails.pageViews :

   ![Janela Definição mostrando o Tipo de Evento e Evento](../assets/marketo-filter.png)

1. Puxe o segmento criado na tabela de forma livre - Exibições de página da Web e obtenha o intervalo de datas Mês. Você obtém as visitas à página da Web por clientes potenciais a cada mês:

   ![Tabela de forma livre mostrando eventos por mês.](../assets/marketo-freeform.png)

1. Ou obtém as seguintes dimensões: Chave de pessoa ou endereço de email de trabalho. Você obtém as visitas à página da Web por cada lead:

   ![Tabela de forma livre mostrando Eventos e workEmail.Address e Exibições de Página da Web.](../assets/marketo-freeform2.png)
