---
title: Configurações do componente de formato
description: Configure como uma métrica é formatada.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: a236b2126c4b998b4d97caab014556e3ee3a9e83
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 21%

---

# Configurações do componente de formato {#format-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_format"
>title="Formato"
>abstract="Determine como um componente é exibido quando usado em relatórios."

<!-- markdownlint-enable MD034 -->


O Formato permite determinar como uma determinada métrica é exibida quando usada em relatórios.

## Definir configurações de formato para uma métrica

Você pode determinar como uma determinada métrica é exibida ajustando suas configurações de formato.

1. No Customer Journey Analytics, selecione a guia [!UICONTROL **Visualizações de dados**].

1. Selecione a visualização de dados que contém o componente cuja configuração de formato você deseja configurar.

1. Selecione a guia [!UICONTROL **Componentes**].

1. Selecione o componente que você deseja configurar e expanda a seção [!UICONTROL **Formato**] no lado direito da página.

   ![Configurações de formato](../assets/format-settings.png)

1. Especifique as seguintes informações:

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Formato]** | Permite especificar a formatação de uma métrica como Decimal, Hora, Porcentagem ou Moeda. |
   | **[!UICONTROL Decimal]** | Isso não é visível nos dados de esquema do tipo Integer. Permite especificar o número de casas decimais que uma métrica deve exibir. |
   | **[!UICONTROL Data]** | Permite determinar como você deseja que o campo de data e hora seja exibido quando usado como uma dimensão no relatório. [Saiba mais](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Data e hora]** | Permite determinar como você deseja que o campo de data e hora seja exibido quando usado como uma dimensão no relatório. [Saiba mais](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Moeda]** | Permite determinar em qual moeda a métrica será exibida. <p>Se você analisar dados globais nos quais ocorrem transações em moedas diferentes, consulte [Usar conversão de moeda](#use-currency-conversion).</p> |
   | **[!UICONTROL Exibir tendência ascendente como]** | Permite especificar se uma tendência de alta nessa métrica é boa (verde) ou ruim (vermelho). |
   | **[!UICONTROL Valor verdadeiro]** e **[!UICONTROL Valor falso]** | Visível somente em dados de esquema do tipo Booleano. Permite personalizar o rótulo do item de dimensão para valores `true` e `false`. |

   {style="table-layout:auto"}

## Usar conversão de moeda

A conversão de moeda em Customer Journey Analytics pode ser extremamente valiosa para empresas que operam internacionalmente. Ao eliminar as complexidades da conversão manual de moeda, a conversão de moeda no Customer Journey Analytics traz uniformidade e clareza aos dados financeiros. A conversão de moeda acompanha as taxas de câmbio históricas diárias e mantém essas taxas diárias por um período de 4 anos.

Por exemplo, se uma empresa de comércio eletrônico operar nos EUA, Reino Unido e UE, os dados de vendas podem ser convertidos automaticamente para USD, garantindo uma fácil comparação e compreensão holística do desempenho.

>[!NOTE]
>
>Antes de começar a configurar uma métrica para conversão de moeda, considere o seguinte:
>
>* A métrica selecionada para conversão de moeda deve ter um tipo numérico (Duplo, Longo, Inteiro, Curto, Byte).
>* Configure sua conexão Customer Journey Analytics para conter pelo menos um conjunto de dados de evento que contenha uma dimensão de código de moeda para cada evento que contenha uma métrica de moeda. Essa dimensão de código de moeda usa um código de moeda alfabético em conformidade com o padrão [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) para representar moedas. Esses valores devem estar no formato totalmente em maiúsculas, como USD por $, EUR por €, GBP por £.

Para determinar como as moedas são exibidas e convertidas para uma determinada métrica:

1. Comece a configurar a métrica para a qual deseja usar moeda como o formato, conforme descrito acima em [Definir configurações de formato para uma métrica](#configure-format-settings-for-a-metric).

1. Com a métrica selecionada, faça as seguintes seleções na seção [!UICONTROL **Formato**] à direita da página:

   * No campo [!UICONTROL **Formato**], selecione [!UICONTROL **Moeda**].

   * No campo [!UICONTROL **Casas decimais**], escolha o número de casas decimais que a métrica exibirá.

     Essa opção só estará disponível se a métrica tiver um tipo numérico de &quot;Duplo&quot;.

   * Selecione a opção [!UICONTROL **Converter Moeda**].

   * No campo [!UICONTROL **Selecionar dimensão do código de moeda**], selecione a dimensão que representa a moeda da qual você está convertendo (a moeda em que seus dados se baseiam). Por exemplo, selecione uma dimensão chamada [!UICONTROL **Código monetário**].

     Se você não tiver uma dimensão em seu esquema de dados atual que contenha um campo de código monetário, poderá criar um novo campo de código monetário usando [Preparo de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR), [Distiller de dados](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html) ou [Campos derivados](/help/data-views/derived-fields/derived-fields.md). O Preparo de dados é adequado somente para novas implementações, pois é apenas progressivo. Dependendo da configuração de uma organização, o Data Distiller e os Campos derivados podem ser usados para acessar os valores do código monetário historicamente.

   * No campo [!UICONTROL **Converter e exibir moeda em**], escolha a moeda na qual deseja converter os dados.

1. Repita essas etapas se desejar aplicar a conversão de moeda a métricas adicionais.



### Perguntas frequentes

+++ Como a conversão de moeda é executada?

Após o tempo do relatório, o valor da métrica e o código de moeda original são convertidos em USD e, em seguida, convertidos na moeda configurada para exibição. Para essa conversão, são usadas as taxas de câmbio diárias da moeda, aplicáveis no momento do evento.

+++

