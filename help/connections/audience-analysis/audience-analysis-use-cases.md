---
title: Casos de uso da análise de público-alvo
description: Saiba mais sobre casos de uso para análise de público-alvo.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
exl-id: 4f465e71-f1b5-4f38-a1db-645550856849
source-git-commit: d14163794fd4d31b29bfc6f55622d839b67ab3d7
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---

# Casos de uso da análise de público-alvo {#analyze-audiences-use-cases}

A Análise de público-alvo permite a geração de relatórios de dados de associação de público-alvo do Experience Platform no Customer Journey Analytics. Isso é feito por meio de configurações gerenciadas pelo assistente de configurações da Análise de público-alvo, que ajuda a determinar qual conjunto de dados de perfil você está assimilando, juntamente com outros parâmetros e detalhes de configuração. (Para obter informações mais detalhadas, consulte [Visão geral da Análise de público-alvo](/help/connections/audience-analysis/audience-analysis-overview.md). )

Este documento inclui casos de uso de exemplo que destacam o valor fornecido pela Análise de público-alvo. Antes de analisar os casos de uso, familiarize-se com as considerações sobre relatórios abaixo. É importante ter essas considerações em mente ao analisar seus casos de uso, pois eles podem afetar a saída final de seus relatórios.

## Considerações sobre relatórios

A versão inicial da Análise de público-alvo estabelece a base essencial necessária para processar e assimilar públicos-alvo da Experience Platform na Customer Journey Analytics. Ao realizar sua análise, é importante estar atento a vários fatores que podem influenciar seus resultados em projetos do Workspace:

* **Os dados de associação de público-alvo são precisos somente para o dia anterior (&quot;ontem&quot;)**: os dados de associação de público-alvo sempre conterão o conjunto de dados de instantâneo de perfil mais recente gerado pelo Serviço de Perfil Unificado. Esse conjunto de dados de perfil é um instantâneo diário e é preciso somente para o dia anterior (&quot;ontem&quot;), com ele sendo automaticamente gerado e reprocessado todas as noites. As dimensões de público-alvo estão disponíveis para relatórios e detalhamentos, não para reconstruir estados históricos de público-alvo.

   * Exemplo: independentemente da janela de tempo do relatório escolhida, o público-alvo reportável do CJA sempre respeitará o estado de associação de público-alvo presente no instantâneo de perfil assimilado mais recente (&quot;ontem&quot;).

      * Como exemplo, ampliar a janela de tempo do relatório para &quot;últimos 30 dias&quot; incluirá mais eventos e dará a impressão de que o tamanho do público-alvo está mudando. No entanto, a composição do perfil do público-alvo sempre corresponderá ao instantâneo de &quot;ontem&quot;, independentemente da janela de tempo escolhida.

* **As dimensões devem ter um evento correspondente a ser incluído**: as dimensões de Análise de Público-Alvo só podem ser analisadas onde houver eventos correspondentes no CJA. Se um comportamento, canal ou momento do ciclo de vida não for representado como um evento na conexão do CJA, ele não poderá ser analisado.

   * Exemplo: um público-alvo usado para direcionar pessoas com um anúncio incluiria significativamente mais pessoas no público-alvo do RTCDP do que no público-alvo do CJA. Isso ocorre porque o público-alvo do CJA é limitado às pessoas que tiveram um evento no CJA durante a janela de relatórios.

* **A resolução de identidade é baseada exclusivamente em um único namespace**: a resolução de identidade depende totalmente do namespace de identidade selecionado como parte da configuração da Análise de Público-Alvo. A análise será restrita a esse namespace de identidade, com eventos que caem fora dele não estando disponíveis para relatórios de análise de público-alvo.

   * Exemplo: para um conjunto de dados de evento compilado que combina o CRM e a ECID, e a configuração da Análise de público-alvo usa a ID do CRM, somente as linhas que contêm uma ID do CRM serão reconhecidas como parte do público-alvo reportável no CJA. Portanto, o tamanho do público resultante pode ser menor do que o previsto.

## Exemplo de casos de uso

### Caso de uso 1

Entenda como um público-alvo específico se comporta em um determinado canal (por exemplo, web ou aplicativo) para responder a perguntas como:

* _&quot;O que os membros de clientes potenciais de alto valor estão fazendo no site agora (páginas, recursos, funis)?&quot;_

