---
title: Migração da AppMeasurement ou de tags para o XDM
description: Saiba mais sobre como migrar do AppMeasurement ou de tags para o XDM
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
source-git-commit: db34e721f156b3eb0aab20b2dca57e194c83d6fb
workflow-type: tm+mt
source-wordcount: '2379'
ht-degree: 5%

---

# Migrar de tags para XDM {#upgrade-migration-planner}

{{upgrade-note-step}}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_intro"
>title="Visão geral das migrações"
>abstract="Migre uma implementação de Marcas para o Adobe Experience Platform Web SDK ao atualizar para o Customer Journey Analytics.<br/>Continue com uma migração existente ou inicie uma nova."

<!-- markdownlint-enable MD034 -->

O Planejador de migração fornece um assistente de migração que automatiza a migração de tags para o XDM, incluindo a criação de esquemas. Essas são algumas das tarefas mais complexas e demoradas associadas a uma atualização do Adobe Analytics para o Customer Journey Analytics.

## Implementações compatíveis com o Adobe Analytics

O Planejador de migração é compatível com implementações do Adobe Analytics que usam a extensão do Analytics (tags).

O Planejador de migração não está disponível para implementações do Adobe Analytics que usam o AppMeasurement ou o Experience Platform Web SDK.

## Tarefas de atualização incluídas no Planejador de migração

O Planejador de Migração fornece um assistente de migração que automatiza as seguintes tarefas de atualização complexas e demoradas:

* **Criação do esquema XDM**: cria automaticamente um novo esquema XDM com base nas variáveis do conjunto de relatórios do Adobe Analytics. O Planejador de migração verifica de forma inteligente as variáveis do conjunto de relatórios do Adobe Analytics e, em seguida, usa essas informações para criar os campos necessários no XDM. O esquema XDM resultante inclui somente os campos necessários no esquema do Customer Journey Analytics.

  Como alternativa, você pode apontar para um esquema XDM existente ou criar um esquema XDM do zero.

  +++ Se você optar por criar um esquema XDM do zero, poderá expandir esta seção para obter informações sobre recursos úteis.

  * [Planeje sua arquitetura de esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md){target="_blank"}.

  * [Crie o esquema personalizado desejado na Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}.

    Considere as seguintes opções ao criar seu esquema:

    * Se quiser integrar o Customer Journey Analytics com a RTCDP, habilite a opção **[!UICONTROL Perfil]** no esquema, conforme descrito em [Criar um esquema XDM para usar com o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}. Com essa opção habilitada, quando os dados são assimilados em conjuntos de dados com base nesse esquema, esses dados são mesclados ao Perfil do cliente em tempo real.

    * Se quiser incluir dados de transmissão de mídia, você deve [configurar seu esquema para assimilar e usar dados de transmissão](/help/data-ingestion/streaming.md){target="_blank"}.

    +++

  * **Migração da implementação do Adobe Analytics para a Web SDK**: independentemente de a implementação do Adobe Analytics usar marcas ou JavaScript, o Planejador de Migração o orientará durante a migração para a Experience Platform Web SDK.

    * **Migrar propriedades de marca do AppMeasurement para a Web SDK**:

    * **Migrar uma implementação do JavaScript do AppMeasurement para a biblioteca JavaScript do Web SDK**

  * **Criação de visualizações de dados no Customer Journey Analytics**: cria visualizações de dados automaticamente e as preenche com componentes, com base nos campos de esquema XDM criados.


## Antes de começar

Antes de criar uma migração, verifique se você tem o seguinte:

* Uma implementação de Adobe Analytics compatível (a extensão do Analytics para tags). Consulte [Implementações compatíveis do Adobe Analytics](#supported-adobe-analytics-implementations).

* Acesse a propriedade Tags da Adobe que você deseja migrar, na organização da Experience Cloud na qual você está conectado.

* Acesso ao conjunto de relatórios do Adobe Analytics cujas variáveis você deseja mapear para XDM.

* Permissão para criar esquemas no Adobe Experience Platform.

<!-- Confirm the exact roles and permissions required to use the Migration Planner and to create schemas and Data Views. -->

## Migrar uma implementação do Analytics para o Web SDK

Uma migração passa por três estágios: [!UICONTROL **Auditoria**], [!UICONTROL **Mapeamento**] e [!UICONTROL **Implementação**]. Use as etapas a seguir para criar uma migração e, em seguida, continue com [Validar e implantar uma migração](#validate-and-deploy-a-migration) para concluir cada estágio.

1. No Customer Journey Analytics, abra o [!UICONTROL **Planejador de Migração**].

   <!-- Confirm the exact navigation path to open the Migration Planner in Customer Journey Analytics. -->

1. No Planejador de Migração, na guia [!UICONTROL **Migrações**], selecione [!UICONTROL **Novo**].

   ![A caixa de diálogo Nova migração, na qual você escolhe um tipo de migração e insere um nome de migração.](assets/migration-planner-new-migration.png)

1. Especifique as seguintes informações:

   | Nome do campo | Função |
   | --------- | ---------- |
   | [!UICONTROL **Nome**] | Especifique um nome para esta migração. |
   | [!UICONTROL **Descrição**] | Especifique uma descrição opcional para esta migração. |
   | [!UICONTROL **Propriedade de marcas**] | Selecione a propriedade Tags do Adobe que você deseja migrar. Para obter mais informações, consulte [Propriedades](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/admin/companies-and-properties){target="_blank"} na documentação do Experience Platform. |
   | [!UICONTROL **Biblioteca de marcas**] | Selecione o instantâneo da biblioteca de tags no qual a migração se baseia. O instantâneo determina qual versão da biblioteca de tags é usada. Para obter mais informações, consulte [Visão geral da publicação](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview){target="_blank"} na documentação do Experience Platform. |

1. No campo [!UICONTROL **Nome da migração**], especifique um nome para essa migração e selecione [!UICONTROL **Avançar**].

1. Selecione a propriedade de marca que você deseja migrar e selecione [!UICONTROL **Avançar**].

   Somente as propriedades de tag disponíveis para sua organização da Experience Cloud conectada são exibidas.

1. Selecione o instantâneo da biblioteca de marcas que você deseja migrar e selecione [!UICONTROL **Avançar**].

   O instantâneo determina em qual versão da biblioteca de tags a migração se baseia. Cada instantâneo mostra seu ambiente (como [!UICONTROL **Desenvolvimento**], [!UICONTROL **Preparo**] ou [!UICONTROL **Produção**]).

1. Selecione o conjunto de mapeamento para determinar como as variáveis do Analytics serão mapeadas para campos de esquema XDM.

   Realize uma das seguintes ações:

   * Selecione [!UICONTROL **Criar um novo conjunto de mapeamento**].

   * Selecione um conjunto de mapeamento existente.

     Os conjuntos de mapeamentos criados durante uma migração anterior ou como um conjunto de mapeamentos independente estão disponíveis para seleção.

     A reutilização de um conjunto de mapeamento em várias migrações aplica os mesmos mapeamentos a cada migração.

1. Selecione [!UICONTROL **Criar migração**].

1. Continue com a seguinte seção, [Validar e implantar uma migração](#validate-and-deploy-a-migration).

## Validar e implantar uma migração

Após criar uma migração, abra-a para concluir seus três estágios: [!UICONTROL **Auditoria**], [!UICONTROL **Mapeamento**] e [!UICONTROL **Implementação**].

1. No Planejador de migração, selecione a guia [!UICONTROL **Migrações**].

1. Ao lado da migração que você deseja validar, selecione [!UICONTROL **Abrir**].

   A página de visão geral da migração mostra as três etapas a serem concluídas, juntamente com um resumo da migração e seus artefatos.

   ![A página de visão geral da migração com os cartões de estágio de Auditoria, Mapeamento e Implementação.](assets/migration-planner-overview.png)

1. Conclua o estágio [!UICONTROL **Auditoria**]:

   1. No cartão de auditoria ([!UICONTROL **Auditoria de extensão de tag**] ou [!UICONTROL **Auditoria do JavaScript**], dependendo do tipo de migração), selecione [!UICONTROL **Iniciar auditoria**] para examinar as regras e os elementos de dados incluídos na migração.

      ![A página de auditoria, onde você seleciona regras e elementos de dados e resolve qualquer descoberta.](assets/migration-planner-audit.png)

   1. Nas guias [!UICONTROL **Regras**] e [!UICONTROL **Elementos de dados**], selecione os itens a serem incluídos na migração.

      As regras marcadas [!UICONTROL **Na biblioteca**] são publicadas. As regras marcadas como [!UICONTROL **Propriedade somente**] existem na propriedade, mas não fazem parte da biblioteca selecionada.

   1. Revise todas as conclusões sobre as regras selecionadas. Para cada descoberta, selecione [!UICONTROL **Revisar**] para resolvê-la ou [!UICONTROL **Ignorar**] para deixá-la sem endereço.

      Por exemplo, quando duas regras têm condições e eventos idênticos, a descoberta [!UICONTROL **Duplicar eventos de regra**] permite que você mantenha uma regra e remova a outra ou selecione [!UICONTROL **Não fazer nada**] para confirmar a descoberta sem fazer uma alteração.

      Resolver descobertas é opcional antes de continuar. Para obter a lista completa de tipos de conclusões e como resolver cada um, consulte [Revisar e resolver conclusões de auditoria](#review-and-resolve-audit-findings).

   1. Selecione [!UICONTROL **Salvar e continuar**].

1. Conclua o estágio [!UICONTROL **Mapeamento**]:

   1. No cartão [!UICONTROL **Analytics → XDM mapping**], selecione [!UICONTROL **Criar novo mapeamento**].

   1. Escolha se deseja criar um novo esquema com base nas variáveis do Analytics ou mapear com base em um esquema do Experience Platform existente, em seguida, siga as instruções para selecionar o conjunto de relatórios, mapear campos e revisar o esquema.

      Para obter etapas detalhadas, consulte [Mapear variáveis do Analytics para campos XDM](#map-analytics-variables-to-xdm-fields). Para reutilizar um conjunto de mapeamentos em migrações, consulte [Criar e gerenciar conjuntos de mapeamentos](#create-and-manage-mapping-sets).

1. Conclua o estágio de [!UICONTROL **Implementação**]:

   1. No cartão [!UICONTROL **Gerar implementação do Web SDK**], use os resultados de auditoria e mapeamento para gerar o pacote de implementação do Web SDK e implante-o no site.

      Para obter etapas detalhadas, consulte [Gerar e implantar a implementação do Web SDK](#generate-and-deploy-the-web-sdk-implementation).


## Revisar e resolver conclusões de auditoria

Durante o estágio [!UICONTROL **Auditoria**], o Planejador de Migração sinaliza as descobertas das regras selecionadas. Resolver os achados é opcional antes de continuar, mas resolvê-los ajuda a garantir uma migração limpa.

Para cada descoberta, selecione [!UICONTROL **Revisar**] para abrir a descoberta e escolher como resolvê-la, ou selecione [!UICONTROL **Ignorar**] para deixá-la sem endereço.

O Planejador de migração pode sinalizar os seguintes tipos de descobertas:

* [!UICONTROL **Eventos de regra duplicados**]: duas ou mais regras têm eventos e condições idênticos. Ao revisar a descoberta, compare as regras principais e duplicadas, mantenha uma regra e remova a outra, ou selecione [!UICONTROL **Não fazer nada**] para confirmar a descoberta sem fazer uma alteração.

* [!UICONTROL **Lógica de regra duplicada**]: as regras compartilham a mesma lógica. <!-- Confirm the exact remediation options for this finding type. -->

* [!UICONTROL **Ações de regra desordenadas**]: as ações de uma regra são executadas em uma ordem que pode causar problemas durante a migração. <!-- Confirm the exact remediation options for this finding type. -->

Se uma descoberta não tiver correção guiada, o Planejador de Migração exibirá [!UICONTROL **Nenhum detalhe de correção disponível**]. Revise a descoberta manualmente e descarte-a quando for resolvida.

O painel [!UICONTROL **Descobertas**] mostra quantas descobertas você abordou e quantas ainda estão abertas. Quando terminar, selecione [!UICONTROL **Salvar e continuar**].

## Mapear variáveis do Analytics para campos XDM

Durante o estágio [!UICONTROL **Mapping**], mapeie as variáveis do Analytics para campos XDM e gere ou selecione o esquema de destino. No cartão [!UICONTROL **Analytics → XDM mapping**], selecione [!UICONTROL **Criar novo mapeamento**] e conclua as seguintes etapas:

1. **Opção de esquema**: escolha se deseja criar um novo esquema com base nas variáveis do Analytics ou mapear com base em um esquema do Experience Platform existente.

1. **Conjunto de relatórios**: selecione o conjunto de relatórios do Analytics cujas variáveis você deseja mapear.

1. **Esquema do Experience Platform**: crie o esquema XDM de destino ou selecione o esquema existente para mapear.

1. **Mapeamento manual**: revise os mapeamentos automáticos e ajuste como as variáveis individuais do Analytics são mapeadas para campos XDM.

1. **Revisar esquema**: revise os mapeamentos e o esquema resultantes e, em seguida, confirme.

<!-- The XDM mapping editor was not captured in the walkthrough. Confirm the exact steps, controls, and options on each step (Schema choice, Report suite, Experience Platform schema, Manual mapping, Review schema). -->

Para reutilizar um conjunto de mapeamentos em migrações, consulte [Criar e gerenciar conjuntos de mapeamentos](#create-and-manage-mapping-sets).

## Comparar saídas de migração

Use [!UICONTROL **Comparar saídas**] na página de visão geral da migração para validar sua migração antes de implantá-la.

<!-- The Compare outputs screen was not captured in the walkthrough. Confirm what the comparison shows (for example, AppMeasurement output compared with the Web SDK / XDM output) and how to interpret the results. -->

## Gerar e implantar a implementação do Web SDK

Durante o estágio [!UICONTROL **Implementação**], o Planejador de Migração usa seus resultados de auditoria e mapeamento para criar o pacote de implementação do Web SDK.

1. Na página de visão geral da migração, no cartão [!UICONTROL **Gerar implementação do Web SDK**], gere o pacote de implementação.

1. Crie a biblioteca de marcas para a migração selecionando [!UICONTROL **Criar biblioteca de marcas**].

1. Configure a implantação dupla e implante a implementação do Web SDK no site.

<!-- This stage was not captured in the walkthrough. Confirm the exact steps for generating the package, configuring the dual deployment, building the tag library, and deploying to the site. -->

Para os artefatos produzidos por esse estágio, consulte [Exportar artefatos de migração](#export-migration-artifacts).

## Exportar artefatos de migração

A página de visão geral da migração fornece os artefatos gerados pelo Planejador de migração. Você pode baixar artefatos individuais do painel [!UICONTROL **Artefatos do projeto**] ou selecionar [!UICONTROL **Exportar tudo**] para exportar tudo de uma vez.

Os seguintes artefatos estão disponíveis:

* [!UICONTROL **Mapping JSON**]: o mapeamento entre as variáveis do Analytics e os campos XDM.

* [!UICONTROL **Esquema XDM (JSON)**]: o esquema XDM de destino criado para a migração.

* [!UICONTROL **Biblioteca de desenvolvimento de marcas**]: a biblioteca de marcas criada para a implementação do Web SDK.

Cada artefato mostra seu status, como [!UICONTROL **Pronto**] ou [!UICONTROL **Não criado**]. Um artefato está disponível para download depois de ser gerado no estágio correspondente.

## Criar e gerenciar conjuntos de mapeamento {#mapping-sets}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_sets"
>title="Conjuntos de mapeamento"
>abstract="Os conjuntos de mapeamento determinam como as variáveis do Analytics são mapeadas para campos XDM.<br/>Crie um novo conjunto de mapeamento ou escolha um existente para aplicar os mesmos mapeamentos em várias migrações. Você também pode fazer referência a conjuntos de mapeamento em outras tarefas de migração."

<!-- markdownlint-enable MD034 -->

Os conjuntos de mapeamento determinam como as variáveis do Analytics são mapeadas para campos de esquema XDM.

Você pode criar um novo conjunto de mapeamento [durante o processo de migração](#migrate-an-analytics-implementation-to-the-web-sdk). Ou você pode criar um conjunto de mapeamento independente para usar com uma migração futura ou com outras tarefas de migração.

### Criar um conjunto de mapeamento independente {#xdm-mapping}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_schema"
>title="Escolher um esquema"
>abstract="Os conjuntos de mapeamento determinam como as variáveis do Analytics são mapeadas para campos XDM.<br/>Crie um novo conjunto de mapeamento ou escolha um existente para aplicar os mesmos mapeamentos em várias migrações. Você também pode fazer referência a conjuntos de mapeamento em outras tarefas de migração."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_field_group"
>title="Preferência de grupo de campos"
>abstract="Escolha grupos de campos padrão para usar os grupos de campos do Adobe publicados quando possível. Isso promove a consistência máxima e retorna aos campos de locatário personalizados quando nenhum campo padrão está disponível.<br/>Escolha grupos de campos personalizados para usar campos personalizados de namespace de locatário quando possível. Isso promove a máxima flexibilidade."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_lookback"
>title="Período de pesquisa"
>abstract="Controla a distância a ser observada ao determinar quais variáveis estão recebendo dados ativamente. As variáveis que incluem dados dentro do período de lookback são incluídas no esquema."

<!-- markdownlint-enable MD034 -->

1. No Planejador de migração, selecione a guia [!UICONTROL **Conjuntos de mapeamento**].

1. Selecione [!UICONTROL **Novo conjunto de mapeamento**].

1. No campo [!UICONTROL **Nome**], digite um nome descritivo para poder identificar esse conjunto de mapeamento posteriormente e selecione [!UICONTROL **Avançar**].

1. No menu [!UICONTROL **Conjunto de relatórios**], selecione o conjunto de relatórios cujas variáveis você deseja mapear para campos XDM e selecione [!UICONTROL **Próximo**].

1. Na [!UICONTROL **seção Escolher um esquema para o mapeamento XDM**], escolha se deseja criar um novo esquema com base nas variáveis do Analytics ou mapear com base em um esquema do Experience Platform existente.

   Optar por criar um novo esquema o orienta por meio do processo de mapeamento das variáveis do Analytics para campos XDM. Optar por usar um esquema existente permite mapear manualmente as variáveis a um esquema pré-registrado no registro do esquema do Experience Platform.

   <!-- Screenshot pending: the XDM mapping editor (Create new mapping) was not available for capture in the walkthrough. -->

   * [!UICONTROL **Criar um novo esquema**]: execute as verificações Básicas e Avançadas para sugerir automaticamente mapeamentos de campos XDM para suas variáveis do Analytics e, em seguida, revise o esquema resultante.

   * [!UICONTROL **Usar um esquema existente**]: procure e selecione um esquema que já esteja registrado no registro do esquema do Experience Platform e arraste manualmente as variáveis do Analytics para os campos XDM.

1. No menu suspenso [!UICONTROL **Preferência de grupo de campos**], escolha como você deseja organizar as variáveis personalizadas em grupos de campos:

   * [!UICONTROL **Padrão primeiro**]: usar grupos de campos do Adobe publicados quando possível. Isso promove a consistência máxima e retorna aos campos de locatário personalizados quando nenhum campo padrão está disponível.

   * [!UICONTROL **Personalizar primeiro**]: usar campos personalizados de namespace do locatário quando possível. Isso promove a máxima flexibilidade.

   <!-- * [!UICONTROL **Ask each time**]: Prompt for each signal so you can decide individually. -->

1. No campo [!UICONTROL **Período de lookback**], selecione o período retroativo a ser observado ao determinar quais variáveis estão recebendo dados ativamente. As variáveis que incluem dados dentro do período de lookback são incluídas no esquema.

1. Selecione [!UICONTROL **Criar conjunto de mapeamento**].

O novo conjunto de mapeamento aparece na guia [!UICONTROL **Conjuntos de mapeamento**], onde você pode abri-lo para examinar seus detalhes.

### Exportar um conjunto de mapeamento

É possível exportar um conjunto de mapeamento para usá-lo com outras tarefas de migração ou em outras ferramentas.

<!-- Confirm where the export control lives (the Mapping sets list exposes only an Open action) and the export format (for example, JSON). -->

### Conjuntos de mapeamento de publicação e versão

Cada conjunto de mapeamento tem um status e uma versão. Na guia [!UICONTROL **Conjuntos de mapeamento**], um conjunto de mapeamento pode aparecer como:

* [!UICONTROL **rascunho**]: o conjunto de mapeamento ainda está sendo editado.

* [!UICONTROL **publicado**]: o conjunto de mapeamento foi finalizado.

* [!UICONTROL **na migração**]: o conjunto de mapeamento está associado a uma ou mais migrações.

<!-- Confirm how to publish a mapping set, how versions are created (v1, v2, v3), and what "bindings" represent. -->

### Editar um conjunto de mapeamento <!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be edited after creation and where the edit control lives (the Mapping sets list exposes only an Open action). -->

### Excluir um conjunto de mapeamento <!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be deleted, and whether deletion is blocked while the set is in use by a migration. -->

## Gerenciar migrações existentes

### Encontrar e controlar suas migrações

A guia [!UICONTROL **Migrações**] lista suas migrações e seu progresso. Use-o para localizar uma migração para continuar ou para verificar o status das migrações em andamento.

* **Pesquisa**: use o campo de pesquisa para localizar uma migração por nome ou propriedade.

* **Filtro**: filtre a lista por tipo de migração ou por status.

* **Rastrear progresso**: cada migração mostra seu progresso através dos três estágios (por exemplo, 1/3) e um status geral:

  * [!UICONTROL **Não iniciado**]: a migração foi criada, mas nenhum estágio foi concluído.

  * [!UICONTROL **Em andamento**]: pelo menos um estágio foi concluído.

  * [!UICONTROL **Concluído**]: todos os três estágios estão concluídos.

Para continuar a migração, selecione [!UICONTROL **Abrir**] próximo a ela.

<!-- The row actions ("...") menu was not captured in the walkthrough. Confirm which actions it contains (for example, rename, duplicate, or delete a migration). -->

