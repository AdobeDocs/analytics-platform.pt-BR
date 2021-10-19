---
description: Usar filtros ad hoc no Analysis Workspace.
title: Filtros de projeto ad hoc
feature: Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
source-git-commit: 5877c7a39605f7a5ce1f84673dbd4123762ccc61
workflow-type: ht
source-wordcount: '370'
ht-degree: 100%

---

# Filtros de projeto ad hoc

Aqui está um vídeo sobre como criar filtros de projeto ad hoc:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

É possível criar filtros de projeto ad hoc caso queira explorar rapidamente como um filtro pode afetar o projeto, sem acessar o Construtor de segmentos. Pense nesses filtros como temporários, baseados em projetos. Normalmente, eles não farão parte da “biblioteca” de filtros, como os filtros de componentes no painel esquerdo. No entanto, é possível salvá-los, conforme mostrado abaixo.

Para uma comparação do que os filtros de projeto ad hoc podem fazer com relação aos filtros completos baseados em componente, acesse [aqui](/help/components/filters/filters-overview.md).

1. Solte qualquer tipo de componente (dimensão, item de dimensão, evento, métrica, filtro, modelo de filtro, intervalo de datas) dentro da área de destino do filtro, na parte superior de um painel. Os tipos de componentes são convertidos automaticamente em filtros.
Aqui está um exemplo de como criar um filtro para o domínio referenciador do Twitter:

   ![](assets/ad-hoc1.png)

   O painel aplica esse filtro automaticamente e os resultados podem ser vistos instantaneamente.

1. Você pode adicionar um número ilimitado de componentes a um painel.
1. Se decidir salvar esse filtro, consulte a seção abaixo.

Lembre-se:

* **Não** é possível soltar os seguintes tipos de componentes na zona de filtros: métricas calculadas e dimensões/métricas a partir das quais você não pode criar filtros.
* Para dimensões e eventos completos, o Analysis Workspace cria filtros de ocorrência “existe”. Exemplos: `Hit where eVar1 exists` ou `Hit where event1 exists`.
* Se “não especificado” ou “nenhum” forem soltos na área de destino do filtro, eles serão automaticamente convertidos em um filtro “não existe” para que sejam tratados corretamente durante a filtragem.

>[!NOTE]
>
>Segmentos criados desse modo são internos no projeto.

## Salvar filtros de projeto ad hoc {#ad-hoc-save}

Você pode optar por salvar esses filtros seguindo estas etapas:

1. Passe o mouse sobre o filtro no local onde os segmentos são colocados e clique no ícone “i”.
1. No painel de informações que for exibido, clique em **[!UICONTROL Salvar]**.

   ![](assets/segment-info.png)

## O que são filtros exclusivos de projeto?

Filtros exclusivos de projeto são filtros rápidos ou filtros de projeto ad hoc do Workspace. Ao editá-los/abri-los no construtor de filtros, a caixa exclusivo de projeto será exibida. Se eles APLICAREM um filtro rápido no construtor, mas não marcarem a caixa para disponibilizá-lo, ele ainda será um filtro exclusivo de projeto, mas não poderá mais ser aberto no construtor de QS. Se eles marcarem a caixa e SALVAREM, agora ele será um filtro de lista de componentes.