* _&quot;Quais campanhas e conteúdo sobrepõem o índice desse público-alvo em comparação com todos os outros?&quot;_

#### Fluxo de configuração

1. Configure a Análise de público-alvo no CJA para um único namespace de identidade (por exemplo, ECID ou CRM_ID) e uma visualização de dados focada na Web.

   * Isso assimilará automaticamente os dados de associação de público-alvo na conexão escolhida por meio da exportação diária do instantâneo do perfil

   * É recomendável selecionar o namespace de identidade que você acredita ter a maior cobertura no conjunto de dados do evento

1. Crie seus projetos do Workspace para:

   * Detalhe o Nome do público-alvo por página, produto, campanha, dispositivo etc.

   * Compare o público-alvo com o não público-alvo (ou com outro público-alvo) em métricas como sessões, taxa de conversão, receita por pessoa.

1. Use os insights gerados para ajustar as estratégias de otimização de canal (por exemplo, regras de direcionamento, conteúdo ou ajuste de oferta).

#### Considerações de resolução de identidade

| Caso de uso | Pergunta principal de negócios | Consideração da resolução de identidade | Organizações de alta autenticação/namespace único (eventos já com menos de uma ID de pessoa, por exemplo, logon /CRM) | Organizações fragmentadas/com vários namespaces (eventos em ECID + CRM + outros) |
|---------|----------|---------|---------|---------|
| Comportamento do público-alvo no estado atual em detalhes | _&quot;O que o público-alvo X está fazendo no canal Y neste momento?&quot; (páginas, funis, conteúdo, ofertas)_ | Eventos e perfis devem compartilhar um namespace de identidade consistente na conexão do CJA e na configuração da Análise de público-alvo para uma cobertura ideal. | A maioria das atividades já está vinculada a uma ID de logon/CRM, portanto, os públicos-alvo do AEP se associam perfeitamente aos dados comportamentais no CJA. <p>Você tem uma visão clara do que cada público-alvo está fazendo em um determinado canal com o mínimo de lacunas de relatório esperadas.</p> | Mesmo quando unidos a um conjunto de dados compilado, os relatórios ainda serão restritos ao único namespace de identidade escolhido na configuração. <p>Se alguns clientes estiverem em outras IDs, seu comportamento não será incluído, o que pode resultar em uma exibição parcial durante os relatórios.</p> |

### Caso de uso 2

Ajude os profissionais de marketing ou designers de jornadas a entender quais públicos se sobrepõem para que eles possam desduplicar experiências e evitar colisões de ofertas entre campanhas:

* _&quot;Quantas sobreposições existem hoje entre Membros de Fidelidade, Abandonadores de Carrinho e Alta Propensão para Abandono?&quot;_

* _&quot;Quais públicos-alvo têm maior probabilidade de colidir em ofertas promocionais de alto valor esta semana?&quot;_

#### Fluxo de configuração

1. Configure a Análise de público-alvo no CJA para um único namespace de identidade alinhado à ativação do RTCDP/AJO (por exemplo, CRM_ID se as jornadas forem baseadas em pessoas).

   * Isso assimilará automaticamente os dados de associação de público-alvo na conexão escolhida por meio da exportação diária do instantâneo do perfil.

   * Isso pode ser usado para enriquecer uma visualização de dados existente que já capacita os principais relatórios de envolvimento e conversão.

1. Use o modelo pronto para uso Visão geral da análise de público-alvo e as visualizações de sobreposição:

   * Execute interseções de público-alvo e exibições de sobre/subindexação (por exemplo, % de abandonadores de carrinho que também estão no Loyalty Gold).

   * Sobreposições de fatias por dimensões principais (por exemplo, tipo de dispositivo, interesse pelo produto) para entender onde os conflitos são mais importantes.

1. Use os insights para ajustar aspectos críticos, como:

   * Oferecer regras de conflito ou regras de ação de marketing no RTCDP e no AJO.

   * Refinamento de público-alvo (por exemplo, maior rigor nas definições de público-alvo em que a sobreposição é muito alta).

#### Considerações de resolução de identidade

