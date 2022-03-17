---
description: Usar filtros ad hoc no Analysis Workspace.
title: Filtros de projeto ad hoc
feature: CJA Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
source-git-commit: 5743bece216431fecc073528ca2509cd2ed72f2b
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 54%

---

# Filtros de projeto ad hoc

Os filtros de projeto ad-hoc permitem arrastar e soltar qualquer componente diretamente na área de soltar do painel para criar um filtro. O filtro se torna um [filtro de nível de projeto](https://experienceleague.adobe.com/docs/analytics-platform/analysis-workspace/components/filters/quick-filters.html?#what-are-project-only-segments) local para o projeto atual.

Aqui está um vídeo sobre como criar filtros de projeto ad hoc:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)


1. 
   1. Solte qualquer tipo de componente (dimensão, item de dimensão, evento, métrica, segmento, modelo de segmento, intervalo de datas) na zona de soltar de filtro na parte superior de um painel. Os tipos de componentes são convertidos automaticamente em filtros ad-hoc ou [Filtros rápidos](/help/components/filters/quick-filters.md) se compatível.

   Aqui está um exemplo de como criar um filtro para o domínio referenciador do Twitter:

   ![](assets/ad-hoc1.png)

   O painel aplica esse filtro automaticamente e os resultados podem ser vistos instantaneamente.

1. Você pode adicionar um número ilimitado de filtros a um painel.
1. Se decidir salvar esse filtro, consulte a seção abaixo.

Lembre-se:

* **Não** é possível soltar os seguintes tipos de componentes na zona de filtros: métricas calculadas e dimensões/métricas a partir das quais você não pode criar filtros.
* Para dimensões e eventos completos, o Analysis Workspace cria filtros de ocorrência “existe”. Exemplos: `Hit where eVar1 exists` ou `Hit where event1 exists`.
* Se “não especificado” ou “nenhum” forem soltos na área de destino do filtro, eles serão automaticamente convertidos em um filtro “não existe” para que sejam tratados corretamente durante a filtragem.

## Salvar filtros de projeto ad hoc {#ad-hoc-save}

Você pode optar por salvar esses filtros seguindo estas etapas:

1. Passe o mouse sobre o filtro no local onde os segmentos são colocados e clique no ícone “i”.
1. Clique no lápis de edição para acessar o Construtor de filtros.
1. Verificar **[!UICONTROL Disponibilizar para todos os projetos e adicionar à lista de componentes]**.
1. Clique em **[!UICONTROL SALVAR]**.

Depois de salvo, o filtro fica disponível na lista de componentes do painel esquerdo e pode ser compartilhado com outros usuários no Gerenciador de filtros.

