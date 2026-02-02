---
title: Selecionar Um Intervalo De Dados No Report Builder
description: Saiba como selecionar um intervalo de datas no Report Builder.
role: User
feature: Report Builder
type: Documentation
exl-id: 7252214f-a7d6-451b-99c9-d39e8e47120b
solution: Customer Journey Analytics
source-git-commit: 31d3b40ad7a081aefa4297d7f4a3b986711ead03
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 50%

---

# Selecionar um intervalo de datas

Para alterar o intervalo de datas de um bloco de dados existente:

- Selecione **[!UICONTROL Editar um bloco de dados]** ou
- Selecione o link **[!UICONTROL Intervalo de datas]** em **[!UICONTROL Edição rápida]**.

Use as seguintes opções para alterar um intervalo de datas para um bloco de dados.

## Calendário

A opção **[!UICONTROL Calendário]** permite criar datas estáticas ou contínuas usando estas opções:

### Intervalo de datas

O campo Intervalo de datas exibe o intervalo de datas atual para a solicitação de bloco de dados. Você pode inserir datas diretamente ou usar o ![Calendário](/help/assets/icons/Calendar.svg) para especificar um intervalo de datas.

![Calendário de intervalo de datas](assets/date-range-calendar.png){zoomable="yes"}

### Predefinições

Use o menu suspenso Predefinições para selecionar uma predefinição. Também é possível digitar texto para procurar predefinições.

![Predefinições de intervalo de datas](assets/date-range-presets.png){zoomable="yes"}

O menu suspenso predefinido inclui um conjunto padrão de intervalos de datas predefinidos, além de componentes de intervalo de datas, para uma visualização de dados que você salvou ou para uma visualização de dados que foi compartilhada com você.

### Datas do acumulado

Para definir datas do acumulado:

![Datas do acumulado](assets/date-range-rolling-date.png){zoomable="yes"}

1. Selecione **[!UICONTROL Usar datas do acumulado]** para definir a lógica de uma definição de data do acumulado. É possível selecionar o texto entre parênteses (por exemplo, **[!UICONTROL início fixo - rolagem diária]**) para estender o painel e especificar detalhes para **[!UICONTROL Início]** e **[!UICONTROL Fim]**.

1. Selecione **[!UICONTROL Início de]**, **[!UICONTROL Fim de]** ou **[!UICONTROL Dia fixo]**.

   - Ao selecionar **[!UICONTROL Início de]** ou **[!UICONTROL Fim de]**, você pode criar uma expressão completa. Por exemplo: **[!UICONTROL Fim do]** **[!UICONTROL ano atual]** **[!UICONTROL mais]** `1` **[!UICONTROL dia]**. Escolha o valor apropriado para cada parte individual da expressão.

      - Selecione um valor para o atual. Por exemplo, **[!UICONTROL ano atual]**.
      - Selecione um valor para um cálculo adicional opcional. Por exemplo, **[!UICONTROL mais]**.
      - Após definir um cálculo adicional, especifique um valor. Por exemplo, `1`.
      - Depois de especificar um cálculo adicional, selecione o período a ser usado para o cálculo. Por exemplo, **[!UICONTROL dia]**.

   - Ao selecionar **[!UICONTROL Dia Fixo]**, especifique um dia fixo ou use o seletor para selecionar um dia.

1. Selecione **[!UICONTROL ocultar]** para ocultar os detalhes do cálculo das datas do acumulado.


### Expressões personalizadas

A opção de expressão personalizada permite alterar o intervalo de datas, criando uma expressão personalizada ou possibilitando a inserção de uma fórmula aritmética.

![Expressão personalizada de intervalo de datas](assets/date-range-custom-expression.png){zoomable="yes"}

1. Selecionar **[!UICONTROL Usar datas do acumulado]**.

1. Selecionar **[!UICONTROL Usar expressão personalizada]**.

   Ao selecionar **[!UICONTROL Usar expressão personalizada]**, os controles padrão de intervalo de datas do acumulado são desabilitados.

