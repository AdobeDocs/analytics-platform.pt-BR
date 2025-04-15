---
description: A preparação permite limitar os componentes antes de compartilhar um projeto.
keywords: Preparação do Analysis Workspace
title: Preparar projetos do
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 82%

---

# Preparar projetos do

A preparação permite limitar os componentes (dimensões, métricas, segmentos, intervalos de datas) antes de compartilhar um projeto. Quando um recipient abrir o projeto, ele verá um conjunto limitado de componentes que você preparou para eles. A preparação é uma etapa opcional, mas recomendada, antes de compartilhar um projeto.

>[!NOTE]
> Os perfis de produto são o principal mecanismo que controla os componentes que um usuário pode ver. Eles são gerenciados por meio do [Admin Console da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR). A curadoria é um segmento secundário.

## Aplicar preparação de projeto

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Preparar dados do projeto]**.
Os componentes usados no projeto serão adicionados automaticamente.
1. (Opcional) Para adicionar mais componentes, arraste os componentes que deseja compartilhar do painel esquerdo para o campo [!UICONTROL Preparar componentes].
1. Clique em **[!UICONTROL Concluído]**.

A preparação também pode ser aplicada no menu [!UICONTROL Compartilhar] clicando em **[!UICONTROL Preparar e Compartilhar]**. Essa opção organiza automaticamente o projeto para os componentes em uso no projeto. Você pode adicionar outros componentes seguindo as etapas acima.

![A janela Preparar Componentes mostrando os componentes em uso no projeto.](assets/curation-field.png)

## Visualização de projeto preparado

Quando um recipient abrir um projeto preparado, ele verá apenas o conjunto preparado de componentes que você definiu:

![Um projeto com curadoria compartilhada mostrando os componentes que você definiu.](assets/curate-project.png)

## Remover preparação do projeto

Para remover a preparação do projeto e restaurar o conjunto completo de componentes no painel esquerdo:

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Preparar dados do projeto]**.
1. Clique em **[!UICONTROL Remover preparação]**.
1. Clique em **[!UICONTROL Concluído]**.

## Opções de curadoria de componentes

Em um projeto com curadoria, o recipient terá a opção de **[!UICONTROL Mostrar todos os]** componentes no painel esquerdo. [!UICONTROL Mostrar tudo] revela conjuntos diferentes de componentes, dependendo dos seguintes fatores:

* O nível de permissão do usuário (administrador ou não)
* Função do projeto (proprietário/editor ou não)
* Tipo de curadoria aplicada (no nível do projeto)

| Tipo de curadoria | O administrador pode visualizar | O proprietário não administrador do projeto (ou com função de edição) pode visualizar | O usuário não administrador com função duplicada pode visualizar |
| --- | --- | --- | --- |
| **Componentes &quot;ocultos&quot; de uma visualização de dados** | Todos os componentes de visualização de dados disponíveis para relatórios (os componentes ocultos exigem que se clique em &quot;Mostrar tudo&quot;) | Não disponível para relatório | Não disponível para relatório |
| **Componentes adicionados ou removidos de uma visualização de dados** | Somente componentes adicionados à visualização de dados (ocultos ou não ocultos). Os administradores não podem criar relatórios sobre campos ou componentes que não estejam definidos pela visualização de dados. | Somente componentes adicionados à visualização de dados ou componentes de propriedade ou compartilhados com o usuário. Componentes ocultos não estão disponíveis (como curadoria de conjunto de relatórios virtual). | Somente os componentes adicionados ao DV não estão ocultos e foram incluídos na curadoria do projeto. |
| **Componentes preparados em um projeto** | Todos os componentes de visualização de dados disponíveis para relatórios (os componentes ocultos exigem que se clique em &quot;Mostrar tudo&quot;) | Todos os componentes de visualização de dados não ocultos (exige que se clique em &quot;mostrar tudo&quot;) | Somente componentes preparados, além de quaisquer componentes de propriedade ou compartilhados com o usuário |
| **Projeto preparado usando uma visualização de dados com componentes ocultos** | Todos os componentes de dados disponíveis para relatórios (é necessário clicar em &quot;Mostrar tudo&quot;, para os componentes ocultos e não preparados) | Todos os componentes de projeto não preparados, todos os componentes de visualização de dados não ocultos e quaisquer componentes de propriedade do usuário ou compartilhados com o usuário | Somente componentes preparados, além de quaisquer componentes de propriedade do usuário ou compartilhados com o usuário |
