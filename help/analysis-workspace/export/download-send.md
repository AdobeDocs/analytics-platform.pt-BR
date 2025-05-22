---
description: É possível baixar dados do Analysis Workspace copiando-os ou em formatos PDF e CSV.
title: Baixar dados do Customer Journey Analytics
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: 9a15cb4d771892ff656fe72b8e53d890a3fd99f7
workflow-type: tm+mt
source-wordcount: '1194'
ht-degree: 100%

---

# Baixar dados do Customer Journey Analytics

Você pode baixar dados do Customer Journey Analytics para a sua estação de trabalho pessoal. Os dados exportados podem estar no formato de dados copiados, CSV ou PDF. Um PDF geralmente é melhor, se você quiser que as visualizações sejam incluídas no arquivo. CSV e dados copiados são melhores se você simplesmente quiser dados de texto simples.

Outros métodos de exportação de dados do Customer Journey Analytics também estão disponíveis, conforme descrito em [Visão geral da exportação](/help/analysis-workspace/export/export-project-overview.md).

## Baixar como CSV ou PDF {#download-project}

Considere o seguinte ao baixar projetos:

* Ao baixar projetos como CSV ou PDF, o projeto pode estar salvo ou não quando você solicita o download do projeto. No entanto, somente os projetos salvos podem ser [agendados](/help/analysis-workspace/export/t-schedule-report.md).

* Ao baixar projetos como PDF:
   * Os downloads podem levar vários minutos para ser exportados, porque o projeto é executado novamente em servidores da Adobe antes da renderização no formato PDF. Recomendamos não sair do projeto até que o PDF seja baixado no navegador. No entanto, você pode continuar fazendo alterações no projeto enquanto espera. Se um PDF demorar mais de 5 minutos para ser renderizado, você será solicitado a enviá-lo por email.
   * Os downloads são renderizados como uma página única sem paginação aplicada.
   * As renderizações em PDF contêm o que está na página no Workspace. Se um projeto tiver visualizações e painéis com tamanhos personalizados, é necessário alterá-los para terem tamanhos automáticos (botão no canto superior direito) para que não haja truncamento de conteúdo.
   * Quaisquer [hiperlinks](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) existentes nas tabelas de forma livre não funcionarão no PDF baixado.

Para baixar um projeto como um arquivo CSV ou PDF:

1. Siga o procedimento adequado a seguir, dependendo do formato no qual deseja fazer o download:

   * **PDF:** selecione **[!UICONTROL Projeto]** > **[!UICONTROL Baixar PDF]**.

     Escolha essa opção se desejar que o arquivo baixado contenha todas as tabelas e visualizações exibidas (visíveis) no projeto.

   * **CSV:** selecione **[!UICONTROL Projeto]** > **[!UICONTROL Baixar CSV]**.

     Escolha esta opção se quiser que o arquivo baixado seja de texto sem formatação.

   ![O menu suspenso “Projeto”, com as opções de “Baixar CSV” e “Baixar PDF” realçadas.](assets/download-project.png)

1. (Condicional) Se você optar por baixar um PDF, uma mensagem será exibida depois que o projeto estiver pronto para ser baixado. Selecione [!UICONTROL **Download**].

## Copiar para a área de transferência (tecla de atalho: Ctrl+C) {#copy-data}

A opção do botão direito do mouse de **[!UICONTROL Copiar para a área de transferência]** permite copiar dados do Customer Journey Analytics a partir do Workspace e colá-los em uma ferramenta de terceiros rapidamente.

* Se desejar que a tabela exibida seja copiada, clique com o botão direito do mouse no cabeçalho da tabela e escolha **Copiar dados para a área de transferência**.
* Se quiser que um subconjunto de dados seja copiado, faça uma seleção na tabela, clique com o botão direito do mouse e, em seguida, em **Copiar seleção para a área de transferência**.

>[!TIP]
>
>Você pode usar o atalho `Ctrl+C` para copiar sua seleção para a área de transferência. Em seguida, use `Ctrl+V` para colá-la em uma ferramenta de terceiros.


![A opção de “Copiar seleção para a área de transferência”. ](assets/copy-selection.png)

## Baixar como CSV {#download-data}

A opção do botão direito do mouse de **[!UICONTROL Baixar dados como CSV]** permite baixar uma tabela de dados do Customer Journey Analytics ou a fonte de dados de qualquer visualização como CSV.

* No cabeçalho de qualquer tabela ou visualização, clique com o botão direito do mouse e escolha **[!UICONTROL Baixar dados como CSV]**.  Isso baixa os dados do Customer Journey Analytics exibidos na tabela ou na fonte de dados subjacente de uma visualização como CSV. 

  >[!NOTE]
  >
  >  Observação: a visualização de mapa não é compatível com essa opção.


