---
title: Configurações do componente de formato
description: Configure como uma métrica é formatada.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 32%

---

# Configurações do componente de formato

O Formato permite definir como uma determinada métrica é exibida.

![Configurações de formato](../assets/format-settings.png)

| Configuração | Descrição |
| --- | --- |
| **[!UICONTROL Formato]** | Permite especificar a formatação de uma métrica como Decimal, Hora, Porcentagem ou Moeda. |
| **[!UICONTROL Casas decimais]** | Isso não é visível nos dados de esquema do tipo Integer. Permite especificar o número de casas decimais que uma métrica deve exibir. |
| **[!UICONTROL Data]** | Permite determinar como você deseja que o campo de data e hora seja exibido quando usado como uma dimensão no relatório. [Saiba mais](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL Data e hora]** | Permite determinar como você deseja que o campo de data e hora seja exibido quando usado como uma dimensão no relatório. [Saiba mais](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL Moeda]** | Permite determinar em qual moeda a métrica será exibida. Consulte [Moeda](#currency) mais detalhes. |
| **[!UICONTROL Exibir tendência ascendente como]** | Permite especificar se uma tendência de alta nessa métrica é boa (verde) ou ruim (vermelho). |
| **[!UICONTROL Valor verdadeiro]** e **[!UICONTROL Valor falso]** | Visível somente em dados de esquema do tipo Booleano. Permite personalizar o rótulo do item de dimensão para valores `true` e `false`. |

{style="table-layout:auto"}


## Moeda

Ao selecionar **[!UICONTROL Moeda]** como o [!UICONTROL Formato] para uma métrica, você pode determinar como exibir e converter moedas.

### Exibir moeda

Para exibir uma moeda para uma métrica:

1. Insira o número de **[!UICONTROL Casas decimais]**.

2. Selecione uma moeda na caixa **[!UICONTROL Exibir moeda em]** lista.


### Converter e exibir moeda

[!BADGE Novo recurso]{type=Positive}

{{release-limited-testing-section}}

Para ativar a conversão de uma moeda para uma métrica:

- Configure sua conexão Customer Journey Analytics para conter pelo menos um conjunto de dados de evento que contenha uma dimensão de código de moeda para cada evento que contenha uma métrica de moeda. Essa dimensão de código monetário usa um código monetário alfabético em conformidade com a [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) padrão para representação de moedas. Por exemplo, USD por $, EUR por €, GBP por £.

- Você aplicou (opcionalmente) a variável [!UICONTROL Código de moeda] rótulo de contexto para uma ou mais dimensões que definem códigos monetários disponíveis em seu conjunto de dados.

  Para aplicar o [!UICONTROL Código de moeda] rótulo de contexto, no campo [!UICONTROL Componentes] da sua Visualização de dados:

  <!--![Currency Context Label](../assets/currency-context-label.png)-->

   1. Selecione a dimensão de um de seus conjuntos de dados que contém os códigos monetários. Por exemplo, [!UICONTROL Código de moeda].

   2. Selecionar **[!UICONTROL Código de moeda]** do [!UICONTROL Rótulos de contexto] lista.

  Repita essas etapas caso tenha mais dimensões com códigos de moeda que deseja usar para a conversão de moeda.

>[!NOTE]
>
>A métrica selecionada para conversão de moeda deve ter um tipo numérico (Duplo, Longo, Inteiro, Curto, Byte).


Para definir como converter e exibir uma moeda para uma métrica:

1. Insira o número de **[!UICONTROL Casas decimais]**.

2. Selecionar **[!UICONTROL Converter Simultaneidade]**.

3. Com base no rótulo de contexto aplicado, a dimensão apropriada do **[!UICONTROL Dimensão do código de moeda]** é selecionada automaticamente. É possível selecionar qualquer outra dimensão, incluindo dimensões às quais você aplicou adicionalmente o rótulo de contexto Código monetário.

4. Selecione uma moeda na caixa **[!UICONTROL Converter e exibir moeda em]** lista.

### Perguntas frequentes

+++ Como a conversão de moeda é executada?

Após o tempo do relatório, o valor da métrica e o código de moeda original são convertidos em USD e, em seguida, convertidos na moeda configurada para exibição. Para essa conversão, são usadas as taxas de câmbio diárias da moeda, aplicáveis no momento do evento.

+++

