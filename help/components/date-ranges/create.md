---
title: 'Criar intervalos de datas '
description: Criar um intervalo de datas para uso em relatórios.
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
role: User
source-git-commit: 3f9c185c86f2ae2727881d0d74ca54815867adb1
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 81%

---

# Criar intervalos de datas 


Qualquer pessoa pode criar um intervalo de datas personalizado. Um intervalo de datas pode ser criado das seguintes maneiras:

![Criar uma anotação](assets/create-date-range.png)

* **A** - Na interface principal, selecione **[!UICONTROL Componentes]** e selecione **[!UICONTROL Intervalo de datas]**. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Adicionar]** no gerenciador de [[!UICONTROL Intervalo de datas]](/help/components/date-ranges/manage.md).
* **B** - Em um projeto do Workspace, no menu de contexto em uma visualização, selecione **[!UICONTROL Intervalo de datas personalizado para este intervalo de datas]**.
* **C** - Em um projeto do Workspace, selecione **[!UICONTROL Componentes]** no menu e selecione **[!UICONTROL Criar intervalo de datas]**
* **D** - Em um projeto do Workspace, use o atalho **[!UICONTROL ctrl+shift+d]** (Windows) ou **[!UICONTROL shift+command+d]** (macOS).
* **E** - Em um projeto do Workspace, no painel esquerdo Componentes, selecione ![Adicionar](/help/assets/icons/Add.svg) em ![Calendário](/help/assets/icons/Calendar.svg) **Intervalos de datas**.
* **F** - Em uma visualização com suporte, como uma visualização de linha, no menu de contexto de um ponto de dados, selecione **[!UICONTROL Anotar Seleção]**.

Para definir a anotação, use o [[!UICONTROL Criador de intervalos de datas]](#annotation-builder):

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## Construtor de intervalo de datas {#date-range-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_dateranges_endtime"
>title="Horário de término"
>abstract="Os horários de término sempre incluem 59 segundos."

<!-- markdownlint-enable MD034 -->




A caixa de diálogo **[!UICONTROL Novo intervalo de datas]** ou **[!UICONTROL Editar intervalo de datas]** é usada para criar novos intervalos de datas ou editar intervalos de datas existentes.

![Janela de detalhes da anotação mostrando campos e opções descritos na próxima seção.](assets/edit-date-range.png)


1. Especifique um **[!UICONTROL Título]** para o intervalo de datas Por exemplo, **[!UICONTROL Trimestral]**.
1. Opcionalmente, especifique uma **[!UICONTROL Descrição]**.
1. Organize o filtro, criando ou aplicando uma ou mais **[!UICONTROL Tags]**.  Comece a digitar para encontrar as tags existentes que você pode selecionar. Ou pressione **[!UICONTROL ENTER]** para adicionar uma nova tag. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover uma tag.
1. Selecione um **[!UICONTROL Intervalo de datas]**, escolhendo primeiro a data inicial e, em seguida, a data final.
Também é possível selecionar uma **[!UICONTROL predefinição]** no menu suspenso [!UICONTROL *Selecionar uma predefinição*].

1. Ou selecione **[!UICONTROL Mostrar configurações avançadas]** para:

   * Especificar uma **[!UICONTROL Hora de início]** e **[!UICONTROL Hora de término]** diferentes das opções padrão `12:00 AM` (`0:00`) e `11:59 PM` (`23:59`). Os horários de término sempre incluem 59 segundos. No caso de um intervalo de datas que abrange muitos dias, a hora inicial se aplica ao primeiro dia do intervalo de datas, e a hora final se aplica ao último dia do intervalo de datas. Use **[!UICONTROL (Redefinir valores de tempo)]** para redefinir os valores padrão de hora inicial e final.
   * **[!UICONTROL Usar datas contínuas]**. Se habilitado, os intervalos de datas predefinidos, como **[!UICONTROL Últimos 7 dias completos]**, serão atualizados dinamicamente de acordo com a data e hora atuais. Se desabilitada, essas predefinições não são atualizadas depois de aplicadas.

     É possível selecionar o texto entre parênteses (por exemplo, **[!UICONTROL início fixo: acumulado trimestralmente]**) para estender o painel e especificar os detalhes de **[!UICONTROL Início]** e **[!UICONTROL Fim]**.

     ![Datas contínuas](assets/rolliing-dates.png)

      1. Selecione **[!UICONTROL Início de]**, **[!UICONTROL Fim de]** ou **[!UICONTROL Dia fixo]**.
      1. Ao selecionar **[!UICONTROL Início de]** ou **[!UICONTROL Fim de]**, você pode criar uma expressão completa. Por exemplo: **[!UICONTROL Fim do]** **[!UICONTROL trimestre atual]** **[!UICONTROL menos]** `20` **[!UICONTROL dias]**.  Escolha o valor apropriado para cada parte individual da expressão.
         * Selecione um valor para o atual. Por exemplo, **[!UICONTROL trimestre atual]**.
         * Selecione um valor para o cálculo adicional. Por exemplo, **[!UICONTROL menos]**.
         * Após definir um cálculo adicional, especifique um valor. Por exemplo, `20`.
         * Depois de especificar um cálculo adicional, selecione o período a ser usado para o cálculo. Por exemplo, **[!UICONTROL dias]**.

     Selecione **[!UICONTROL Ocultar detalhes]** para ocultar os detalhes do cálculo de datas contínuas.

1. Selecione:
   * **[!UICONTROL Salvar]** para salvar o intervalo de datas.
   * **[!UICONTROL Salvar como]** para salvar uma cópia do intervalo de datas.
   * **[!UICONTROL Cancelar]** para cancelar quaisquer alterações feitas em um intervalo de datas ou a criação de um novo intervalo de datas.


<!--


You can create a date range using either of the following two methods:

* Directly in a workspace project by clicking the '`+`' button next to the list of date range components on the left
* Within the date range manager

To create a date range in the date range manager:

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your AdobeID credentials.
1. Navigate to [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Click the [!UICONTROL Add] button to open the modal window that creates a date range.

## Create a date range modal window

The modal window has four fields you can edit:

* **Date range**: The date range you want for this component.
* **Title**: The name you want for this component. The title is used in workspace projects.
* **Description**: The description you want for this component. The description is seen when clicking the ![i](../assets/i.png) icon.
* **Tags**: Use tags to organize your date ranges. A date range can belong to multiple tags.

## Selecting a date range

When clicking the date range in the modal window, you have several options:

* **Calendar**: Select the start and end date.
* **Use rolling dates**: Check this box if you want the date range to change as time goes on. Do not check this box if you want your date range to remain static.
* **Select preset**: Use this drop-down selection if you want a custom date range based on a range that Adobe offers by default. When you select a preset, you can further customize the date range to suit your needs. It does not affect the preset that Adobe offers.

## Rolling date ranges

If you want a rolling date range, you can customize when it rolls. You can control when the start and end dates roll independently of each other.

* **When the date starts**: Choose if the date starts at the beginning of a time period, at the end of a time period, or use a fixed day.
* **The time period to use**: Choose how often the date range rolls. You can have it roll every day, every week, every month, every quarter, or every year.
* **Offset**: Choose the offset of the date range. You can add or subtract days, weeks, months, quarters, or years.

## Rolling date examples

Some date ranges can be useful in certain reports.

Year-to-date:

```text
Start: Start of current year
End: End of current day
```

Last Thursday to this Thursday:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Fiscal year (for example, if a fiscal year starts in December)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```


-->
