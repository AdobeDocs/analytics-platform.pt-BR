---
title: Incluir Excluir valores configurações do componente
description: Inclua ou exclua condicionalmente um item de dimensão dependendo de seu valor.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 56%

---


# Incluir Excluir valores configurações do componente

Incluir valores de Excluir permite criar regras que dependem do valor de um item de dimensão. Os valores que não atendem aos critérios definidos são tratados no Analysis Workspace como se nunca existissem, embora os dados ainda existam no conjunto de dados subjacente.

![Incluir exclusão](../assets/include-exclude.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Definir a inclusão/exclusão de valores] | Uma caixa de seleção que permite ativar as condições em que os dados são incluídos em uma visualização de dados. |
| [!UICONTROL Diferencia maiúsculas de minúsculas] | Visível nos tipos de dados do esquema String. O padrão é ativar. Essa configuração se aplica somente à lógica [!UICONTROL Incluir/Excluir valores], não ao valor resultante. Ela permite especificar se a regra diferencia maiúsculas de minúsculas. |
| [!UICONTROL Corresponder] | Permite especificar quais valores você gostaria de considerar para os relatórios antes da atribuição e filtros (por exemplo, usar apenas valores contendo a frase &quot;erro&quot;). Você pode especificar **[!UICONTROL Se todos os critérios forem atendidos]** ou **[!UICONTROL Se algum critério for atendido]**. |
| [!UICONTROL Critérios] | Permite especificar a lógica de correspondência que deve ser aplicada a uma regra de filtro específica.<ul><li>**Sequência**: Contém a frase, Contém qualquer termo, Contém todos os termos, Não contém nenhum termo, Não contém a frase, É igual, Não é igual, Começa com, Termina com</li><li>**Duplo/Número inteiro**: é igual, não é igual, é maior que, é menor que, é maior que ou igual a, é menor que ou igual a</li><li>**Data**: é igual a, não é igual, é posterior a, é anterior, ocorre dentro de</li></ul> |
| [!UICONTROL Corresponder operando] | Permite especificar o operando correspondente ao qual o operador deve ser aplicado.<ul><li>**Sequência**: Campo de texto</li><li>**Duplo/Número inteiro**: Campo de texto com setas para cima/para baixo para valores numéricos</li><li>**Data**: Seletor de granularidade do dia (calendário)</li><li>**Data Hora**: Seletor de granularidade de data e hora</li></ul> |
| [!UICONTROL Adicionar regra] | Permite especificar um operador e um operando de correspondência adicional. |
