---
title: Configurações do componente Opções de valor nulo
description: Determine como tratar uma dimensão se ela estiver vazia.
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 1a696662f10fddd42f3bbdbb79a6e735bf203bdf
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 53%

---

# Configurações do componente Opções de valor nulo {#no-value-options-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_novalueoptions"
>title="Sem opções de valor"
>abstract="Configure o comportamento padrão para quando nenhum valor estiver presente em uma dimensão."

<!-- markdownlint-enable MD034 -->


[!UICONTROL Nenhuma opção de valor] permite determinar como o Analysis Workspace trata situações em que um evento em um conjunto de dados contém uma métrica, mas a dimensão não continha um valor. Permite escolher o nome desse item de dimensão, ocultá-lo totalmente ou até mesmo tratá-lo como um valor real.

![Sem opções de valor](../assets/no-value-options.png)

## Configurações  {#settings}

| Configuração | Descrição |
| --- | --- |
| **[!UICONTROL Se exibido, chamar de “Valor nulo”]** | Um campo de texto que permite dar um outro nome para o item de dimensão **[!UICONTROL Valor nulo]**. |
| **[!UICONTROL Não mostrar &quot;Nenhum valor&quot; por padrão]** | Não mostra esse valor nos relatórios. Ocorrências de métrica não vinculadas a essa dimensão não são visíveis no relatório. |
| **[!UICONTROL Mostrar &quot;Nenhum valor&quot; por padrão]** | Mostra esse valor nos relatórios. |
| **[!UICONTROL Tratar &quot;Nenhum valor&quot; como um valor]** | (Sem suporte para dimensões numéricas) Substitui valores em branco nos dados pelo texto especificado em [!UICONTROL Se exibido, chame &quot;Nenhum valor&quot;]. Por exemplo, se você tiver tipos de dispositivo móvel como a dimensão, poderá renomear o item **[!UICONTROL Nenhum valor]** para &quot;Desktop&quot;. Ao alterar este campo para um valor personalizado, ele será tratado como um valor legítimo de sequência de caracteres. Portanto, se você inserir o valor &quot;Vermelho&quot; nesse campo, qualquer instância da sequência &quot;Vermelho&quot; que for mostrada nos próprios dados também será inserida sob o mesmo item da linha especificado. |

## Suporte a &quot;Nenhum valor&quot; para dimensões numéricas {#numeric}

Ao usar um valor numérico como uma dimensão, você pode

* Configure a opção &quot;Nenhum valor&quot; em uma visualização de dados. Observe que todas as configurações mostradas acima são suportadas, exceto para **[!UICONTROL Tratar &quot;Nenhum valor&quot; como um valor]**.
* Use **[!UICONTROL Incluir &quot;Nenhum valor&quot;]** para dimensões numéricas em uma tabela de Forma livre no Workspace.
* No Construtor de filtros, use os operadores **[!UICONTROL existe]** ou **[!UICONTROL não existe]** com dimensões numéricas.


>[!MORELIKETHIS]
>
>Esta é uma postagem de blog relacionada sobre [manipulação de &quot;nenhum valor&quot; no Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/handling-quot-no-value-quot-in-customer-journey-analytics/ba-p/597339).

