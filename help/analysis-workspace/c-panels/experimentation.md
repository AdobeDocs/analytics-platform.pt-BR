---
description: Saiba mais sobre como analisar os resultados de testes A/B no painel Experimentação do CJA.
title: Painel de experiência
feature: Panels
source-git-commit: 2c217c7d31819ac8eb27d2d1010e0df787601e21
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---


# Painel de experiência

>[!NOTE]
>
>Esta funcionalidade está atualmente em [testes limitados](/help/release-notes/releases.md).

O **[!UICONTROL Experimentação]** O painel permite que você compare diferentes variações de experiência do usuário, marketing ou mensagens para determinar qual é a melhor maneira de conduzir um resultado específico. Você pode avaliar o aumento e a confiança de qualquer experimento A/B de qualquer plataforma de experimentação - online, offline, de soluções de Adobe, Adobe Journey Optimizer e até mesmo dados BYO (traga seus próprios).

>[!IMPORTANT]
>
>Neste ponto, [Adobe Analytics para Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=pt-BR) Os dados do (A4T) não podem ser avaliados na variável [!UICONTROL Experimentação] painel.

## Controle de acesso

O painel Experimentação está disponível para todos os usuários do Customer Journey Analytics (CJA). Não são necessários direitos de administrador ou outras permissões. No entanto, a configuração exige rótulos nas visualizações de dados que somente os Administradores podem atribuir.

## Terminologia

* **Experimento**: Um experimento é um conjunto de variações em uma experiência que foi exposta a usuários finais para determinar qual é melhor manter a perpetuidade. Um experimento é composto de duas ou mais variações, uma das quais é considerada a variação de controle.

* **Variação**: Uma de duas ou mais alterações na experiência de um usuário final que estão sendo comparadas com o objetivo de identificar a melhor alternativa. Deve ser selecionada uma variação como controlo e só pode ser considerada uma variação como variação de controlo.

* **Controle**: Uma variação específica que representa o status quo ou o estado padrão da experiência de um usuário. Todas as outras variações estão sendo comparadas.

* **Métrica de normalização**: A base (sessões ou pessoas) na qual um teste será executado. Por exemplo, um teste pode comparar as taxas de conversão de várias variações, onde a taxa de conversão é calculada como conversões por sessão ou conversões por pessoa.

* **Métrica de conversão**: A métrica com a qual um usuário está comparando variações. A variação com o resultado mais desejável para a métrica de conversão (mais alta ou mais baixa) é declarada como &quot;vencedora&quot; de um experimento.

## Etapa 1: Criar conexão com conjuntos de dados de experimento

Depois que seus dados de experimento tiverem sido [ingerido](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) no Adobe Experience Platform, [criar uma conexão no CJA](/help/connections/create-connection.md) para um ou mais conjuntos de dados de experimento.

## Etapa 2: Adicionar rótulos de contexto em visualizações de dados

Nas configurações de exibições de dados do CJA, os administradores podem adicionar [rótulos de contexto](/help/data-views/component-settings/overview.md) para uma dimensão ou métrica e serviços CJA como [!UICONTROL Experimentação] O painel pode usar esses rótulos para suas finalidades. Dois rótulos predefinidos são usados para o painel Experimentação :

* [!UICONTROL Experimento]
* [!UICONTROL Variante]

Na visualização de dados que contém dados de experimentação, escolha duas dimensões, uma com os dados de experimentação e outra com os dados da variante. Em seguida, rotule essas dimensões com o **[!UICONTROL Experimento]** e **[!UICONTROL Variante]** rótulos.

![rótulo de contexto](assets/context-label.png)

Sem esses rótulos presentes, o painel Experimento não funciona.

## Etapa 3: Configurar o painel Experimento

1. No CJA Workspace, arraste o painel Experimentação para um projeto.

![painel de experimento](assets/experiment.png)




