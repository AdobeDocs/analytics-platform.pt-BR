---
title: Criar filtros
description: Entenda a interface do usuário de criação de filtro.
translation-type: tm+mt
source-git-commit: 21bf268600c12dbf1db24dbc10028a0c29fc48a7
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 100%

---


# Criar filtros

O Construtor de filtros fornece uma tela para arrastar e soltar métricas, dimensões, filtros e eventos para filtrar visitantes com base na lógica, nas regras e nos operadores da hierarquia do contêiner. Essa ferramenta de desenvolvimento integrada permite construir e salvar filtros simples ou complexos que identificam os atributos e as ações do visitante nas visitas e ocorrências da página.

Você pode criar filtros instantâneos soltando qualquer tipo de componente (dimensão, item de dimensão, evento, métrica, segmento, modelo de segmento, intervalo de datas) na zona de soltar do filtro no topo de um painel.

Os tipos de componentes são convertidos automaticamente em filtros. Como alternativa, você pode clicar no sinal “+” na caixa de depósito **[!UICONTROL Adicionar filtro]**.

Lembre-se:

* **Não** é possível soltar os seguintes tipos de componentes na zona de filtros: métricas calculadas e dimensões/métricas a partir das quais você não pode criar filtros.
* Para dimensões e eventos completos, o Analysis Workspace cria filtros de ocorrência “existe”. Exemplos: “Ocorrência em que eVar1 existe” ou “Ocorrência em que event1 existe”.
* Se as opções “não especificado” ou “nenhum” forem soltas na zona de soltar dos filtros, serão automaticamente convertidas em um filtro “não existe” para que sejam tratadas corretamente.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>Filtros criados desse modo são internos no projeto.

Você pode escolher se deseja tornar os filtros públicos (globais) seguindo estas etapas:

1. Passe o mouse sobre o filtro no local onde os segmentos são colocados e clique no ícone “i”.
1. No painel de informações que é exibido, clique em **[!UICONTROL Tornar público]**.

   ![](assets/segment-info.png)

## Outros métodos para aplicar filtros

Existem vários outros métodos para aplicar os filtros a um projeto:

| Ação | Descrição |
|--- |--- |
| Criar filtro a partir da seleção | Criar um filtro em linha. Selecione as linhas, clique com o botão direito do mouse na seleção e crie um filtro em linha. Este filtro se aplica somente ao projeto aberto e não é salvo como um filtro CJA. 1. Selecione as linhas.  2. Clique com o botão direito na seleção.  3. Clique em *Criar filtro a partir da seleção*. |
| Componentes > Novo filtro | Exibe o Construtor de filtros. Consulte [Construtor de filtros](https://docs.adobe.com/content/help/pt-BR/analytics/components/segmentation/segmentation-workflow/seg-build.html) para obter mais informações sobre filtragem. |
| Compartilhar > Compartilhar projeto ou compartilhar > Preparar dados do projeto | Em [Preparar e compartilhar](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6) aprenda como os filtros que você aplica ao projeto estão disponíveis na análise compartilhada para o recipient. |
| Usar filtros como dimensões | Vídeo: Usar filtros como dimensões no Analysis Workspace |

>[!VIDEO](https://video.tv.adobe.com/v/23974)
