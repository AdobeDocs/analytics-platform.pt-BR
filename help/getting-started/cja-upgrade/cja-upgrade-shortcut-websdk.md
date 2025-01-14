---
title: Atalho de atualização Migrar uma implementação de extensão do AppMeasurement ou do Analytics para usar o Web SDK
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 83927cf0-b3b4-42b4-9ca5-0c81c091383f
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 58%

---

# Atalho de atualização: migrar uma implementação de extensão do AppMeasurement ou do Analytics para usar o SDK da web {#shortcut-migrate-websdk}

>[!NOTE]
>
>Esta documentação deve ser usada como parte do [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_migrate_aa_to_websdk"
>title="Migrar a sua implementação do Analytics para usar o SDK da web"
>abstract="Em vez de enviar dados por meio de um objeto XDM, você pode enviar todas as variáveis no formato do AppMeasurement por meio do objeto de dados. Este atalho permite que você continue usando a lógica do AppMeasurement para enviar dados à Platform."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migrate_aa_to_websdk"
>title="Migrar a sua implementação do Analytics para usar o SDK da web"
>abstract="Em vez de enviar dados por meio de um objeto XDM, você pode enviar todas as variáveis no formato do AppMeasurement por meio do objeto de dados. Este atalho permite que você continue usando a lógica do AppMeasurement para enviar dados à Platform."

<!-- markdownlint-enable MD034 -->

Ao atualizar para Customer Journey Analytics, o Adobe [recomenda uma nova implementação do Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). No entanto, dependendo de vários fatores, como linha do tempo e restrições de recursos, as etapas de atualização recomendadas podem não ser práticas para sua organização.

Se a implementação do Adobe Analytics for o AppMeasurement ou a extensão do Analytics, um atalho de atualização estará disponível e permitirá migrar a implementação do Adobe Analytics para usar o Adobe Experience Platform Web SDK para começar a enviar dados para o Edge Network e o Adobe Analytics, antes de enviá-los para o Customer Journey Analytics.

## Vantagens e desvantagens

Considere as seguintes vantagens e desvantagem do atalho de atualização para migrar sua implementação de extensão do AppMeasurement ou do Analytics para usar o Web SDK:

| Vantagens | Desvantagens |
|----------|---------|
| <ul><li>**Mostra todas as vantagens de hospedar dados na Experience Edge Network**: <p>As vantagens incluem:</p><ul><li>Geração de relatórios com alto desempenho e disponibilidade de dados devido à capacidade da Adobe Experience Platform de potencializar [casos de uso de personalização em tempo real](https://experienceleague.adobe.com/br/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidar a implementação da coleção de dados da Adobe Experience Cloud entre outros produtos da Experience Cloud (AJO, RTCDP e assim por diante)</li><li>Não dependente da nomenclatura do Adobe Analytics (prop, eVar, evento etc.)</li></ul><li>**Uso da implementação existente**: embora sejam necessárias algumas alterações de implementação, essa abordagem não exige uma implementação totalmente nova. Você pode usar sua camada de dados e código existentes com alterações mínimas na lógica de implementação sem afetar os relatórios existentes do Adobe Analytics.</li><li>**Flexibilidade para criar um esquema XDM para a organização posteriormente**: é possível migrar sua implementação existente do Adobe Analytics para usar o SDK da web, verificar se tudo está funcionando no Adobe Analytics e criar o esquema XDM. Essa flexibilidade permite uma atualização mais metódica e ponderada para o Customer Journey Analytics.</li></ul> | <ul><li>**Requisito de mapeamento para envio de dados para a Platform**: quando sua organização estiver pronta para usar o Customer Journey Analytics, envie dados para um conjunto de dados na Adobe Experience Platform. Essa ação exige que cada campo no objeto de dados seja uma entrada na ferramenta de mapeamento de sequência de dados que o atribui a um campo de esquema XDM. O mapeamento só precisa ser feito uma vez para esse fluxo de trabalho e não é necessário fazer alterações de implementação. No entanto, essa é uma etapa extra que não é necessária ao enviar dados em um objeto XDM.</li><li>**Dívida técnica**: como essa abordagem usa uma forma modificada da implementação existente, pode ser mais difícil rastrear a lógica de implementação e executar alterações futuras quando necessário. </li></ul> |

{style="table-layout:auto"}

## Etapas básicas

Se você decidir usar o atalho de atualização para migrar sua implementação de extensão do AppMeasurement ou do Analytics para usar o Web SDK, uma nova etapa será adicionada às etapas geradas dinamicamente para sua organização no [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

As etapas básicas para migrar uma implementação de extensão do AppMeasurement ou do Analytics para usar o Web SDK são:

1. Comece a enviar dados para a Platform.

   Se você já estiver enviando dados para a Platform com a implementação do Adobe Analytics, esta etapa não será necessária. Basta criar uma conexão entre os conjuntos de dados da plataforma e o Customer Journey Analytics, conforme descrito posteriormente neste processo.

1. (Opcional) Crie um esquema XDM para sua organização assim que possível.

1. (Condicional) Se você criou um esquema XDM, use o mapeamento de sequência de dados para mapear todos os campos no objeto de dados para o esquema XDM.
