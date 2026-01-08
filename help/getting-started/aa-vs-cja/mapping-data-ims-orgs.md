---
title: Mapear dados do Analytics de várias organizações IMS
description: Saiba como você pode solicitar o mapeamento de dados de conjuntos de relatórios de várias organizações IMS de origem para uma organização IMS de destino.
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
hide: true
hidefromtoc: true
source-git-commit: 3c34bd50c12b370f5e9f95ac5d6357de4f63e5f6
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# Mapear dados do Analytics de várias organizações IMS

O conector de origem do Analytics só pode assimilar dados de conjuntos de relatórios do Adobe Analytics que pertençam à mesma organização para a qual você tem direito a usar o Customer Journey Analytics. O recurso para mapear dados do Analytics de várias organizações IMS fornece uma solução para essa limitação. O processo para ativar esse recurso está descrito neste artigo.


## Cenário

Você está provisionado com várias organizações IMS e tem dados do Analytics em vários conjuntos de relatórios nessas organizações IMS. Essa configuração pode ser resultado de:

* aquisições ou fusões
* requisitos de estrutura organizacional
* restrições de implantação regional

Pronto para uso, não é possível relatar a combinação de dados de vários conjuntos de relatórios em várias organizações IMS no Customer Journey Analytics. O motivo para essa limitação é que a assimilação de dados do Adobe Analytics na Experience Platform por meio do conector de origem do Analytics é compatível apenas com a assimilação de dados de propriedade de uma única organização IMS. A organização IMS para a qual você está provisionado e que usa para fazer logon na Adobe Analytics, Experience Platform e Customer Journey Analytics.

Com o recurso *mapear dados do Analytics de várias organizações IMS*, você pode solicitar que a Adobe mapeie dados. O recurso usa o conector de origem do Analytics para mapear dados de conjuntos de relatórios que residem em várias organizações IMS de *origem* para conjuntos de dados que fazem parte de uma organização IMS de *destino*. Por exemplo:

| Ilustração | Explicação |
|---|---|
| ![Mapear dados em várias organizações IMS](/help/getting-started/assets/map-data-across-ims-orgs.svg) | Esse mapeamento permite relatar conjuntos de relatórios que existem na Organização IMS 1, Organização IMS 2 e Organização IMS 3 de uma conexão no Customer Journey Analytics provisionada na Organização IMS 3. |

{style="table-layout:fixed"}

## Como usar

Para configurar e habilitar o recurso *mapear dados do Analytics de várias organizações IMS*, é necessário solicitar o mapeamento por meio do gerente de conta da Adobe. Para fazer isso:

1. Como administrador da organização IMS de destino, solicite emails de aprovação de todo o administrador da organização IMS de origem para o qual você deseja mapear conjuntos de relatórios. Você pode usar o texto a seguir como modelo para o email para solicitar aprovação dos administradores da organização IMS de origem.

   | Modelo de email de exemplo |
   | --- |
   | *Representante de nome de empresa*, para conceder à organização de destino selecionada acesso às seguintes organizações IMS (lista de organizações IMS de origem), precisamos garantir que um administrador de cada organização IMS envie sua aprovação para permitir o acesso aos seus dados. Isso ajuda a garantir que temos permissões de acesso a dados respeitadas de qualquer organização IMS afetada. Para garantir que temos a aprovação adequada, peça a um administrador registrado do Adobe para cada organização administrativa que responda a este email com seu nome e organização IMS que eles representam, dizendo: &quot;Eu aprovo&quot; para indicar que eles aprovam para que os dados desta organização IMS apareçam na organização de destino [list destination IMS org]. Observe que esse administrador precisa ser um administrador registrado no sistema da Adobe como um administrador para essa organização IMS. |

1. Envie um email como administrador da organização IMS de destino para o gerente de conta da Adobe que solicita o mapeamento dos conjuntos de relatórios em várias organizações IMS de origem para a organização IMS de destino. Anexe os emails de aprovação que você recebeu dos administradores da organização IMS de origem.

Depois que o gerente de conta recebe o email com a solicitação para mapear os dados do Analytics de várias organizações, a solicitação é revisada no Adobe. O gerente de conta entra em contato com você para esclarecer dúvidas adicionais, treinamento opcional e outras informações.

Depois de aprovado, o mapeamento solicitado é criado e você é notificado. O nome da organização IMS de origem está anexado ao nome do conjunto de relatórios na [lista dos conjuntos de relatórios do Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data) no Experience Platform.

## Limitações e riscos

As seguintes limitações se aplicam aos *dados de mapa do Analytics de várias organizações IMS*:

* Você pode conectar um conjunto de relatórios apenas uma vez entre organizações.
* É necessário excluir todas as conexões para uma organização IMS definida como a organização IMS de destino em um mapeamento antes de solicitar a exclusão do mapeamento.
* As ECIDs não são compatíveis entre organizações IMS de origem mapeadas e não são compatíveis com a organização IMS de destino.
* Um usuário com permissões suficientes para configurar o conector de origem do Analytics na organização IMS de destino pode assimilar dados do Analytics de qualquer organização IMS de origem mapeada. Nenhuma permissão é verificada para esse usuário em nenhuma das organizações IMS de origem.
