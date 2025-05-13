---
description: Saiba como criar um projeto no Analysis Workspace
title: Criar projetos
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: fb7e0e911de2a4a702d6069ca2f53d7769ec608b
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 79%

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

* Adicionar [painéis](/help/analysis-workspace/c-panels/panels.md) ao seu projeto. Por exemplo, o **[!DNL Example Panel]** ➊.

* Adicione [visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) aos seus painéis. Por exemplo:
   * Visualização ➋ de **[!DNL Line Graph]** [Linha](/help/analysis-workspace/visualizations/line.md)
   * **[!DNL Countries]** [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) visualização ➌
* Adicionar [componentes](/help/components/overview.md) às suas visualizações. Por exemplo:
   * **[!DNL Store Country]** [dimensão](/help/components/dimensions/overview.md) ➍
   * **[!DNL People]** [métrica](/help/components/apply-create-metrics.md) ➎
   * **[!DNL Avg Order Value]** [métrica calculada](/help/components/calc-metrics/calc-metr-overview.md) ➏
   * **[!DNL Mobile App Sessions]** [segmento](/help/components/filters/filters-overview.md) ➐
   * **[!DNL Last Month]** [intervalo de datas](/help/components/date-ranges/overview.md) ➑
   * **[!DNL Example]** [anotação](/help/components/annotations/overview.md) ➒


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
>abstract="Quando ativada, uma área de comentários fica disponível no painel direito do projeto no Analysis Workspace."


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
| Permitir comentários | **Observação:** esta funcionalidade está na fase de Teste Limitado da versão e pode não estar disponível ainda em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [versões de recursos do Customer Journey Analytics](/help/release-notes/releases.md). <p>Quando essa opção está ativada, uma área de comentários fica disponível no painel direito do projeto no Analysis Workspace. Para obter mais informações, consulte [Adicionar e gerenciar comentários em projetos](/help/analysis-workspace/build-workspace-project/comment-projects.md).</p> |



