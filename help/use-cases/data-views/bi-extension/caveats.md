---
title: Avisos
description: Avisos para a extensão BI em várias ferramentas de BI no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: cb0102923f10f39becd40cc4187d2e11fb8c4e2f
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 0%

---

# Avisos


Cada uma das ferramentas de BI compatíveis tem algumas limitações ao trabalhar com a extensão Customer Journey Analytics BI.

+++ Ferramentas de BI

>[!BEGINTABS]

>[!TAB Power BI Desktop]

* A filtragem avançada de intervalo de datas do Power BI Desktop é exclusiva.  Para a data final, é necessário selecionar um após o dia em que deseja criar o relatório. Por exemplo, **[!UICONTROL está em ou após]** `1/1/2023` **[!UICONTROL e antes]** `1/2/2023`.
* O padrão da Área de Trabalho do Power BI é **[!UICONTROL Importar]** quando você cria uma conexão. Use a **[!UICONTROL Consulta Direta]**.
* O Power BI Desktop expõe as transformações de dados por meio do Power Query.  O Power Query funciona principalmente com conexões do tipo Importar, de modo que muitas transformações aplicadas, como funções de data ou sequência, exibem um erro informando que é necessário alternar para uma conexão do tipo Importar.  Se você precisar transformar dados no momento da consulta, use dimensões e métricas derivadas para que o Power BI não precise fazer as transformações por si só.
* O Power BI Desktop não entende como lidar com colunas do tipo date-time, portanto, as dimensões **[!UICONTROL daterange *X *]**, como&#x200B;**[!UICONTROL daterangehour &#x200B;]**&#x200B;e&#x200B;**[!UICONTROL daterangeminute &#x200B;]**, não são suportadas.
* O Power BI Desktop, por padrão, tenta fazer várias conexões usando mais sessões do Serviço de consulta.  Acesse as configurações do Power BI para o seu projeto e desative as consultas paralelas.
* O Power BI Desktop faz toda a classificação e limitação no lado do cliente. O Power BI Desktop também tem diferentes semânticas para a filtragem *X* superior que inclui valores vinculados. Portanto, não é possível criar a mesma classificação e limitação que você pode criar no Analysis Workspace.
* Versões anteriores da versão de outubro de 2024 do Power BI Desktop quebram as fontes de dados PostgreSQL. Certifique-se de usar a versão mencionada neste artigo.

>[!TAB Tableau Desktop]

* A filtragem de Intervalo de Datas do Tableau Desktop é exclusiva. Para a data final, é necessário selecionar um após o dia em que deseja criar o relatório.
* Por padrão, quando você adiciona uma dimensão de data ou hora como **[!UICONTROL Daterangemonth]** às linhas de uma planilha, o Tableau Desktop envolve o campo em uma função **[!UICONTROL YEAR()]**.  Para obter o que deseja, selecione essa dimensão e, no menu suspenso, selecione a função de data que deseja usar.  Por exemplo, altere **[!UICONTROL Year]** para **[!UICONTROL Month]** quando estiver tentando usar **[!UICONTROL Daterangemonth]**.
* Limitar os resultados ao *X* Superior não é óbvio no Tableau Desktop. É possível limitar os resultados explicitamente ou usando um campo calculado e a função **[!UICONTROL INDEX()]**.  Adicionar um filtro *X* Superior a uma dimensão gera um SQL complexo usando uma junção interna que não tem suporte.

>[!TAB Pesquisador]

* O Looker tem um número máximo de conexões por configuração de nó que deve estar entre 5 e 100.  Não é possível definir esse valor como 1.  Essa configuração implica que uma conexão de Pesquisador sempre use no mínimo 5 das sessões de Serviço de consulta disponíveis.
* O Looker permite criar um projeto com uma visualização baseada em uma visualização de dados do Customer Journey Analytics. Em seguida, o Looker cria um modelo com base nas dimensões e métricas, disponíveis na visualização de dados, usando o LookerML.  Esta Visualização de projeto não é atualizada automaticamente para corresponder à origem.  Se você fizer alterações ou adições às dimensões, métricas, métricas calculadas ou segmentos da Visualização de dados do CJA, essas alterações não serão exibidas automaticamente no Looker.  Você precisa atualizar manualmente a Visão do Projeto ou criar um novo Projeto.
* A experiência do usuário do pesquisador em campos de data ou hora como **[!UICONTROL Data do intervalo de datas]** ou **[!UICONTROL Data do intervalo de datas]** é confusa.
* O intervalo de datas do observador é exclusivo em vez de inclusivo.  O **[!UICONTROL até (antes)]** está em cinza, portanto, você pode perder esse aspecto.  Para o dia final, é necessário selecionar um após o dia em que deseja criar o relatório.
* O Looker não trata automaticamente suas métricas como métricas.  Quando você seleciona uma métrica, por padrão, o Looker tenta tratar a métrica como uma dimensão na consulta.  Para tratar uma métrica como uma métrica, é necessário criar um campo personalizado conforme ilustrado acima. Como atalho, você pode selecionar **&#x200B;**, selecionar **[!UICONTROL Agregação]** e depois selecionar **[!UICONTROL Soma]**.

>[!TAB Jupyter Notebook]

* A principal advertência do Jupyter Notebook é que a ferramenta não faz uma interface de usuário de arrastar e soltar como outras ferramentas de BI. Você pode criar bons visuais, mas precisa escrever código para conseguir isso.

>[!TAB RStudio]

* A implantação do R funciona com um esquema simples, de modo que a opção **[!UICONTROL FLATTEN]** é necessária.
* O principal aviso do RStudio é que a ferramenta não faz uma interface de usuário de arrastar e soltar como outras ferramentas de BI. Você pode criar bons visuais, mas precisa escrever código para conseguir isso.

>[!ENDTABS]

+++