| Caso de uso | Pergunta principal de negócios | Consideração da resolução de identidade | Organizações de alta autenticação/namespace único (eventos já com menos de uma ID de pessoa, por exemplo, logon /CRM) | Organizações fragmentadas/com vários namespaces (eventos em ECID + CRM + outros) |
|---------|----------|---------|---------|---------|
| Sobreposição de público e detecção de colisão | _&quot;Quais públicos-alvo se sobrepõem hoje para que possamos evitar colisões de ofertas?&quot;_ | A sobreposição é calculada somente para públicos-alvo que usam a mesma ID de pessoa e com atividade na conexão do CJA. | Como a maioria das atividades já está vinculada a uma única ID de logon/CRM, espera-se que isso forneça um mapa de sobreposição confiável entre os públicos-alvo. <p>Os gráficos de sobreposição fornecem uma imagem confiável de quais públicos-alvo colidem e onde aplicar supressões ou regras de prioridade.</p> | Se partes da jornada estiverem em outras IDs (por exemplo, navegação anônima somente ECID, IDs da central de atendimento), esses eventos não serão exibidos na análise de sobreposição. <p>As pessoas ainda podem existir em vários namespaces.</p><p>A sobreposição será baseada no namespace de identidade incluído na configuração. Se alguns perfis ainda forem divididos entre IDs, a sobreposição pode reportar colisões verdadeiras.</p> |

### Caso de uso 3

Entenda o comportamento dos clientes que deixaram um público-alvo importante recentemente e o que fizeram ao redor dessa saída, para responder a perguntas como:

* _&quot;Quem acabou de deixar um público-alvo-chave, e o que eles fizeram ao sair?&quot;_

* _&quot;O que aconteceu exatamente antes de sair? (erros, baixo engajamento, mudanças de preço).&quot;_

#### Fluxo de configuração

1. Configure a Análise de público-alvo no CJA para um único namespace de identidade (por exemplo, CRM_ID ou ID de logon) e as visualizações de dados relevantes (Web, aplicativo, CRM etc.).

   * Isso assimila automaticamente os dados de associação de público-alvo na conexão escolhida por meio da exportação diária de instantâneos do perfil.

   * É recomendável selecionar o namespace de identidade que você acha que tem mais cobertura no conjunto de dados do evento.

1. No modelo Análise de público-alvo/Visão geral do público-alvo (corrigido para _ontem_), use:

   * Membros atuais: que ainda está no público

   * Público-alvo encerrado: que saiu ontem

1. Crie seus projetos do Workspace para:

   * Filtre para perfis que saíram do Audience X ontem e observe:

      * O comportamento deles até a saída (últimas sessões, erros, exposição de preço/oferta, mix de canais).

      * Seu comportamento após a saída (eles trocaram de produto, fizeram downgrade e ficaram inativos).

   * Detalhe esse coorte de saída por região, dispositivo, estabilidade, nível de valor para encontrar bolsos de alto impacto.

1. Use os insights para atualizações de jornada e configurações de públicos-alvo de retorno no RTCDP ou no AJO.

#### Considerações de resolução de identidade

| Caso de uso | Pergunta principal de negócios | Consideração da resolução de identidade | Organizações de alta autenticação/namespace único (eventos já com menos de uma ID de pessoa, por exemplo, logon /CRM) | Organizações fragmentadas/com vários namespaces (eventos em ECID + CRM + outros) |
|---------|----------|---------|---------|---------|
| Públicos-alvo encerrados - análise de churn | _&quot;Quem acabou de deixar um público-alvo-chave?&quot;_ <p>_&quot;O que eles fizeram ao sair?&quot;_</p> | A saída do público é rastreada na mesma ID de pessoa usada para a conexão e a configuração do público-alvo. | Saídas medidas em uma ID de logon/CRM estável tendem a refletir a verdadeira mudança de comportamento. <p>Quando alguém deixa um público-alvo com essa ID, geralmente significa uma mudança real (churn, downgrade, inatividade).</p><p>Você pode analisar o comportamento recente deles para ajustar as jornadas e as ofertas vencedoras com confiança.</p> | As saídas só são visíveis onde perfis e eventos compartilham a ID configurada e, portanto, exigirão interpretação cuidadosa.<p>Use coortes encerradas como uma dica ou sinal forte, mas é recomendável fazer a verificação cruzada com outros pontos de dados antes de tomar decisões críticas.</p> |
