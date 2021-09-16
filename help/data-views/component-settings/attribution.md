---
title: Configurações do componente de atribuição
description: Permite definir a atribuição padrão para uma métrica.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 69%

---


# Configurações do componente de atribuição

A atribuição permite definir um modelo de atribuição padrão para uma métrica. Você pode substituir um determinado modelo de atribuição de métrica ao trabalhar no Analysis Workspace.

![Atribuição](../assets/attribution-settings.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Definir atribuição] | Ativa um modelo de atribuição padrão quando essa métrica é usada. Esse padrão pode ser sobreposto em uma [!UICONTROL Tabela de forma livre] ou em uma Métrica calculada. |
| [!UICONTROL Modelo de atribuição] | Permite que você especifique o [modelo de atribuição](/help/analysis-workspace/attribution/models.md) padrão a ser usado. O padrão é [!UICONTROL Último contato]. As opções são: Último contato, Primeiro contato, Linear, Participação, Mesmo contato, Forma de U, Curva de J, J inverso, Declínio de tempo, Personalizado, Algorítmico. Algumas dessas opções criam campos adicionais que precisam ser preenchidos - como Personalizado ou Declínio de tempo. É possível criar várias métricas usando o mesmo campo. Isso significa que você pode ter uma métrica de receita de [!UICONTROL Último contato] e uma métrica de receita de [!UICONTROL Primeiro contato], mas com base no mesmo campo de receita no esquema. |
| [!UICONTROL Janela de lookback] | Permite que você especifique uma janela de retrospectiva padrão para uma métrica. As opções são: [!UICONTROL Pessoa] (Janela de relatório), [!UICONTROL Sessão] e [!UICONTROL Personalizado]. Quando a opção [!UICONTROL Personalizado] está selecionada, também oferecemos a opção de selecionar qualquer número de dias/semanas/meses/etc. (até 90 dias), exatamente como o [!UICONTROL Attribution IQ]. Você pode ter várias métricas usando o mesmo campo de esquema, mas cada uma com uma janela de pesquisa separada. |
