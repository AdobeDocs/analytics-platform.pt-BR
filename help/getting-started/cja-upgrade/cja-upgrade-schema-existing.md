---
title: Escolha seu esquema para o Customer Journey Analytics
description: Saiba mais sobre as opções disponíveis ao escolher um esquema para Customer Journey Analytics e as vantagens e desvantagens de cada um
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 38%

---

# Escolha seu esquema para o Customer Journey Analytics {#choose-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-tailored"
>title="Usar um esquema personalizado"
>abstract="(Recomendado) A personalização do esquema permite que sua organização rastreie somente o que é necessário e evite a sobrecarga vinculada a campos desnecessários e confusos. Essa opção inclui grupos de campos adicionados pelo Web SDK e grupos de campos personalizados para sua organização."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-default"
>title="Usar o esquema padrão"
>abstract="(Não recomendado) O esquema do Adobe Analytics contém mais de mil campos, o que pode resultar em esquema desordenado e complexo. Sua organização seria forçada a continuar aderindo ao conceito de props e eVars, que é um conceito herdado não usado no Customer Journey Analytics. A integração com outros serviços da Adobe Experience Platform é mais difícil."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>Esta documentação deve ser usada como parte do [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

Ao atualizar para o Customer Journey Analytics, a Adobe recomenda criar um esquema personalizado do Experience Data Model (XDM) para se alinhar melhor às necessidades da sua organização à medida que você começa a usar outros serviços da Platform. Como alternativa, você pode optar por usar o esquema existente do Adobe Analytics.

Considere as vantagens e desvantagens de cada uma.

## Criar um esquema personalizado adaptado à sua organização (Recomendado)

O Adobe recomenda criar um esquema personalizado ao atualizar para o Customer Journey Analytics.

| Vantagens | Desvantagens |
|----------|---------|
| <ul><p>As vantagens de atualizar para seu próprio esquema personalizado incluem:</p><ul><li>Um esquema simplificado e adaptado às necessidades da organização e aos aplicativos específicos da Platform que você usa.</li><p>Quando é preciso realizar alterações no esquema, não é necessário analisar milhares de campos não utilizados para localizar o campo que precisa de atualização.</p></ul> | <p>As desvantagens de atualizar para seu próprio esquema personalizado incluem:</p><ul><li>A atualização do esquema é um processo demorado e necessário antes de você começar a enviar dados para a Platform.</li></ul> |

## Usar seu esquema existente do Adobe Analytics

A opção para usar o esquema existente do Adobe Analytics com o Customer Journey Analytics só estará disponível se a implementação do Adobe Analytics estiver configurada com o Adobe Experience Platform Web SDK. <!-- correct? Or can you do this with an AppMeasurement implementation?-->

| Vantagens | Desvantagens |
|----------|---------|
| <p>As vantagens de usar o esquema do Adobe Analytics incluem:</p><ul><li>Facilidade de atualização<p>Se você já estiver enviando dados para o Adobe Analytics com o SDK da web da Adobe Experience Platform, é possível adicionar um serviço extra à sequência de dados para enviar dados para a Adobe Experience Platform (que também pode ser usado na configuração do Customer Journey Analytics).</p></li></ul> | <p>As desvantagens de usar o esquema do Adobe Analytics incluem:</p><ul><li>Embora o uso do esquema do Adobe Analytics não limite a maneira como você utiliza outros aplicativos da Platform, ele é um esquema um pouco mais complexo. Isso ocorre porque o esquema do Adobe Analytics contém muitos objetos específicos do Adobe Analytics que provavelmente não serão usados pela organização.<p>Quando é preciso realizar alterações no esquema, é necessário analisar milhares de campos não utilizados para localizar o campo que precisa de atualização.</p></li></ul> |




<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->
