---
title: Configurações do componente de formato
description: Configure como uma métrica é formatada.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 6fdb6cbd6f12a0417f513565b02e3ad60c8df6cb
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 88%

---

# Configurações do componente de formato {#format-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format"
>title="Formato"
>abstract="Determine como um componente é exibido quando usado em relatórios."

<!-- markdownlint-enable MD034 -->


O Formato permite determinar como um determinado componente é exibido quando usado em relatórios.

## Definir configurações de formato para um componente

Você pode determinar como um determinado componente é exibido ajustando suas configurações de formato.

1. No Customer Journey Analytics, acesse a guia [!UICONTROL **Exibições de dados**].

1. Selecione a exibição de dados que contém o componente cuja configuração de formato você deseja definir.

1. Selecione a guia [!UICONTROL **Componentes**].

1. Selecione o componente que você deseja configurar e expanda a seção [!UICONTROL **Formato**] no lado direito da página.

   ![Configurações de formato](../assets/format-settings.png)

1. Especifique as seguintes informações:

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Formato]** | Permite especificar a formatação de um componente como Decimal, Hora, Porcentagem ou Moeda. |
   | **[!UICONTROL Decimal]** | Isso não é visível nos tipos de dados Integer do esquema. Permite especificar o número de casas decimais que um componente exibe. |
   | **[!UICONTROL Data]** | Permite determinar como você deseja que o campo de data e hora seja exibido quando usado como uma dimensão no relatório. [Saiba mais](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Data e hora]** | Permite determinar como você deseja que o campo de data e hora seja exibido quando usado como uma dimensão no relatório. [Saiba mais](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Moeda]** | Permite determinar em qual moeda o componente será exibido. <p>Se você analisar dados globais onde as transações ocorrem em moedas diferentes, consulte  [Usar conversão de moeda](#use-currency-conversion).</p> |
   | **[!UICONTROL Exibir tendência ascendente como]** | Permite especificar se uma tendência de alta neste componente é boa (verde) ou ruim (vermelho). |
   | **[!UICONTROL Valor verdadeiro]** e **[!UICONTROL Valor falso]** | Visível somente em tipos de dados Boolean do esquema. Permite personalizar o rótulo do item de dimensão para valores `true` e `false`. |

   {style="table-layout:auto"}

## Usar conversão de moeda {#use-currency-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format_currencyconversion"
>title="Conversão de moeda"
>abstract="Selecione uma dimensão de código de moeda para configurar e exibir a moeda no tipo de moeda selecionado."

<!-- markdownlint-enable MD034 -->

A conversão de moeda no Customer Journey Analytics pode ser extremamente valiosa para empresas que operam internacionalmente. Ao eliminar as complexidades da conversão manual de moeda, a conversão de moeda no Customer Journey Analytics proporciona uniformidade e clareza aos dados financeiros. A conversão de moeda acompanha as taxas de câmbio históricas diárias e mantém essas taxas diárias por um período de 4 anos.

Por exemplo, se uma empresa de comércio eletrônico operar nos EUA, no Reino Unido e na UE, os dados de vendas podem ser convertidos automaticamente para USD, garantindo uma fácil comparação e compreensão holística do desempenho.

>[!NOTE]
>
>Antes de começar a configurar uma métrica para conversão de moeda, considere o seguinte:
>
>* A métrica selecionada para conversão de moeda deve ter um tipo numérico (Duplo, Longo, Inteiro, Curto, Byte).
>* Configure sua conexão com o Customer Journey Analytics para conter pelo menos um conjunto de dados de evento que contenha uma dimensão de código de moeda para cada evento que contenha uma métrica de moeda. Essa dimensão de código de moeda usa um código de moeda alfabético em conformidade com o padrão [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) para representar moedas. Esses valores devem estar no formato totalmente em maiúsculas, como USD para $, EUR para €, GBP para £.

Para determinar como as moedas são exibidas e convertidas para uma determinada métrica:

1. Comece a configurar a métrica para a qual deseja usar moeda como o formato, conforme descrito acima em [Definir configurações de formato para uma métrica](#configure-format-settings-for-a-metric).

1. Com a métrica selecionada, faça as seguintes seleções na seção [!UICONTROL **Formato**] à direita da página:

   * No campo [!UICONTROL **Formato**], selecione [!UICONTROL **Moeda**].

   * No campo [!UICONTROL **Casas decimais**], escolha o número de casas decimais que a métrica exibirá.

     Essa opção só estará disponível se a métrica tiver um tipo numérico de “Duplo”.

   * Selecione a opção [!UICONTROL **Converter moeda**].

   * No campo [!UICONTROL **Selecionar dimensão de código de moeda**], selecione a dimensão que representa a moeda da qual você está convertendo (a moeda na qual seus dados são baseados). Por exemplo, selecione uma dimensão chamada [!UICONTROL **Código monetário**].

     Se você não tiver uma dimensão em seu esquema de dados atual que contenha um campo de código monetário, será possível criar um novo campo de código monetário usando [Preparo de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-prep/home), [Destilador de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/query/data-distiller/overview) ou [Campos derivados](/help/data-views/derived-fields/derived-fields.md). O Preparo de dados é adequado somente para novas implementações, pois é apenas progressivo. Dependendo da configuração de uma organização, o Destilador de dados e os Campos derivados podem ser usados para acessar os valores do código monetário historicamente.

   * No campo [!UICONTROL **Converter e exibir moeda em**], escolha a moeda na qual deseja converter os dados.

1. Repita essas etapas se desejar aplicar a conversão de moeda a métricas adicionais.



### Perguntas frequentes

+++ Como a conversão de moeda é executada?

Após o tempo do relatório, o valor da métrica e o código monetário original são convertidos em USD e, em seguida, convertidos na moeda configurada para exibição. Para essa conversão, são usadas as taxas de câmbio diárias da moeda, aplicáveis no momento do evento.

+++

