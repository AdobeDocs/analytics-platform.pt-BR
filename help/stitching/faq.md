---
title: Perguntas frequentes sobre compilação
description: Perguntas frequentes sobre costura
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
source-git-commit: 94df90b64a25bfbeb5ed5e270925b1ef1ed89b8a
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 35%

---

# Perguntas frequentes

Aqui estão algumas perguntas frequentes sobre a compilação:

+++**Como posso usar a compilação para ver como as pessoas mudam de um canal para outro?**

Você pode usar uma visualização de Fluxo com a dimensão ID de conjunto de dados.

1. Efetue logon no [Customer Journey Analytics](https://analytics.adobe.com) e crie um projeto em branco do Workspace.
2. Selecione o **[!UICONTROL ** Visualizações **]** à esquerda e arraste uma **[!UICONTROL ** Fluxo **]** para a tela à direita.
3. Selecione o **[!UICONTROL ** Componentes **]** e arraste a dimensão **[!UICONTROL ** ID do conjunto de dados **]** ao local central rotulado **[!UICONTROL ** Dimension ou Item **]**.
4. Este relatório de fluxo é interativo. Para expandir os fluxos para páginas subsequentes ou anteriores, selecione qualquer um dos valores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.

Se você quiser renomear itens de dimensão da ID de conjunto de dados, poderá usar um conjunto de dados de pesquisa.

+++

+++**Até que ponto a compilação repete os visitantes?**

A janela de pesquisa para rechaveamento depende da frequência desejada de [repetição](explained.md) de dados. Por exemplo, se você configurar a compilação para repetir os dados uma vez por semana, a janela de pesquisa para rechaveamento será de sete dias. Se você configurar a compilação para repetir dados todos os dias, a janela de pesquisa para rechaveamento será de um dia.

+++

+++**Como os dispositivos compartilhados são manipulados?**

Em algumas situações, é possível que várias pessoas façam logon no mesmo dispositivo. Os exemplos incluem um dispositivo compartilhado em casa, PCs compartilhados em uma biblioteca ou um quiosque em uma loja de varejo.

A ID transitória substitui a ID persistente; portanto, os dispositivos compartilhados são considerados pessoas separadas (mesmo que sejam originários do mesmo dispositivo).

+++

+++**Como a compilação lida com situações em que uma única pessoa tem muitas IDs persistentes?**

Em algumas situações, um usuário individual pode ser associado a muitas IDs persistentes. Um exemplo é a limpeza frequente de cookies do navegador ou o uso do modo privado/anônimo do navegador.

O número de IDs persistentes é irrelevante em favor da ID transitória. Um único usuário pode pertencer a qualquer número de dispositivos sem afetar a capacidade do Customer Journey Analytics de compilar entre dispositivos.

+++

+++**Quando eu entrar em contato com minha equipe de conta do Adobe com as informações desejadas, quanto tempo levará para o conjunto de dados rechaveado ficar disponível?**

A compilação em tempo real está disponível aproximadamente uma semana depois de o Adobe ativar a compilação. A disponibilidade do preenchimento retroativo depende da quantidade de dados existentes. Os pequenos conjuntos de dados (menos de um milhão de eventos por dia) normalmente levam alguns dias, enquanto grandes conjuntos de dados (um bilhão de eventos por dia) podem levar uma semana ou mais.

+++

+++**Qual é a diferença entre a análise entre dispositivos (um recurso no Analytics tradicional) e a análise entre canais?**

[Análise entre dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=pt-BR) O é um recurso específico do Adobe Analytics tradicional que permite compreender como as pessoas operam em dispositivos. Ela oferece dois workflows para vincular dados do dispositivo: compilação em campo e gráfico do dispositivo.

A análise entre canais é um caso de uso específico do Customer Journey Analytics que permite compreender como as pessoas operam em dispositivos e canais. Ela compila a ID de pessoa de um conjunto de dados, permitindo que esse conjunto de dados seja combinado perfeitamente com outros conjuntos de dados. Esse recurso opera em design de forma semelhante à compilação em campo da análise entre dispositivos, mas a implementação é diferente devido à arquitetura de dados diferente entre o Analytics tradicional e o Customer Journey Analytics. Consulte [Costura](overview.md) e a variável [análise entre canais](../use-cases/cross-channel/cross-channel.md) caso de uso para obter mais informações.

+++

+++**Como a compilação lida com solicitações do GDPR e CCPA?**

O Adobe lida com solicitações do GDPR e CCPA de acordo com as leis locais e internacionais. A Adobe oferece o [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=pt-BR) para enviar solicitações de acesso e exclusão de dados. As solicitações se aplicam aos conjuntos de dados originais e rechaveados.

+++

+++**O que acontece se o campo ID persistente em um ou mais eventos estiver em branco?**

Se o campo ID persistente estiver em branco em um evento em um conjunto de dados que está sendo compilado, a ID compilada para esse evento será determinada de uma das duas formas a seguir:

* Se o campo ID transitória não estiver em branco, o Customer Journey Analytics usará o valor em ID transitória como a ID compilada.
* Se o campo ID transitória estiver em branco, o Customer Journey Analytics também deixará a ID compilada em branco. Nesse caso, a ID persistente, a ID transitória e a ID compilada estão em branco no evento. Esses tipos de eventos são descartados de qualquer conexão Customer Journey Analytics usando o conjunto de dados que está sendo compilado em que a ID compilada foi escolhida como a ID de pessoa.

+++

+++**Como as métricas nos conjuntos de dados compilados em Customer Journey Analytics se comparam com métricas semelhantes nos conjuntos de dados não compilados em Customer Journey Analytics e com o Adobe Analytics?**

Determinadas métricas no Customer Journey Analytics são semelhantes às métricas no Analytics tradicional, mas outras são diferentes, dependendo do que você está comparando. A tabela abaixo compara várias métricas comuns:

| **dados compilados do Customer Journey Analytics** | **dados não compilados do Customer Journey Analytics** | **Adobe Analytics** | **Analytics Ultimate com CDA** |
| ----- | ----- | ----- | ----- |
| **Pessoas** = Contagem de IDs de pessoa distintas, em que a ID com título é escolhida como ID de pessoa. **Pessoas** pode ser superior ou inferior a **Visitantes únicos** no Adobe Analytics tradicional, dependendo da saída do processo de compilação.  | **Pessoas** = Contagem de IDs de pessoa distintas com base na coluna selecionada como ID de pessoa. **Pessoas** nos conjuntos de dados do conector de origem do Analytics é semelhante a **Visitantes únicos** no Adobe Analytics tradicional se `endUserIDs._experience.aaid.id` é usada como ID de pessoa no Customer Journey Analytics. | **Visitantes únicos** = Contagem de IDs de visitante distintas. **Visitantes únicos** pode não ser o mesmo que a contagem de **ECID** s. | Consulte [de pessoas](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=pt-BR). |
| **Sessões**: Definido com base nas configurações de sessão na visualização de dados Customer Journey Analytics. O processo de compilação pode combinar sessões individuais de vários dispositivos em uma única sessão. | **Sessões**: Definido com base nas configurações de sessão especificadas na visualização de dados do Customer Journey Analytics. | **Visitas**: consulte [Visitas](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=pt-BR). | **Visitas**: definido com base nas configurações de sessão especificadas no [conjunto de relatórios virtuais do CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=pt-BR). |
| **Eventos** = contagem de linhas nos dados compilados no Customer Journey Analytics. Normalmente, essa métrica está próxima de **Ocorrências** na Adobe Analytics tradicional. No entanto, observe as Perguntas frequentes acima que estão relacionadas às linhas com uma ID persistente em branco. | **Eventos** = contagem de linhas nos dados não compilados no Customer Journey Analytics. Normalmente, essa métrica está próxima de **Ocorrências** na Adobe Analytics tradicional. Observe, no entanto, que se qualquer evento tiver uma ID de pessoa em branco nos dados não compilados no data lake do Experience Platform, esses eventos não são incluídos no Customer Journey Analytics. | **Ocorrências**: consulte [Ocorrências](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=pt-BR). | **Ocorrências**: consulte [Ocorrências](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=pt-BR). |

Outras métricas podem ser semelhantes no Customer Journey Analytics e no Adobe Analytics. Por exemplo, a contagem total de Adobe Analytics [eventos personalizados](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=pt-BR) 1-100 é comparável entre o Adobe Analytics tradicional e o Customer Journey Analytics (seja compilado ou não). [Diferenças nos recursos](/help/getting-started/aa-vs-cja/cja-aa.md)), como a desduplicação de eventos entre o Customer Journey Analytics e o Adobe Analytics, pode causar discrepância entre os dois produtos.

+++

+++**O Customer Journey Analytics pode usar campos do Mapa de identidade?**

Não, o Customer Journey Analytics não pode usar campos do Mapa de identidade para compilação no momento.

+++
