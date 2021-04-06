---
description: A preparação permite limitar os componentes antes de compartilhar um projeto.
keywords: Preparação do Analysis Workspace
title: Preparar projetos do
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 44%

---

# Preparar projetos do

A preparação permite limitar os componentes (dimensões, métricas, filtros, intervalos de datas) antes de compartilhar um projeto. Quando um recipient abrir o projeto, ele verá um conjunto limitado de componentes que você preparou para eles. A preparação é uma etapa opcional, mas recomendada, antes de compartilhar um projeto.

>[!NOTE]
> Os perfis de produto são o principal mecanismo que controla os componentes que um usuário pode ver. Eles são gerenciados por meio do [Adobe Experience Cloud Admin Console](https://docs.adobe.com/content/help/pt-BR/core-services/interface/manage-users-and-products/admin-getting-started.html). A Preparação é um filtro secundário.

## Aplicar preparação de projeto

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Preparar dados do projeto]**.
Os componentes usados no projeto serão adicionados automaticamente.
1. (Opcional) Para adicionar mais componentes, arraste os componentes que deseja compartilhar do painel esquerdo para o campo [!UICONTROL Preparar componentes].
1. Clique em **[!UICONTROL Concluído]**.

A preparação também pode ser aplicada no menu [!UICONTROL Compartilhar] clicando em **[!UICONTROL Preparar e Compartilhar]**. Essa opção organiza automaticamente o projeto para os componentes em uso no projeto. Você pode adicionar outros componentes seguindo as etapas acima.

![](assets/curation-field.png)

## Visualização de projeto preparado

Quando um recipient abrir um projeto preparado, ele verá apenas o conjunto preparado de componentes que você definiu:

![](assets/curate-project.png)

## Remover preparação do projeto

Para remover a preparação do projeto e restaurar o conjunto completo de componentes no painel esquerdo:

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Preparar dados do projeto]**.
1. Clique em **[!UICONTROL Remover preparação]**.
1. Clique em **[!UICONTROL Concluído]**.

## Opções de curadoria de componentes

Em um projeto preparado, o recipient terá a opção de **[!UICONTROL Mostrar todos]** componentes no painel esquerdo. [!UICONTROL Mostrar tudo] revela conjuntos diferentes de componentes, dependendo do/da:

* Nível de permissão do usuário (admin ou non-admin)
* Função do projeto (proprietário/editor ou não)
* Tipo de preparação aplicada (no nível do projeto)

| Tipo de preparação | O administrador pode visualizar | O proprietário do projeto que não é administrador (ou a função de edição) pode ver | A função duplicada de não administrador pode ver |
| --- | --- | --- | --- |
| **Componentes &quot;ocultos&quot; de uma visualização de dados** | Todos os componentes de visualização de dados disponíveis para relatórios (os componentes ocultos exigem o clique em &quot;Mostrar tudo&quot;) | Não disponível para relatório | Não disponível para relatório |
| **Componentes adicionados ou removidos de uma visualização de dados** | Somente componentes adicionados à visualização de dados (ocultos ou não ocultos). Os administradores não podem criar relatórios sobre campos ou componentes que não estão definidos pela visualização de dados. | Somente componentes adicionados à visualização de dados ou componentes de propriedade ou compartilhados com o usuário. Componentes ocultos não estão disponíveis (como curadoria de VRS). | Somente os componentes adicionados ao DV não estão ocultos e foram incluídos na preparação do projeto. |
| **Componentes preparados em um projeto** | Todos os componentes de visualização de dados disponíveis para relatórios (os componentes ocultos exigem o clique em &quot;Mostrar tudo&quot;) | Todos os componentes de visualização de dados não ocultos (requer clicar em &quot;mostrar tudo&quot;) | Somente componentes preparados, além de quaisquer componentes de propriedade ou compartilhados com o usuário |
| **Projeto preparado usando uma visualização de dados com componentes ocultos** | Todos os componentes de dados disponíveis para relatórios (componentes ocultos e não preparados exigem o clique em &quot;Mostrar tudo&quot;) | Todos os componentes de projeto não preparados, todos os componentes de visualização de dados não ocultos e quaisquer componentes de propriedade ou compartilhados pelo usuário | Somente componentes preparados, além de quaisquer componentes de propriedade ou compartilhados com o usuário |
