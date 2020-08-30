---
description: 'null'
keywords: Analysis Workspace
title: Criar projeto - visão geral
topic: Reports and analytics
uuid: a68be05d-f31e-4e6d-ad04-c784ecb0eb00
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 100%

---


# Criar projeto - visão geral

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

**[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**

Você pode criar um projeto robusto do Analytics com base em uma combinação de exibições, componentes de relatórios e tabelas de dados. Ele adiciona muitos dos recursos do criador de tabelas da Ad Hoc Analysis ao Analytics.

No Analysis Workspace, você pode comparar e examinar os dados de maneiras que não eram possíveis anteriormente. Por exemplo, é possível configurar relatórios classificados e faça alterações iterativas imediatas à consulta de dados e acesse e manipule os valores no nível de relatório.

A consulta vai diretamente para o mecanismo de relatórios. É possível fazer alterações em linha com outros relatórios para criar a sua análise. Os resultados retornam imediatamente, sem nenhuma atualização do navegador.

## Página da lista de projetos da Workspace {#section_39AA007D7C384F4E869F842F1C7B11F8}

Na primeira vez que for até **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, a página listará todos os projetos que você possuir ou aos quais tiver acesso. Para definir essa página como a página de aterrissagem do Adobe Analytics, clique em **[!UICONTROL Definir como página de aterrissagem]**. (Se você não encontrar essa opção, como na captura de tela abaixo, ela já é sua página inicial).

![](assets/sample-project.png)

A página da lista de projeto do Workspace contém as informações a seguir:

| Elemento | Descrição |
|---|---|
| Projeto [Modelos](/help/analysis-workspace/build-workspace-project/starter-projects.md) | Você pode usar esses modelos de projeto pré-preenchidos como estão ou adaptá-los às suas necessidades (adicionando ou substituindo métricas ou visualizações, por exemplo) e salvá-los com um novo nome. |
| [Criar novo projeto](/help/analysis-workspace/home.md) | Clique nesse link para criar um novo projeto a partir do zero. |
| Gerenciar projetos | Clicar nesse link o direciona para o Gerenciador de componentes de projetos (**[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Projetos]**), que lista todos os projetos e permite marcar, compartilhar, excluir, renomear, aprovar e exportar projetos para CSV. |
| Exibir tutoriais | O direciona para os [vídeos no YouTube do Analysis Workspace](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS). |
| Nome | Nome do projeto do Workspace. |
| Criado por | A pessoa que criou o projeto (você ou alguém que compartilhou o projeto com você.) |
| Tags | As tags aplicadas ao projeto, no Gerenciador de componentes de projetos, ou em **[!UICONTROL Workspace]** > **[!UICONTROL Projeto]** > **[!UICONTROL Informações e configurações do projeto]**. |
| Última modificação | Data e hora em que o projeto foi modificado pela última vez. |

## Informações e configurações do projeto {#section_63773D0B9E4543E88068ECECB9EEB4C6}

**[!UICONTROL Workspace]** > **[!UICONTROL Projeto]** > **[!UICONTROL Informações e configurações do projeto]**

![](assets/projectinfo.png)

**[!UICONTROL Informações e configurações do projeto]** fornecem informações sobre o projeto ativo no momento.

| Configuração | Descrição |
|---|---|
| Projeto Nome | O nome fornecido ao projeto. Você pode clicar duas vezes no nome para editá-lo. |
| Criado por | Nome do proprietário do projeto. |
| Última modificação | Data da última modificação do projeto. |
| Tags | Lista qualquer tag aplicada a um projeto para classificar com mais facilidade. Além disso, também é possível adicionar tags a projetos ao salvá-los. Exiba as tags de um projeto na Página inicial do Workspace na coluna [!UICONTROL Tags]. |
| Descrição | Uma descrição é útil para esclarecer a finalidade de um projeto. Você pode clicar duas vezes na descrição para editá-la. |
| Contagem de instâncias repetidas no projeto | Especifica se as instâncias repetidas devem ser contadas nos relatórios. Se você tiver vários valores em sequência para a mesma variável, pode contá-las como uma ou várias instâncias dessa variável. |
| Esquema de cores da visualização | É possível alterar o esquema de cores utilizado no Workspace, escolhendo em uma paleta de cores diferente ou especificando sua própria paleta. Esse recurso afeta muitas coisas no Workspace, incluindo a maioria das visualizações. |
| Exibir densidade | Permite ver mais dados na tela, ao reduzir o preenchimento vertical do painel à esquerda, em tabelas de forma livre e de coorte. |

## Menu de projetos {#section_850CDFCB86A64EB0A0AD5B9E0FCB7013}

O menu superior de Projetos tem a seguinte aparência:

![](assets/new-project-menus.png)

O submenu contém as seguintes opções.

>[!NOTE]
>
>As opções marcadas com um asterisco (*) são exibidas somente em projetos **salvos**.

| Projeto | Editar | Inserir | Componentes | Compartilhar | Ajuda |
|---|---|---|---|---|---|
| Novo | Desfazer | Novo painel | Novo segmento | Compartilhar projeto | Vídeos |
| Abrir | Limpar | Novo painel de forma livre | Nova métrica | Obter link do projeto* | Teclas de atalho |
| Salvar | Limpar tudo | Novo painel de Comparação de segmentos | Novo intervalo de datas | Enviar arquivo agora* | Fórum de ajuda |
| Salvar como* |  | Nova tabela de forma livre | Novo alerta | Enviar arquivo agendado* |  |
| Definir como Página inicial* |  | Nova linha | Atualizar componentes | Preparar dados do projeto |  |
| Atualizar projeto |  | Nova barra |  |  |  |
| Baixar CSV |  |  |  |  |  |
| Baixar o PDF* |  |  |  |  |  |
| Informações e configurações do projeto |  |  |  |  |  |

## Trilho da esquerda {#section_271295C26EC840ABB2A8E7EC0498B60E}

O painel da esquerda tem 3 ícones, que permitem acessar os Painéis, as [Visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) e os [Componentes](/help/components/overview.md) (Dimensões, Métricas, Segmentos, Intervalos de data) com um clique:

![](assets/panels.png) ![](assets/visualizations.png) ![](assets/components.png)

Foi adicionado um **[!UICONTROL Painel em branco]** à lista de painéis que pode ser acessada no painel esquerdo. Para criar um **novo Painel de coorte**, arraste um Painel em branco e solte-o em uma visualização de Tabela de coorte.
