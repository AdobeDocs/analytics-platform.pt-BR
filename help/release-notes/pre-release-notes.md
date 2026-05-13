---
title: Notas de pré-lançamento do Customer Journey Analytics
description: Visualizar as notas de pré-lançamento mais recentes do Customer Journey Analytics
feature: Release Notes
hide: true
exl-id: 61982e38-b43a-41b5-85e0-59ed374463a9
TQID: https://experienceleague.adobe.com/V4jdf363mA1GmsYjZ7yv3MiAMc7sJ7U3s7kXeY47Uyo
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 662
ht-degree: 80%

---

# Notas de pré-lançamento do Adobe Customer Journey Analytics

>[!IMPORTANT]
>
>Este documento é uma **visualização** das notas de versão do mês atual. Os itens da versão estão sujeitos a alterações e podem ser adicionados ou removidos na versão final.

Essas notas de versão abrangem o período de lançamento de 2 de junho de 2025 a 15 de julho de 2025. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos.

Consulte a documentação a seguir para obter as notas de versão do Adobe Experience Platform e seus outros aplicativos:

* [Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/release-notes/pre-release-notes)
* [Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/whats-new/release-notes?lang=en)
* [Adobe Journey Optimizer B2B](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/release-notes?lang=en)
* [Composição de público-alvo federado](https://experienceleague.adobe.com/en/docs/federated-audience-composition/using/release-notes?lang=en)
* [Colaboração da Real-Time CDP](https://experienceleague.adobe.com/en/docs/real-time-cdp-collaboration/using/latest?lang=en)

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **O painel esquerdo do Analysis Workspace não abre e fecha ao passar o mouse** | O painel esquerdo no Analysis Workspace é usado para adicionar componentes, painéis e visualizações ao seu projeto. A opção de abrir temporariamente o painel esquerdo passando o mouse sobre um dos ícones à esquerda não está mais disponível. Em vez disso, basta clicar em um desses ícones para manter o painel aberto e, em seguida, clicar no mesmo ícone para fechá-lo. |  | 2 de junho de 2025 <p>(Planejado originalmente para lançamento em 29 de maio de 2025)</p> |
| **Customer Journey Analytics B2B Edition** | O Customer Journey Analytics B2B Edition ajuda as empresas B2B a alinhar suas equipes de marketing, vendas e produtos fornecendo insights de conta acionáveis que impulsionam o crescimento da receita. Com a conta posicionada no centro do modelo de dados, toda a análise se concentra na jornada da conta. Adicionar uma nova camada de entidades (contas, oportunidades e grupos de compras) sobre eventos baseados em pessoas e eventos baseados em tempo cria uma imagem completa do ciclo de vida de marketing e receita B2B. [Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 18 de junho de 2025 |
| **Suporte para Destinos Seguros no Report Builder** | Novos destinos de exportação foram adicionados ao complemento do Report Builder. Os seguintes destinos de armazenamento na nuvem são compatíveis: <ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> |  | 18 de junho de 2025 |
| **Nova experiência de visualização** | O painel usado para visualizar segmentos, métricas calculadas, entre outras coisas, agora usa uma visualização de barra horizontal, em vez de uma visualização de rosca. |  | 18 de junho de 2025 |
| **Caixa de diálogo do modelo de atribuição modificada** | Agora você pode definir o container e o período separadamente na caixa de diálogo do modelo de atribuição. |  | 18 de junho de 2025 |
| **Mapa de conexão** | Uma nova [interface do mapa de conexão](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-connections/create-connection#connection-map) está disponível para exibir visualmente a configuração da sua conexão. |  | 18 de junho de 2025 |
| **Adicionar e exibir comentários em projetos do Analysis Workspace** | Um novo [recurso de comentários](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) no Analysis Workspace permite que você compartilhe insights e faça perguntas dentro do contexto de um projeto do Analysis Workspace. Isso pode agilizar as discussões sobre os dados, mantendo as conversas dentro do contexto dos dados que estão sendo discutidos. É possível <ul><li>Comentar em qualquer projeto do Analysis Workspace ao qual você tenha acesso</li><li>Comentar em um ponto específico de uma visualização ou fazer comentários gerais sobre um projeto</li><li>Marcar outros usuários para notificá-los sobre seus comentários</li><li>Gerenciar comentários existentes (editar, fixar, resolver e assim por diante)</li></ul>Os administradores do Customer Journey Analytics podem [desabilitar comentários no nível da organização](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Os proprietários do projeto podem [desabilitar comentários no nível do projeto](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  | 25 de junho de 2025 <p>(Planejado originalmente para lançamento em 29 de maio de 2025)</p> |
