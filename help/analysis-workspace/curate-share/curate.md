---
description: Saiba como preparar projetos no Analysis Workspace. A preparação limita o acesso a componentes antes de compartilhar um projeto.
keywords: Preparação do Analysis Workspace
title: Preparar projetos
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
role: User
source-git-commit: 084c995658a5cf698d253f1c15229f621a8c55d5
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 52%

---

# Preparar projetos do

A preparação permite limitar os componentes (dimensões, métricas, segmentos, intervalos de datas) antes de compartilhar um projeto. Quando um recipient abre o projeto, ele vê um conjunto limitado de componentes que você preparou para eles. A preparação é uma etapa opcional, mas recomendada, antes de compartilhar um projeto.

>[!NOTE]
> Os perfis de produto são o principal mecanismo que controla os componentes que um usuário pode ver. Eles são gerenciados por meio do [Admin Console da Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/administration/admin-tool-experience-cloud). A preparação é um segmento secundário.

## Aplicar preparação de projeto

1. Selecione **[!UICONTROL Compartilhar]** > **[!UICONTROL Preparar Dados do Projeto]**.
Os componentes usados no projeto são adicionados automaticamente.
Se um projeto tiver várias visualizações de dados, você verá um destino de preparação para cada visualização de dados no projeto.
1. (Opcional) Para adicionar mais componentes, arraste os componentes que deseja compartilhar do painel esquerdo para a área de soltar **[!UICONTROL Preparar componentes]** da exibição de dados.
1. Selecione **[!UICONTROL Concluído]**.

<!--
Curation can also be applied from the [!UICONTROL Share] menu by selecting **[!UICONTROL Curate and Share]**. This option automatically curates the project to the components in use in the project. You can add additional components following the steps above.
-->

![A janela Preparar componentes mostrando os componentes em uso no projeto.](assets/curation-field.png)

Quando um recipient abre um projeto preparado, ele só vê o conjunto preparado de componentes que você definiu:


## Remover preparação do projeto

Para remover a curadoria do projeto e restaurar o conjunto completo de componentes no painel esquerdo:

1. Selecione **[!UICONTROL Compartilhar]** > **[!UICONTROL Preparar Dados do Projeto]**.
1. Selecione **[!UICONTROL Remover Preparação]**.
1. Selecione **[!UICONTROL Concluído]**.

## Opções de curadoria de componentes

Em um projeto com curadoria, o recipient tem a opção de **[!UICONTROL Mostrar todos]** componentes no painel esquerdo. [!UICONTROL Mostrar tudo] revela conjuntos diferentes de componentes, dependendo dos seguintes fatores:

* O nível de permissão do usuário (administrador ou não)
* Função do projeto (proprietário/editor ou não)
* Tipo de curadoria aplicada (no nível do projeto)

| Tipo de curadoria | O administrador pode visualizar | O proprietário não administrador do projeto (ou com função de edição) pode visualizar | O usuário não administrador com função duplicada pode visualizar |
| --- | --- | --- | --- |
| **Componentes *ocultos* de uma visualização de dados** | Todos os componentes de visualização de dados estão disponíveis para relatórios (os componentes ocultos exigem que você selecione **[!UICONTROL Mostrar tudo]**) | Não disponível para relatório | Não disponível para relatório |
| **Componentes adicionados ou removidos de uma visualização de dados** | Somente componentes adicionados à visualização de dados (ocultos ou não ocultos). Os administradores não podem criar relatórios sobre campos ou componentes que não estejam definidos na visualização de dados. | Somente componentes adicionados à visualização de dados ou componentes de propriedade ou compartilhados com o usuário. Componentes ocultos não estão disponíveis (como curadoria de conjunto de relatórios virtuais). | Somente os componentes adicionados à visualização de dados não estão ocultos e são incluídos na curadoria do projeto. |
| **Componentes preparados em um projeto** | Todos os componentes de exibição de dados disponíveis para relatórios (os componentes ocultos exigem que você selecione **[!UICONTROL Mostrar tudo]**) | Todos os componentes de visualização de dados não ocultos (exige que se clique em &quot;mostrar tudo&quot;) | Somente componentes preparados, além de quaisquer componentes de propriedade ou compartilhados com o usuário |
| **Projeto preparado usando uma visualização de dados com componentes ocultos** | Todos os componentes de dados disponíveis para relatórios (os componentes ocultos e não preparados exigem que você selecione **[!UICONTROL Mostrar tudo]**) | Todos os componentes de projeto não preparados, todos os componentes de visualização de dados não ocultos e quaisquer componentes de propriedade do usuário ou compartilhados com o usuário | Somente componentes preparados, além de quaisquer componentes de propriedade do usuário ou compartilhados com o usuário |