* Em uma tabela, clique com o botão direito do mouse e escolha **[!UICONTROL Baixar seleção como CSV]**. Somente a seleção é baixada com essa opção, em vez da tabela completa.

![A opção de “Baixar dados como CSV”.](assets/download-data-viz.png)

## Baixar itens como CSV {#download-items}

Se quiser analisar mais do que as 400 linhas de dados visíveis em uma tabela, clique com o botão direito no cabeçalho da tabela ou em qualquer linha e selecione **Baixar itens como CSV (_Nome da dimensão_)**. Esta opção exporta até 50 mil itens de dimensão (com base na classificação da tabela) para a dimensão selecionada, com opções de ordenação e filtros aplicados. Se você escolher essa opção na parte superior da tabela, a primeira dimensão na tabela será exportada. Embora nenhum limite seja empregado na tabela de forma livre, é recomendável que a opção Baixar itens seja usada em tabelas com menos de 20 colunas para garantir o desempenho ideal.

>[!TIP]
>
> Se sua dimensão exceder 50.000 itens, baixe o arquivo com diferentes métricas de classificação aplicadas ou use um segmento. Por exemplo, classifique em ordem decrescente por Visitas em um download e em ordem crescente por Visitas em um segundo download. Esta dica pode ajudar você a recuperar itens mais longos.

É possível executar várias tarefas no projeto e até mesmo navegar para um novo projeto do Workspace na mesma guia enquanto o download está em andamento. O download será pausado se você abrir uma nova guia do navegador. O download será cancelado se você sair do Workspace completamente ou fechar a guia do navegador.

![A opção de “Baixar itens como CSV (Página)”.](assets/download-items.png)

### Arquivo de itens baixados {#items-file}

Os recursos da tabela serão aplicados ao arquivo baixado da seguinte maneira:

* Todos os segmentos do painel são aplicados como filtros.
* Os detalhamentos **acima** da dimensão selecionada na tabela são aplicados como filtros acima de cada coluna.
* Detalhamentos **abaixo** da dimensão selecionada na tabela são removidos.

No exemplo acima, os itens de Página são baixados com o segmento do painel (Novos clientes visitantes), os componentes acima (Canal de marketing = Email) são aplicados como filtros e os componentes abaixo (Tipo de dispositivo móvel) são removidos do CSV baixado.

![O arquivo .csv baixado aberto no Excel.](assets/downloaded-file.png)

### Baixar notificações {#notifications}

À medida que o arquivo for baixado, você verá uma notificação informativa com o progresso. A qualquer momento, você pode cancelar o download clicando em **[!UICONTROL Cancelar download]**. Fechar a janela **não** cancela o download.

Quando o arquivo for concluído, você verá uma notificação de conclusão e o arquivo será baixado no navegador.

Se solicitar mais de um download por vez, você receberá uma notificação de que cada download adicional será enfileirado até que o download anterior seja concluído.

![A notificação de status do download, mostrando a porcentagem concluída e um link para cancelar o download.](assets/toast.png)

## Baixar dados sigilosos {#sensitive}

Se a [política de governança de dados](/help/data-views/data-governance.md) de **[!UICONTROL Forçar download]** estiver ativada na visualização de dados sobre a qual você está gerando o relatório, qualquer download (como envios por email ou compartilhamento de PDFs) de projetos do Workspace aplicará uma função de hash aos campos de dados rotulados como sigilosos. Ainda é possível fazer a análise desses campos no espaço de trabalho, mas se você tentar enviar um email ou compartilhar um projeto de outra forma, os campos bloqueados aparecerão vazios no arquivo PDF ou CSV.

Se algum campo de dados rotulado como sigiloso for incluído na [!UICONTROL Visualização de dados], a opção de selecionar e copiar dados da tela será restrita para todos os dados na [!UICONTROL Visualização de dados].

## Perguntas frequentes {#faq}

| Pergunta | Resposta |
| --- | --- |
| Por que meu PDF baixado tem apenas uma página? | O Workspace não faz a paginação de PDFs baixados no momento. |
| Posso exportar mais de 50.000 itens com a opção “Baixar itens como CSV”? | Embora cada download possa conter até 50.000 itens de dimensão, você pode alterar a classificação da tabela para recuperar itens mais longos ou aplicar um filtro para baixar itens mais específicos. |
| O que a opção **[!UICONTROL Copiar visualização]** faz? | Ao contrário de [!UICONTROL **Copiar dados para a área de transferência**] ou [!UICONTROL **Copiar seleção para a área de transferência**], a opção do menu de contexto **[!UICONTROL Copiar visualização]** não é uma opção de exportação. Ela permite copiar uma visualização ou painel de um local no Workspace para outro. Por exemplo, de um painel para outro no mesmo projeto ou de um projeto para outro. [Vídeo intravinculante](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html?lang=pt-BR) |
