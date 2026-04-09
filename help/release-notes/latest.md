---
title: Notas de versão atuais do Customer Journey Analytics
description: Exibir as notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 701279f92877ee186160f901f0d4df74fd42f547
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 36%

---

# Notas de versão atuais do Customer Journey Analytics (abril de 2026)

**Última atualização**: 9 de abril de 2026

Essas notas de versão abordam o período de lançamento de abril de 2026. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso e descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| -----------|-----------|-----------|
| **Suporte para o idioma italiano**<br/> A localidade italiana (it-IT) agora é compatível com o Analysis Workspace no Customer Journey Analytics. <p>O Customer Journey Analytics oferece suporte a todos os idiomas com suporte na interface do usuário do Experience Platform, conforme descrito em [Suporte a navegador e idioma para a interface do usuário do Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/landing/platform-ui/browser-language-support#language-support).</p><p>Você pode [alterar seu idioma padrão](https://experienceleague.adobe.com/pt-br/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language) no Experience Platform.</p> | | quinta-feira, 8 de abril de 2026 |
| **Validação de dados no Agente de Engenharia da Adobe** <br/>Novas habilidades de validação de dados estão disponíveis na Data Engineering Agent. Essas habilidades ajudam as equipes a avaliar rapidamente a qualidade dos dados diretamente no Adobe Experience Platform, antes que os dados sejam analisados no Customer Journey Analytics. <p>As habilidades de validação de dados permitem a validação sob demanda, em nível de campo e em nível de conjunto de dados, combinando resumos estatísticos com a detecção inteligente de valores inválidos ou anômalos. </p><p>O uso de habilidades de validação de dados reduz o esforço manual de controle de qualidade e acelera a integração de dados confiáveis e as transformações em fluxos de trabalho de engenharia de dados.</p><p>(Link da documentação em breve).<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/pt-br/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | Final de abril de 2026 <p>(Planejado originalmente para lançamento em quarta-feira, 31 de março de 2026)</p> |
| **Servidores MCP para Customer Journey Analytics** <br/>Agora é possível vincular o Customer Journey Analytics aos seus fluxos de trabalho de agente existentes usando o MCP (Model Context Protocol). Você pode solicitar relatórios e insights usando a linguagem natural.<p>(Link para a documentação a seguir).</p> | | Final de abril de 2026 |
| **Serviços de mídia de streaming: Dados de agendamento de suporte** <br/>Agora você pode carregar dados de agendamento de conteúdo de mídia de streaming ao vivo anteriores para rastrear a audiência com mais facilidade e precisão.<p>Veja a seguir alguns exemplos de conteúdo ao vivo que são compatíveis com o upload de dados de programação:</p><ul><li>Plataformas FAST (TV com suporte a anúncios gratuitos)</li><li>Transmissões locais</li><li>Esportes ao vivo</li></ul><p>O upload de dados de programação permite acompanhar os dados de de número de visualizadores de programas individuais que foram executados durante o período designado no arquivo de upload. É possível até coletar dados do número de visualizadores para tópicos ou segmentos de programa específicos.</p><p>Esses recursos estão disponíveis independentemente de como você implementou a coleta de mídias de transmissão.</p><p>Anteriormente, era difícil vincular com precisão uma determinada sessão a programas específicos ao analisar o conteúdo ao vivo e não era possível vincular uma determinada sessão a tópicos ou segmentos de programa individuais.</p><p>Para obter mais informações, consulte [Fazer upload de dados de agendamento para rastrear conteúdo ao vivo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de outubro de 2025 | Primeiro semestre de 2026<p>(Planejado originalmente para lançamento em 29 de outubro de 2025)</p> |
| **Relatórios de API de várias dimensões**<br/> Relate várias dimensões em uma única solicitação de API e faça pesquisas no nível da dimensão. [Saiba mais](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | Março de 2026 |
| **Classificação de API de várias colunas**<br/> Classificar vários objetos de dimensão e métrica em uma solicitação de API. Misturar dimensões e métricas na mesma definição de classificação. [Saiba mais](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | Março de 2026 |

## Correções no Customer Journey Analytics

**Analysis Workspace**: AN-442813, AN-442410, AN-442231, AN-441943, AN-441717, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Componentes**:
**Conexões**: AN-442824, AN-440937, AN-440092, AN-429781
**Content Analytics**
**Análise guiada**:
**Exportações**:
**Visualizações de dados**: AN-442809, AN-434824, AN-434210, AN-424000
**Implementação**:
**Report Builder**: AN-441136, AN-438147, AN-425150
**Relatórios**: AN-443900, AN-441811, AN-441506, AN-440919, AN-440545, AN-440505, AN-440300
**Segmentação**:
**Relatórios agendados**:
**Métricas e dimensões compartilhadas**:
**Outros**: AN-423359, AN-406242, AN-397985


## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| **Remoção de conjuntos de cifras do TLS 1.2** | quinta-feira, 11 de fevereiro de 2026 | Aviso aos administradores: a Adobe planeja remover o suporte aos seguintes conjuntos de cifras TLS 1.2 dos servidores de coleta de dados da Adobe em 27 de maio de 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>Nenhuma ação do cliente é necessária para a maioria das implementações. Essa alteração afeta principalmente os dados do Analytics enviados de aplicativos nativos herdados que usam bibliotecas TLS desatualizadas e um pequeno número de visitantes da Web em navegadores ou sistemas operacionais obsoletos. A remoção do suporte para esses conjuntos de cifras melhora a segurança e alinha o Adobe aos padrões de criptografia modernos. Menos de 0,1% do tráfego da coleta de dados atualmente depende desses conjuntos de cifras.</p> |

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
