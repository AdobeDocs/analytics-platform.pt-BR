---
title: Transferir ativos
description: Saiba como transferir componentes de um usuário para outro
role: Admin
solution: Customer Journey Analytics
exl-id: c5ed81ea-1d55-4193-9bb1-a2a93ebde91f
source-git-commit: 3e521cb4ef532d57b9f408fc12dcf138f130f059
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 98%

---

# Transferir ativos

A ferramenta Transferência de ativos permite transferir a propriedade dos ativos para outros usuários. Os ativos podem incluir componentes como projetos, segmentos, intervalos de datas, métricas calculadas, anotações, alertas e projetos agendados.

Os ativos geralmente estão vinculados a um proprietário individual e, em alguns casos, como no de segmentos e métricas calculadas, não podem ser editados ou compartilhados nem mesmo por admins. Quando os usuários saem da organização ou sua função muda, pode ser necessário transferir a propriedade desses ativos para outros usuários para garantir a continuidade e o acesso apropriado.

## Permissões

A transferência de ativos exige a permissão de admin de produto do Customer Journey Analytics.

## Transferir ativos

1. No CJA, navegue até **[!UICONTROL Ferramentas]** > **[!UICONTROL Transferência de ativos]**.

   ![Item de menu de transferência de ativos](/help/tools/asset-transfer/assets/asset-transfer.png)

1. Na caixa de diálogo **[!UICONTROL Usuários]**, procure e selecione o usuário do qual deseja transferir ativos.

   >[!IMPORTANT]
   >
   >Você só pode fazer uma transferência de 1:1, de um usuário para outro. Não há suporte para transferências “um para muitos” ou “muitos para um”.


1. Depois de selecionar um usuário, a opção Transferir ativos é exibida na parte inferior da tela.

   ![Opção de menu Transferir ativos](/help/tools/asset-transfer/assets/after-selection.png)

1. Clique em **[!UICONTROL Transferir ativos]**.

1. Na tela **[!UICONTROL Transferir ativos]**, selecione primeiro o destinatário para o qual deseja transferir ativos.

1. Agora passe por cada pasta de componentes na navegação à esquerda para selecionar componentes individuais ou todos os ativos em uma pasta para transferir.

   >[!NOTE]
   >
   >A transferência de ativos de um usuário admin para um não admin não atualiza o destinatário para um usuário admin.


   >[!NOTE]
   >
   >    Ao transferir ativos que fazem referência a outros componentes (por exemplo, projetos que fazem referência a outros segmentos e métricas calculadas), os componentes que não pertencem ao proprietário atual do projeto serão compartilhados somente com o destinatário. A propriedade de todos os outros componentes será transferida para o destinatário.

1. Para selecionar _todos_ os ativos em uma pasta, marque a caixa ao lado de **[!UICONTROL Nome]** na parte superior da tabela.

   ![selecione os ativos a serem transferidos](/help/tools/asset-transfer/assets/select-assets.png)

1. Clique em **[!UICONTROL Transferir]** na parte superior direita depois de fazer todas as seleções.

1. Clique em **[!UICONTROL Confirmar]** quando a mensagem de confirmação for exibida.

   >[!IMPORTANT]
   >
   >Não feche a tela durante a transferência para evitar a interrupção do processo. Isso garante uma experiência de transferência perfeita.

## Resultados da transferência

Há três resultados possíveis para uma transferência:

- **Transferência bem-sucedida**: “Ativos transferidos com sucesso.”

- **Sucesso parcial**: “Alguns ativos foram transferidos com sucesso.”

- **Falha na transferência**: “Falha ao transferir ativos. Tente novamente.”

### Possíveis motivos para a falha na transferência de ativos

- Serviços dependentes que causam falhas: a transferência de ativos interage com um serviço diferente para cada tipo de componente (por exemplo, problemas de rede, problemas de serviço downstream), portanto, isso pode causar uma falha parcial ou completa ou falhas intermitentes.

- Componente ausente ou transferido por outro(a) admin: um componente foi excluído por outro usuário ou transferido por outro(a) admin para outra pessoa enquanto um trabalho de transferência de ativos ainda estava em andamento.

- O corpo da API POST não é preenchido corretamente: um componente pode não ser enviado no corpo da API POST quando vários tipos de componentes são selecionados.

- O usuário não existe: o usuário foi excluído durante a transferência ou se tornou inválido por outro motivo. Se o usuário se tornar inválido antes do início da transferência, a ferramenta detectará essa informação e não processará o trabalho. Se o usuário foi excluído durante a transferência, isso poderá causar falhas parciais.

- Falha de conexão/rede: a conexão cai no meio da transferência. Todos os lotes de trabalhos de transferência que já foram transmitidos para o back-end ainda serão processados até a conclusão, mas o usuário não verá a mensagem de resultado da transferência com um resumo das tarefas bem-sucedidas e das que falharam.

- Guia do navegador fechada durante a transferência: no caso de transferências muito grandes, se a guia do navegador fechar ou a navegação pela página for interrompida durante a transferência, somente as solicitações de rede feitas antes disso ocorrer transferirão corretamente os ativos. Se o usuário navegar de volta para a página, a mensagem de status de resposta que indica quais ativos foram transferidos e quais não foram não será exibida.

## Transferir ativos durante a atualização do Adobe Analytics para o Customer Journey Analytics

Um dos principais casos de uso para transferência de ativos é durante a atualização do Adobe Analytics para o Customer Journey Analytics.

O recurso [Migração de componentes](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/component-migration/component-migration) do Adobe Analytics permite migrar projetos de propriedade do(a) admin para outros(as) admins. Todos os componentes que compõem esses projetos são recriados no Customer Journey Analytics e o(a) admin destinatário(a) tem a propriedade de todos esses componentes, independentemente de quem os criou.

Essa ferramenta de transferência de ativos permite que admins reatribuam componentes aos proprietários legítimos, sejam admins ou não.

>[!IMPORTANT]
>
>Embora seja possível transferir componentes usando essa ferramenta, como admin você ainda precisará garantir que o destinatário tenha acesso às visualizações de dados necessárias para exibir/usar esses componentes. Você pode exibir e atribuir permissões no [Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html).

## Exportar para CSV

A opção **[!UICONTROL Exportar para CSV]** permite que admins baixem apenas uma lista de usuários exibida para um arquivo .csv. Não é possível exportar uma lista de ativos transferidos para um arquivo .csv.

## Usuários inativos

Todos os usuários excluídos anteriormente aparecem em uma lista de “Usuários inativos”, junto com todos os seus componentes órfãos. Esses componentes podem ser transferidos para um novo destinatário. Esse recurso estará disponível em janeiro.

![Usuários inativos aparecendo na interface Transferir ativos](assets/inactive-users.png)

