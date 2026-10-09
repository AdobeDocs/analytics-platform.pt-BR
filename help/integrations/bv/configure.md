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
source-git-commit: fbbb3ffb1b0d1d5361b594e81c260dab25f44338
workflow-type: tm+mt
source-wordcount: '1783'
ht-degree: 0%
---
# Definir e configurar a integração de entrada

Este artigo detalha os [pré-requisitos](#prerequisites), [responsabilidades](#responsibilities), [etapas a serem verificadas](#verification), [etapas de solução de problemas](#troubleshoot) e [critérios de conclusão](#completion-criteria) para configurar a integração de entrada do Brand Visibility com o Customer Journey Analytics.

## Pré-requisitos

Considere os seguintes pré-requisitos antes de habilitar a integração de entrada. E utilizar o procedimento de verificação para verificar

### Encaminhamento de log BYOCDN

Os logs de acesso do CDN devem ser encaminhados para e recebidos pela Adobe Brand Visibility para cada site do Brand Visibility para que o conector de origem do Brand Visibility possa ser viável.

Esse requisito se aplica a cada site de Visibilidade da marca. Uma configuração de CDN ou feed de log para um site, domínio ou subdomínio cobre somente esse site, a menos que a Adobe confirme essa cobertura para outro site.

Verifique com o Adobe as duas partes da entrega:

1. Você configurou o CDN ou pipeline de log relevante para encaminhar os logs de acesso necessários para o destino do Amazon S3 fornecido pela Adobe.
1. A Adobe confirmou que os registros estão sendo recebidos e detectados para o site relevante.

O encaminhamento de log BYOCDN fornece os dados de solicitação de CDN do lado do servidor usados para análise de tráfego de agente automatizado. Os dados não dependem da execução das tags JavaScript em um navegador. O necessário
O feed de log da CDN garante que o conjunto de dados de resumo de downstream contenha os dados de tráfego de agente de Visibilidade da marca desejados. Consulte a [referência de encaminhamento de log BYOCDN](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview) para obter mais informações.

### Informações necessárias

Certifique-se de que você tenha valores para todos os detalhes necessários listados na tabela abaixo para cada site do Brand Visibility.

| Valor obrigatório | Verificação ou notas |
|---|---|
| Visibilidade da marca site ou domínio | Confirme o site coberto pelo encaminhamento de log da CDN. |
| Provedor de CDN | Identifique o CDN que atende o site. |
| Status do encaminhamento de log da CDN | Prova de que os registros do site são encaminhados e detectados pela Visibilidade da marca. |
| Confirmação de disponibilidade do Brand Visibility | Confirme com a equipe de conta da Adobe a prontidão antes de habilitar e agendar o conector. |
| Organização IMS | Use a organização IMS exata associada ao Brand Visibility, Experience Platform. |
| Sandbox | Use o nome exato da sandbox designada para a integração de entrada. |
| Conexão | Identifique a conexão de Jornada do cliente que deve incluir o conjunto de dados. |
| Exibição de dados | Identifique uma visualização de dados nova ou existente do Customer Journey Analytics que deve incluir os componentes. |
| Administrador ou proprietário | Forneça o nome ou o grupo que é o contato de configuração. |

Antes de o Adobe agendar o conector gerenciado, a equipe de conta da Adobe deve confirmar se o site está pronto para a integração de entrada. As comunicações de entrega referem-se a isso como aprovação de Visibilidade da marca ou confirmação de disponibilidade do site. O agendamento do conector gerenciado é um requisito de serviço gerenciado, não uma ação de autoatendimento do cliente.

### Sandbox

O conector gerenciado deve criar o conjunto de dados na sandbox da AEP nomeada específica designada pelo cliente na Organização IMS.

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

O conector gerenciado cria o conjunto de dados de resumo no Experience Platform usando:

* A classe **[!UICONTROL Métricas de resumo XDM]**
* O grupo de campos **[!UICONTROL Resumo das Solicitações de CDN]**
* Campos organizados em um objeto **[!UICONTROL cdn]**

O conector cria o conjunto de dados para cada site do Brand Visibility, usando o seguinte padrão de nomenclatura: <code>Conjunto de Dados do Adobe Brand Visibility (ABV) - _baseUrl sem esquema_</code>. <br/>Por exemplo `Adobe Brand Visibility (ABV) Dataset - example.com` para o site <https://example.com>.

Os conjuntos de dados criados antes da adoção dessa convenção de nomenclatura exibem o conjunto de dados <code>Otimização de LLM (LLMO) padrão anterior - _baseUrl sem esquema_</code>.
Em todos os casos, os clientes precisam confirmar o nome exato do conjunto de dados ou a ID do conjunto de dados com a equipe de conta da Adobe após a criação.

O conjunto de dados é de resumo agregado. Ao analisar o volume de solicitações no Customer Journey Analytics, use a métrica **[!UICONTROL Contagem de solicitações da CDN]** fornecida, em vez de contar linhas do conjunto de dados.

Verifique os campos disponíveis no esquema do conjunto de dados criado para o site de Visibilidade da marca específico. Para planejar a configuração da visualização de dados, reveja os campos.

## Responsabilidades

O Adobe gerencia o conector de entrada e, após a confirmação dos pré-requisitos:

* Ativa o conector ABV → AEP gerenciado.
* Cria o conjunto de dados de resumo para cada site ABV configurado.
* Traz o conjunto de dados para a sandbox da AEP fornecida pelo cliente.
* Fornece ao cliente o nome do conjunto de dados ou a ID do conjunto de dados para verificação.

Suas responsabilidades como cliente são:

* Para garantir que os logs CDN sejam encaminhados para e recebidos pelo Brand Visibility para cada site do Brand Visibility.
* Para fornecer a organização IMS correta e a sandbox Experience Platform nomeada.
* Para selecionar a conexão do Customer Journey Analytics que deve incluir o conjunto de dados.
* Para adicionar o conjunto de dados a essa conexão.
* Para selecionar os campos a serem expostos como componentes na visualização de dados relevante do Customer Journey Analytics.
* Para validar se as dimensões e métricas resultantes suportam a análise desejada.

>[!IMPORTANT]
>
>O conector gerenciado para intencionalmente após criar e preencher o conjunto de dados do Experience Platform. A Adobe não modifica as conexões ou visualizações de dados do Customer Journey Analytics.

O conjunto de dados não estará disponível para análise da Customer Journey Analytics até que você o adicione a uma conexão. Os dados
O não estará disponível para usuários por meio de uma visualização de dados até que os campos relevantes tenham sido adicionados a ela.

## Verificação

Use o procedimento a seguir para verificar a integração de entrada:

1. Confirmar disponibilidade do site ABV e do log de CDN

   Para cada site ABV:

   * Confirme o site ou domínio exato coberto pela solicitação.
   * Confirme o provedor de CDN.
   * Confirme se o pipeline de CDN ou log está encaminhando os logs de acesso necessários.
   * Confirme se o Brand Visibility está recebendo ou detectando logs desse site.
   * Obtenha da Adobe a confirmação de disponibilidade do Brand Visibility do site.

   Não continue usando uma declaração geral de que &quot;os registros CDN estão ativados&quot;, a menos que a confirmação cubra o site ABV específico.

1. Verificar o conjunto de dados gerenciado no Experience Platform

   Depois que a Adobe confirmar que o conector gerenciado criou o conjunto de dados:
   1. Faça logon no **[!UICONTROL Experience Platform]**.
   1. Selecione a sandbox nomeada fornecida durante a entrada na lista de sandboxes.
   1. Localize o nome do conjunto de dados ou a ID do conjunto de dados fornecida pela Adobe em **[!UICONTROL Conjuntos de Dados]**.
   1. Confirme se o conjunto de dados está associado ao site de Visibilidade da marca esperado.
   1. Registre a **[!UICONTROL ID do Conjunto de Dados]** e o **[!UICONTROL Esquema]** vinculado.
   1. Revise a contagem de registros do conjunto de dados, as informações mais recentes de assimilação e os dados de amostra disponíveis, quando permitido.
   1. Abra o esquema vinculado e verifique a estrutura XDM esperada:
      * Classe: **[!UICONTROL Métricas de resumo XDM]**
      * Grupo de campos: **[!UICONTROL Resumo de Solicitações da CDN]**
      * Objeto: **[!UICONTROL cdn]**
      * Dimensões e métricas esperadas, como **[!UICONTROL botType]**, **[!UICONTROL cdnProvider]**, **[!UICONTROL url]**, **[!UICONTROL host]**, **[!UICONTROL status]**, **[!UICONTROL solicitações]** e **[!UICONTROL timeToFirstByte]**.

1. Adicionar o conjunto de dados a uma conexão

   O administrador do Customer Journey Analytics deve adicionar o conjunto de dados gerenciado à conexão desejada:

   1. Faça logon no Customer Journey Analytics.
   1. [Crie uma nova conexão ou edite a conexão pretendida existente](/help/connections/create-connection.md). Confirme se a conexão usa a mesma sandbox da Experience Platform em que o conjunto de dados gerenciado foi criado.
   1. Procure o conjunto de dados usando o nome ou a ID do conjunto de dados fornecida pela Adobe.
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
      * **[!UICONTROL Tipo de bot]**
      * **[!UICONTROL Provedor da CDN]**
      * **[!UICONTROL URL]**
      * **[!UICONTROL Host]**
      * **[!UICONTROL Status HTTP]**
      * **[!UICONTROL Contagem de Solicitações]**
      * **[!UICONTROL Tempo até o Primeiro Byte]**
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

O tempo exato necessário para que os dados fiquem disponíveis depende da assimilação gerenciada e do fluxo de trabalho de processamento do Customer Journey Analytics. Sua equipe de conta da Adobe deve fornecer todas as expectativas de processamento aplicáveis para sua solicitação.

## Solução de problemas

Veja abaixo o que fazer se ocorrerem problemas:

* O conjunto de dados não aparece no AEP.

  Verifique se:

  * A organização IMS está correta.
  * A sandbox do Experience Platform selecionada está correta.
  * A Adobe confirmou que o conector gerenciado estava ativado.
  * O nome ou ID do conjunto de dados fornecido pela Adobe foi usado.
  * O conjunto de dados foi criado para o site de Visibilidade da marca correto.

* O conjunto de dados existe, mas não contém os dados esperados.

  Verifique se:
  * Os logs CDN estão sendo encaminhados para o site de Visibilidade da marca exato.
  * O ABV confirmou que os logs estão sendo recebidos ou detectados.
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


## Critérios de conclusão


A integração de entrada está pronta para a configuração do Customer Journey Analytics do lado do cliente quando todos os itens a seguir forem confirmados:

* Os logs CDN são encaminhados para e recebidos pelo Brand Visibility para cada site ABV solicitado.
* A Adobe confirmou a disponibilidade do site para o conector gerenciado.
* A organização IMS foi fornecida.
* A sandbox de destino exata do Experience Platform foi fornecida.
* A Adobe criou o conjunto de dados de resumo por site nessa sandbox.
* Você verificou o conjunto de dados e seu esquema XDM.
* Você adicionou o conjunto de dados à conexão do CJA pretendida.
* Você configurou os componentes relevantes da Visualização de dados do CJA.

