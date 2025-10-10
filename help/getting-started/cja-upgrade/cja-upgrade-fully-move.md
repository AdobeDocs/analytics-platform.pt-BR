---
title: Avalie por quanto tempo você precisa do Adobe Analytics após atualizar para o Customer Journey Analytics
description: Saiba como avaliar por quanto tempo você precisa do Adobe Analytics após atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 7142ef84-66a6-49eb-938b-b67c9b65bf93
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 100%

---

# Avalie quando desabilitar o Adobe Analytics após atualizar para o Customer Journey Analytics {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="Migrar totalmente para o Customer Journey Analytics"
>abstract="(Recomendado) A Adobe recomenda realizar a transição completa do Adobe Analytics para o Customer Journey Analytics. Durante o período de transição, você deve planejar a execução do Adobe Analytics junto com o Customer Journey Analytics para realizar comparações de dados lado a lado. Após se acostumar com os dados, desabilite o Adobe Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="Manter os dois produtos de análise"
>abstract="(Não recomendado) Se você selecionar essa opção, seu contrato com a Adobe incluirá o Adobe Analytics e o Customer Journey Analytics, o que pode ser mais caro para a sua organização ao longo do tempo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-source-connector"
>title="Desabilitar o conector de origem do Analytics para usar apenas dados do SDK da Web"
>abstract="O conector de origem do Analytics é usado para fornecer comparação de dados lado a lado, dados históricos e acesso a alguns recursos que não estão totalmente disponíveis no Customer Journey Analytics. Quando não precisar mais do Adobe Analytics para essas finalidades, você poderá desabilitar o conector de origem do Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

A maioria das organizações desabilitará o Adobe Analytics após a atualização para o Customer Journey Analytics. Isso se deve ao custo e à complexidade de manter dois ambientes de análise.

No entanto, a Adobe recomenda que você mantenha seu ambiente do Adobe Analytics em execução por um período após implementar o Customer Journey Analytics. As seções a seguir descrevem os motivos para fazer isso, bem como o momento sugerido para desabilitar o Adobe Analytics.

## Usos do Adobe Analytics durante e após uma atualização

Ao decidir se e quando sua organização deve desabilitar o Adobe Analytics, considere os seguintes usos do Adobe Analytics durante e após uma atualização para o Customer Journey Analytics:

