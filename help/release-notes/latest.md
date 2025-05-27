---
title: Notas de versão atuais do Customer Journey Analytics
description: Exibir as notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 6fdb6cbd6f12a0417f513565b02e3ad60c8df6cb
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 36%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (maio de 2025)

**Última atualização**: sexta-feira, 22 de maio de 2025


Essas notas de versão abrangem o período de lançamento de 22 de abril a 18 de junho de 2025. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Campos XDM atualizados para coleta de dados de transmissão de mídia na Adobe Experience Platform** | Ao coletar dados de mídia de transmissão no Adobe Experience Platform, os caminhos de campo XDM mostrados no cabeçalho de &quot;Caminho do campo XDM&quot; da documentação de parâmetros de mídia de transmissão não devem mais ser usados. Esses caminhos de campo são encontrados nas seguintes páginas e são marcados como &quot;Obsoletos&quot;: [Parâmetros de áudio e vídeo](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parâmetros de anúncios](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters), [Parâmetros de capítulo](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parâmetros de estado do player](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters) e [Parâmetros de qualidade](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters). <p>Em vez disso, os clientes devem migrar para os caminhos de campo `mediaReporting`, como mostrado no cabeçalho &quot;Caminho do campo XDM do relatório&quot; da documentação de parâmetros de mídia de streaming mencionada acima.<p>Durante um período de transição de três meses, a assimilação de dados nos caminhos de campo XDM obsoletos continuará. No entanto, no final de julho de 2025, os caminhos de campo obsoletos serão totalmente removidos e não estarão mais visíveis na interface do esquema do Adobe Experience Platform, e os dados serão enviados somente usando os caminhos de campo `mediaReporting`.<p>Os clientes que implementaram o conector de origem do Analytics para coletar dados de mídia de transmissão na Platform antes de 22 de abril de 2025 devem migrar suas configurações existentes para usar os novos caminhos de campo. Essa migração deve ser concluída até o final de julho de 2025. Entre em contato com os serviços da Adobe Consulting ou com a equipe de conta para obter suporte à migração. Nenhuma ação será necessária para clientes que implementarem o conector de origem do Analytics após 22 de abril de 2025.</p> |  | 22 de abril de 2025 |
| **Compilação: recuperar IDs persistentes e transitórias do identityMap de XDM** | Esse recurso oferece suporte ao uso de identidades armazenadas no identityMap de XDM no processo de compilação. O identityMap pode ser usado como ID persistente ou transitória na compilação baseada em campos e como ID persistente na compilação baseada em gráficos.  É possível usar um namespace específico ou uma identidade principal do identityMap. Saiba mais [aqui](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/fbs#identitymap) e [aqui](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/gbs#identitymap) |  | terça-feira, 28 de abril de 2025 |
| **Métricas e dimensões compartilhadas entre exibições de dados** | Permite aplicar configurações de dimensão e métrica em várias exibições de dados. As alterações feitas em uma dimensão ou métrica compartilhada se aplicam a todas as instâncias dessa dimensão ou métrica em todas as exibições de dados aplicáveis. Essa interface permite que admins do Customer Journey Analytics gerenciem componentes com mais facilidade ao utilizar muitas exibições de dados. [Saiba mais](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 30 de abril de 2025 |
| **Aumento em limites completos de exportação de tabela** | A Adobe aumentou o número de colunas que você pode usar com a [exportação completa de tabela](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/export/export-cloud#comparison-of-full-table-export-in-customer-journey-analytics-to-data-warehouse-in-adobe-analytics) de 5 dimensões e 5 métricas para 10 dimensões e 10 métricas. Isso se aplica a todos os níveis do Customer Journey Analytics. Não há alteração nos direitos para o número de linhas que podem ser exportadas. |  | 30 de abril de 2025 |
| **Dimensão de Profundidade do Evento** | Uma nova [dimensão de Profundidade do Evento](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference#required-standard-components) foi adicionada à lista de componentes padrão necessários para uma visualização de dados. |  | sexta-feira, 8 de maio de 2025 |
| **Desabilitar o arquivo de manifesto ao exportar tabelas completas** | Permite desabilitar o arquivo de manifesto incluído por padrão ao exportar tabelas completas do Analysis Workspace. [Saiba mais](/help/analysis-workspace/export/export-cloud.md) |  | quarta-feira, 20 de maio de 2025 |
| **Data Insights Agent** | O Data Insights Agent, parte do Assistente de IA no Customer Journey Analytics, é um agente de conversação de IA generativa. Ele usa componentes da visualização de dados e dos dados reais para responder de forma rápida e eficiente a perguntas centradas em dados, criando visualizações relevantes no Analysis Workspace. [Saiba mais](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) |  | quinta-feira, 28 de maio de 2025 |
| **O painel esquerdo do Analysis Workspace não abre e fecha ao passar o mouse** | O painel esquerdo do Analysis Workspace é usado para adicionar componentes, painéis e visualizações ao projeto. A opção de abrir temporariamente o painel esquerdo passando o mouse sobre um dos ícones à esquerda não está mais disponível. Em vez disso, basta clicar em um desses ícones para manter o painel aberto e clicar novamente no ícone para fechá-lo. |  | 29 de maio de 2025 |
| **O padrão do formato Dimension é 2 para dimensões do tipo Double** | Para esquemas com tipos de dados Double, o formato da dimensão agora assume o padrão de 2 casas decimais. Você pode alterar esse número para 0 a 5 casas decimais.<p>Anteriormente, o formato assumia como padrão 0 casas decimais.</p><p>Isso significa que, se estiver usando dimensões do tipo duplo nos relatórios do Analysis Workspace, nenhuma casa decimal será exibida por padrão. Esses mesmos relatórios mostrarão agora 2 casas decimais.</p><p>Para obter mais informações sobre como atualizar o número de casas decimais exibidas para dimensões do tipo duplo, consulte [Configurações do componente de Formato](/help/data-views/component-settings/format.md).</p> | | 29 de maio de 2025 |
| **Customer Journey Analytics B2B edition** | O Customer Journey Analytics B2B edition ajuda as empresas B2B a alinhar suas equipes de marketing, vendas e produtos, fornecendo insights de conta acionáveis que impulsionam o crescimento da receita. Com a conta colocada no centro do modelo de dados, toda a análise se concentra na jornada da conta. Adicionar uma nova camada de entidades (contas, oportunidades e grupos de compras) sobre eventos pessoais e baseados em tempo cria uma imagem completa do ciclo de vida de marketing e receita B2B. [Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | quinta-feira, 18 de junho de 2025 |
| **Adicionar e exibir comentários em projetos do Analysis Workspace** | Um novo recurso [de comentários](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) no Analysis Workspace permite que você compartilhe insights e faça perguntas no contexto de um projeto do Analysis Workspace. Isso pode simplificar as discussões sobre os dados, mantendo conversas no contexto dos dados que estão sendo discutidos. É possível <ul><li>Comentar em qualquer projeto do Analysis Workspace ao qual você tenha acesso</li><li>Comentar em um ponto específico em uma visualização ou fazer comentários gerais sobre um projeto</li><li>Marque outros usuários para notificá-los sobre seus comentários</li><li>Gerenciar comentários existentes (editar, fixar, resolver e assim por diante)</li></ul>Os administradores do Customer Journey Analytics podem [desabilitar comentários no nível da organização](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Os proprietários do projeto podem [desabilitar comentários no nível do projeto](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). |  | quinta-feira, 25 de junho de 2025 <p>(Planejado originalmente para lançamento em 29 de maio de 2025)</p> |

## Correções no Customer Journey Analytics

**Analysis Workspace**: AN-361874; AN-371360; AN-373079; AN-374382; AN-374447; AN-375277; AN-375680
**Públicos-alvo**: AN-372343
**Log de auditoria**: AN-378168
**Conexões**: AN-373121; AN-372996
**Exclusão de dados**: AN-375450
**Campos derivados**: AN-373689; AN-377852
**Exportar locais**: AN-374167
**Tela do Jornada**: AN-373319
**Report Builder**: AN-369786
**Relatórios**: AN-377326; AN-378051
**Gerente de atividades de relatório**: AN-377148


## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| N/A | | |

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
