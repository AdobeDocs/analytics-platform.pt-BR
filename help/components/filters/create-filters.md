---
title: Criar filtros
description: Entenda a interface do usuário de criação de filtro.
translation-type: tm+mt
source-git-commit: 0c5bd5ce0b0ba4ba758a1ef1adf5a4a519e9cf8c
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 38%

---


# Criar filtros

O Construtor de filtros fornece uma tela para arrastar e soltar métricas, dimensões, filtros e eventos para filtrar visitantes com base na lógica, nas regras e nos operadores da hierarquia do contêiner. Essa ferramenta de desenvolvimento integrada permite construir e salvar filtros simples ou complexos que identificam os atributos e as ações do visitante nas visitas e ocorrências da página.

Você pode criar filtros instantâneos soltando qualquer tipo de componente (dimensão, item de dimensão, evento, métrica, segmento, modelo de segmento, intervalo de datas) na área de depósito de filtro na parte superior de um painel.

Os tipos de componentes são convertidos automaticamente em filtros. Alternatively, you can click the &quot;+&quot; sign in the **[!UICONTROL Add Filter]** drop box.

Lembre-se:

* You **cannot** drop the following component types into the filter zone: calculated metrics and dimensions/metrics from which you cannot build filters.
* Para dimensões e evento completos, o Analysis Workspace cria filtros de ocorrência &quot;existe&quot;. Exemplos: “Ocorrência em que eVar1 existe” ou “Ocorrência em que event1 existe”.
* Se &quot;não especificado&quot; ou &quot;nenhum&quot; for solto na zona de depósito do filtro, ele será automaticamente convertido em um filtro &quot;não existe&quot; para que seja tratado corretamente.

![](assets/segment-dropzone.png)

>[!NOTE] Filtros criados dessa forma são internos ao projeto.

Você pode optar por tornar esses filtros públicos (globais) seguindo estas etapas:

1. Passe o cursor do mouse sobre o filtro na zona para soltar e clique no ícone &quot;i&quot;.
1. No painel de informações que é exibido, clique em **[!UICONTROL Tornar público]**.

   ![](assets/segment-info.png)

## Outros métodos de aplicação de filtros

Existem vários outros métodos para aplicar filtros a um projeto:

| Ação | Descrição |
|--- |--- |
| Criar filtro a partir da seleção | Crie um filtro em linha. Selecione linhas, clique com o botão direito do mouse na seleção e crie um filtro em linha. Esse filtro se aplica somente ao projeto aberto e não é salvo como um filtro CJA. 1. Selecione as linhas.  2. Clique com o botão direito na seleção.  3. Click *Create filter from selection*. |
| Componentes > Novo filtro | Exibe o Construtor de filtro. See [Filter Builder](https://docs.adobe.com/content/help/pt-BR/analytics/components/segmentation/segmentation-workflow/seg-build.html) for more information about filtering. |
| Compartilhar > Compartilhar projeto ou compartilhar > Preparar dados do projeto | In [Curate and Share](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), learn how filters that you apply to the project are available in shared analysis for the recipient. |
| Usar filtros como dimensões | Vídeo: [Usar segmentos como Dimensões no Analysis Workspace](https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39) |
