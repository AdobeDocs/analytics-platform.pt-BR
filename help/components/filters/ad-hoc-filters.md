---
description: Use filtros ad-hoc no Analysis Workspace.
title: Filtros de projeto ad-hoc
feature: Workspace Basics
role: User, Admin
source-git-commit: 275c552b14a4c2a47e00d0600ac3eae6811beae9
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 17%

---


# Filtros de projeto ad-hoc

Este é um vídeo sobre como criar filtros de projeto ad-hoc:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Você pode criar filtros de projeto ad-hoc se quiser explorar rapidamente como um filtro pode afetar seu projeto, sem acessar o Construtor de segmentos. Pense nesses filtros como filtros temporários em nível de projeto. Normalmente, eles não farão parte de sua &quot;biblioteca&quot; de filtros como filtros de componentes no painel esquerdo. No entanto, você pode salvá-las, conforme mostrado abaixo.

Para uma comparação do que os filtros de projeto ad-hoc podem fazer com relação aos filtros de nível de componente completos, acesse [aqui](/help/components/filters/filters-overview.md).

1. Solte qualquer tipo de componente (dimensão, item de dimensão, evento, métrica, filtro, modelo de filtro, intervalo de datas) na zona de soltar do filtro na parte superior de um painel. Os tipos de componentes são convertidos automaticamente em filtros.
Este é um exemplo de como criar um filtro para o domínio de referência do Twitter:

   ![](assets/ad-hoc1.png)

   O painel obtém esse filtro automaticamente e você pode ver os resultados instantaneamente.

1. Você pode adicionar um número ilimitado de componentes a um painel.
1. Se decidir salvar esse filtro, consulte a seção abaixo.

Lembre-se:

* **Não** é possível soltar os seguintes tipos de componentes na zona de filtros: métricas calculadas e dimensões/métricas a partir das quais você não pode criar filtros.
* Para dimensões e eventos completos, o Analysis Workspace cria filtros de ocorrência “existe”. Exemplos: `Hit where eVar1 exists` ou `Hit where event1 exists`.
* Se as opções &quot;não especificado&quot; ou &quot;nenhum&quot; forem soltas na zona de soltar do filtro, serão automaticamente convertidas em um filtro &quot;não existe&quot; para que sejam tratadas corretamente na filtragem.

>[!NOTE]
>
>Segmentos criados desse modo são internos no projeto.

## Salvar filtros de projeto ad-hoc {#ad-hoc-save}

Você pode optar por salvar esses filtros seguindo estas etapas:

1. Passe o mouse sobre o filtro no local onde os segmentos são colocados e clique no ícone “i”.
1. No painel de informações que é exibido, clique em **[!UICONTROL Salvar]**.

   ![](assets/segment-info.png)

## O que são filtros somente de projeto?

Os filtros somente do projeto são filtros rápidos ou filtros de projeto ad-hoc do Workspace. Ao editá-los/abri-los no construtor de filtros, a caixa somente do projeto será exibida. Se eles APLICAREM um filtro rápido no construtor, mas não marcarem a caixa disponibilizar , ele ainda será um filtro somente de projeto, mas não poderá mais ser aberto no construtor de QS. Se eles marcarem a caixa e SALVAR, agora é um filtro de lista de componentes.