---
title: Adicionar eventos de atrito de Métrica quântica ao Customer Journey Analytics
description: Adicione profundidades aos insights no Customer Journey Analytics usando eventos de atrito coletados na Métrica quântica.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Adicionar eventos de atrito de Métrica quântica ao Customer Journey Analytics

A Métrica Quantum coleta eventos de atrito, como lentidão de carregamento de página, erros de carregamento de página, cliques de intervalo e muito mais. Esses eventos podem ser transmitidos para o Customer Journey Analytics como eventos complementares na jornada do usuário. Com esses dados combinados, é possível entender melhor o impacto do atrito nas métricas downstream.

## Pré-requisitos:

Este caso de uso tem dois requisitos:

* Você deve ter direito ao pacote **Dev Ops** da Métrica Quantum.
* Você deve usar tags na Coleção de dados da Adobe Experience Platform.

## Etapa 1: Capturar eventos de atrito usando a extensão de tag da Métrica Quantum

A equipe de CSM da Métrica Quantum pode ajudar você a determinar os elementos de esquema corretos para adicionar e instruir você a modificar sua implementação para coletar os dados desejados para uso no Customer Journey Analytics. Entre em contato com o gerente de sucesso do cliente da Métrica Quantum para obter mais informações.

Por fim, convém começar a rastrear o nome do evento de atrito em um campo.

## Etapa 2: Confirmar campos incluídos do conjunto de dados

Confirme se os conjuntos de dados na sua conexão agora têm a ID de sessão de Métrica quântica no conjunto de dados desejado.

## Etapa 3: adicionar uma ou mais dimensões e métricas à visualização de dados no Customer Journey Analytics

Edite sua visualização de dados existente para adicionar a ID da sessão como uma dimensão disponível no Customer Journey Analytics.

1. Faça logon em [experience.adobe.com](https://experience.adobe.com).
1. Navegue até Customer Journey Analytics e selecione **[!UICONTROL Visualizações de dados]**, como opção a partir de **[!UICONTROL Gerenciamento de dados]**, no menu superior.
1. Selecione a visualização de dados existente desejada.
1. Localize a lista de campos de evento de atrito Métrica quântica à esquerda e arraste-a para a área de métricas no centro.
1. No painel direito, defina a configuração [Incluir/Excluir valores](/help/data-views/component-settings/include-exclude-values.md) para os eventos de atrito desejados. É possível adicionar vários eventos de atrito à mesma métrica para combiná-los. Você também pode arrastar outra cópia do campo de eventos de atrito para a área de métricas para rastrear outros eventos de atrito como uma métrica separada.
1. Depois de criar todas as dimensões e métricas desejadas, clique em **[!UICONTROL Salvar]**.

## Etapa 4: use a dimensão e as métricas com o restante dos dados no Analysis Workspace

Com os dados do evento de atrito de Métrica quântica coletados junto com o restante dos dados do visitante, é possível usá-los exatamente como faria com qualquer outra dimensão ou métrica no Customer Journey Analytics.

1. Faça logon em [experience.adobe.com](https://experience.adobe.com).
1. Navegue até Customer Journey Analytics e selecione **[!UICONTROL Workspace]** no menu superior.
1. Selecione um projeto existente ou crie um projeto.
1. Crie uma [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Arraste as dimensões e métricas desejadas para a tela do Workspace para análise.

As possíveis ideias de análise são:

* Dados do evento de atrito de tendência ao longo do tempo
* Em uma visualização de fallout ou funil, adicione eventos do Customer Journey Analytics como algumas etapas e eventos de atrito de Métrica quântica como outros. Esse relatório permite ver onde os visitantes geralmente encontram problemas.
* Criar e aplicar um filtro para visitantes que experimentam eventos de atrito para análise mais profunda
