---
title: Configurações de componente de atribuição
description: Permite definir a atribuição padrão de uma métrica.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: b353983b13cbbfb4c846e75aecc1b78da26ddeb2
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 100%

---

# Configurações de componente de atribuição

A atribuição permite definir um modelo de atribuição padrão para uma métrica. É possível substituir um determinado modelo de atribuição de métrica ao trabalhar no Analysis Workspace.

![Atribuição](../assets/attribution-settings.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Definir atribuição] | Ativa um modelo de atribuição padrão quando essa métrica é usada. Esse padrão pode ser sobreposto em uma [!UICONTROL Tabela de forma livre] ou em uma Métrica calculada. |
| [!UICONTROL Modelo de atribuição] | Permite especificar qual [modelo de atribuição](/help/analysis-workspace/attribution/models.md) padrão utilizar. O padrão é [!UICONTROL Último contato]. As opções são: Último contato, Primeiro contato, Linear, Participação, Mesmo contato, Forma de U, Curva de J, J inverso, Declínio de tempo, Personalizado, Algorítmico. Algumas dessas opções criam campos adicionais que precisam ser preenchidos - como Personalizado ou Declínio de tempo. É possível criar várias métricas usando o mesmo campo. Isso significa que você pode ter uma métrica de receita de [!UICONTROL Último contato] e uma métrica de receita de [!UICONTROL Primeiro contato], mas com base no mesmo campo de receita no esquema. |
| [!UICONTROL Janela de lookback] | Permite especificar uma janela de retrospectiva padrão para uma métrica. As opções são: [!UICONTROL Pessoa] (Janela de relatório), [!UICONTROL Sessão] e [!UICONTROL Personalizado]. Quando a opção [!UICONTROL Personalizado] está selecionada, também oferecemos a opção de selecionar qualquer número de dias/semanas/meses/etc. (até 90 dias), exatamente como o [!UICONTROL Attribution IQ]. Você pode ter várias métricas usando o mesmo campo de esquema, mas cada uma com uma janela de pesquisa separada. |

{style=&quot;table-layout:auto&quot;}
