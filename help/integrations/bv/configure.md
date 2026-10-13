---
title: Configuração da integração de entrada do Brand Visibility
description: Saiba como configurar a integração do Brand Visibility com o Customer Journey Analytics
feature: Experience Platform Integration
role: Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e3958dfbad19f5fdd78b2755817d21afad8f8e84
workflow-type: tm+mt
source-wordcount: '2118'
ht-degree: 0%
---
# Definir e configurar a integração de entrada

Este artigo detalha os [pré-requisitos](#prerequisites), [responsabilidades](#responsibilities), [etapas a serem verificadas](#verification), [etapas de solução de problemas](#troubleshoot) e [critérios de conclusão](#completion-criteria) para configurar a integração de entrada do Brand Visibility com o Customer Journey Analytics.

## Pré-requisitos

Considere os seguintes pré-requisitos antes de habilitar a integração de entrada. Use o [procedimento de verificação](#verification) abaixo para confirmar cada pré-requisito.

### Encaminhamento de log BYOCDN

Os logs de acesso do CDN devem ser encaminhados para e recebidos pela Adobe Brand Visibility para cada site do Brand Visibility para que o conector de origem do Brand Visibility possa ser viável.

Esse requisito se aplica a cada site de Visibilidade da marca. Uma configuração de CDN ou feed de log para um site, domínio ou subdomínio abrange somente esse site.

Confirme ambas as partes da entrega:

1. Você configurou o CDN ou pipeline de log relevante para encaminhar os logs de acesso necessários para o destino do Amazon S3 fornecido pela Adobe.
1. O Brand Visibility está recebendo e detectando os logs do site relevante. O site está então disponível para seleção na origem do Adobe Brand Visibility no Experience Platform.

O encaminhamento de log BYOCDN fornece os dados de solicitação de CDN do lado do servidor usados para análise de tráfego de agente automatizado. Os dados não dependem da execução das tags JavaScript em um navegador. O necessário
O feed de log da CDN garante que o conjunto de dados de resumo de downstream contenha os dados de tráfego de agente de Visibilidade da marca desejados. Consulte a [referência de encaminhamento de log BYOCDN](https://experienceleague.adobe.com/pt-br/docs/brand-visibility/using/log-forwarding/log-forwarding-overview) para obter mais informações.

### Informações necessárias

Certifique-se de que você tenha valores para todos os detalhes necessários listados na tabela abaixo para cada site do Brand Visibility.

| Valor obrigatório | Verificação ou notas |
|---|---|
| Visibilidade da marca site ou domínio | Confirme o site coberto pelo encaminhamento de log da CDN. |
| Provedor de CDN | Identifique o CDN que atende o site. |
| Status do encaminhamento de log da CDN | Prova de que os registros do site são encaminhados e detectados pela Visibilidade da marca. |
| Site disponível na origem do Brand Visibility | Confirme se o site está disponível para seleção na origem da Visibilidade da marca. Um site está disponível com base na disponibilidade de logs CDN analisados no Brand Visibility. |
| Organização IMS | Use a organização IMS exata associada ao Brand Visibility, Experience Platform. |
| Sandbox | Use o nome exato da sandbox designada para a integração de entrada. |
| Conexão | Identifique a conexão de Jornada do cliente que deve incluir o conjunto de dados. |
| Exibição de dados | Identifique uma visualização de dados nova ou existente do Customer Journey Analytics que deve incluir os componentes. |
| Administrador ou proprietário | Forneça o nome ou o grupo que é o contato de configuração. |

Confirme se cada site está disponível para seleção na origem do Adobe Brand Visibility antes de continuar.

### Sandbox

Você pode adicionar o conjunto de dados à conexão do CJA depois que ele for exibido em **[!UICONTROL Conjuntos de dados]** nessa sandbox.

Confirme o seguinte:

* Organização IMS
* Sandbox do Target Experience Platform

A sandbox do AEP de destino é a mesma sandbox nomeada usada pela conexão ou conexões correspondentes do Customer Journey Analytics que incluem o conjunto de dados.

O cliente pode adicionar o conjunto de dados à conexão apropriada do CJA somente após a Adobe confirmar que o conjunto de dados gerenciado foi criado.

### Conjunto de dados de resumo

A integração de entrada fornece um conjunto de dados de resumo agregado no Experience Platform que contém informações de solicitação de CDN do lado do servidor associadas ao LLM, bot e agente automatizado
tráfego.

O Brand Visibility usa logs de acesso da CDN para identificar solicitações de bots e agentes automatizados. Esse tráfego não dispara tags JavaScript do navegador e, portanto, não é capturado por meio de uma implementação de análise da Web convencional.

Para obter a descrição detalhada da integração de entrada, estrutura do conjunto de dados e campos disponíveis, consulte [sobre o conjunto de dados](#about-the-dataset).

A origem da Visibilidade da marca cria o conjunto de dados de resumo no Experience Platform usando:

* A classe **[!UICONTROL Métricas de resumo XDM]**
* O grupo de campos **[!UICONTROL Resumo das Solicitações de CDN]**
* Campos organizados em um objeto **[!UICONTROL cdn]**

O conector cria o conjunto de dados para cada site do Brand Visibility, usando o seguinte padrão de nomenclatura: <code>Conjunto de Dados do Adobe Brand Visibility (ABV) - _baseUrl sem esquema_</code>. <br/>Por exemplo `Adobe Brand Visibility (ABV) Dataset - example.com` para o site <https://example.com>.

Os conjuntos de dados criados antes da adoção dessa convenção de nomenclatura exibem o conjunto de dados <code>Otimização de LLM (LLMO) padrão anterior - _baseUrl sem esquema_</code>.

Localize o conjunto de dados em **[!UICONTROL Conjuntos de dados]** na sandbox onde você criou o fluxo de dados.

O conjunto de dados é de resumo agregado. Ao analisar o volume de solicitações no Customer Journey Analytics, use a métrica **[!UICONTROL Contagem de solicitações da CDN]** fornecida, em vez de contar linhas do conjunto de dados.

Verifique os campos disponíveis no esquema do conjunto de dados criado para o site de Visibilidade da marca específico. Para planejar a configuração da visualização de dados, reveja os campos.

## Responsabilidades

Após ativar a origem da Visibilidade da marca, Visibilidade da marca:

* Fornece o conjunto de dados de resumo para o site selecionado.
* Traz o conjunto de dados para a sandbox onde você criou o fluxo de dados.

Suas responsabilidades como cliente são:

* Para garantir que os logs CDN sejam encaminhados para e recebidos pelo Brand Visibility para cada site do Brand Visibility.
* Para ativar a origem da Visibilidade da marca na sandbox correta, confirme se o site está disponível para seleção e selecione-o.
* Para selecionar a conexão do Customer Journey Analytics que deve incluir o conjunto de dados.
* Para adicionar o conjunto de dados a essa conexão.
* Para selecionar os campos a serem expostos como componentes na visualização de dados relevante do Customer Journey Analytics.
* Para validar se as dimensões e métricas resultantes suportam a análise desejada.

>[!IMPORTANT]
>
>O conector gerenciado para intencionalmente após criar e preencher o conjunto de dados do Experience Platform. A Adobe não modifica as conexões ou visualizações de dados do Customer Journey Analytics.

O conjunto de dados não estará disponível para análise da Customer Journey Analytics até que você o adicione a uma conexão. Os dados
O não estará disponível para usuários por meio de uma visualização de dados até que os campos relevantes tenham sido adicionados a ela.

Para ativar a origem:

1. No Experience Platform, selecione a sandbox em que deseja o conjunto de dados. Um site pode ser alocado apenas uma vez. Portanto, verifique se esta sandbox é a que você deseja.
1. Vá para **[!UICONTROL Fontes]**, depois **[!UICONTROL Catálogo]** e depois para aplicativos Adobe. No cartão **[!UICONTROL Adobe Brand Visibility]**, selecione **[!UICONTROL Configurar]** na primeira vez. Depois disso, o cartão mostra **[!UICONTROL Adicionar dados]**.

   ![Selecionar Visibilidade da marca de Fontes](assets/aep-sources-select-bv.png)

1. Selecione **[!UICONTROL Adicionar dados]**.

   ![Adicionar dados à origem da Visibilidade da marca](assets/aep-sources-bv-add-data.png)

1. Na etapa ➊ **[!UICONTROL Selecionar dados]**:

   1. Selecione o site na tabela **[!UICONTROL Nome do site]**. Depois que um site é alocado a um fluxo de dados, você não pode selecionar o site novamente nessa ou em qualquer outra sandbox.

      ![Etapa 1 da configuração da fonte de Visibilidade da marca](assets/bv-source-step-1.png)

   1. Selecione **[!UICONTROL Próximo]**.

1. Na etapa ➋ **[!UICONTROL detalhes do fluxo de dados]**:

   1. Insira um **[!UICONTROL Nome do fluxo de dados]** e uma **[!UICONTROL Descrição]** opcional. Você também pode assinar os alertas **[!UICONTROL Início da Execução do Fluxo de Dados de Fontes]**, **[!UICONTROL Êxito na Execução do Fluxo de Dados de Fontes]** e **[!UICONTROL Falha na Execução do Fluxo de Dados de Fontes]**.

      ![Etapa 2 da configuração da fonte de visibilidade da marca](assets/bv-source-step-2.png)

   1. Selecione **[!UICONTROL Próximo]**.

1. Na etapa ➌ **[!UICONTROL Avaliação]**:

   1. Verifique a conexão e a atribuição do conjunto de dados.

      ![Etapa 3 da configuração da fonte de Visibilidade da marca](assets/bv-source-step-3.png)

   1. selecione **[!UICONTROL Concluir]**.

O conjunto de dados é atribuído automaticamente e nenhum mapeamento de campo é necessário.

>[!IMPORTANT]
>
>Um site pode ser alocado apenas uma vez. Para usar o site em uma sandbox diferente, exclua o fluxo de dados ao qual o site está alocado. A exclusão do fluxo de dados afeta qualquer conexão ou visualização de dados do Customer Journey Analytics que dependa dos dados dessa fonte.
>


## Verificação

Use o procedimento a seguir para verificar a integração de entrada:

1. Confirme o site ABV e a preparação do log de CDN.

   Para cada site ABV:

   * Confirme o site ou domínio exato coberto pelo encaminhamento de log CDN.
   * Confirme se o site está disponível para seleção na fonte de Visibilidade da marca no Experience Platform. Um site está disponível com base na disponibilidade de logs CDN analisados no Brand Visibility.
   * Não continue com uma declaração geral de que &quot;os logs de CDN estão ativados&quot;. Continue quando o site ABV específico estiver disponível para seleção.
   * Confirme se o Brand Visibility está recebendo ou detectando logs desse site.
   * Obtenha da Adobe a confirmação de disponibilidade do Brand Visibility do site.

1. Verifique o conjunto de dados na Experience Platform.

   Depois de criar o fluxo de dados:
   1. Faça logon no **[!UICONTROL Experience Platform]**.
   1. Selecione a sandbox em que você criou o fluxo de dados.
   1. Localize o conjunto de dados do seu site do Brand Visibility em **[!UICONTROL Conjuntos de dados]**.
   1. Confirme se o conjunto de dados está associado ao site de Visibilidade da marca esperado.
   1. Registre a **[!UICONTROL ID do Conjunto de Dados]** e o **[!UICONTROL Esquema]** vinculado.
   1. Revise a contagem de registros do conjunto de dados, as informações mais recentes de assimilação e os dados de amostra disponíveis, quando permitido.
   1. Abra o esquema vinculado e verifique a estrutura XDM esperada:
      * Classe: **[!UICONTROL Métricas de resumo XDM]**
      * Grupo de campos: **[!UICONTROL Resumo de Solicitações da CDN]**
      * Objeto: **[!UICONTROL cdn]**
      * Dimensões e métricas esperadas, como **[!UICONTROL botType]**, **[!UICONTROL cdnProvider]**, **[!UICONTROL url]**, **[!UICONTROL host]**, **[!UICONTROL status]**, **[!UICONTROL solicitações]** e **[!UICONTROL timeToFirstByte]**.

1. Adicionar o conjunto de dados a uma conexão

   O administrador do Customer Journey Analytics deve adicionar o conjunto de dados à conexão desejada:

   1. Faça logon no Customer Journey Analytics.
   1. [Crie uma nova conexão ou edite a conexão pretendida existente](/help/connections/create-connection.md). Confirme se a conexão usa a mesma sandbox da Experience Platform em que o conjunto de dados foi criado.
   1. Procure o conjunto de dados por nome ou ID de conjunto de dados.
   1. Adicione o conjunto de dados à conexão.
   1. Defina as configurações do conjunto de dados de acordo com o design do Customer Journey Analytics do cliente.
   1. Salve a conexão.
   1. Para confirmar se o conjunto de dados está incluído e se a assimilação está progredindo, analise os detalhes da conexão.

1. Configurar ou atualizar a visualização de dados

   Depois que o conjunto de dados fizer parte da conexão:
   1. Faça logon no Customer Journey Analytics.
   1. [Crie uma nova visualização de dados ou edite a visualização de dados](/help/data-views/create-dataview.md) associada ao caso de uso de relatórios pretendido.
   1. Selecione a conexão que contém o conjunto de dados de Visibilidade da marca gerenciada.
   1. Adicione os campos de esquema necessários como dimensões ou métricas.
   1. Inclua os campos necessários para a análise planejada, como:
      * **[!UICONTROL Tipo de bot da CDN]**
      * **[!UICONTROL Provedor da CDN]**
      * **[!UICONTROL URL DA CDN]**
      * **[!UICONTROL Host da CDN]**
      * **[!UICONTROL Status HTTP da CDN]**
      * **[!UICONTROL Contagem de Solicitações da CDN]**
      * **[!UICONTROL Tempo Médio até o Primeiro Byte da CDN]**
   1. Salve a visualização de dados.
   1. Valide os campos no Analysis Workspace ou no fluxo de trabalho de relatório selecionado pelo cliente.

1. Validar o resultado completo

   Use um período de relatório recente e verifique se:

   * O site de Visibilidade da marca esperado é representado.
   * O provedor de CDN e os valores de host esperados estão presentes.
   * O tráfego de bot ou agente automatizado é representado.
   * As dimensões URL e status HTTP contêm os valores esperados.
   * A Contagem de solicitações CDN e as métricas de desempenho estão disponíveis.
   * O conjunto de dados está incluído na conexão desejada.
   * Os campos obrigatórios são expostos na visualização de dados desejada.

O tempo exato necessário para que os dados fiquem disponíveis depende do fluxo de trabalho de assimilação e processamento do Customer Journey Analytics.

## Solução de problemas

Revise as seguintes etapas se ocorrerem problemas:

* O conjunto de dados não aparece no AEP.

  Verifique se:

  * A organização IMS está correta.
  * A sandbox do Experience Platform selecionada está correta.
  * A origem foi habilitada depois que o encaminhamento de log CDN estava funcionando.
  * O nome ou ID do conjunto de dados fornecido pela Adobe foi usado.
  * O conjunto de dados foi criado para o site de Visibilidade da marca correto.

* O conjunto de dados existe, mas não contém os dados esperados.

  Verifique se:
  * Os logs CDN estão sendo encaminhados para o site de Visibilidade da marca exato.
  * O Brand Visibility está recebendo ou detectando logs do site.
  * O site ou domínio na configuração do CDN corresponde ao site do Brand Visibility.
  * O conector gerenciado foi habilitado depois que a preparação do log de CDN foi confirmada.
  * O intervalo de datas selecionado inclui o período após o início da assimilação de log.


* O conjunto de dados existe no Experience Platform, mas não está disponível no Customer Journey Analytics.

  Verifique se:
  * A conexão do Customer Journey Analytics usa a mesma sandbox Experience Platform nomeada.
  * O conjunto de dados foi adicionado explicitamente à conexão.
  * O administrador do Customer Journey Analytics tem as permissões necessárias.
  * A conexão foi salva após a adição do conjunto de dados.

* O conjunto de dados está na conexão, mas os campos não estão disponíveis para relatórios.

  Verifique se:
  * A visualização de dados seleciona a conexão correta do Customer Journey Analytics.
  * Os campos de esquema esperados foram adicionados como componentes de visualização de dados.
  * Os campos foram colocados na seção pretendida **[!UICONTROL Dimensões]** ou **[!UICONTROL Métricas]**.
  * A visualização de dados foi salva após a adição dos componentes.
  * O esquema do conjunto de dados corresponde à estrutura de grupo de campos esperada do **[!UICONTROL Resumo de Solicitações CDN]**.

* O site não está na lista.

  Verifique se:

  * Um site está disponível para seleção com base na disponibilidade de logs CDN analisados no Brand Visibility.
  * O encaminhamento de log CDN está configurado e funcionando para o site.

* Não é possível selecionar o site.

  Observe que, uma vez alocado um site a um fluxo de dados, ele não poderá ser selecionado novamente nessa ou em qualquer outra sandbox. Para usar o site em uma sandbox diferente, exclua o fluxo de dados ao qual o site está alocado. O site pode ser selecionado novamente. A exclusão do fluxo de dados afeta qualquer conexão ou visualização de dados do Customer Journey Analytics que dependa dos dados dessa fonte.

* O fluxo de dados mostra um status de falha.

  Use o painel **[!UICONTROL Monitoramento]**. A visão geral de **[!UICONTROL Fontes]** observa que um fluxo de dados de origem que falha continuamente por 30 dias é desabilitado automaticamente.


## Critérios de conclusão


A integração de entrada está pronta para a configuração do Customer Journey Analytics do lado do cliente quando todos os itens a seguir forem confirmados:

* Os logs CDN são encaminhados para e recebidos pelo Brand Visibility para cada site ABV solicitado.
* Cada site de Visibilidade da marca está disponível para seleção na origem do Adobe Brand Visibility.
* Você ativou a origem do Adobe Brand Visibility na sandbox desejada.
* O conjunto de dados de resumo por site é exibido nessa sandbox.
* Você verificou o conjunto de dados e seu esquema XDM.
* Você adicionou o conjunto de dados à conexão do CJA pretendida.
* Você configurou os componentes relevantes da Visualização de dados do CJA.

