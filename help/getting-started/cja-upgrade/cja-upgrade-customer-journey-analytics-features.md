---
title: Entenda os recursos exclusivos do Customer Journey Analytics
description: Saiba mais sobre os recursos exclusivos do Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 78%

---

# Entenda os recursos exclusivos do Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="Unir dados de origens variadas"
>abstract="(Recomendado) Vincule dados de várias propriedades web, móveis e offline para criar uma visualização única e consolidada do comportamento do cliente. A capacidade de combinar dados de análise de outros canais é o principal caso de uso do Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="Compilar ocorrências de vários conjuntos de dados"
>abstract="Se um dos seus conjuntos de dados não compartilhar um identificador principal (como uma ID da Experience Cloud), você ainda poderá compilar esses dados usando outra dimensão, como o nome de usuário de logon ou endereço de email."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="Entre em contato com o Atendimento ao cliente da Adobe para gerar um conjunto de dados compilado"
>abstract="Se você tiver um campo que contém um identificador que existe em vários conjuntos de dados, mas esse não for o identificador principal, poderá usá-lo para gerar um novo conjunto de dados com um identificador consistente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="Integração com a Real-time CDP"
>abstract="Combine dados de perfil de várias fontes para gerar públicos-alvo e segmentos com base nas características do usuário."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="Integração temporária com o Adobe Target"
>abstract="A Adobe recomenda a integração com o Adobe Journey Optimizer para casos de uso de personalização. A integração com o Adobe Target é possível, mas é uma solução de curto prazo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="Integração com o Journey Optimizer"
>abstract="Ofereça experiências conectadas, contextuais e personalizadas aos clientes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="Integração temporária com o Adobe Audience Manager"
>abstract="A Adobe recomenda a integração com a Adobe Real-time CDP para casos de uso baseados em público-alvo. A integração com o Audience Manager é possível, mas é uma solução de curto prazo."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

A lista a seguir mostra apenas os recursos do Customer Journey Analytics que exigem consideração durante o processo de atualização. Para obter uma lista abrangente que mostra quais recursos do Adobe Analytics são totalmente compatíveis, parcialmente compatíveis ou incompatíveis com o Customer Journey Analytics, consulte [compatibilidade com recursos do Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Considere quais dos seguintes recursos do Customer Journey Analytics você deseja adotar ao atualizar para o Customer Journey Analytics:

| Recurso do Customer Journey Analytics | Função |
|---------|----------|
| [Vincular dados da web com dados de outros canais, como dados de centrais de atendimento](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | O Customer Journey Analytics possui a habilidade da Experience Platform de armazenar toda espécie de esquemas de dados e tipos. Com o [Experience Data Model (XDM)](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/home), os dados podem ser representados e organizados uniformemente, para que estejam prontos para combinação e exploração. O Adobe Analytics foca predominantemente em dados de análise móveis e da Web com alguns recursos de [importação de dados](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=pt-BR). |
| [Compile ocorrências de outros conjuntos de dados com uma dimensão personalizada](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/stitching/overview) | O Customer Journey Analytics permite [combinar dados](/help/connections/combined-dataset.md) de vários conjuntos de relatórios como se fossem um único conjunto de relatórios no Adobe Analytics. |
| [Integrar à CDP em tempo real do Adobe](/help/components/audiences/audiences-overview.md) | Você pode [criar e publicar públicos-alvo](/help/components/audiences/audiences-overview.md) descobertos no Customer Journey Analytics no Perfil do cliente em tempo real na Adobe Experience Platform para direcionamento e personalização de clientes. |
| [Integrar ao Adobe Target (A4T)](/help/integrations/at.md) | Os Relatórios do Target no Customer Journey Analytics permitem [medir e relatar atividades do Adobe Target](/help/integrations/at.md) diretamente no Customer Journey Analytics. No entanto, a Adobe recomenda a integração com o Adobe Journey Optimizer para casos de uso de personalização. |
| [Integrar ao Adobe Journey Optimizer](/help/integrations/ajo.md) | Você pode configurar os dados gerados pelo Journey Optimizer para [executar análise avançada no Customer Journey Analytics](/help/integrations/ajo.md). |
| [Integrar ao Adobe Audience Manager](https://experienceleague.adobe.com/pt-br/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | Você pode [compartilhar características e segmentos do Audience Manager com a Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing). No entanto, a Adobe recomenda a integração com a Adobe Real-time CDP para casos de uso baseados em público-alvo. |
