---
description: Saiba como criar um projeto no Analysis Workspace
title: Criar projetos
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 519e7d583edc1eab9b6dd10fec024ac4bb2b93cf
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 40%

---

# Criar projetos {#create-projects}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_countrepeatinstances"
>title="Contar instâncias repetidas"
>abstract="Especifica se as instâncias repetidas devem ser contadas nos relatórios.<br/><br/>Observação: essa configuração não se aplica às visualizações de Fluxo ou Fallout."

<!-- markdownlint-enable MD034 -->


[Os projetos](/help/analysis-workspace/build-workspace-project/freeform-overview.md) no Analysis Workspace permitem que você crie e visualize análises comerciais críticas.  Essas análises podem ser compartilhadas com as partes interessadas dentro ou fora da organização.

1. No Customer Journey Analytics, selecione **[!UICONTROL Workspace]**.

1. Selecione **[!UICONTROL Projetos]** no painel esquerdo e, em seguida, **[!UICONTROL Criar projeto]**.

1. Selecione **Projeto do Workspace em branco** para criar seu projeto do Workspace usando um navegador.

   Consulte [Cartão de pontuação para dispositivos móveis em branco](/help/mobile-app/curator.md) para obter mais informações sobre como criar um projeto de Cartão de pontuação para dispositivos móveis que você pode compartilhar com outras partes interessadas usando um aplicativo para dispositivos móveis. E consulte [Análise guiada](/help/guided-analysis/overview.md) para obter mais informações sobre as várias opções disponíveis para criar seu projeto de análise guiada.

1. Selecione [!UICONTROL **Criar**].


Agora que você criou um projeto Workspace em branco, verifique se está familiarizado com a interface do usuário do [Analysis Workspace](/help/analysis-workspace/home.md). Depois de pronto, você pode criar seu projeto. Para fazer isso:

![Exemplo de projeto](assets/example-project.png)

* Adicione [painéis](/help/analysis-workspace/c-panels/panels.md) ao seu projeto. Por exemplo, o ➊ **[!DNL Example Panel]**.

* Adicione [visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) aos seus painéis. Por exemplo:
   * ➋ de visualização de **[!DNL Line Graph]** [Linha](/help/analysis-workspace/visualizations/line.md)
   * ➌ de visualização de **[!DNL Countries]** [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)
* Adicione [componentes](/help/components/overview.md) às suas visualizações. Por exemplo:
   * **[!DNL Store Country]** [dimensão](/help/components/dimensions/overview.md) ➍
   * **[!DNL People]** [métrica](/help/components/apply-create-metrics.md) ➎
   * **[!DNL Avg Order Value]** [métrica calculada](/help/components/calc-metrics/calc-metr-overview.md) ➏
   * **[!DNL Mobile App Sessions]** [filtro](/help/components/filters/filters-overview.md) ➐
   * **[!DNL Last Month]** [intervalo de datas](/help/components/date-ranges/overview.md) ➑
   * **[!DNL Example]** [anotação](/help/components/annotations/overview.md) ➒


## Informações e configurações do projeto {#project-info-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_repeatinstances"
>title="Contar instâncias repetidas"
>abstract="Especifica se as instâncias repetidas devem ser contadas nos relatórios.<br/>Observação: essa configuração não se aplica às visualizações de Fluxo ou Fallout."

<!-- markdownlint-enable MD034 -->


As configurações do projeto fornecem informações sobre o projeto ativo no momento.

![A janela Informações e Configurações do Projeto.](./assets/projectinfo.png)

As configurações incluem:

| Configuração | Descrição |
|---|---|
| Nome do projeto | O nome fornecido ao projeto. Você pode clicar duas vezes no nome para editá-lo. |
| Proprietário | Nome do proprietário do projeto. |
| Última modificação | Data da última modificação do projeto. |
| Tags | Lista qualquer tag aplicada a um projeto para classificar com mais facilidade. |
| Descrição | Uma descrição é útil para esclarecer a finalidade de um projeto. Você pode clicar duas vezes na descrição para editá-la. |
| Contar instâncias repetidas | Especifique se as instâncias repetidas serão contadas nos relatórios. Observação: essa configuração não se aplica às visualizações de Fluxo ou Fallout. |
| Mostrar anotações | Especifique se as anotações são mostradas para este projeto ou não. |
| [Paleta de cores do projeto](/help/analysis-workspace/build-workspace-project/color-palettes.md) | É possível alterar a paleta de cores categórica usada no Espaço de trabalho escolhendo entre paletas predefinidas que foram otimizadas para a cegueira de cores ou especificando a paleta personalizada. Esse recurso afeta muitas coisas no Espaço de trabalho, incluindo a maioria das visualizações. |
| [Exibir densidade](/help/analysis-workspace/build-workspace-project/view-density.md) | Permite ver mais dados na tela, ao reduzir o preenchimento vertical do painel esquerdo, em tabelas de forma livre e de coorte. |



