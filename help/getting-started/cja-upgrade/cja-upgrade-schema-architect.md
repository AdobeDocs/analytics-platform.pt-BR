---
title: Projete o seu esquema para uso com o Customer Journey Analytics
description: Saiba como projetar um esquema XDM que desbloqueia a flexibilidade do Customer Journey Analytics, ao mesmo tempo que oferece suporte a um caminho de migração prático do Adobe Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 3dc53d6955eab3048ebf8a7c9d232b4b5739c6bd
workflow-type: tm+mt
source-wordcount: '1455'
ht-degree: 9%

---

# Projete o seu esquema para uso com o Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Projetar um esquema"
>abstract="Discuta sobre os requisitos da coleção de dados em sua organização e determine como deseja criar um esquema para uso na Adobe Experience Platform. Essa etapa aparece porque você deseja usar o processo recomendado de utilização de um esquema personalizado para sua organização. Executar corretamente essa etapa é essencial, pois ter um esquema ao qual todas as equipes em sua organização se alinham facilita muito a ingestão de dados.<br><br>O tempo estimado para alinhar todas as partes relevantes em sua organização a um esquema unificado é de 1 a 2 meses. Esse intervalo de tempo depende muito do número de equipes que é necessário coordenar e do número de dimensões e métricas às quais elas devem se alinhar."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

A Adobe recomenda criar um esquema personalizado [Experience Data Model](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/home) (XDM) para o Customer Journey Analytics ao implementar a [Coleção de dados do Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/home). A criação desse esquema geralmente é feita antes de qualquer alteração de implementação ou código ser tocado. Um esquema personalizado permite criar um contrato de dados conciso e específico da organização sem herdar restrições da Adobe Analytics ou gerenciar milhares de campos não utilizados. Consulte [Escolher seu esquema para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) para saber mais sobre os tipos de esquemas disponíveis para sua organização.

Os esquemas são versões aprimoradas de como você deseja que seus dados sejam estruturados a longo prazo. As alterações nos esquemas são caras porque afetam a coleta de dados, a validação e os serviços downstream. Você pode adicionar a esquemas ao longo do tempo, conforme os requisitos de negócios permitem; no entanto, os campos de esquemas não podem ser removidos depois que os dados começam a fluir para eles.

## Comparar esquemas a visualizações de dados

O pipeline de dados do Customer Journey Analytics contém áreas separadas para coleta e interpretação de dados. Ao atualizar do Adobe Analytics, uma etapa errada comum é tentar recriar props e eVars com seus comportamentos no XDM. Em vez disso, use o Web SDK para coletar os dados e usar [Visualizações de dados](/help/data-views/data-views.md) para determinar como esses dados são interpretados nos relatórios.

| Camada | Finalidade principal | O que pertence a | O que não pertence a |
|---|---|---|---|
| **Esquema XDM** | Definir a estrutura durável e o significado dos dados coletados | Forma de evento e entidade, significado de campo, relacionamentos, valores permitidos, reutilização entre canais | &quot;Slots&quot; numerados (eVar1/prop1), lógica de atribuição/persistência, soluções alternativas específicas para relatórios |
| **Visualizações de dados** | Definir como os dados coletados se comportam na análise | Configurações de componentes, comportamento de atribuição e persistência, campos derivados, métricas filtradas e métricas calculadas | Significado fundamental dos campos; esse significado deve ser estável no esquema |

## Comparar esquemas com a coleção de dados da Adobe Analytics

O Experience Data Model que a Customer Journey Analytics usa oferece muito mais flexibilidade do que a maioria das outras soluções do Analytics (incluindo o Adobe Analytics). Estabelecer um esquema sólido é a oportunidade de sua organização de evitar a transferência de restrições existentes em outros produtos do Analytics.

