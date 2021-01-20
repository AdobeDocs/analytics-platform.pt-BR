---
title: Perguntas frequentes sobre análise de Canais cruzados
description: Perguntas frequentes sobre o Cross-Canal Analytics
translation-type: tm+mt
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 20%

---


# Perguntas frequentes

## Como posso usar o CCA para ver como as pessoas se movem de um canal para outro?

Você pode usar uma visualização de Fluxo com a dimensão ID do conjunto de dados.

1. Faça logon em [analytics.adobe.com](https://analytics.adobe.com) e crie um projeto vazio do Workspace.
2. Clique na guia Visualizações à esquerda e arraste uma visualização de Fluxo para a tela à direita.
3. Clique na guia Componentes à esquerda e arraste a dimensão &#39;ID do conjunto de dados&#39; para o local central chamado &#39;Dimension ou Item&#39;.
4. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.

Se você deseja renomear itens de dimensão da ID do conjunto de dados, é possível usar um conjunto de dados de pesquisa.

## Até que ponto o CCA reporta visitantes?

A janela de pesquisa para rechaveamento depende da frequência desejada de dados [replay](replay.md). Por exemplo, se você configurar o CCA para reproduzir os dados uma vez por semana, a janela de pesquisa para rechaveamento será de 7 dias. Se você configurar o CCA para reproduzir dados todos os dias, a janela de pesquisa para rechaveamento será de 1 dia.

## Como os dispositivos compartilhados são manipulados?

Em algumas situações, é possível que várias pessoas façam logon no mesmo dispositivo. Os exemplos incluem um dispositivo compartilhado em casa, PCs compartilhados em uma biblioteca ou um quiosque em uma loja de varejo.

A ID transitória substitui a ID persistente, de modo que os dispositivos compartilhados sejam considerados pessoas separadas (mesmo se forem originários do mesmo dispositivo).

## Como a CCA lida com situações em que uma única pessoa tem um grande número de IDs persistentes?

Em algumas situações, um usuário individual pode se associar a um grande número de IDs persistentes. Os exemplos incluem a limpeza frequente de cookies do navegador, ou o uso do modo particular/cognito do navegador.

O número de IDs persistentes é irrelevante em favor da ID transitória. Um único usuário pode pertencer a qualquer número de dispositivos sem afetar a capacidade do CCA de unir os dispositivos.

## Quando eu entrar em contato com meu Gerente de conta com as informações desejadas, quanto tempo leva para o conjunto de dados rechaveado ficar disponível?

A correção ao vivo está disponível aproximadamente 1 semana depois que o Adobe ativa o Cross-Canal Analytics. A disponibilidade do preenchimento retroativo depende da quantidade de dados existentes. Os pequenos conjuntos de dados (menos de 1 milhão de eventos por dia) normalmente levam alguns dias, enquanto grandes conjuntos de dados (1 bilhão de eventos por dia) podem levar uma semana ou mais.

## Como o Cross-Canal Analytics lida com solicitações GDPR e CCPA?

O Adobe lida com solicitações do RGPD e CCPA de acordo com as leis locais e internacionais. O Adobe oferta o [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) para enviar solicitações de acesso e exclusão de dados. As solicitações se aplicam aos conjuntos de dados originais e rechaveados.
