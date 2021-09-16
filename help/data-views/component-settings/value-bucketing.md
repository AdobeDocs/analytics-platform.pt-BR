---
title: Configurações do componente de divisão de valores
description: Combine valores numéricos em uma dimensão.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 12%

---


# Configurações do componente de Registro de Valor

Ao criar ou editar uma visualização de dados, a divisão de valores permite combinar valores numéricos com base em um intervalo. Ela só está disponível para dimensões que usam os tipos de dados Integer ou Double schema .

A divisão de valores é importante quando você deseja agrupar intervalos em vez de tratar cada número exclusivo como um item de dimensão separado. Por exemplo, um bucket de &quot;Entre 5 e até 10&quot; aparece como um item de linha &quot;5 a 10&quot; no Analysis Workspace.

![Classificação de valor](../assets/value-bucketing.png)

Se você quiser a flexibilidade de relatórios em uma dimensão segmentada e não segmentada, arraste duas cópias do componente para a lista de dimensões disponíveis. Ative o particionamento em uma dimensão e desative-a na outra.

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Valor do bloco] | Uma caixa de seleção que permite habilitar o agrupamento. |
| [!UICONTROL Menos que] | O limite superior do primeiro bucket de dimensão. |
|  [!UICONTROL Inclusão e menor que] | Limites de compartimentos subsequentes. |
| [!UICONTROL Maior que ou igual a] | O limite inferior do último bucket de dimensão. |
| [!UICONTROL Adicionar bloco] | Permite adicionar outro intervalo à classificação de dimensão numérica. Você pode adicionar até 20 buckets em uma única dimensão. |
