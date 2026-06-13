---
title: Por que os dados do GA4 e do Customer Journey Analytics diferem
description: Entenda por que os dados entre o GA4 e o Customer Journey Analytics podem ser diferentes e como auditar discrepâncias.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 7e4b9a2f-1c5d-4b8a-e3f9-6d2c8b7a4051
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 1300
ht-degree: 0%

---


# Por que os dados do GA4 e do Customer Journey Analytics diferem

É normal que o GA4 e o Customer Journey Analytics relatem números diferentes para o mesmo período e a mesma métrica aparente. Diferentes métodos de coleta de dados, definições de métricas, modelos de identidade e regras de sessão contribuem para discrepâncias. Esta página explica as fontes mais comuns de diferença e fornece orientação para a auditoria de lacunas não explicadas.

## Sessões envolvidas

O GA4 trata uma sessão como **engajada** se ela durar 10 ou mais segundos, incluir pelo menos um evento principal ou tiver 2 ou mais exibições de página. Essa única definição apoia várias métricas do GA4, incluindo Taxa de engajamento, Taxa de rejeição e o limite de engajamento atrás dos usuários ativos.

A Customer Journey Analytics não tem métrica ou dimensão de sessão de engajamento integrada; você define o engajamento para corresponder à sua empresa. A Adobe recomenda criar um segmento que capture seus critérios de engajamento e reutilize esse segmento sempre que o engajamento for importante. O administrador também pode promover essa definição a uma métrica na visualização de dados para que ela fique disponível para todos.

Ao formular seus próprios critérios, escolha os sinais que realmente indicam o valor do site. Três componentes básicos comuns para o contrato incluem:

* **Duração**: uma duração mínima de sessão, como 10 segundos ou mais
* **Profundidade**: um número mínimo de eventos ou exibições de página, como 2 ou mais
* **Ação**: a presença de um evento de conversão ou de chave, como uma inscrição ou uma compra

Você pode combiná-los com `OR` para que uma sessão seja contada como engajada se atender a qualquer uma das condições (como o GA4 faz) ou combiná-la com `AND` para um requisito mais estrito. Se a paridade com GA4 for sua meta, comece com os padrões e faça o ajuste a partir daí.

### Taxa de participação

Depois de ter uma definição de sessões engajadas, a taxa de engajamento é o compartilhamento das sessões que foram engajadas. Para criá-la como uma métrica calculada:

1. No Analysis Workspace, selecione o ícone **[!UICONTROL +]** próximo à lista de métricas para abrir o Criador de métricas calculadas.
2. Nomeie-a como &quot;Taxa de participação&quot; e defina o formato como **[!UICONTROL Percentual]**.
3. Defina a fórmula como o segmento de suas sessões engajadas dividido por **[!UICONTROL Sessões]**.
4. Selecione **[!UICONTROL Salvar]**.

### Taxa de rejeição

No GA4, uma rejeição é o inverso de uma sessão engajada, portanto, a taxa de rejeição do GA4 é igual a `1 - Engagement Rate`. Crie-o no Customer Journey Analytics como uma segunda métrica calculada usando essa fórmula.

O Customer Journey Analytics também fornece uma métrica **[!UICONTROL Taxa de rejeição]** interna, mas sua definição padrão é diferente: ela conta sessões em que apenas um único evento foi gravado, o que é diretamente oposto à definição do GA4 para muitos sites. A comparação da taxa de rejeição do GA4 com a métrica padrão [!UICONTROL Taxa de rejeição] — em vez do cálculo `1 - Engagement Rate` — produz números materialmente diferentes.

>[!TIP]
>
>A definição da sessão no Customer Journey Analytics pode ser configurada por visualização de dados. As definições de rejeição e engajamento podem ser ajustadas para corresponder aos critérios do GA4 (duração de 10 segundos, mais de 2 visualizações de página ou um evento principal) se essa paridade for um requisito de relatório para sua organização.

## Sessões

O GA4 e o Customer Journey Analytics assumem como padrão um tempo limite de inatividade de 30 minutos, e ambos mantêm uma sessão em andamento durante a meia-noite e durante uma alteração de campanha no meio da sessão. (O Universal Analytics redefine as sessões em ambos os casos, portanto, elas são uma fonte comum de confusão, mas não são diferenças entre o GA4 e o Customer Journey Analytics.) As regras que diferem são:

| Regra | GA4 | Customer Journey Analytics |
|---|---|---|
| Tempo limite de inatividade | Ajustável em toda a propriedade (padrão de 30 minutos, até 7 horas e 55 minutos) | Configurável por visualização de dados |
| Eventos de início de sessão | Somente `session_start` (automático) | Configurável; qualquer evento pode iniciar uma sessão |
| Eventos de fim de sessão | Nenhum | Configurável; qualquer evento pode encerrar uma sessão |

Como a definição de sessão do Customer Journey Analytics é configurável, a contagem de sessões depende de como a visualização de dados é configurada. Corresponder o tempo limite de uma visualização de dados e os eventos de início de sessão à propriedade do GA4 aproxima as contagens de sessão entre as plataformas.

## Pessoas e usuários ativos

