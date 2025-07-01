---
description: Saiba mais sobre as várias possibilidades de baixar dados do seu projeto do Analysis Workspace.
title: Baixar Projetos E Dados Do Analysis Workspace
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: 084c995658a5cf698d253f1c15229f621a8c55d5
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 25%

---

# Baixar projetos e dados

Você pode baixar projetos e dados do Analysis Workspace no seu dispositivo local. Esse download pode ser copiado com dados, um arquivo CSV (dados de valores separados por vírgula) ou um documento PDF (formato de documento portátil).

* Selecione a opção PDF se desejar que as visualizações sejam incluídas no arquivo baixado.
* Selecione as opções CSV e dados copiados se precisar apenas de dados de texto simples.

Métodos adicionais para exportar dados do Customer Journey Analytics estão descritos na [Visão geral da exportação](/help/analysis-workspace/export/export-project-overview.md).

## Baixar como CSV ou PDF {#download-project}

![O menu suspenso “Projeto”, com as opções de “Baixar CSV” e “Baixar PDF” realçadas.](assets/download-project.png)

Considere o seguinte ao baixar um projeto as a PDF:

* O download pode levar vários minutos, pois o projeto é executado novamente em servidores Adobe para renderizar no formato PDF. Não saia do projeto até que ele seja baixado no navegador.  Você pode continuar a fazer alterações no projeto enquanto o download é renderizado. Se uma PDF levar mais de 5 minutos para ser renderizada, você será solicitado a [enviar um email para a PDF](../curate-share/send-schedule-files.md).
* Os downloads são renderizados como uma página única sem paginação aplicada.
* O PDF contém o que está visível na página do navegador no Analysis Workspace. É necessário dimensionar automaticamente as visualizações e painéis com tamanhos personalizados para evitar conteúdo truncado. Selecione ![Redimensionar](/help/assets/icons/Resize.svg) para dimensionar automaticamente uma visualização ou painel com tamanho personalizado.
* [Hiperlinks](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) nas tabelas de forma livre como hiperlinks no PDF baixado.



Para baixar um projeto como um arquivo PDF:

1. Selecione **[!UICONTROL Projeto]** > **[!UICONTROL Baixar o PDF]**.
Uma barra verde com a mensagem ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Seu download foi solicitado. Aguarde.]** é exibido.

1. Assim que o download estiver pronto, uma barra verde com a mensagem ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL *Name of the project *PDF estará pronta.]**&#x200B;aparece.
Selecione&#x200B;**[!UICONTROL Baixar]**&#x200B;para baixar a PDF. A forma como o PDF é apresentado ou baixado depende da configuração do navegador para lidar com os documentos do PDF.


Para baixar um projeto como um arquivo CSV:

* Selecione **[!UICONTROL Projeto]** > **[!UICONTROL Baixar CSV]**. O projeto é baixado diretamente para a pasta de download configurada como parte da configuração do navegador. O nome do arquivo é composto por *nome do projeto* - *nome do conjunto de relatórios* - *data*, por exemplo `Example Project - Omni-Channel - Luma - Jun 30, 2025.csv`.

## Copiar para área de transferência {#copy-data}

A opção **[!UICONTROL Copiar para a área de transferência]** do menu de contexto permite copiar dados do Analysis Workspace rapidamente e colá-los em uma ferramenta de terceiros.

* Se desejar que os dados da tabela exibidos sejam copiados, selecione o cabeçalho da tabela e selecione **Copiar dados para a área de transferência** no menu de contexto.
* Se quiser que um subconjunto dos dados seja copiado, faça uma seleção na tabela e selecione **Copiar seleção para a área de transferência** no menu de contexto.

>[!TIP]
>
>Você pode usar a tecla de atalho **_cmd + c_** (macOS) ou **_ctrl + c_** (Windows) para copiar sua seleção para a área de transferência. Em seguida, use o **_cmd + v_** (macOS) ou o **_ctrl + v_** (Windows) para colar os dados.


![A opção de “Copiar seleção para a área de transferência”. ](assets/copy-clipboard.png){zoomable="yes"}

## Baixar como CSV {#download-data}

As opções Baixar como CSV no menu de contexto permitem baixar uma tabela de dados ou a fonte de dados de qualquer visualização como CSV.

Para fazer isso:

* No cabeçalho de qualquer tabela ou visualização, selecione **[!UICONTROL Baixar dados como CSV]** no menu de contexto. Isso baixa os dados exibidos na tabela ou na fonte de dados subjacente de uma visualização como CSV. 

<!-- Only relevant as soon as CJA supports Map visualization 
  >[!NOTE]
  >
  >  Note: the Map visualization does not support this option.
-->

* Em uma tabela, selecione **[!UICONTROL Baixar seleção como CSV]** no menu de contexto. Somente a seleção é baixada com essa opção, em vez da tabela completa.

