---
description: Saiba como gerar apresentações em formato pptx a partir de relatórios do Workspace.
keywords: Analysis Workspace
title: Gerar apresentações a partir de relatórios do Workspace
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 9e23382800326440ed2a583e80029c9f27bb2494
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 4%

---

# Narrativa de dados: gere apresentações de slides a partir de relatórios do Workspace {#generate-powerpoint}

Usuários com [as permissões necessárias](#permission-requirements-to-generate-slides) podem gerar automaticamente apresentações .pptx de projetos da Analysis Workspace. Ao gerar essas apresentações de slides, a Customer Journey Analytics cria automaticamente uma história com base em seus dados, identificando os principais insights e convertendo-os em slides prontos para as partes interessadas.

Essa funcionalidade reduz o tempo e o esforço necessários para exibir conclusões de seus projetos do Workspace e permite criar rapidamente narrativas executivas e comunicar o impacto comercial às partes interessadas.

Essa história de dados gerada automaticamente permite que os analistas se concentrem na exploração de dados, enquanto a Customer Journey Analytics organiza e formata os achados do analista para consumo das partes interessadas.

## Compreender as histórias de dados em apresentações de slides

O Analysis Workspace usa IA gerativa para criar histórias de dados em apresentações de slides. Essas histórias de dados complementam uma análise para um determinado projeto do Workspace, fornecendo contexto adicional, revelando destaques importantes e fornecendo ideias para as próximas etapas. informe tendências ocultas, anomalias, fatores que contribuem, principais impulsionadores

### Valor adicional fornecido pelas histórias de dados

As histórias de dados complementam uma análise para um determinado projeto do Workspace por:

* Fornecimento de contexto adicional

* Destacar insights importantes

* Chamar tendências ocultas, anomalias e outros fatores que contribuem

* Identificação dos principais drivers

* Fornecendo ideias para as próximas etapas

### Elementos de projeto que formam histórias de dados

O Analysis Workspace cria histórias de dados considerando os seguintes elementos do projeto:

* Relacionamentos interdimensionais e intermétricos

* Os elementos individuais que formam a base da análise: dimensões, métricas, filtros, estrutura da tabela de forma livre, visualizações e painéis

* Os nomes dados aos painéis, tabelas e visualizações

* A ordem das métricas em uma tabela de forma livre (para determinar a prioridade)

* Números de resumo e textos de resumo (para determinar as métricas que precisam ser destacadas na história dos dados)

### Elementos de apresentação de uma história de dados

As histórias de dados consistem em um slide de resumo executivo, slides de detalhes e divisores de seção.

**Resumo executivo:** prioriza os insights de maior valor e cria uma história abrangente com 1 a 5 frases de comprimento.

**Slides de detalhes:** gera insights relacionados a quaisquer tabelas, painéis ou visualizações em um projeto do Workspace. Os insights consistem em tendências, sazonalidades, anomalias e correlações.

**Divisores de seção:** divide os insights com divisores de seção posicionados e nomeados adequadamente.

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

1. Vá para o projeto do Workspace que contém os dados que você deseja usar como a base da sua apresentação de slides.

1. Selecione **[!UICONTROL Gerar slides]** no canto superior direito da página.

   A caixa de diálogo Gerar slides é exibida.

   ![Caixa de diálogo Gerar slides](assets/generate-slides.png)

1. Especifique as seguintes informações:

   | Opção | Descrição |
   |---------|----------|
   | **[!UICONTROL Título da capa]** | Especifique um título para a apresentação. Este título aparece no slide de título da apresentação. |
   | **[!UICONTROL Incluir nome do apresentador]** | Especifique o nome do apresentador. Esse nome aparece no slide de título da apresentação, abaixo do título da capa. |
   | **[!UICONTROL Painéis e visualizações a serem incluídos]** | Escolha os painéis e a visualização que deseja incluir na apresentação. É possível incluir até 50 visualizações.<p>A maioria dos painéis e visualizações é compatível. Para obter informações sobre painéis e visualizações sem suporte, consulte [Elementos e recursos do projeto sem suporte](#unsupported-project-elements-and-features).</p> |
   | **[!UICONTROL Descrições do painel e da visualização]** | |
   | **[!UICONTROL Anotações]** | |
   | **[!UICONTROL Enfatizar componentes]** | Escolha até 5 métricas e 5 dimensões nas visualizações que você deseja enfatizar na apresentação.<p>Quando nenhuma ênfase é aplicada, os componentes são exibidos nas apresentações da seguinte maneira:<ul><li>**Métricas e dimensões:** Itálico</li><li>**Itens do Dimension:** Aspas</li></ul></p><p>Quando a ênfase é aplicada, os componentes são exibidos nas apresentações da seguinte maneira:</p><ul><li>**Métricas e dimensões:** Itálico e negrito</li><li>**Itens do Dimension:** Negrito quando a dimensão correspondente é enfatizada<p>Uma cor também é aplicada ao item de dimensão quando ele é realçado no gráfico.</p></li></ul> |

1. (Condicional) Selecione **[!UICONTROL Tema padrão]** se quiser gerar slides rapidamente em menos etapas e se um tema corporativo não for necessário para a apresentação de slides.

   Basta escolher o tema de cores da sua apresentação selecionando a cor desejada.

   ![Gerar slides com o tema padrão](assets/generate-slides-default-theme.png)

1. (Condicional) Selecione **[!UICONTROL Carregar modelo]** se a apresentação de slides precisar corresponder a um tema corporativo. Essa opção exige que você faça upload de um modelo personalizado e aplique seus estilos personalizados.

   ![Gerar slides com um modelo personalizado](assets/generate-slides-upload-template.png)

   Para fazer upload de um modelo personalizado, siga um destes procedimentos:

   * (Recomendado) Baixe um modelo em branco e modifique-o.

      1. Baixe este modelo em branco. <!--add link-->

      1. Aplique estilos personalizados ao modelo em branco.

      1. Recarregue o modelo sem alterar nenhum nome de layout mestre.

   * Faça upload de um modelo personalizado diretamente.

      1. A partir do sistema de arquivos, arraste o modelo personalizado para a área designada.

         Ou

         Selecione **[!UICONTROL Procurar]** e procure e selecione seu modelo personalizado no sistema de arquivos.

         Verifique se o arquivo carregado tem layouts principais com os seguintes nomes: &quot;Title_Slide&quot;, &quot;Section_Divider&quot;, &quot;Title_Text&quot;, &quot;Title_Chart&quot;, &quot;Title_Two_Content_Mixed&quot;, &quot;Title_Three_Content_Mixed&quot;

         Arquivos .pptx e .potx de até 25 MB são suportados.

1. Selecione **[!UICONTROL Exportar PPT]**.

1. (Recomendado) Revise e edite a apresentação .ppt e faça as alterações necessárias, conforme descrito na seção a seguir, [Editar slides de uma apresentação gerada anteriormente](#edit-slides-from-a-previously-generated-presentation).

## Editar slides de uma apresentação gerada anteriormente


## Baixar uma apresentação .pptx gerada



## Requisitos de permissão para gerar slides

>[!AVAILABILITY]
>
>Se sua organização não tiver acesso para gerar apresentações de slides de um projeto do Workspace, entre em contato com o representante de conta da Adobe para saber mais sobre licenciamento.
>
>Esse recurso é habilitado por padrão para todos os usuários em organizações que têm o licenciamento necessário.

Os administradores de perfil de produto cujas organizações têm licença para gerar slides podem desabilitar o acesso, se necessário.

No [!UICONTROL Adobe Admin Console], a permissão [!UICONTROL Reporting Tools] **[!UICONTROL Narrativa de dados]** determina o acesso a esse recurso. Um [administrador de perfil de produto](https://helpx.adobe.com/br/enterprise/using/manage-product-profiles.html) precisa seguir estas etapas no [!UICONTROL Admin Console] se quiser desabilitar o acesso:
1. Navegue até **[!UICONTROL Admin Console]** > **[!UICONTROL Produtos e serviços]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Perfis de produtos]**
1. Selecione o título do perfil de produto para o qual você deseja fornecer acesso à [!UICONTROL narrativa de dados].
1. No perfil de produto específico, selecione **[!UICONTROL Permissões]**.
1. Selecione ![Editar](/help/assets/icons/Edit.svg) para editar as **[!UICONTROL Ferramentas de relatório]**.
1. Selecione ![AddCircle](/help/assets/icons/RemoveCircle.svg) para remover **Data storytelling** de **[!UICONTROL Itens de permissão incluídos]**.

   <!--add screenshot of permission in the admin console-->

1. Clique em **[!UICONTROL Salvar]** para salvar as permissões.

Para obter mais informações, consulte [Acesso de nível de usuário](/help/technotes/access-control.md#user-level-access) em [Controle de acesso](/help/technotes/access-control.md#access-control) para obter mais informações.

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


