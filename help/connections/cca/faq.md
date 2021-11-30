---
title: Perguntas frequentes sobre a Análise de vários canais
description: Perguntas frequentes sobre a Análise de vários canais
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 100%

---

# Perguntas frequentes

## Como posso usar a AVC para ver como as pessoas mudam de um tipo de canal para outro?

Você pode usar uma visualização de Fluxo com a dimensão ID de conjunto de dados.

1. Faça logon em [analytics.adobe.com](https://analytics.adobe.com) e crie um projeto em branco do Workspace.
2. Clique na guia Visualizações à esquerda e arraste uma visualização de Fluxo para a tela à direita.
3. Clique na guia Componentes à esquerda e arraste a dimensão “ID de conjuto de dados” para o local central chamado “Dimensão ou item”.
4. Este relatório de fluxo é interativo. Clique em qualquer um dos valores para expandir os fluxos para páginas subsequentes ou anteriores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.

Se você quiser renomear itens de dimensão da ID de conjunto de dados, poderá usar um conjunto de dados de pesquisa.

## Até que ponto a AVC faz o rechaveamento de visitantes?

A janela de pesquisa para rechaveamento depende da frequência desejada de [repetição](replay.md) de dados. Por exemplo, se você configurar a AVC para repetir os dados uma vez por semana, a janela de pesquisa para rechaveamento será de sete dias. Se você configurar a AVC para repetir dados todos os dias, a janela de pesquisa para rechaveamento será de um dia.

## Como os dispositivos compartilhados são manipulados?

Em algumas situações, é possível que várias pessoas façam logon no mesmo dispositivo. Os exemplos incluem um dispositivo compartilhado em casa, PCs compartilhados em uma biblioteca ou um quiosque em uma loja de varejo.

A ID transitória substitui a ID persistente; portanto, os dispositivos compartilhados são considerados pessoas separadas (mesmo que sejam originários do mesmo dispositivo).

## Como a AVC lida com situações em que uma única pessoa tem um grande número de IDs persistentes?

Em algumas situações, um usuário individual pode ser associado a um grande número de IDs persistentes. Os exemplos incluem a limpeza frequente de cookies do navegador ou o uso do modo privado/anônimo do navegador.

O número de IDs persistentes é irrelevante em favor da ID transitória. Um único usuário pode pertencer a qualquer número de dispositivos sem afetar a capacidade da AVC de compilar entre dispositivos.

## Quando eu entrar em contato com meu Gerente de conta com as informações desejadas, quanto tempo levará para o conjunto de dados rechaveado ficar disponível?

A compilação em tempo real está disponível aproximadamente uma semana depois de a Adobe ativar a Análise de vários canais. A disponibilidade do preenchimento retroativo depende da quantidade de dados existentes. Os pequenos conjuntos de dados (menos de um milhão de eventos por dia) normalmente levam alguns dias, enquanto grandes conjuntos de dados (um bilhão de eventos por dia) podem levar uma semana ou mais.

## Como a Análise de vários canaiss lida com solicitações do GDPR e CCPA?

O Adobe lida com solicitações do GDPR e CCPA de acordo com as leis locais e internacionais. A Adobe oferece o [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=pt-BR) para enviar solicitações de acesso e exclusão de dados. As solicitações se aplicam aos conjuntos de dados originais e rechaveados.

## O que acontece se o campo ID persistente em um ou mais eventos estiver em branco?

Se o campo `Persistent ID` estiver em branco em um evento em um conjunto de dados que está sendo compilado com a compilação em campo, o CCA preencherá o `Stitched ID` desse evento de uma das duas formas a seguir:
* Se o campo `Transient ID` não estiver em branco, o CCA usará o valor em `Transient ID` como `Stitched ID`.
* Se o campo `Transient ID` estiver em branco, o CCA também deixará `Stitched ID` em branco. Nesse caso, `Persistent ID`, `Transient ID` e `Stitched ID` estarão em branco no evento. Eventos como esse são descartados do CJA em qualquer conexão do CJA usando o conjunto de dados que está sendo compilado, onde `Stitched ID` foi escolhido como o `Person ID`.

## Como as métricas nos conjuntos de dados compilados do CJA se comparam com métricas semelhantes nos conjuntos de dados não compilados do CJA e com o Adobe Analytics tradicional?

Certas métricas no CJA são semelhantes às métricas no Analytics tradicional, mas outras são bem diferentes, dependendo do que você está comparando. A tabela abaixo compara várias métricas comuns:

| **Dados compilados do CJA** | **Dados não compilados do CJA** | **Adobe Analytics tradicional** | **Analytics Ultimate com CDA** |
| ----- | ----- | ----- | ----- |
| **Pessoas** = Contagem de `Person ID` distintos, em que `Stitched ID` é escolhido como `Person ID`. **** de pessoas pode ser superior ou inferior a **dos Visitantes únicos** no Adobe Analytics tradicional, dependendo da saída do processo de compilação. | **Pessoas** = Contagem de `Person ID` distintos com base na coluna selecionada como `Person ID`. **O** de pessoas nos conjuntos de dados do Adobe Analytics Connector (ADC) são semelhantes aos **Visitantes** únicos no Adobe Analytics tradicional se `endUserIDs. _experience. aaid.id` são escolhidos como `Person ID` no CJA. | **Visitantes únicos** = Contagem de IDs de visitante distintas. Observe que **Visitantes únicos** podem não ser iguais à contagem de **ECIDs** distintos. | Consulte [de pessoas](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=pt-BR). |
| **Sessões**: é definido com base nas configurações de sessão especificadas na visualização de dados do CJA. O processo de compilação pode combinar sessões individuais de vários dispositivos em uma única sessão. | **Sessões**: é definido com base nas configurações de sessão especificadas na visualização de dados do CJA. | **Visitas**: consulte [Visitas](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=pt-BR). | **Visitas**: é definido com base nas configurações de sessão especificadas no conjunto de relatórios virtual do [CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=pt-BR). |
| **Eventos** = contagem de linhas nos dados compilados no CJA. Geralmente, isso deve estar próximo a **Ocorrências** no Adobe Analytics tradicional. No entanto, observe as Perguntas frequentes acima que estão relacionadas às linhas com um `Persistent ID` em branco. | **Eventos** = contagem de linhas nos dados não compilados no CJA. Geralmente, isso deve estar próximo a **Ocorrências** no Adobe Analytics tradicional. Observe, no entanto, que se qualquer evento tiver um `Person ID` em branco nos dados não compilados no lago de dados da AEP, esses eventos serão descartados (não incluídos) no CJA. | **Ocorrências**: consulte [Ocorrências](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=pt-BR). | **Ocorrências**: consulte [Ocorrências](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en). |

Outras métricas podem ser semelhantes no CJA e no Adobe Analytics tradicional. Por exemplo, a contagem total de eventos personalizados [para o Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=pt-BR) (eventos 1-100) geralmente deve ser muito próxima no Adobe Analytics tradicional e no CJA (seja compilada ou não). No entanto, observe que isso nem sempre pode ser verdadeiro, devido a [diferenças nos recursos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-aa.html?lang=pt-BR), como a desduplicação de eventos entre o CJA e o Adobe Analytics tradicional.
