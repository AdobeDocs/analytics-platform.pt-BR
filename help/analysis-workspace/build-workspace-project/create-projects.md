---
description: Saiba como criar um projeto no Analysis Workspace.
title: Criar projetos
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 518bebc18611136873fce5c23dd7041afafe1220
workflow-type: ht
source-wordcount: '454'
ht-degree: 100%

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
>abstract="Especifica se as instâncias repetidas devem ser contadas nos relatórios.<br/><br/>Observação: essa configuração não se aplica às visualizações de fluxo ou fallout."

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Contar instâncias repetidas"
>abstract="Especifica se as instâncias repetidas devem ser contadas nos relatórios.<br/>Observação: essa configuração não se aplica às visualizações de fluxo ou fallout."


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="Permitir comentários"
>abstract="Quando habilitado, uma área de comentários fica disponível no painel direito do projeto no Analysis Workspace."


As configurações do projeto fornecem informações sobre o projeto ativo no momento.

![A janela Informações e configurações do projeto.](./assets/projectinfo.png)

As configurações incluem:

| Configuração | Descrição |
|---|---|
| Nome do projeto | O nome fornecido ao projeto. Você pode clicar duas vezes no nome para editá-lo. |
| Proprietário | Nome do(a) proprietário(a) do projeto. |
| Última modificação | Data da última modificação do projeto. |
| Tags | Lista qualquer tag aplicada a um projeto para classificar com mais facilidade. |
| Descrição | Uma descrição é útil para esclarecer a finalidade de um projeto. Você pode clicar duas vezes na descrição para editá-la. |
| Contar instâncias repetidas | Especifica se as instâncias repetidas são contadas nos relatórios. Observação: essa configuração não se aplica às visualizações de fluxo ou fallout. |
| Mostrar anotações | Especifica se as anotações do projeto são exibidas ou não. |
| [Paleta de cores do projeto](/help/analysis-workspace/build-workspace-project/color-palettes.md) | É possível alterar a paleta de cores categórica usada no Espaço de trabalho escolhendo entre paletas predefinidas que foram otimizadas para a cegueira de cores ou especificando a paleta personalizada. Esse recurso afeta muitas coisas no Espaço de trabalho, incluindo a maioria das visualizações. |
| [Exibir densidade](/help/analysis-workspace/build-workspace-project/view-density.md) | Permite ver mais dados na tela ao reduzir o preenchimento vertical do painel esquerdo, das tabelas de forma livre e das tabelas de coorte. |
| Permitir comentários | Quando essa opção for habilitada, uma área de comentários ficará disponível no painel direito do projeto no Analysis Workspace. Para obter mais informações, consulte [Adicionar e gerenciar comentários em projetos](/help/analysis-workspace/build-workspace-project/comment-projects.md). |