| Hábito comum do Adobe Analytics | Melhor abordagem no XDM + CJA |
|---|---|
| Criando slots numerados (`eVar1`-`eVar250`, `prop1`-`prop75`) | Criar campos com significado estável (por exemplo, `search.term`, `content.category`, `user.membershipTier`) e reutilizá-los consistentemente |
| Persistência/alocação/expiração de codificação no modelo de dados | Capture fatos duráveis no esquema; aplique o comportamento de atribuição e persistência no nível de visualização de dados |
| Duplicação do mesmo valor em várias variáveis para alcançar comportamentos de relatório | Armazene o valor uma vez e crie vários componentes (dimensões/métricas) a partir dele nas visualizações de dados |
| Criar um &quot;campo de métrica&quot; exclusivo para cada contagem que você deseja | Capture os fatos certos uma vez (geralmente como enums/boolianos/strings) e defina métricas como contagens filtradas nas visualizações de dados |
| Criação de variáveis para &quot;pré-resolver&quot; relatórios | Projete seu esquema para capturar fatos de maneira confiável e usar visualizações de dados para resolver semânticas de relatórios |

## Estabelecimento de um esquema usando atributos comuns

Um esquema unificado em vários canais é possível ao padronizar um conjunto de atributos reutilizáveis que aparecem em muitos eventos. Alguns exemplos incluem:

* **Contexto de experiência:** nome do site/aplicativo, ambiente, localidade, canal, marca
* **Contexto de Jornada:** identificadores de campanha, contexto de referência, identificadores de experimento
* **Estado do usuário:** status de logon, camada de associação, tipo de conta
* **Detalhes da interação:** nome/tipo da interação, região da interface do usuário, rótulo do elemento, categoria do erro

A chave é padronizar o que o campo representa, independentemente do canal. Evite modelar o mesmo conceito de forma diferente entre canais, a menos que realmente represente conceitos diferentes. Por exemplo, convém evitar campos de esquema separados para IDs de campanha da Web e IDs de campanha para dispositivos móveis. Campos de esquema separados dificultam o estabelecimento de retorno entre canais nos dados de gastos de anúncios. Se uma diferenciação for necessária nos relatórios, você poderá segmentar por canal ou concatenar vários campos para fornecer essa distinção. O mesmo campo de esquema pode ser usado em qualquer número de dimensões ou métricas.

Uma maneira prática de oferecer suporte a vários canais, mantendo uma única estratégia de esquema, é usar um padrão **núcleo + extensões**:

* **Núcleo:** campos que se aplicam amplamente entre canais e equipes
* **Extensões:** grupos de campos específicos de canal ou domínio que se aplicam somente onde necessário (interação na Web, comércio, ciclo de vida móvel, especificações do lado do servidor)

Esse padrão suporta uma única estratégia de esquema organizacional sem forçar cada equipe a preencher campos que não se aplicam ao canal.

## Preferir grupos de campos padrão onde eles se encaixem

A Adobe recomenda usar grupos de campos padronizados onde correspondam às suas necessidades e estender com campos personalizados para conceitos específicos da organização.

Os grupos de campos padrão normalmente ajudam a:

* Reduzir ambiguidade usando semântica de campo conhecida
* Alinhar equipes mais facilmente
* Oferece suporte à interoperabilidade entre aplicativos Adobe Experience Platform

Os campos personalizados são apropriados quando:

* Sua organização tem conceitos que não são mapeados corretamente para campos padrão
* Você precisa de atributos adicionais para atender aos requisitos de relatórios, governança ou ativação
* Você deseja representar uma taxonomia específica de negócios (por exemplo, categorias internas de conteúdo)

## Decidir onde fica o &quot;significado da métrica&quot;

No Adobe Analytics, muitas equipes tratam a variável `events` como para onde as métricas vão. No Customer Journey Analytics, você pode modelar métricas de várias maneiras, dependendo do que precisa contar e como deseja interpretá-lo.

Ao arquitetar um esquema, observe os fatos. Por exemplo, `error.type = "validation"`, `user.isLoggedIn = true`, `checkout.step = "shipping"`. Defina métricas na visualização de dados como contagens e contagens filtradas sobre esses fatos. Por exemplo:

* `checkout.step` (enum/cadeia de caracteres) pode ligar:
   * &quot;Check-out: etapa de envio atingida&quot; (contagem em que `checkout.step == "shipping"`)
   * &quot;Check-out: etapa de pagamento atingida&quot;
