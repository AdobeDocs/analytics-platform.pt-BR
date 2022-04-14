---
title: Assimilar dados do Marketo Engage no AEP e relatório no CJA
description: Saiba como trazer dados do Marketo Engage para o CJA
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
source-git-commit: ad8e3c18dbb73a064662a4543cb0e553cd52cec3
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 5%

---

# Assimilar dados do Marketo Engage no AEP e relatório no CJA

Você pode aproveitar os conjuntos de dados do Marketo Engage recém-disponíveis no Adobe Experience Platform (AEP) para fornecer análises e soluções de relatórios valiosas para profissionais de marketing B2B. Em seguida, relate esses conjuntos de dados no Customer Journey Analytics (CJA).

## Etapa 1: Mapear campos de dados de origem do Marketo para seus destinos XDM

Mapeie o [Pessoas](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=en#persons) e [Atividades](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=en#activities) objetos aos respectivos campos de destino do esquema XDM.

## Etapa 2: Assimilar dados do Marketo no AEP

Use o [conector Marketo Engage](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html?lang=en) para trazer os dados do Marketo para o Experience Platform e manter esses dados atualizados usando aplicativos conectados à plataforma.

## Etapa 3: Configurar uma conexão com esse conjunto de dados no CJA

Para criar relatórios sobre conjuntos de dados do Experience Platform, primeiro é necessário estabelecer uma conexão entre conjuntos de dados no Experience Platform e no CJA. Encontre mais informações em [Criar uma conexão](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR).

## Etapa 4: Criar uma ou mais visualizações de dados

A [exibição de dados](/help/data-views/data-views.md) é um contêiner específico do Customer Journey Analytics que permite determinar como interpretar dados de uma conexão. Especifica todas as dimensões e métricas disponíveis no Analysis Workspace - neste caso, métricas e dimensões específicas do Marketo. Também especifica a partir de quais colunas essas dimensões e métricas obtêm seus dados. As visualizações de dados são definidas na preparação de relatórios no Analysis Workspace.

## Etapa 5: Relatório no Analysis Workspace

Um caso de uso que você pode explorar é: Quantas visitas de páginas da Web por clientes potenciais tivemos em abril-Junho de 2020?

1. Abrir [Espaço de trabalho do Analytics](/help/analysis-workspace/home.md) e criar um novo projeto.
Clientes com CDP B2B/B2P podem realizar análise no estilo B2C no CJA. Os objetos B2B ainda não estão disponíveis.

1. Crie um [filter](/help/components/filters/create-filters.md) para exibições de página da Web da seguinte maneira - Tipo de evento = web.webpagedetails.pageViews :

   ![](assets/marketo-filter.png)

1. Na tabela de Forma livre, puxe o filtro criado - Exibições de página da Web e puxe o intervalo de datas Mês . Isso dá a você visitas à página da Web por clientes potenciais a cada mês:

   ![](assets/marketo-freeform.png)

1. Ou insira as seguintes dimensões: Chave de pessoa ou endereço de email de trabalho. Isso dá a você as visitas à página da Web por cada lead:

   ![](assets/marketo-freeform2.png)