A métrica de usuário principal do GA4, **Usuários ativos**, conta os usuários que tiveram pelo menos uma sessão ativada no intervalo de datas. A métrica **[!UICONTROL Pessoas]** no Customer Journey Analytics conta IDs de pessoas exclusivas no intervalo de datas.

Espere que essas métricas sejam diferentes por vários motivos:

* **Limite de engajamento**: GA4 usuários ativos excluem visitantes que não tiveram [sessão engajada](#engaged-sessions). A métrica [!UICONTROL Pessoas] no Customer Journey Analytics inclui todos, independentemente do nível de envolvimento.
* **[!UICONTROL Compilação]**: se a compilação estiver habilitada, uma pessoa que visitou de um dispositivo móvel e de um desktop pode ser contada como uma pessoa no Customer Journey Analytics, mas dois usuários no GA4. Normalmente, a compilação diminui a métrica [!UICONTROL Pessoas] em relação aos usuários do GA4 nos conjuntos de dados compilados.
* **Modelo de identidade**: o GA4 usa um modelo de identidade em cascata; o Customer Journey Analytics usa qualquer ID de pessoa definida no conjunto de dados. Essas diferenças afetam as contagens de pessoas independentemente da compilação.

## Identidade e compilação

O GA4 usa um modelo de identidade em cascata para identificar usuários:

1. ID de usuário (se definida pela sua implementação)
2. Sinais do Google (se o usuário estiver conectado a uma conta do Google com personalização ativada)
3. ID do dispositivo (ID do cliente baseada em cookie)

Na maioria das implementações, essa ID de pessoa é uma ECID (Experience Cloud ID). O recurso **[!UICONTROL Costura]** opcional pode então resolver identidades entre canais e dispositivos usando métodos baseados em gráfico ou em campo, permitindo que uma sessão de aplicativo móvel e uma sessão de navegador de desktop sejam associadas à mesma pessoa.

Como a resolução de identidade difere entre as plataformas, as contagens no nível do usuário raramente correspondem exatamente. Essa discrepância é esperada e não indica um problema de qualidade de dados.

## Atribuição

O GA4 aplica um modelo de atribuição de relatórios configurado no nível da propriedade (em Administração), com atribuição orientada por dados como padrão. Como o Customer Journey Analytics, o GA4 avalia esse modelo no momento do relatório, portanto, alterá-lo atualiza relatórios históricos e futuros retroativamente. No GA4, no entanto, o modelo abrange toda a propriedade e afeta apenas os relatórios de eventos principais que usam dimensões de tráfego com escopo de evento (como Source, Medium e Campaign).

O Customer Journey Analytics também aplica a atribuição no momento do relatório, mas com controle mais granular. Há dois lugares para configurá-la:

* **Configurações de exibição de dados**: um [modelo de atribuição](/help/data-views/component-settings/attribution.md) pode ser definido em qualquer componente de métrica na exibição de dados, estabelecendo o padrão para essa métrica em todos os relatórios. Nenhum modelo de atribuição é aplicado por padrão. É possível configurar uma visualização de dados para conter várias cópias da mesma métrica, cada uma usando um modelo de atribuição padrão diferente.
* **Substituição no nível do componente**: depois de arrastar uma métrica para uma [!UICONTROL Tabela de forma livre], clique com o botão direito em seu cabeçalho de coluna e selecione **[!UICONTROL Usar modelo de atribuição não padrão]** para substituí-la para essa instância. Você também pode arrastar a mesma métrica para a tabela várias vezes, cada uma usando um modelo de atribuição diferente para uma comparação direta lado a lado.

Como o GA4 assume o padrão de atribuição orientada por dados, enquanto o Customer Journey Analytics não aplica nenhum modelo, a menos que você configure um, é provável que as métricas de conversão e canal sejam diferentes até que você as alinhe. Configurar o GA4 como um modelo de último clique e um modelo de último toque correspondente no Customer Journey Analytics é a maneira mais confiável de estabelecer uma linha de base semelhante a. Qualquer alteração de modelo no Customer Journey Analytics se aplica retroativamente a todos os dados históricos sem reprocessamento.

## Discrepâncias de auditoria

Quando os números diferem mais do que o esperado, três caminhos de auditoria estão disponíveis:

* **Assurance**: a ferramenta de validação no produto da Adobe confirma que os eventos XDM estão sendo acionados corretamente, chegando à Edge Network e sendo gravados nos conjuntos de dados da plataforma. Use essa ferramenta para verificar sua implementação antes de comparar os números dos relatórios.
* **Visualizações do conjunto de dados**: na interface do usuário da plataforma, você pode visualizar linhas brutas em qualquer conjunto de dados. Compare esses dados com a exportação DebugView ou BigQuery do GA4 para verificar a precisão no nível do campo.
* **Adobe Consulting**: para discrepâncias inexplicáveis persistentes, sua equipe de conta da Adobe pode realizar uma auditoria de implementação formal com um consultor da Adobe.
* **Revisão de assimilação**: se você suspeitar que a discrepância se origina em como os dados do GA foram trazidos para a Plataforma, em vez de nas definições de relatório, revise a configuração de assimilação em [Migrar dados do Google Analytics](/help/use-cases/third-party/ga/overview.md).
