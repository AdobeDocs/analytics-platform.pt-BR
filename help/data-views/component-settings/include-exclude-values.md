---
title: Configurações do componente dos valores de Inclusão e Exclusão
description: Inclua ou exclua condicionalmente um item de dimensão dependendo de seu valor.
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: a236b2126c4b998b4d97caab014556e3ee3a9e83
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 97%

---

# Configurações do componente dos valores de Inclusão e Exclusão {#include-exclude-values-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_includeexcludevalues"
>title="Incluir/excluir valores"
>abstract="Filtre uma métrica para contar apenas os valores que correspondem a critérios específicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_dimension_includeexcludevalues"
>title="Incluir/excluir valores"
>abstract="Restrinja uma dimensão para incluir apenas valores que correspondam a critérios específicos. As inclusões e exclusões ocorrem antes da alocação e dos filtros nos relatórios.<br/><br/>**Parâmetros **<br/>**Diferenciar maiúsculas de minúsculas**: determine se a lógica de filtro abaixo diferencia maiúsculas de minúsculas."

<!-- markdownlint-enable MD034 -->



Valores de inclusão e exclusão permitem criar regras que dependem do valor de um item de dimensão. Valores que não atendem aos critérios definidos são tratados no Analysis Workspace como se nunca houvessem existido, embora os dados ainda existam no conjunto de dados subjacente.

![Janela de visualizações de dados destacando os valores de exclusão de Inclusão](../assets/include-exclude.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Definir a inclusão/exclusão de valores] | Uma caixa de seleção que permite ativar as condições em que dados são incluídos em uma visualização de dados. |
| [!UICONTROL Diferencia maiúsculas de minúsculas] | Visível nos dados de esquema do tipo String. Definido como ativado por padrão. Essa configuração se aplica somente à lógica dos [!UICONTROL Valores de Inclusão/Exclusão], não ao valor resultante. Permite especificar se a regra diferencia maiúsculas de minúsculas. |
| [!UICONTROL Corresponder] | Permite especificar quais valores você gostaria de considerar para os relatórios antes da atribuição e filtros (por exemplo, usar apenas valores contendo a frase &quot;erro&quot;). Você pode especificar **[!UICONTROL Se todos os critérios forem atendidos]** ou **[!UICONTROL Se algum critério for atendido]**. |
| [!UICONTROL Critérios] | Permite especificar a lógica de correspondência que deve ser aplicada a uma regra de filtro específica.<ul><li>**Sequência**: Contém a frase, Contém qualquer termo, Contém todos os termos, Não contém nenhum termo, Não contém a frase, É igual, Não é igual, Começa com, Termina com</li><li>**Duplo/Número inteiro**: é igual, não é igual, é maior que, é menor que, é maior que ou igual a, é menor que ou igual a</li><li>**Data**: é igual a, não é igual, é posterior a, é anterior, ocorre dentro de</li></ul> |
| [!UICONTROL Corresponder operando] | Permite especificar o operando correspondente ao qual o operador deve ser aplicado.<ul><li>**Sequência**: Campo de texto</li><li>**Duplo/Número inteiro**: Campo de texto com setas para cima/para baixo para valores numéricos</li><li>**Data**: Seletor de granularidade do dia (calendário)</li><li>**Data Hora**: Seletor de granularidade de data e hora</li></ul> |
| [!UICONTROL Adicionar regra] | Permite especificar um operador e um operando de correspondência adicional. |

{style="table-layout:auto"}
