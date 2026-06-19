---
description: Explica a estratégia de lançamento contínuo de recursos do Customer Journey Analytics
title: Estratégia de lançamento de recursos do Customer Journey Analytics
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
feature: Release Notes
autotag-review: '2026-05-19T09:19:46.530Z'
TQID: 'https://experienceleague.adobe.com/nNV-qOa3LVmHUMLf-R2MwNHY0N67hxG2DWbVrpA-ZpI'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: a8e39571-4463-4aa3-8b3f-4e2341ecf3b3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: ht
source-wordcount: 402
ht-degree: 100%

---

# Estratégia de lançamento de recursos do Customer Journey Analytics

As versões do Customer Journey Analytics operam em um modelo de entrega contínua que permite uma abordagem escalável e em fases para a implantação de recursos.

## Estratégia de lançamento

O [!UICONTROL Analysis Workspace] usa sinalizadores de recursos (também conhecidos como “alternadores”) para controlar a visibilidade de novos recursos, permitindo testes de escala controlados antes do lançamento completo. A estratégia de lançamento inclui as seguintes fases:

* **Teste limitado**: uma versão em fases começa com testes feitos por usuários internos da Adobe. Ela é então disponibilizada para um pequeno grupo de contas de clientes para garantir que o recurso atenda às necessidades e expectativas do cliente.

* **Início da implantação**: a implantação de uma versão em fases começa com a fase de teste limitado. A versão é redimensionada de 0% a 100% de disponibilidade aos clientes ao longo de alguns meses. A implementação em fases acontece no nível da organização CX Enterprise, de modo que todos os usuários autorizados em uma organização recebam a mesma experiência.

* **Disponibilidade geral (GA)**: o recurso está disponível para 100% das organizações CX Enterprise autorizadas e o seu lançamento está concluído.

Com cada versão de recurso, a linha do tempo de RTP para GA pode variar. O objetivo é manter as versões curtas, para que, dentro de 2 meses do início do lançamento (RTP), um recurso tenha GA.

## Sinalizadores de recurso

Sinalizadores de recursos são usados para controlar a visibilidade de novos recursos durante o lançamento. A Adobe recomenda habilitar `app.launchdarkly.com` no firewall da sua organização para obter uma experiência ideal durante os lançamentos. Esses sinalizadores são removidos depois que um recurso é lançado para todos. Consulte [Domínios usados pelo Customer Journey Analytics](../technotes/domains.md) para obter mais informações.

Você pode visualizar os sinalizadores de recursos ativos a qualquer momento em **Ajuda > Sobre o Espaço de trabalho > Sinalizadores de recursos ativos**.

## Benefícios

As versões por fases permitem que a Adobe dimensione melhor o processo de implantação de software e garanta que os recursos sejam totalmente testados antes da Disponibilidade geral. Também permite que os recursos sejam lançados assim que estiverem disponíveis, em vez de seguirem uma janela de lançamento mensal fixa.

## Perguntas frequentes

| Pergunta | Resposta |
| --- | --- |
| Posso solicitar acesso antecipado a um recurso? | Não. O acesso antecipado não será concedido.<br>Se você quiser testar os conceitos iniciais do Analytics, recomendamos que você experimente o [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html?lang=pt-BR) para fornecer feedback sobre as inovações líderes do setor. |
| Essa estratégia de lançamento afeta meu acesso aos recursos? | Não. Depois que um recurso chegar à GA, você terá acesso ao recurso se ele fizer parte do seu pacote do Analytics. |