| Usos do Adobe Analytics durante e após a atualização | Explicação |
|---------|----------|
| Fazer uma comparação de dados lado a lado | A Adobe recomenda que você mantenha seu ambiente do Adobe Analytics em execução por um período depois que o novo ambiente do Customer Journey Analytics estiver em execução e coletando dados. Essa é a melhor maneira de comparar os dados do Customer Journey Analytics lado a lado com os dados do Adobe Analytics.<p>Não desabilite o Adobe Analytics até que tenha familiaridade com os dados no ambiente do Customer Journey Analytics.</p><p>**Observação:** a Adobe recomenda uma nova implementação do SDK da web para o ambiente do Customer Journey Analytics, juntamente com o conector de origem do Analytics para dados históricos. [Saiba mais](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Reter dados históricos do Adobe Analytics | A Adobe recomenda que você mantenha seu ambiente do Adobe Analytics ativo com o conector de origem do Analytics por um período depois que o novo ambiente do Customer Journey Analytics estiver em execução e coletando dados. Essa é a melhor maneira de trazer dados históricos do Adobe Analytics para o Customer Journey Analytics.<p>Depois de coletar dados históricos suficientes no Customer Journey Analytics com a nova implementação do SDK da web, é possível remover totalmente o conector de origem do Analytics. Faça isso quando puder depender exclusivamente dos dados históricos coletados com a nova implementação do SDK da web do Customer Journey Analytics.</p><p>**Observação:** a Adobe recomenda uma nova implementação do SDK da web para o ambiente do Customer Journey Analytics, juntamente com o conector de origem do Analytics para dados históricos. [Saiba mais](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Usar Feeds de dados ou outros recursos do Adobe Analytics | Um pequeno conjunto de recursos ainda não está totalmente disponível no Customer Journey Analytics. Se precisar acessar esses recursos, talvez seja necessário usar o Adobe Analytics em conjunto com o Customer Journey Analytics até que eles estejam disponíveis. <p>Os recursos que não estão completamente disponíveis no Customer Journey Analytics incluem o Feeds de dados e a Análise de contribuição. Para obter uma lista completa de recursos que ainda não estão disponíveis, consulte [suporte a recursos do Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).</p> |

## Processo e linha do tempo de desabilitação do Adobe Analytics {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="Desabilitar um sistema de gerenciamento de tags de terceiros"
>abstract="Com os dados do SDK da web totalmente funcionais, trabalhe com o(a) admin de tags para remover a biblioteca do AppMeasurement de seu sistema de gerenciamento de tags de terceiros.<br><br>O tempo estimado para executar esta etapa depende da facilidade de desabilitar o AppMeasurement no produto de gerenciamento de tags, bem como do ciclo de lançamento que sua organização utiliza para implantar e gerenciar o código de tags."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-tags"
>title="Desabilitar a extensão do Analytics nas tags"
>abstract="Quando os dados do SDK da Web estiverem totalmente funcionais, trabalhe com o(a) admin de tags para remover a extensão do Adobe Analytics da propriedade de tag. Antes de fazer isso, verifique se os usuários fizeram a transição do Adobe Analytics para o Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-api"
>title="Desabilitar a coleta de dados da API no Adobe Analytics"
>abstract="Quando os dados do SDK da Web estiverem totalmente funcionais, trabalhe com a equipe de engenharia aplicável para remover o código do Adobe Analytics do projeto. Antes de fazer isso, verifique se os usuários fizeram a transição do Adobe Analytics para o Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

A sua implementação do Adobe Analytics é parte essencial de uma atualização bem-sucedida para o Customer Journey Analytics, conforme descrito na seção acima, [Usos do Adobe Analytics durante e após uma atualização](#uses-of-adobe-analytics-during-and-after-an-upgrade).

Quando não precisar mais do Adobe Analytics para as finalidades descritas na seção acima, use as seguintes informações para removê-lo:

1. Parar de coletar dados com o Adobe Analytics.

   Ao satisfazer-se com as comparações lado a lado dos dados do Adobe Analytics e do Customer Journey Analytics, é possível interromper a coleta de dados com a implementação do Adobe Analytics. Os novos dados do Adobe Analytics não fluirão mais para o Customer Journey Analytics por meio do conector de origem do Analytics.

   No entanto, os dados coletados no ambiente do Adobe Analytics antes desse ponto ainda estão disponíveis como dados históricos no Customer Journey Analytics por meio do conector de origem do Analytics.

   Esse processo possui diferenças dependendo do método de coleta de dados usado para implementar o Adobe Analytics:

   +++ AppMeasurement

   [Desabilitar a coleta de dados do AppMeasurement](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md).

   +++

   +++ Extensão do Analytics (Tags)

   Desabilitar a extensão do Analytics nas tags.

   +++

   +++ API

   Desabilitar a coleta de dados da API.

   +++

   +++ Terceiros

   Trabalhe com o admin de tags para remover a biblioteca do AppMeasurement do sistema de gerenciamento de tags de terceiros.

   +++

1. Remova o Adobe Analytics as a service do fluxo de dados.

   Com os dados do SDK da web totalmente funcionais, trabalhe com o administrador da Platform para remover o Adobe Analytics as a service do fluxo de dados.

   Antes de remover o Adobe Analytics as a service, verifique se os usuários do Analytics estão usando o Customer Journey Analytics e não o Adobe Analytics.

1. Remova completamente o conector de origem do Analytics.

   Depois de coletar dados históricos suficientes no Customer Journey Analytics com a nova implementação do SDK da Web, é possível remover totalmente o conector de origem do Analytics.

   Faça isso quando não precisar mais dos dados históricos do ambiente do Adobe Analytics por meio do conector de origem do Analytics e puder confiar somente nos dados históricos coletados com a nova implementação do SDK da web.

{{upgrade-final-step}}

