---
description: Saiba como os administradores podem adicionar descrições aos componentes usando uma visualização de dados ou o dicionário de dados.
title: Adicionar descrições de componentes
feature: Components
role: Admin
exl-id: 99d531cd-50e9-4e6c-adad-a66b606fd877
TQID: 'https://experienceleague.adobe.com/yXxEhHsXsAw-l9c0oVCNDtwoCUq86UZSnyiwvidKLWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
    internal-label: Data Dictionary
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b46a27ff9faca74c3c2baa7938a588b643633705
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 10%
---
# Adicionar descrições de componentes

As descrições ajudam os usuários a saber como usar os vários componentes ao criar projetos no Analysis Workspace ou ao visualizar relatórios.

Os administradores do Customer Journey Analytics podem adicionar descrições de componentes (dimensões, métricas, segmentos e intervalos de datas) em uma visualização de dados ou usando o Dicionário de dados.

## Visualização de dados

É possível adicionar uma descrição a um componente adicionado à visualização de dados. Consulte [Configurações do componente](/help/data-views/component-settings/overview.md).

## Dicionário de dados

O Dicionário de dados no Analysis Workspace ajuda os usuários e administradores a rastrear e entender melhor os componentes em seu ambiente Customer Journey Analytics. O Dicionário de dados permite que os administradores adicionem descrições de componentes diretamente no Analysis Workspace.

Para obter informações sobre como editar uma descrição de componente no dicionário de dados, consulte [Editar entradas de componente no Dicionário de Dados](/help/components/data-dictionary/edit-entries-data-dictionary.md).

Para obter informações gerais sobre o Dicionário de Dados, consulte a [visão geral do Dicionário de Dados](/help/components/data-dictionary/data-dictionary-overview.md).

>[!MORELIKETHIS]
>
>[Configurações do componente de visualização de dados](/help/data-views/component-settings/overview.md)
>[Entradas do componente do dicionário de dados](/help/components/data-dictionary/edit-entries-data-dictionary.md)
>

## Gerar descrições automaticamente

{{release-limited-testing-section}}

Em vez de escrever cada descrição manualmente, o Customer Journey Analytics pode usar a IA gerativa para escrever descrições para você. Você pode gerar uma descrição para um único componente ou gerar descrições para muitos componentes ao mesmo tempo.

Descrições geradas:

* Não têm mais de 3 frases de comprimento.
* Termine com o texto **[!UICONTROL Gerado pelo Adobe usando a IA]**, para que os usuários saibam que a descrição foi gerada.
* Podem ser editadas depois de geradas.

### Pré-requisitos

Antes de gerar descrições, sua organização deve concordar com determinados termos legais de IA generativa. Se sua organização não tiver concordado com esses termos, a opção para gerar descrições ficará esmaecida. Selecione o ícone de informações ![Informações](/help/assets/icons/InfoOutline.svg) ao lado da opção para saber como habilitar o recurso ou entre em contato com o administrador da organização ou com a equipe de conta da Adobe.

### Como as descrições são geradas

As descrições geradas são baseadas na definição do componente e em contexto adicional sobre como o componente é usado na visualização de dados, como:

* Os itens principais de uma dimensão
* Componentes usados com frequência com o componente

Quando uma métrica calculada ou segmento faz referência a outro segmento, a descrição gerada explica a definição do segmento referenciado.

### Gerar descrições de vários locais

Você pode gerar descrições nas seguintes áreas do Customer Journey Analytics. Alguns locais permitem gerar descrições para vários componentes, enquanto outros não.

Selecione um local para saber como gerar descrições.

| Localização | Componentes compatíveis | Componente único | Vários componentes |
| --- | --- | --- | --- |
| [Dicionário de dados](/help/components/data-dictionary/edit-entries-data-dictionary.md) | <ul><li>Dimensões</li><li>Métricas</li><li>Métricas calculadas</li><li>Segmentos</li><li>Intervalos de datas</li></ul> | Sim | Sim |
| [Visualização de dados](/help/data-views/component-settings/overview.md) | <ul><li>Dimensões</li><li>Métricas</li><li>Campos derivados</li><li>Métricas e dimensões compartilhadas (Para obter mais informações, consulte [Métricas e dimensões compartilhadas](#generate-descriptions-for-shared-metrics-and-dimensions).)</li></ul> | Sim | Sim |
| [Construtor de segmentos](/help/components/segments/seg-builder.md) | Segmentos | Sim | Não |
| [Gerenciador de segmentos](/help/components/segments/seg-manage.md#action-bar) | Segmentos | Não | Sim |
| [Construtor de métrica calculada](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) | Métricas calculadas | Sim | Não |
| [Gerenciador de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-manager.md#action-bar) | Métricas calculadas | Não | Sim |
| [Construtor de intervalo de datas](/help/components/date-ranges/create.md#date-range-builder) | Intervalos de datas | Sim | Não |
| [Gerenciador de intervalos de datas](/help/components/date-ranges/manage.md#action-bar) | Intervalos de datas | Não | Sim |

{style="table-layout:auto"}

### Gerar descrições para métricas e dimensões compartilhadas

Você pode gerar descrições para métricas e dimensões compartilhadas somente de uma visualização de dados, conforme mostrado na tabela em [Gerar descrições de vários locais](#generate-descriptions-from-various-locations). Você não pode gerar descrições do [Gerenciador de métricas e dimensões compartilhado](/help/data-views/shared-metrics-dimensions/smd-overview.md#smd-manager).

Considere o seguinte ao gerar uma descrição para uma métrica ou dimensão compartilhada em uma visualização de dados:

* A descrição se aplica a todas as visualizações de dados em que o componente é compartilhado e substitui qualquer descrição existente desse componente em todas as outras visualizações de dados e no gerenciador de Métricas e dimensões compartilhadas.

* A descrição é baseada no contexto da visualização de dados em que você a gera (como os itens de dimensão principais da visualização de dados).