* `error.type` (enum/cadeia de caracteres) pode ligar:
   * &quot;Erros de validação&quot;
   * &quot;Erros de autorização&quot;
* `user.isLoggedIn` (booleano) pode ligar:
   * &quot;Sessões autenticadas&quot;
   * &quot;Conversões autenticadas&quot;

>[!TIP]
>
>Ao decidir se algo deve ser um campo dedicado em vez de um campo derivado posteriormente, prefira capturar o fato durável no esquema se ele for amplamente útil e estável. Você pode usar campos derivados para corrigir ou remodelar dados após a coleção.

## Manutenção da paridade com o Adobe Analytics durante a transição sem a bagagem do esquema

Algumas organizações precisam continuar os relatórios do Adobe Analytics ao atualizar para o Customer Journey Analytics. Você pode manter a paridade sem introduzir artefatos específicos do Analytics no design do esquema de longo prazo usando a seguinte abordagem:

1. **Use caminhos de campo XDM reconhecidos e mapeados automaticamente pela Adobe Analytics:** Quando você envia campos XDM reconhecidos pela Edge Network para a Adobe Analytics, eles são [mapeados automaticamente](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/aep-edge/xdm-var-mapping) sem configuração extra.
1. **Use campos XDM personalizados para conceitos específicos da organização:** Todos os campos XDM que não são mapeados automaticamente para uma variável do Analytics são encaminhados como [Variáveis de dados de contexto](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/vars/page-vars/contextdata) no Adobe Analytics.
1. **Use as regras de processamento do Adobe Analytics para mapear essas variáveis de dados de contexto como props/eVars:** [As regras de processamento](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/processing-rules/pr-overview) finalmente permitem mapear qualquer campo XDM personalizado em qualquer eVar ou prop. Esse conceito é compatível com relatórios de paridade no Adobe Analytics, mantendo seu esquema limpo e centralizado no Customer Journey Analytics.

## Identificar participantes e definir propriedade

O design do esquema é bem-sucedido quando o significado do campo é acordado e mantido. Embora as estruturas organizacionais variem, as seguintes funções geralmente participam:

* **Administrador/analista do Analytics**: define perguntas sobre relatórios, valida se os campos representam conceitos significativos e revisa a semântica da análise nas visualizações de dados.
* **Desenvolvedor/proprietário da implementação**: garante que os campos possam ser coletados de forma confiável usando o Web SDK e se alinhem à instrumentação da camada de dados/aplicativo.
* **Engenheiro/arquiteto de dados**: garante a consistência do esquema, a reutilização entre domínios e a compatibilidade com serviços downstream.
* **Parte interessada de privacidade/governança**: analisa a minimização de dados, as expectativas de consentimento e as restrições de uso de dados.

Defina um proprietário claro para alterações no esquema. Um esquema estável com controle disciplinado de alterações impede a quebra de downstream e reduz o retrabalho. Considere usar um fluxo de trabalho ou ferramenta de governança de rastreamento para democratizar solicitações e gerenciar o controle de alterações ao longo do tempo.

## Considerações de privacidade e governança

O design do esquema deve refletir as expectativas de privacidade e governança, de acordo com as políticas de privacidade da sua organização. Considere os seguintes pontos ao arquitetar o esquema:

* Colete somente o que for necessário para oferecer suporte a casos de uso definidos.
* Garanta que os requisitos de consentimento e uso de dados sejam refletidos em sua estratégia de coleta. Consulte [Usar o Web SDK para processar dados de consentimento do cliente](https://experienceleague.adobe.com/pt-br/docs/experience-platform/landing/governance-privacy-security/consent/sdk) para obter mais informações.
* Considere como os campos confidenciais são rotulados e controlados nas ferramentas de governança do Adobe Experience Platform. Consulte [Adobe Customer Journey Analytics e governança de dados](/help/privacy/privacy-overview.md) para obter mais informações.

## Próximas etapas

Depois de estabelecer e concordar com uma arquitetura de esquema, você pode começar a criá-la no Adobe Experience Platform. Consulte [Criar um esquema personalizado para usar com o Customer Journey Analytics](cja-upgrade-schema-create.md) para obter mais informações.
