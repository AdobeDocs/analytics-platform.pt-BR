---
description: Saiba como gerar apresentações em formato pptx a partir de relatórios do Workspace.
keywords: Analysis Workspace
title: Gerar apresentações a partir de relatórios do Workspace
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 680799fdf18703acbd0569e25b41e6ecbc154d62
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 3%

---

# Narrativa de dados: gere apresentações de slides a partir de relatórios do Workspace {#generate-powerpoint}

Você pode gerar automaticamente apresentações .pptx de projetos da Analysis Workspace. Ao gerar apresentações, o Customer Journey Analytics identifica os principais insights automaticamente e os converte em slides prontos para as partes interessadas.

Essa funcionalidade reduz o tempo e o esforço necessários para exibir descobertas de seus projetos do Workspace e permite criar rapidamente narrativas executivas e comunicar o impacto nos negócios.

## Gerar uma apresentação .pptx com base em um projeto do Workspace

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-powerpoint-include-visualizations"
>title="Painéis e visualizações incluídos"
>abstract="Escolha os painéis e as visualizações que deseja incluir na apresentação. É possível incluir até 50 visualizações."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-presentation-emphasized-components"
>title="Componentes destacados"
>abstract="Escolha até 5 métricas e 5 dimensões nas visualizações que você deseja enfatizar na apresentação. As métricas escolhidas são mostradas em itálico, as dimensões são mostradas em negrito e os itens de dimensão são mostrados em uma cor contrastante."

<!-- markdownlint-enable MD034 -->

1. Vá para o projeto do Workspace que contém os dados que você deseja usar como a base da sua apresentação.

1. Selecione **[!UICONTROL Gerar slides]** no canto superior direito da página.

1. Especifique as seguintes informações:

   | Opção | Descrição |
   |---------|----------|
   | **[!UICONTROL Título da capa]** | Especifique um título para a apresentação. Este título aparece no slide de título da apresentação. |
   | **[!UICONTROL Incluir nome do apresentador]** | Especifique o nome do apresentador. Esse nome aparece no slide de título da apresentação, abaixo do título da capa. |
   | **[!UICONTROL Painéis e visualizações a serem incluídos]** | Escolha os painéis e a visualização que deseja incluir na apresentação. É possível incluir até 50 visualizações.<p>A maioria dos painéis e visualizações é compatível. Para obter informações sobre painéis e visualizações sem suporte, consulte [Elementos e recursos do projeto sem suporte](#unsupported-project-elements-and-features).</p> |
   | **[!UICONTROL Descrições do painel e da visualização]** | |
   | **[!UICONTROL Anotações]** | |
   | **[!UICONTROL Enfatizar componentes]** | Escolha até 5 métricas e 5 dimensões nas visualizações que você deseja enfatizar na apresentação.<p>Quando nenhuma ênfase é aplicada, os componentes são exibidos nas apresentações da seguinte maneira:<ul><li>**Métricas e dimensões:** Itálico</li><li>**Itens do Dimension:** Aspas</li></ul></p><p>Quando a ênfase é aplicada, os componentes são exibidos nas apresentações da seguinte maneira:</p><ul><li>**Métricas e dimensões:** Itálico e negrito</li><li>**Itens do Dimension:** Negrito quando a dimensão correspondente é enfatizada<p>Uma cor também é aplicada ao item de dimensão quando ele é realçado no gráfico.</p></li></ul> |

(Condicional) Selecione **[!UICONTROL Tema padrão]** se desejar que seus slides sejam gerados com o tema padrão.

1. Selecione se deseja usar um tema padrão ou fazer upload de um modelo personalizado:

   * **[!UICONTROL Tema padrão]**:

   * **[!UICONTROL Carregar modelo]**:





## Editar slides de uma apresentação gerada anteriormente


## Baixar uma apresentação .pptx gerada

## Elementos e recursos do projeto não compatíveis {#unsupported}

Os seguintes elementos e recursos do Analysis Workspace usados em um projeto não são compatíveis ao gerar slides:

* Painel de atribuição

  Esse painel é exibido como esmaecido quando as opções de configuração são exibidas.

  Todos os outros painéis podem ser incluídos em slides gerados de um projeto do Workspace.

* Algumas visualizações

  A maioria das visualizações pode ser incluída em slides gerados de um projeto do Workspace. No entanto, as seguintes visualizações não podem ser incluídas e são exibidas como esmaecidas quando as opções de configuração são exibidas:

   * Tabela de coorte

   * Tela da jornada

   * Marcador

   * Combinado

   * Dispersão

   * Mapa de árvore

* Detalhamentos

* Análises guiadas


