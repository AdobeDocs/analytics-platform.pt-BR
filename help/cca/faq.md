---
title: Perguntas frequentes sobre o Cross-Channel Analytics
description: Perguntas frequentes sobre o Cross-Channel Analytics
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analysis
hide: true
hidefromtoc: true
source-git-commit: ca037fa439a6a94ca071c610089a3ad931cc921d
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 66%

---

# Perguntas frequentes

## Como posso usar a CCA para ver como as pessoas mudam de um tipo de canal para outro?

Você pode usar uma visualização de Fluxo com a dimensão ID de conjunto de dados.

1. Faça logon em [analytics.adobe.com](https://analytics.adobe.com) e crie um projeto em branco do Espaço de trabalho.
2. Clique na guia Visualizações à esquerda e arraste uma visualização de Fluxo para a tela à direita.
3. Clique na guia Componentes à esquerda e arraste a dimensão “ID de conjunto de dados” para o local central rotulado como “Dimensão ou item”.
4. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.

Se você quiser renomear itens de dimensão da ID de conjunto de dados, poderá usar um conjunto de dados de pesquisa.

## Até que ponto a AVC faz o rechaveamento de pessoas?

A janela de pesquisa para rechaveamento depende da frequência desejada de [repetição](replay.md) de dados. Por exemplo, se você configurar o CCA para repetir os dados uma vez por semana, a janela de pesquisa para rechaveamento será de sete dias. Se você configurar o CCA para repetir dados todos os dias, a janela de pesquisa para rechaveamento será de um dia.

## Como os dispositivos compartilhados são manipulados?

Em algumas situações, é possível que várias pessoas façam logon no mesmo dispositivo. Os exemplos incluem um dispositivo compartilhado em casa, PCs compartilhados em uma biblioteca ou um quiosque em uma loja de varejo.

A ID transitória substitui a ID persistente; portanto, os dispositivos compartilhados são considerados pessoas separadas (mesmo que sejam originários do mesmo dispositivo).

## Como o CCA lida com situações em que uma única pessoa tem muitas IDs persistentes?

Em algumas situações, um usuário individual pode ser associado a muitas IDs persistentes. Os exemplos incluem a limpeza frequente de cookies do navegador ou o uso do modo privado/anônimo do navegador.

O número de IDs persistentes é irrelevante em favor da ID transitória. Um único usuário pode pertencer a qualquer número de dispositivos sem afetar a capacidade da CCA de compilar entre dispositivos.

## Quando eu entrar em contato com minha equipe de conta do Adobe com as informações desejadas, quanto tempo levará para o conjunto de dados rechaveado ficar disponível?

A compilação em tempo real está disponível aproximadamente uma semana depois de a Adobe ativar o Cross-Channel Analytics. A disponibilidade do preenchimento retroativo depende da quantidade de dados existentes. Os pequenos conjuntos de dados (menos de um milhão de eventos por dia) normalmente levam alguns dias, enquanto grandes conjuntos de dados (um bilhão de eventos por dia) podem levar uma semana ou mais.

## Qual é a diferença entre o Cross-Device Analytics (um recurso no Adobe Analytics) e o Cross-Channel Analytics?

[Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=pt-BR) é um recurso específico do Adobe Analytics tradicional que permite compreender como as pessoas operam em dispositivos. Ela oferece dois workflows para vincular dados do dispositivo: compilação em campo e gráfico do dispositivo.

[Cross-Channel Analytics](/help/cca/overview.md) é um recurso específico do Customer Journey Analytics que permite compreender como as pessoas operam em dispositivos e canais. É uma nova chave da ID de pessoa de um conjunto de dados, permitindo que esse conjunto de dados seja combinado perfeitamente com outros conjuntos de dados. Esse recurso opera em design de forma semelhante à compilação em campo do CDA, mas a implementação é diferente devido à arquitetura de dados diferente entre o Adobe Analytics e o Customer Journey Analytics.

## Como o Cross-Channel Analytics lida com solicitações do GDPR e CCPA?

O Adobe lida com solicitações do GDPR e CCPA de acordo com as leis locais e internacionais. A Adobe oferece o [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=pt-BR) para enviar solicitações de acesso e exclusão de dados. As solicitações se aplicam aos conjuntos de dados originais e rechaveados.

## O que acontece se o campo ID persistente em um ou mais eventos estiver em branco?

Se o campo `Persistent ID` estiver em branco em um evento em um conjunto de dados que está sendo compilado com a compilação em campo, o CCA preencherá o `Stitched ID` desse evento de uma das duas formas a seguir:

* Se o campo `Transient ID` não estiver em branco, o CCA usará o valor em `Transient ID` como `Stitched ID`.
* Se o campo `Transient ID` estiver em branco, o CCA também deixará `Stitched ID` em branco. Neste caso, `Persistent ID`, `Transient ID` e `Stitched ID` estão em branco no evento. Esses tipos de eventos são descartados de qualquer conexão Customer Journey Analytics usando o conjunto de dados que está sendo compilado, onde `Stitched ID` foi escolhida como a `Person ID`.

## Como as métricas nos conjuntos de dados compilados em Customer Journey Analytics se comparam com métricas semelhantes nos conjuntos de dados não compilados em Customer Journey Analytics e com o Adobe Analytics tradicional?

Determinadas métricas do Customer Journey Analytics são semelhantes às métricas do Adobe Analytics, mas outras são bem diferentes, dependendo do que você está comparando. A tabela abaixo compara várias métricas comuns:

| **dados compilados do Customer Journey Analytics** | **dados não compilados do Customer Journey Analytics** | **Adobe Analytics tradicional** | **Analytics Ultimate com CDA** |
| ----- | ----- | ----- | ----- |
| **Pessoas** = Contagem de `Person ID` distintos, em que `Stitched ID` é escolhido como `Person ID`. **Pessoas** pode ser superior ou inferior a **Visitantes únicos** no Adobe Analytics tradicional, dependendo da saída do processo de compilação.  | **Pessoas** = Contagem de `Person ID` distintos com base na coluna selecionada como `Person ID`. **Pessoas** nos conjuntos de dados do conector de origem do Analytics é semelhante a **Visitantes únicos** no Adobe Analytics tradicional se `endUserIDs._experience.aaid.id` é escolhido como `Person ID` em Customer Journey Analytics. | **Visitantes únicos** = Contagem de IDs de pessoa distintas. **Visitantes únicos** pode não ser o mesmo que a contagem de **ECID** s. | Consulte [de pessoas](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=pt-BR). |
| **Sessões**: Definido com base nas configurações de sessão na visualização de dados Customer Journey Analytics. O processo de compilação pode combinar sessões individuais de vários dispositivos em uma única sessão. | **Sessões**: Definido com base nas configurações de sessão especificadas na visualização de dados do Customer Journey Analytics. | **Visitas**: consulte [Visitas](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=pt-BR). | **Visitas**: definido com base nas configurações de sessão especificadas no [conjunto de relatórios virtuais do CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=pt-BR). |
| **Eventos** = contagem de linhas nos dados compilados no Customer Journey Analytics. Normalmente, essa métrica está próxima de **Ocorrências** na Adobe Analytics tradicional. No entanto, observe as Perguntas frequentes acima que estão relacionadas às linhas com um `Persistent ID` em branco. | **Eventos** = contagem de linhas nos dados não compilados no Customer Journey Analytics. Normalmente, essa métrica está próxima de **Ocorrências** na Adobe Analytics tradicional. Observe, no entanto, que se algum evento tiver um em branco `Person ID` nos dados não compilados no data lake Experience Platform, esses eventos não são incluídos no Customer Journey Analytics. | **Ocorrências**: consulte [Ocorrências](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=pt-BR). | **Ocorrências**: consulte [Ocorrências](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=pt-BR). |

Outras métricas podem ser semelhantes no Customer Journey Analytics e no Adobe Analytics tradicional. Por exemplo, a contagem total de Adobe Analytics [eventos personalizados](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=pt-BR) 1-100 geralmente é comparável entre o Adobe Analytics tradicional e o Customer Journey Analytics (seja compilado ou não). [Diferenças nos recursos](/help/getting-started/aa-vs-cja/cja-aa.md)), como a eliminação da duplicação de eventos entre o Customer Journey Analytics e o Adobe Analytics tradicional, pode causar discrepância entre os dois produtos.

## O CCA pode usar campos do Mapa de identidade?

Não, o CCA atualmente não pode usar campos do Mapa de identidade.
