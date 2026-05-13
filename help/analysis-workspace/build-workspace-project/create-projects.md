---
description: Saiba como criar um projeto no Analysis Workspace.
title: Criar projetos
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
TQID: https://experienceleague.adobe.com/DWTWJ2Bd9iEPO2awiiOLcUzUGPc-clZul3dNFcyWvxk
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: a8b1c240-f315-46e3-b813-f545c4279dd1id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: fa6ac035-8403-478b-9ce1-3fe29d211fca
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 459
ht-degree: 88%

---

# Criar projetos {#create-projects}


Os [projetos](/help/analysis-workspace/build-workspace-project/freeform-overview.md) do Analysis Workspace permitem que você crie e visualize análises vitais para os negócios.  Essas análises podem ser compartilhadas com as partes interessadas dentro ou fora da organização.

1. No Customer Journey Analytics, selecione **[!UICONTROL Espaço de trabalho]**.

1. Selecione **[!UICONTROL Projetos]** no painel esquerdo e clique em **[!UICONTROL Criar projeto]**.

1. Selecione **Projeto do espaço de trabalho em branco** para criar o projeto usando um navegador.

   Consulte [Cartão de pontuação móvel em branco](/help/mobile-app/curator.md) para obter mais informações sobre como criar um projeto de cartão de pontuação para dispositivos móveis que você pode compartilhar com outras partes interessadas usando um aplicativo móvel. E consulte [Análise guiada](/help/guided-analysis/overview.md) para obter mais informações sobre as várias opções disponíveis para criar seu projeto de análise guiada.

1. Selecione [!UICONTROL **Criar**].


Agora que você criou um projeto do espaço de trabalho em branco, certifique-se de que saiba usar a interface do [Analysis Workspace](/help/analysis-workspace/home.md). Quando estiver tudo pronto, você pode criar o seu projeto. Para fazer isso:

![Exemplo de projeto](assets/example-project.png)

* Adicionar [painéis](/help/analysis-workspace/c-panels/panels.md) ao seu projeto. Por exemplo, o **[!DNL Example Panel]** ➊.

* Adicione [visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) aos seus painéis. Por exemplo:
   * Visualização de **[!DNL Line Graph]** [linha](/help/analysis-workspace/visualizations/line.md) ➋
   * Visualização de **[!DNL Countries]** [tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ➌
* Adicionar [componentes](/help/components/overview.md) às suas visualizações. Por exemplo:
   * [Dimensão](/help/components/dimensions/overview.md) de **[!DNL Store Country]** ➍
   * [Métrica](/help/components/apply-create-metrics.md) **[!DNL People]** ➎
   * [Métrica calculada](/help/components/calc-metrics/calc-metr-overview.md) **[!DNL Avg Order Value]** ➏
   * [Segmento](/help/components/segments/seg-overview.md) **[!DNL Mobile App Sessions]** ➐
   * [Intervalo de datas](/help/components/date-ranges/overview.md) **[!DNL Last Month]** ➑
   * [Anotação](/help/components/annotations/overview.md) de **[!DNL Example]** ➒


## Informações e configurações do projeto {#project-info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="Contar instâncias repetidas"
>abstract="Especifica se as instâncias repetidas são contadas nos relatórios.<br/><br/>Observação: essa configuração não se aplica às visualizações de fluxo ou fallout."

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Contar instâncias repetidas"
>abstract="Especifica se as instâncias repetidas são contadas nos relatórios.<br/>Observação: essa configuração não se aplica às visualizações de fluxo ou fallout."


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="Permitir comentários"
>abstract="Quando habilitado, uma área de comentários fica disponível no painel direito do projeto no Analysis Workspace."


As configurações do projeto fornecem informações sobre o projeto ativo no momento.

![A janela Informações e configurações do projeto.](./assets/projectinfo.png)

As configurações incluem:

| Configuração | Descrição |
|---|---|
| Nome do projeto | O nome dado ao projeto. Você pode clicar duas vezes no nome para editá-lo. |
| Proprietário | Nome do(a) proprietário(a) do projeto. |
| Última modificação | Data da última modificação no projeto. |
| Tags | Lista as tags aplicadas a um projeto para facilitar a categorização. |
| Descrição | Uma descrição é útil para esclarecer a finalidade de um projeto. Você pode clicar duas vezes na descrição para editá-la. |
| Contar instâncias repetidas | Especifica se as instâncias repetidas são contadas nos relatórios. Observação: essa configuração não se aplica às visualizações de fluxo ou fallout. |
| Mostrar anotações | Especifica se as anotações do projeto são exibidas ou não. |
| [Paleta de cores do projeto](/help/analysis-workspace/build-workspace-project/color-palettes.md) | É possível alterar a paleta de cores categórica usada no Espaço de trabalho escolhendo entre paletas predefinidas que foram otimizadas para a cegueira de cores ou especificando a paleta personalizada. Esse recurso afeta muitas coisas no Espaço de trabalho, incluindo a maioria das visualizações. |
| [Exibir densidade](/help/analysis-workspace/build-workspace-project/view-density.md) | Permite ver mais dados na tela ao reduzir o preenchimento vertical do painel esquerdo, das tabelas de forma livre e das tabelas de coorte. |
| Permitir comentários | Quando essa opção for habilitada, uma área de comentários ficará disponível no painel direito do projeto no Analysis Workspace. Para obter mais informações, consulte [Adicionar e gerenciar comentários em projetos](/help/analysis-workspace/build-workspace-project/comment-projects.md). |



