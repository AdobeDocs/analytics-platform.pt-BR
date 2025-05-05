---
title: Perguntas frequentes sobre compilação
description: Perguntas frequentes sobre costura
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: 1a003b38ef26eb811b19cd091c6e089f33ddb6f6
workflow-type: tm+mt
source-wordcount: '1918'
ht-degree: 28%

---

# Perguntas frequentes

Aqui estão algumas perguntas frequentes sobre a compilação:

## Mover entre canais

+++ Como posso usar a compilação para ver como as pessoas mudam de um canal para outro?

Você pode usar uma visualização de Fluxo com a dimensão ID de conjunto de dados.

1. Faça logon no [Customer Journey Analytics](https://analytics.adobe.com) e crie um projeto do Workspace em branco.
2. Selecione a guia **[!UICONTROL ** Visualizações **]** à esquerda e arraste uma visualização de **[!UICONTROL **&#x200B; Fluxo &#x200B;**]** para a tela à direita.
3. Selecione a guia **[!UICONTROL ** Componentes **]** à esquerda e arraste a dimensão **[!UICONTROL ** ID de conjunto de dados **]** para o local central rotulado **[!UICONTROL **&#x200B; Dimension ou Item &#x200B;**]**.
4. Este relatório de fluxo é interativo. Para expandir os fluxos para páginas subsequentes ou anteriores, selecione qualquer um dos valores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.

Se você quiser renomear itens de dimensão da ID de conjunto de dados, poderá usar um conjunto de dados de pesquisa.

+++

## Reproduzir novamente

+++ Até que ponto a compilação repete os visitantes?

A janela de pesquisa para rechaveamento depende da frequência desejada de repetição de dados. Por exemplo, se você configurar a compilação para repetir os dados uma vez por semana, a janela de pesquisa para rechaveamento será de sete dias. Se você configurar a compilação para repetir dados todos os dias, a janela de pesquisa para rechaveamento será de um dia.

+++

## Dispositivos compartilhados

+++ Como os dispositivos compartilhados são manipulados?

Em algumas situações, é possível que várias pessoas façam logon no mesmo dispositivo. Os exemplos incluem um dispositivo compartilhado em casa, PCs compartilhados em uma biblioteca ou um quiosque em uma loja de varejo.

A ID transitória substitui a ID persistente; portanto, os dispositivos compartilhados são considerados pessoas separadas (mesmo que sejam originários do mesmo dispositivo).

Consulte o caso de uso [Dispositivos compartilhados](/help/use-cases/stitching/shared-devices.md) para obter mais detalhes.

+++

## Muitas IDs persistentes

+++ Como a compilação lida com situações em que uma única pessoa tem muitas IDs persistentes?

Em algumas situações, um usuário individual pode ser associado a muitas IDs persistentes. Um exemplo é a limpeza frequente de cookies do navegador ou o uso do modo privado/anônimo do navegador.

Para a compilação em campo, o número de IDs persistentes é irrelevante em favor da ID transitória. Um único usuário pode pertencer a qualquer número de dispositivos sem afetar a capacidade da Customer Journey Analytics de compilar entre dispositivos.

Para a compilação baseada em gráficos, uma única pessoa pode ter muitas ID persistentes no gráfico de identidade. A compilação baseada em gráfico usa a ID persistente com base no namespace especificado. Caso haja mais ID persistente para o mesmo namespace, a primeira ID persistente lexicográfica será usada.

+++

## Processo de compilação

+++ Após entrar em contato com minha equipe de contas da Adobe e fornecer as informações desejadas, quanto tempo levará para o conjunto de dados rechaveado ser disponibilizado?

A compilação em tempo real está disponível aproximadamente uma semana depois que o Adobe ativa a compilação. A disponibilidade do preenchimento retroativo depende da quantidade de dados existentes. Os pequenos conjuntos de dados (menos de um milhão de eventos por dia) normalmente levam alguns dias, enquanto grandes conjuntos de dados (um bilhão de eventos por dia) podem levar uma semana ou mais.

+++

## Análise entre dispositivos versus análise entre canais

+++ Qual é a diferença entre a análise entre dispositivos (um recurso no Analytics tradicional) e a análise entre canais?

A [Análise entre dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=pt-BR) é um recurso específico do Adobe Analytics tradicional que permite compreender como as pessoas operam entre dispositivos. Ela oferece dois workflows para vincular dados do dispositivo: compilação em campo e gráfico do dispositivo.

A análise entre canais é um caso de uso específico do Customer Journey Analytics que permite entender como as pessoas operam em dispositivos e canais. Ela compila a ID de pessoa de um conjunto de dados, permitindo que esse conjunto de dados seja combinado perfeitamente com outros conjuntos de dados. Esse recurso opera em design de forma semelhante à compilação em campo da análise entre dispositivos, mas a implementação é diferente devido à arquitetura de dados diferente entre o Analytics tradicional e o Customer Journey Analytics. Consulte [Costura](overview.md) e o caso de uso [análise entre canais](../use-cases/cross-channel/cross-channel.md) para obter mais informações.

+++

## Privacidade

+++ Como a compilação lida com solicitações de privacidade?

O Adobe lida com solicitações de privacidade de acordo com as leis locais e internacionais. A Adobe oferece o [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=pt-BR) para enviar solicitações de acesso e exclusão de dados. As solicitações se aplicam aos conjuntos de dados originais e rechaveados.

>[!IMPORTANT]
>
>O processo de descompilação, como parte das solicitações de privacidade, muda no início de 2025. O processo de descompilação atual recompila os eventos usando a versão mais recente de identidades conhecidas. Essa reatribuição de eventos para outra identidade pode ter consequências legais indesejáveis. Para solucionar essas preocupações, a partir de 2025, o novo processo de descompilação atualiza os eventos que são objeto da solicitação de privacidade com a ID persistente.
> 

Para ilustrar, imagine os seguintes dados para identidades, eventos antes e depois da compilação.

| Mapa de identidade | ID | carimbo de data e hora | ID persistente | namespace persistente | id transitória | namespace transitório |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | Bob | CustId |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de dados de eventos | ID | carimbo de data e hora | ID persistente | namespace persistente | id transitória | namespace transitório |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de dados compilados | ID | carimbo de data e hora | ID persistente | namespace persistente | id transitória | namespace transitório | ID com título | Namespace compilado |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | Bob | CustId |
| | 2 | ts1 | 123 | ecid | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Processo atual para solicitação de privacidade**

Quando uma solicitação de privacidade é recebida para o cliente com CustID Bob, as linhas com entradas tachadas são excluídas. Outros eventos são corrigidos usando o mapa de identidade. Por exemplo, a primeira ID compilada no conjunto de dados compilado é atualizada para **Alex**.

| Mapa de identidade | ID | carimbo de data e hora | ID persistente | namespace persistente | id transitória | namespace transitório |
|:---:|---|---|---|---|---|---|
| ![ExcluirEstruturaDeTópicos](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de dados de eventos | ID | carimbo de data e hora | ID persistente | namespace persistente | id transitória | namespace transitório |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![ExcluirEstruturaDeTópicos](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de dados compilados | ID | carimbo de data e hora | ID persistente | namespace persistente | id transitória | namespace transitório | ID com título | Namespace compilado |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **Alex** | CustId |
| ![ExcluirEstruturaDeTópicos](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Novo processo para solicitação de privacidade**

Quando uma solicitação de privacidade é recebida para o cliente com CustID Bob, as linhas com entradas tachadas são excluídas. Outros eventos são corrigidos usando a ID persistente. Por exemplo, a primeira ID compilada no conjunto de dados compilado é atualizada para **123**.

| Mapa de identidade | ID | carimbo de data e hora | ID persistente | namespace persistente | id transitória | namespace transitório |
|:---:|---|---|---|---|---|---|
| ![ExcluirEstruturaDeTópicos](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de dados de eventos | ID | carimbo de data e hora | ID persistente | namespace persistente | id transitória | namespace transitório |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![ExcluirEstruturaDeTópicos](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de dados compilados | ID | carimbo de data e hora | ID persistente | namespace persistente | id transitória | namespace transitório | ID com título | Namespace compilado |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![ExcluirEstruturaDeTópicos](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |

+++

## Valores de ID persistentes em branco

+++ O que acontece se o campo ID persistente em um ou mais eventos estiver em branco?

Se o campo ID persistente estiver em branco em um evento em um conjunto de dados que está sendo compilado, a ID compilada para esse evento será determinada de uma das duas formas a seguir:

* Se o campo ID transitória não estiver em branco, o Customer Journey Analytics usará o valor em ID transitória como a ID compilada.
* Se o campo ID transitória estiver em branco, o Customer Journey Analytics também deixará a ID compilada em branco. Nesse caso, a ID persistente, a ID transitória e a ID com título estão em branco no evento. Esses tipos de eventos são descartados de qualquer conexão do Customer Journey Analytics usando o conjunto de dados que está sendo compilado em que a ID compilada foi escolhida como a ID de pessoa.

+++


## Valores de ID transitórios indefinidos

+++ O que acontece se o campo ID Transitória em um ou mais eventos tiver valores de espaço reservado, como `Undefined`?

Tenha cuidado com o &quot;recolhimento de pessoas&quot;, que ocorre quando a compilação é aplicada a dados que usam valores de espaço reservado para IDs transitórias. Na tabela de exemplo abaixo, IDs de pessoa indefinidas originárias de um conjunto de dados proveniente de um sistema CRM são preenchidas com o valor &quot;Indefinido&quot;, resultando na representação incorreta de pessoas.

| Evento | Carimbo de data e hora | ID persistente (ID do cookie) | ID transitória (ID de logon) | ID compilada (após repetição) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **Cory** |
| 2 | 2023-05-12 12:02 | 123 | Cory | **Cory** |
| 3 | 2023-05-12 12:03 | 456 | Indefinido | **Indefinido** |
| 4 | 2023-05-12 12:04 | 456 | - | **Indefinido** |
| 5 | 2023-05-12 12:05 | 789 | Indefinido | **Indefinido** |
| 6 | 2023-05-12 12:06 | 012 | Indefinido | **Indefinido** |
| 7 | 2023-05-12 12:07 | 012 | - | **Indefinido** |
| 8 | 2023-05-12 12:03 | 789 | Indefinido | **Indefinido** |
| 9 | 2023-05-12 12:09 | 456 | - | **Indefinido** |
| 10 | 2023-05-12 12:02 | 123 | - | **Cory** |
| | | **4 dispositivos** | **2 pessoas**:<br/>Eventos 1, 4, 7, 9, 10 descartados | **2 pessoas**:<br/>Cory, Não autenticado (recolhido para uma pessoa) |

+++

## Comparação de métricas

+++ Como as métricas nos conjuntos de dados compilados do Customer Journey Analytics se comparam com métricas semelhantes nos conjuntos de dados não compilados do Customer Journey Analytics e com o Adobe Analytics?

Determinadas métricas no Customer Journey Analytics são semelhantes às métricas no Analytics tradicional, mas outras são diferentes, dependendo do que você está comparando. A tabela abaixo compara várias métricas comuns:

| **Dados compilados do Customer Journey Analytics** | **Dados não compilados do Customer Journey Analytics** | **Adobe Analytics** | **Analytics Ultimate com CDA** |
| ----- | ----- | ----- | ----- |
| **Pessoas** = Contagem de IDs de pessoa distintas em que a ID compilada é escolhida como ID de pessoa. **Pessoas** pode ser superior ou inferior a **Visitantes únicos** no Adobe Analytics tradicional, dependendo da saída do processo de compilação.  | **Pessoas** = Contagem de IDs de pessoa distintas com base na coluna selecionada como ID de pessoa. **Pessoas** nos conjuntos de dados do conector de origem do Analytics é semelhante a **Visitantes únicos** no Adobe Analytics tradicional se `endUserIDs._experience.aaid.id` for usado como ID de pessoa no Customer Journey Analytics. | **Visitantes únicos** = Contagem de IDs de visitante distintas. **Visitantes únicos** pode não ser o mesmo que a contagem de **ECID** s. | Consulte [de pessoas](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=pt-BR). |
| **Sessões**: definidas com base nas configurações de sessão na visualização de dados do Customer Journey Analytics. O processo de compilação pode combinar sessões individuais de vários dispositivos em uma única sessão. | **Sessões**: definidas com base nas configurações de sessão especificadas na visualização de dados do Customer Journey Analytics. | **Visitas**: consulte [Visitas](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=pt-BR). | **Visitas**: definido com base nas configurações de sessão especificadas no [conjunto de relatórios virtuais do CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=pt-BR). |
| **Eventos** = contagem de linhas nos dados compilados no Customer Journey Analytics. Essa métrica é bem semelhante às **Ocorrências** do Adobe Analytics tradicional. No entanto, observe as Perguntas frequentes acima que estão relacionadas às linhas com uma ID persistente em branco. | **Eventos** = contagem de linhas nos dados não compilados no Customer Journey Analytics. Essa métrica é bem semelhante às **Ocorrências** do Adobe Analytics tradicional. Observe, no entanto, que se qualquer evento tiver uma ID de pessoa em branco nos dados não compilados no data lake da Experience Platform, esses eventos não são incluídos no Customer Journey Analytics. | **Ocorrências**: consulte [Ocorrências](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=pt-BR). | **Ocorrências**: consulte [Ocorrências](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=pt-BR). |

Outras métricas podem ser semelhantes no Customer Journey Analytics e no Adobe Analytics. Por exemplo, a contagem total de [eventos personalizados](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=pt-BR) 1-100 do Adobe Analytics é comparável entre o Adobe Analytics tradicional e o Customer Journey Analytics (seja compilada ou não). [As diferenças nos recursos](/help/getting-started/aa-vs-cja/cja-aa.md)), como a eliminação da duplicação de eventos entre o Customer Journey Analytics e o Adobe Analytics, podem causar discrepância entre os dois produtos.

+++

## Mapa de identidade

+++ O Customer Journey Analytics pode usar campos do Mapa de identidade?

Não, no momento, o Customer Journey Analytics não pode usar campos do Mapa de identidade para compilação.

+++

## Alternar para a compilação baseada em gráfico

+++ Os dados precisarão ser assimilados novamente para alternar da compilação em campo para a compilação em gráfico?

Os dados não precisam ser assimilados novamente no Experience Platform, no entanto, eles precisarão ser reconfigurados no Customer Journey Analytics. Siga estas etapas:

1. Configure o novo conjunto de dados compilado com base em gráfico.
1. Configure o novo conjunto de dados como parte de uma nova conexão no Customer Journey Analytics.
1. Alterne sua Visualização de dados existente para usar a nova conexão (e, como tal, o novo conjunto de dados compilado com base em gráfico)
1. Remova a conexão antiga que estava usando o conjunto de dados compilado com base em campo.

+++

## Interrupção de relatórios

+++ Haveria alguma interrupção nos relatórios existentes?

Não se seguir as etapas descritas acima. Caso contrário, solicite suporte adicional à Adobe Consulting.

+++


