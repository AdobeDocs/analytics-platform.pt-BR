---
description: É possível baixar dados do Analysis Workspace copiando-os ou em formatos PDF e CSV.
title: Baixar arquivos PDF ou CSV
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 12%

---

# Baixar arquivos PDF ou CSV

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

Há várias maneiras diferentes de exportar dados do Analysis Workspace, dependendo do conjunto de dados que você deseja analisar fora da ferramenta e de quem precisa receber as informações. Os dados exportados podem estar no formato de dados copiados, arquivos CSV ou PDF. Um PDF geralmente é preferido se você deseja que visualizações sejam incluídas no arquivo, enquanto um CSV (ou dados copiados) é preferido se você simplesmente deseja dados de texto simples.

## Baixar projeto como CSV ou PDF {#download-project}

Você pode baixar um projeto completo indo até **[!UICONTROL Projeto > Baixar como PDF (ou como CSV)]**. O arquivo baixado contém todas as tabelas e visualizações exibidas (visíveis) no projeto. Um PDF geralmente é preferido se você deseja que visualizações sejam incluídas no arquivo, enquanto um CSV é preferido se você simplesmente quiser dados de texto simples.

![](assets/download-project.png)

Para downloads de projetos, lembre-se:

* O projeto pode ser salvo ou não quando você solicita um download do projeto. No entanto, somente os projetos salvos podem ser [agendados](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html).
* Os PDFs baixados no navegador podem levar vários minutos para serem exportados porque o projeto é executado novamente em servidores Adobe antes da renderização no formato PDF. Recomendamos não sair do projeto até que o PDF seja baixado no navegador. No entanto, você pode continuar fazendo alterações no projeto enquanto espera. Se um PDF demorar mais de 5 minutos para ser renderizado, você será solicitado a enviá-lo por email.
* Os downloads de PDF são renderizados como uma única página sem paginação aplicada.
* Quando um projeto é renderizado para PDF, renderizamos o que está na página. Se um projeto tiver visualizações e painéis com tamanhos personalizados, é necessário alterá-los para terem tamanhos automáticos (botão no canto superior direito) para que não haja truncamento de conteúdo.

## Copiar dados para a área de transferência (tecla de atalho): Ctrl+C) {#copy-data}

A opção **[!UICONTROL Copy to clipboard]** permite copiar dados rapidamente do Workspace e colá-los em outro lugar.

* Se desejar que a tabela exibida seja copiada, clique com o botão direito do mouse no cabeçalho da tabela e escolha **Copiar dados para a área de transferência**.
* Se quiser que um subconjunto de dados seja copiado, faça uma seleção na tabela e clique com o botão direito do mouse em > **Copiar seleção para a área de transferência**.

Além disso, a tecla de atalho `Ctrl+C` copia sua seleção para a área de transferência. Depois de copiadas, você pode entrar em outra ferramenta e colar as informações (ou pressionar `Ctrl+V`).

![](assets/copy-selection.png)

## Baixar dados como CSV {#download-data}

A opção de clique com o botão direito **[!UICONTROL Baixar dados como CSV]** permite baixar uma tabela de dados ou a fonte de dados de qualquer visualização como CSV.

* No cabeçalho de qualquer tabela ou visualização, clique com o botão direito do mouse em **[!UICONTROL Baixar dados como CSV]**. Isso baixa os dados exibidos na tabela ou na fonte de dados subjacente de uma visualização como CSV. Observação: a visualização de mapa não oferece suporte a essa opção.
* Se uma seleção for feita na tabela, a opção dirá **[!UICONTROL Baixar seleção como CSV]**. Somente a seleção é baixada com essa opção, em vez da tabela cheia e exibida.

![](assets/download-data-viz.png)

## Baixar itens como CSV {#download-items}

Se quiser analisar mais do que as 400 linhas de dados visíveis em uma tabela, clique com o botão direito do mouse no cabeçalho da tabela ou em qualquer linha e selecione **Baixar itens como CSV (nome do Dimension)**. Essa opção exportará até 50.000 itens de dimensão (com base na classificação da tabela) para a dimensão selecionada, com filtros e filtros aplicados. Se você escolher essa opção na parte superior da tabela, a primeira dimensão na tabela será exportada. Embora nenhum limite seja empregado na tabela de forma livre, é recomendável que a opção Baixar itens seja usada em tabelas com menos de 20 colunas para garantir o desempenho ideal.

>[!TIP]
>
> Se sua dimensão exceder 50.000 itens, baixe o arquivo com métricas de classificação diferentes aplicadas ou aplique um filtro. Por exemplo, classifique decrescente por Visitas em um download e crescente por Visitas em um segundo download. Esta dica pode ajudá-lo a recuperar itens de cauda mais longos.

É possível executar várias tarefas no projeto e até mesmo navegar para um novo projeto do Workspace na mesma guia enquanto o download está em andamento. O download será pausado se você abrir uma nova guia do navegador. O download será cancelado se você sair do Workspace completamente ou fechar a guia do navegador.

![](assets/download-items.png)

### Arquivo de itens baixados

Os recursos da tabela serão aplicados ao arquivo baixado da seguinte maneira:

* Todos os filtros de painel são aplicados como filtros.
* Os detalhamentos **acima** da dimensão selecionada na tabela são aplicados como filtros acima de cada coluna.
* Detalhamentos **abaixo** a dimensão selecionada na tabela são removidas.

No exemplo acima, os itens de Página são baixados com o filtro de painel (Clientes de novos visitantes) e os componentes acima (Canal de marketing = Email) aplicados como filtros, e os componentes abaixo (Tipo de dispositivo móvel) são removidos do CSV baixado.

![](assets/downloaded-file.png)

### Baixar notificações

Conforme o arquivo é baixado, você verá uma notificação informativa com o progresso. A qualquer momento, você pode cancelar o download clicando em **[!UICONTROL Cancelar download]**. Fechar o brinde **não** cancela o download.

Quando o arquivo for concluído, você verá uma notificação de conclusão e o arquivo será baixado no navegador.

Se você solicitar mais de um download por vez, receberá uma notificação de que cada download adicional será enfileirado até que o download anterior seja concluído.

![](assets/toast.png)

## Perguntas frequentes {#faq}

| Pergunta | Resposta |
| --- | --- |
| Por que meu PDF baixado é uma página? | O Workspace não pagina os PDFs baixados no momento. |
| Posso exportar mais de 50.000 itens com a opção &quot;Baixar itens como CSV&quot;? | Embora cada download possa conter até 50.000 itens de dimensão, você pode alterar a classificação da tabela para recuperar itens de cauda mais longos ou aplicar um filtro para baixar itens mais específicos. |
| O que a **[!UICONTROL Copiar visualização]** faz? | **[!UICONTROL A]** visualização Copiar não é uma opção de exportação. Ela permite copiar uma visualização ou painel de um local no Workspace para outro. Por exemplo, de um painel para outro no mesmo projeto ou de um projeto para outro. [Vídeo intravinculante](https://docs.adobe.com/content/help/pt-BR/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html) |
