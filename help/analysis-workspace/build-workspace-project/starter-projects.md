---
description: Use modelos no Workspace e crie modelos personalizados.
title: Modelos
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
exl-id: 464032a1-6dae-4df5-b4db-b277788e88c2
translation-type: tm+mt
source-git-commit: a0ea2be203aa2e0df7b195e259b6d98c0c027652
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 95%

---

# Modelos

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

Você pode criar um projeto a partir de:

* **Projeto em branco (padrão)**: para obter instruções, consulte [Criar um projeto no Analysis Workspace](/help/analysis-workspace/home.md).
* **Modelo padrão**: esses modelos são criados pela Adobe e fornecidos com o produto.
* **Modelo personalizado**: esses modelos podem ser criados, compartilhados ou excluídos por usuários com direitos de administrador ou por não administradores, desde que tenham recebido a permissão [!UICONTROL Analysis Workspace: salvar como modelo] no Admin Console. [Saiba mais...](https://docs.adobe.com/content/help/pt-BR/analytics/admin/admin-console/permissions/product-profile.html)

![](assets/start_modal.png)

## Criar um modelo personalizado {#create-custom-template}

Os usuários com direitos de administrador podem tornar qualquer projeto criado por ele um modelo personalizado. Veja como:

1. Abrir o projeto.
1. Vá até **[!UICONTROL Projeto]** > **[!UICONTROL Salvar como modelo]**.

   ![](assets/save_project_template.png)

   O projeto será salvo com o nome do projeto atual, seguido da palavra (Modelo) entre parênteses. Os administradores podem alterar esse nome ao editar o modelo.

   >[!NOTE]
   >
   >Por padrão, os modelos de projeto estão visíveis para todos em sua organização. Você pode organizá-los aplicando tags. (Vá até **[!UICONTROL Projeto]** > **[!UICONTROL Informações e configurações do projeto]** para editar tags e descrições.)

### Ações executáveis nos modelos personalizados

![](assets/custom_templates.png)

| Ação | Descrição |
|--- |--- |
| Editar modelo | Permite que um administrador edite o modelo ao alterar a fonte de dados, modificar componentes, exibições, intervalos de data etc.  Para editar um modelo personalizado,<ul><li>abra a lista de modelos personalizados do Analysis Workspace, selecione um e clique em Editar modelo, ou</li><li>no Analytics, clique em Componentes > Projetos e filtre por Modelos. Clique no nome do modelo que deseja editar.</li></ul>**Observação:** após editar um modelo, dependendo da situação, você terá duas opções: Salvar, Salvar como. Elas se diferem da seguinte forma:<ul><li>**Salvar:** atualiza o modelo personalizado para todos os usuários. Quando outra pessoa cria um projeto a partir deste modelo personalizado, ela verá suas alterações.</li><li>**Salvar como:** cria uma cópia do modelo personalizado com suas alterações. (Você saberá que está no modo de edição quando o item de menu Compartilhar > Compartilhar projeto estiver desativado.)</li></ul> |
| Pesquisar nos modelos | Na caixa de diálogo Modelos personalizados, clique em Pesquisar modelos. |
| Classificar modelos | É possível classificar modelos por ordem alfabética, relevância e data de criação.  Na caixa de diálogo Modelos personalizados, clique em Classificar. |
| Aplicar tags ao modelo | Abra o modelo e vá até Projeto > Informações e configurações do projeto. Clique em Adicionar tags. |
| Modificar descrição do modelo | Abra o modelo e vá até Projeto > Informações e configurações do projeto. Clique duas vezes na descrição e edite-a. |


## Modelos padrão

Quando você abre um Workspace pela primeira vez, os modelos ficam disponíveis no painel esquerdo. Os modelos do Analysis Workspace abrangem casos usuais. Eles são agrupados pela vertical à qual pertencem e são preenchidos com diferentes dimensões, filtros, métricas e visualizações, dependendo da exibição de dados selecionada.

Você pode usar esses modelos pré-preenchidos como estão ou adaptá-los às suas necessidades (adicionando ou substituindo métricas ou visualizações, por exemplo) e salvá-los com um novo nome.

>[!VIDEO](https://video.tv.adobe.com/v/23960)

*(2:46)*

Estes são os modelos disponíveis e as perguntas que cada modelo ajuda a responder.

### Treinamento

Esses modelos padrão orientam você pela terminologia e etapas comuns para criar sua primeira análise no Workspace. Eles estão disponíveis como modelo padrão no modal Novo projeto e substituem o projeto de amostra atual para novos usuários que não têm outros projetos na lista.

* **Tutorial de treinamento - Análise de pesquisa interna**: o tutorial de Pesquisa interna ajuda você a entender o que seus visitantes estão procurando no site ou aplicativo, mas não estão achando. A análise desse tipo de dados pode exibir oportunidades de otimização de conteúdo.

* **Tutorial de treinamento - Análise de marketing**: este tutorial mostra como fazer uma análise de marketing para seus executivos, incluindo quais dimensões e métricas personalizadas são importantes.

### Mídia

* **Consumo de áudio**: que conteúdo está sendo mais consumido pelos usuários, resultando em interações?
* **Recenticidade - Frequência - Fidelidade**: quem são meus leitores fiéis?


### Varejo

* **Desempenho da campanha:** que campanhas estão gerando mais receita?
* **Produtos:** que produtos estão tendo o melhor desempenho?

### Web

* **Aquisição:** quais são os principais impulsionadores de tráfego do meu site?
* **Consumo de conteúdo:** quais são os lugares mais acessados do meu site?
* **Retenção:** que tipo de usuário tem maior probabilidade de se tornar um usuário fiel do meu site?
* **Tecnologia:** que tecnologia as pessoas estão usando para acessar o meu site?

