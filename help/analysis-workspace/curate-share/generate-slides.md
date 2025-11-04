---
description: Saiba como gerar apresentações em formato pptx a partir de relatórios do Workspace.
keywords: Analysis Workspace
title: Gerar apresentações a partir de relatórios do Workspace
feature: Curate and Share
role: User
source-git-commit: 87e3b3cfdf765a57ecdb70921696013bcba4feac
workflow-type: tm+mt
source-wordcount: '1585'
ht-degree: 3%

---

# Narrativa de dados: gere apresentações de slides a partir de relatórios do Workspace {#generate-powerpoint}

{{release-limited-testing}}

<!-- also remove lmited testing note from: /help/technotes/access-control.md -->

Usuários com [as permissões necessárias](#permission-requirements-to-generate-slides) podem gerar automaticamente apresentações .pptx com base em projetos do Analysis Workspace. Ao gerar essas apresentações de slides, a Customer Journey Analytics cria automaticamente uma história com base em seus dados, identificando os principais insights e convertendo-os em slides prontos para as partes interessadas.

Essa história de dados gerada reduz o tempo, o esforço e a experiência necessários para exibir conclusões de um projeto do Workspace. Os analistas podem se concentrar mais na exploração de dados e, ao mesmo tempo, permitir que a Customer Journey Analytics crie e formate a narrativa executiva e comunique o impacto nos negócios para as partes interessadas.

## Compreender as histórias de dados em apresentações de slides

Uma **história sobre dados** é a narrativa que o Customer Journey Analytics cria com base nos dados do Workspace. Usando a IA generativa, o Customer Journey Analytics identifica temas importantes nos painéis e visualizações que você escolhe incluir em sua apresentação de slides. Ele gera insights e passa por um processo de desduplicação e pontuação para identificar um subconjunto de insights a ser usado para criar a história dos dados.

As seções a seguir descrevem o valor adicional fornecido pelas histórias de dados, os elementos necessários de um projeto que ajudam a moldar a narrativa e os elementos principais incluídos na saída da apresentação .pptx.

### Valor adicional fornecido pelas histórias de dados

As histórias de dados fornecem valor e insights para um projeto do Workspace, tornando os dados acessíveis a usuários menos experientes na análise de dados.

As histórias de dados complementam uma análise para um determinado projeto do Workspace por:

* Fornecimento de contexto adicional

* Destacar insights importantes

* Avaliar se determinadas variáveis estão sendo subavaliadas ou sobreavaliadas

* Chamar tendências ocultas, anomalias e outros fatores que contribuem

* Fornecendo ideias para as próximas etapas

### Elementos de projeto que formam histórias de dados

O Analysis Workspace cria histórias de dados considerando os seguintes elementos do projeto:

* Relacionamentos interdimensionais e intermétricos

* Os elementos individuais que formam a base da análise (dimensões, métricas, filtros, estrutura da tabela de forma livre, visualizações e painéis)

* Os nomes dados aos painéis, tabelas e visualizações

* A ordem das métricas em uma tabela de forma livre (para determinar a prioridade)

* A ordem das visualizações em um painel (para determinar a prioridade)

* Números de resumo e textos de resumo (para determinar as métricas que precisam ser destacadas na história dos dados)

### Elementos de apresentação de uma história de dados

As histórias de dados consistem em um slide de título, um slide de resumo executivo, slides de detalhes e divisores de seção.

**Slide de título:** mostra o título e o nome do apresentador que você especificar. Informações são mostradas nas notas do palestrante que descrevem o processo de como o tema e a narrativa foram criados, quantos insights foram gerados e usados e quais painéis foram usados.

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
   | **[!UICONTROL Painéis e visualizações a serem incluídos]** | Escolha os painéis e a visualização que deseja incluir na apresentação. É possível incluir até 50 visualizações.<p>Se uma visualização estiver esmaecida, ela será seguida pelo texto **[!UICONTROL (sem suporte)]** ou **[!UICONTROL (dados restritos)]**.</p><ul><li>**Sem suporte**: a maioria dos painéis e visualizações tem suporte. Para obter informações sobre painéis e visualizações sem suporte, consulte [Elementos e recursos do projeto sem suporte](#unsupported-project-elements-and-features).</li><li>**Dados restritos**: a visualização contém um componente que está impedido de ser exportado por uma política de governança de dados aplicada pela sua organização. Entre em contato com o administrador do sistema para ver quais componentes estão restritos para não serem exportados e remova os componentes restritos antes de gerar slides.</li></ul> |
   | **[!UICONTROL Enfatizar componentes]** | Escolha as métricas e dimensões nas visualizações que deseja enfatizar na apresentação. Os componentes escolhidos são classificados em posições mais altas e recebem mais peso quando os temas e a narrativa abrangente da história dos dados são criados. <p>Quando nenhuma ênfase é aplicada, os componentes são exibidos nas apresentações da seguinte maneira:<ul><li>**Métricas e dimensões:** Itálico</li><li>**Itens do Dimension:** Aspas</li></ul></p><p>Quando a ênfase é aplicada, os componentes são exibidos nas apresentações da seguinte maneira:</p><ul><li>**Métricas e dimensões:** Itálico e negrito</li><li>**Itens do Dimension:** Negrito quando a dimensão correspondente é enfatizada<p>Uma cor também é aplicada ao item de dimensão quando ele é realçado no gráfico.</p></li></ul> |

   <!-- add this later: - **[!UICONTROL Panel and visualization descriptions]** - Choose whether to include panel and visualization descriptions in your generated slide presentation. - 
   - **[!UICONTROL Annotations]** - Choose whether annotations are visible in your generated slide presentation. For more information about annotations, see [Annotations overview](/help/components/annotations/overview.md).  -  -->

1. (Condicional) Selecione **[!UICONTROL Tema padrão]** se quiser gerar slides em menos etapas e se um tema corporativo não for necessário para a apresentação de slides.

   Basta escolher o tema de cores da sua apresentação selecionando a cor desejada.

   ![Gerar slides com o tema padrão](assets/generate-slides-default-theme.png)

1. (Condicional) Selecione **[!UICONTROL Carregar modelo]** se a apresentação de slides precisar corresponder a um tema corporativo. Essa opção exige que você faça upload de um modelo personalizado e aplique seus estilos personalizados.

   O modelo personalizado mais recente que você carregou é armazenado localmente no cache do navegador e está disponível ao gerar apresentações de slides futuras.

   ![Gerar slides com um modelo personalizado](assets/generate-slides-upload-template.png)

   Para fazer upload de um modelo personalizado, siga um destes procedimentos:

   * (Recomendado) Baixe um modelo em branco e modifique-o.

      1. Baixe [este modelo em branco](https://d30ln29764hddd.cloudfront.net/deploy/builds/data-storytelling.2025-10-20T15:10:19/resources/components/Blank.potx?).

      1. Aplique estilos personalizados ao modelo em branco.

      1. Recarregue o modelo sem alterar nenhum nome de layout mestre:

         A partir do sistema de arquivos, arraste o modelo em branco que tem seus estilos personalizados aplicados à área de soltar.

         Ou

         Selecione **[!UICONTROL Procurar]** e procure e selecione seu modelo em branco que tenha seus estilos personalizados aplicados do sistema de arquivos.

      1. Na seção **[!UICONTROL Mapeamento de layout]**, cada layout de slide usado em apresentações geradas é mapeado automaticamente para um slide do tema carregado. Revise as seleções para verificar se estão corretas.

         ![Mapeamento de layout](assets/generate-slides-layout-mapping.png)

      1. (Condicional) Se um layout de slide for mapeado incorretamente, selecione **[!UICONTROL Alterar seleção]** acima do slide que foi escolhido na apresentação carregada e escolha o slide que corresponde ao layout.

         Repita esse processo para cada slide que foi mapeado incorretamente.

   * Faça upload de um modelo personalizado diretamente.

      1. A partir do sistema de arquivos, arraste o modelo personalizado para a área designada.

         Ou

         Selecione **[!UICONTROL Procurar]** e procure e selecione seu modelo personalizado no sistema de arquivos.

         Verifique se o arquivo carregado tem layouts principais com os seguintes nomes: &quot;Title_Slide&quot;, &quot;Section_Divider&quot;, &quot;Title_Text&quot;, &quot;Title_Chart&quot;, &quot;Title_Two_Content_Mixed&quot;, &quot;Title_Three_Content_Mixed&quot;.

         São suportados até 15 layouts principais.

         Arquivos .pptx e .potx de até 25 MB são suportados.

      1. Na seção **[!UICONTROL Mapeamento de layout]**, cada layout de slide usado em apresentações geradas é mapeado automaticamente para um slide do tema carregado. Revise as seleções para verificar se estão corretas.

         ![Modelo personalizado de mapeamento de layout](assets/generate-slides-layout-mapping-custom-template.png)

      1. (Condicional) Se um layout de slide for mapeado incorretamente, selecione **[!UICONTROL Alterar seleção]** acima do slide que foi escolhido na apresentação carregada e escolha o slide que corresponde ao layout.

         Repita esse processo para cada slide que foi mapeado incorretamente.

1. Selecione **[!UICONTROL Exportar PPT]**.

   A apresentação .pptx é baixada automaticamente para sua estação de trabalho.

1. (Recomendado) Abra a apresentação .pptx e revise-a. Faça as alterações necessárias.

## Requisitos de permissão para gerar slides

>[!AVAILABILITY]
>
>Se sua organização não tiver acesso para gerar apresentações de slides de um projeto do Workspace, entre em contato com o representante de conta da Adobe para saber mais sobre licenciamento.

A capacidade de gerar slides é habilitada por padrão para todos os usuários em organizações que têm o licenciamento necessário.

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

   * Área

   * Marcador

   * Tabela de coorte

   * Combinado

   * Fallout

   * Fluxo

   * Tela da jornada

   * Dispersão

   * Mapa de árvore

* Detalhamentos

  Os dados para detalhamentos são incluídos em apresentações geradas, mas são exibidos no mesmo nível que os itens de dimensão.

* Análises guiadas

* Componentes impedidos de serem exportados por uma política de governança de dados

  Para obter mais informações, consulte [Solucionar problemas de exportações com falha](/help/components/exports/troubleshoot-exports.md).


