---
title: Analisar públicos da Experience Platform no Customer Journey Analytics
description: Saiba como analisar públicos do Experience Platform no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 996d7d7bb0c0da566a926f9a3a4c465baca69a9a
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# Analisar públicos da Experience Platform no Customer Journey Analytics {#analyze-audiences-RTCDP}

Após [criar uma configuração de análise de público-alvo](/help/connections/audience-analysis/audience-analysis-configure.md), os dados de público-alvo ficam disponíveis como novas dimensões nas visualizações de dados em que você os configura para serem criados. Você pode usar as novas dimensões de público-alvo em qualquer lugar no Analysis Workspace se tiver acesso a uma visualização de dados em que as dimensões de análise de público-alvo foram adicionadas.

## Usar o modelo de visão geral do público-alvo

Um template de visão geral do público-alvo está disponível no Customer Journey Analytics.

<!-- Can you also use the new audience dimensions in any project, regardless of whether it's a template? I assume so -->

<!-- What are the names of the new dimensions? Are they customized to whatever your audience names are in AEP, or are they always the same? Are they the dimensions available in the Audience overview template? (Audience Name, Audience Origin, Exited Audience Name, Exited Audience Origin; Audience Description, Exited Audience Description). Metrics included (Distinct Audiences) -->

Para obter informações sobre como acessar o modelo de visão geral de Público-alvo, consulte [Acessar e executar um modelo](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) em [Usar modelos](/help/analysis-workspace/templates/use-templates.md).

O modelo Visão geral do público-alvo contém os seguintes painéis:

## Painel de visão geral de uso

Mostra os dados de todos os públicos-alvo com eventos de uso associados à visualização de dados selecionada. Os dados de associação de público-alvo são atualizados diariamente pela Experience Platform. Os dados são sempre exibidos para ontem, portanto, alterar o intervalo de datas do painel resulta em dados imprecisos.

Use a tabela neste painel para entender melhor o comportamento do público-alvo. Arraste a dimensão Descrição do público-alvo da visualização de dados selecionada e adicione-a como um detalhamento. Ou use qualquer outra dimensão de interação (como Página, Ação etc.) como o detalhamento.

## Painel de principais origens de público-alvo

Mostra onde o público-alvo foi criado, seja no RTCDP, Customer Journey Analytics e assim por diante.

Use a tabela neste painel para entender melhor como a origem do público-alvo pode afetar outros fatores. Arraste a dimensão Nome do público-alvo da visualização de dados selecionada e adicione-a como um detalhamento. Ou use qualquer outra dimensão de interação (como Página, Ação etc.) como o detalhamento.

## Painel de sobreposição de público

Mostra os dados de todos os públicos-alvo com eventos de uso associados à visualização de dados selecionada. Os dados são sempre exibidos para ontem, portanto, alterar o intervalo de datas do painel resulta em dados imprecisos.

Selecione até três públicos-alvo na tabela neste painel para ver como eles se sobrepõem no diagrama de Venn correspondente.

## Sair do painel de uso do público-alvo

Mostra os dados de todos os públicos-alvo com eventos de uso associados à visualização de dados selecionada. Os dados são sempre exibidos para ontem, portanto, alterar o intervalo de datas do painel resulta em dados imprecisos. &quot;Públicos-alvo encerrados&quot; são públicos-alvo nos quais pessoas com eventos de uso saíram ou saíram ontem.

Use a tabela neste painel para entender melhor o comportamento do público-alvo. Arraste a dimensão Descrição de público-alvo encerrado da visualização de dados selecionada e adicione-a como um detalhamento. Ou use qualquer outra dimensão ou métrica de interação (como Página, Ação e assim por diante) como o detalhamento.

## Painel de origens do público-alvo principal encerrado

Mostra onde cada público-alvo que saiu foi criado originalmente, seja no RTCDP, no Customer Journey Analytics e assim por diante.

Use a tabela neste painel para entender melhor como a origem do público-alvo pode afetar outros fatores. Arraste a dimensão Nome de público-alvo da visualização de dados selecionada e adicione-a como um detalhamento. Ou use qualquer outra dimensão ou métrica de interação (como Página, Ação e assim por diante) como o detalhamento.








