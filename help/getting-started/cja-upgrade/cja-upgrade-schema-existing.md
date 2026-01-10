---
title: Escolha o esquema para o Customer Journey Analytics
description: Saiba mais sobre as opções disponíveis ao escolher um esquema para o Customer Journey Analytics e as vantagens e desvantagens de cada um
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
source-git-commit: 3dc53d6955eab3048ebf8a7c9d232b4b5739c6bd
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---

# Escolha o esquema para o Customer Journey Analytics {#choose-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-tailored"
>title="Usar um esquema personalizado"
>abstract="(Recomendado) A personalização do esquema permite que sua organização monitore somente o que é necessário e evita a sobrecarga relacionada a campos desnecessários e confusos. Esta opção inclui grupos de campos adicionados pelo SDK da Web e grupos de campos personalizados para sua organização."

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-default"
>title="Usar o esquema padrão"
>abstract="(Não recomendado) O esquema do Adobe Analytics contém mais de mil campos, o que pode resultar em um esquema desordenado e complexo. Sua organização seria forçada a continuar aderindo ao conceito de props e eVars, que é um conceito legado não usado no Customer Journey Analytics. A integração com outros serviços da Adobe Experience Platform é mais difícil."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

Ao atualizar para o Customer Journey Analytics, a Adobe recomenda criar um esquema personalizado do Experience Data Model (XDM) para se alinhar melhor às necessidades da organização à medida que você começa a usar outros serviços da Platform. Como alternativa, você pode optar por usar o esquema existente do Adobe Analytics.

Considere as vantagens e desvantagens de cada um.

## Criar um esquema personalizado adaptado à sua organização (Recomendado)

A Adobe recomenda criar um esquema personalizado ao atualizar para o Customer Journey Analytics.

| Vantagens | Desvantagens |
|----------|---------|
| <ul><p>As vantagens de atualizar para seu próprio esquema personalizado incluem:</p><ul><li>Um esquema simplificado e adaptado às necessidades da organização e aos aplicativos específicos da Platform que você usa.</li><p>Quando é preciso realizar alterações no esquema, não é necessário analisar milhares de campos não utilizados para localizar o campo que precisa de atualização.</p></ul> | <p>As desvantagens de atualizar para seu próprio esquema personalizado incluem:</p><ul><li>A atualização do esquema é um processo demorado e necessário para começar a enviar dados à Platform.</li></ul> |

## Use o esquema existente do Adobe Analytics

A opção de usar o esquema existente do Adobe Analytics com o Customer Journey Analytics estará disponível somente se sua implementação do Adobe Analytics estiver configurada com o SDK da web da Adobe Experience Platform. <!-- correct? Or can you do this with an AppMeasurement implementation?-->

| Vantagens | Desvantagens |
|----------|---------|
| <p>As vantagens de usar o esquema do Adobe Analytics incluem:</p><ul><li>Facilidade para atualizar<p>Se você já estiver enviando dados para o Adobe Analytics com o SDK da web da Adobe Experience Platform, é possível adicionar um serviço extra à sequência de dados para enviar dados para a Adobe Experience Platform (que também pode ser usado na configuração do Customer Journey Analytics).</p></li></ul> | <p>As desvantagens de usar o esquema do Adobe Analytics incluem:</p><ul><li>Embora o uso do esquema do Adobe Analytics não limite a maneira como você utiliza outros aplicativos da Platform, ele é um esquema um pouco mais complexo. Isso ocorre porque o esquema do Adobe Analytics contém muitos objetos específicos do Adobe Analytics que provavelmente não serão usados pela organização.<p>Quando é preciso realizar alterações no esquema, é necessário analisar milhares de campos não utilizados para localizar o campo que precisa de atualização.</p></li></ul> |




<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the Customer Journey Analytics Upgrade Guide.

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->