1. Insira uma [expressão personalizada](#create-a-custom-expression).

1. Use a **[!UICONTROL Visualização de data]** para verificar o intervalo de datas resultante.

#### Criar uma expressão personalizada

1. Insira uma [referência de data](#date-references).

1. Adicione um [operador de data](#date-operators) opcional para mover a data para o passado ou futuro.

Você pode inserir uma expressão personalizada que inclua vários operadores, como `tm-11m-1d`.

#### Referências de data

A tabela a seguir lista exemplos de referência de data.

| Referência de data | Tipo | Descrição |
|----------------|--------------|----------------------------|
| `1/1/10` | Data estática | Inserido no formato de Data ISO |
| `td` | Data do acumulado | Início do dia atual |
| `tw` | Data do acumulado | Início da semana atual |
| `tm` | Data do acumulado | Início do mês atual |
| `tq` | Data do acumulado | Início do trimestre atual |
| `ty` | Data do acumulado | Início do ano atual |

#### Operadores de data

A tabela a seguir lista exemplos de operadores de data.

| Operador de data | Unidade | Descrição |
|----------------|---------|--------------------|
| `+6d` | Dia | Adicionar 6 dias à referência de data |
| `+1w` | Semana | Adicionar uma semana inteira à referência de data |
| `-2m` | Mês | Subtrair 2 meses completos da referência da data |
| `-4q` | Trimestre | Subtrair 4 trimestres da referência de data |
| -`1y` | Ano | Subtrair um ano da referência de data |

#### Expressões de datas

A tabela a seguir lista exemplos de expressão de data.

| Expressão de data | Significado |
|-----------------|--------------------------------------|
| `td` | Hoje |
| `td-1w` | Primeiro dia da semana passada |
| `tm-1d` | Último dia do mês anterior |
| `td-52w` | Mesmo dia 52 semanas atrás |
| `tm-11m-1d` | Último dia do mesmo mês do ano passado |
| `"2020-09-06"` | Data específica, 9 de setembro de 2020 |



## Intervalo de datas da célula

O intervalo de datas pode ser especificado em células da planilha. Use a opção **[!UICONTROL Intervalo de datas da célula]** para escolher a data inicial e final do bloco de dados a partir das células selecionadas. Ao selecionar a opção **[!UICONTROL Da célula]**, o painel exibe os campos **[!UICONTROL De]** e **[!UICONTROL Para]**, nos quais você pode inserir um local de célula ou usar ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) para escolher a célula selecionada no momento.

![Selecionar da célula Folha1!H4 para Folha1!I4](./assets/date-range-from-cell.png){zoomable="yes"}


## Excluir hoje

Selecione **[!UICONTROL Excluir hoje]** para excluir hoje de um intervalo de datas selecionado. O dia atual é excluído de todos os modos usados para definir um intervalo de datas: calendário, datas do acumulado ou expressões personalizadas.


## Intervalos de datas válidos

A lista a seguir descreve formatos válidos de intervalo de datas.

- As datas inicial e final devem estar no seguinte formato: AAAA-MM-DD

- A data inicial deve ser anterior ou igual à data final. Ambas as datas podem ser definidas para o futuro.

- Ao usar datas em andamento, a data inicial deve ser hoje ou no passado. O dia de início deve estar no passado se **[!UICONTROL Excluir hoje]** estiver selecionado.

- É possível criar um intervalo de datas estático para o futuro. Por exemplo, talvez seja necessário definir uma data futura para um lançamento de campanha de marketing na próxima semana. Essa opção cria um monitoramento de pasta de trabalho para uma campanha antecipadamente.

## Alterar intervalo de datas

É possível editar o intervalo de datas de um bloco de dados existente.

1. Selecione uma célula em seu bloco de dados.

- Selecione **[!UICONTROL Editar bloco de dados]** no painel **[!UICONTROL Comandos]** ou
- Selecione o link **[!UICONTROL Intervalo de datas]** no painel **[!UICONTROL Edição rápida]**.

1. Modifique o intervalo de datas usando qualquer uma das opções de seleção de data disponíveis.

1. Selecione **[!UICONTROL Aplicar]**.

O Report Builder aplica o novo intervalo de datas a todos os blocos de dados na seleção.