![A opção de “Baixar dados como CSV”.](assets/download-data-as-csv.png)

## Baixar itens como CSV {#download-items}

Se quiser analisar mais do que as 400 linhas de dados visíveis em uma tabela, selecione **Baixar itens como CSV (_Nome da Dimension_)** no menu de contexto do cabeçalho da tabela ou de qualquer linha. Esta opção exporta até 50 mil itens de dimensão (com base na classificação da tabela) para a dimensão selecionada, com opções de ordenação e filtros aplicados. Se você selecionar essa opção na parte superior da tabela, a primeira dimensão na tabela será exportada.

![A opção de “Baixar itens como CSV (Página)”.](assets/download-items-as-csv.png)

Nenhum limite é aplicado na tabela de forma livre. Para garantir o desempenho ideal, recomenda-se usar essa opção em tabelas com menos de 20 colunas.

>[!TIP]
>
> Se sua dimensão exceder 50.000 itens, baixe o arquivo com diferentes métricas de classificação aplicadas ou use um segmento. Por exemplo, classifique em ordem decrescente por Visitas em um download e em ordem crescente por Visitas em um segundo download. Esta dica pode ajudar você a recuperar itens mais longos.

É possível executar várias tarefas no projeto e até mesmo navegar para um novo projeto do Workspace na mesma guia enquanto o download está em andamento. O download será pausado se você abrir uma nova guia do navegador. O download será cancelado se você sair do Workspace completamente ou fechar a guia do navegador.


### Arquivo de itens baixados {#items-file}

Os seguintes recursos de uma tabela de forma livre são aplicados ao arquivo baixado:

* Todos os segmentos do painel são aplicados como filtros.
* Os detalhamentos **acima** da dimensão selecionada na tabela são aplicados como filtros acima de cada coluna.
* Detalhamentos **abaixo** da dimensão selecionada na tabela são removidos.

![O arquivo .csv baixado aberto no Excel.](assets/download-items-file.png)

### Baixar notificações {#notifications}

À medida que o arquivo é baixado, você vê as seguintes notificações:

* Um **[!UICONTROL _Nome de tabela _-_Dimension _.csv azul foi solicitado._x _% concluído]**&#x200B;indicando o progresso. Para cancelar o download a qualquer momento, selecione **[!UICONTROL Cancelar download]**. Selecione ![CrossSize100](/help/assets/icons/CrossSize100.svg) se desejar fechar a mensagem, o que não cancela o download.
* Uma notificação de conclusão **[!UICONTROL _do nome da tabela _-_Dimension _.csv foi baixada]**&#x200B;assim que o download do arquivo foi concluído. O arquivo é baixado na pasta de downloads configurada para o seu navegador.

Se solicitar mais de um download por vez, você receberá uma notificação de que cada download adicional será enfileirado até que o download anterior seja concluído.


## Baixar dados sigilosos {#sensitive}

Imagine uma [política de governança de dados](/help/data-views/data-governance.md) que impeça o download de dados. E que essa política está ativada na visualização de dados para a qual você está relatando. Como resultado, qualquer download (como ao enviar um email ou compartilhar arquivos do PDF) dos projetos coloca os campos de dados rotulados como sigilosos. Você ainda pode fazer análises nesses campos no Analysis Workspace. Se você tentar enviar um email ou compartilhar um projeto de outra forma, os campos de dados confidenciais aparecerão vazios no arquivo PDF ou CSV.

Se campos de dados rotulados como confidenciais forem incluídos na visualização de dados, a opção para selecionar e copiar dados da tela será restrita para todos os dados na visualização de dados.

## Perguntas frequentes {#faq}

| Pergunta | Resposta |
| --- | --- |
| Por que meu PDF baixado consiste em apenas uma página? | A funcionalidade [Baixar PDF](#download-as-csv-or-pdf) não faz a paginação de PDFs baixados. |
| Posso exportar mais de 50.000 itens com a opção **[!UICONTROL Baixar itens como CSV]**? | Embora cada download possa conter até 50.000 itens de dimensão, você pode alterar a classificação da tabela para recuperar itens mais longos ou aplicar um filtro para baixar itens mais específicos. |
| O que a opção **[!UICONTROL Copiar visualização]** faz? | Ao contrário de [!UICONTROL **Copiar dados para a área de transferência**] ou [!UICONTROL **Copiar seleção para a área de transferência**], a opção de menu de contexto **[!UICONTROL Copiar visualização]** não é uma opção de exportação. Esta opção permite [copiar uma visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu) ou [copiar um painel](/help/analysis-workspace/c-panels/panels.md#context-menu) de um local no Workspace para outro. Por exemplo, de um painel para outro no mesmo projeto ou de um projeto para outro. |
