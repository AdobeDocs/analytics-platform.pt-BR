---
title: Criar e publicar públicos-alvo
description: Saiba como publicar públicos-alvo do Customer Journey Analytics
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '2368'
ht-degree: 96%

---

# Criar e publicar públicos-alvo {#create-and-publish-audiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_refreshfrequency"
>title="Frequência de atualização"
>abstract="Veja a frequência com que a associação de um público-alvo é reavaliada.<br/>Públicos-alvo únicos são avaliados apenas uma vez."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_audiencelimit"
>title="Limite de público-alvo"
>abstract="As atualizações de públicos-alvo são limitadas com base na frequência com que são atualizadas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_refreshlookbackwindow"
>title="Atualizar janela de retrospectiva"
>abstract="Defina o número de dias da retrospectiva, a partir de hoje, com base na qual o público-alvo será avaliado."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_audiencesizelimit"
>title="Limite de tamanho do público-alvo"
>abstract="O público-alvo não pode exceder um tamanho de 20 milhões de membros."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_namespacesincluded"
>title="Namespaces incluídos"
>abstract="As identidades nesse público-alvo são compostas pelos namespaces abaixo."

<!-- markdownlint-enable MD034 -->




Este tópico discute como criar e publicar públicos-alvo identificados no Customer Journey Analytics no [Perfil do cliente em tempo real](https://experienceleague.adobe.com/pt-br/docs/experience-platform/profile/home) na Adobe Experience Platform para segmentação e personalização de clientes.

Leia esta [visão geral](/help/components/audiences/audiences-overview.md) para se familiarizar com o conceito de públicos-alvo do Customer Journey Analytics.

## Criar e publicar um público-alvo {#create}

1. Para criar e publicar um público-alvo, siga um destes procedimentos:

   | Método de criação | Detalhes |
   | --- | --- |
   | Na interface de **[!UICONTROL Públicos-alvo]** | Selecione **[!UICONTROL Componentes]** > **[!UICONTROL Públicos-alvo]** no menu principal do Customer Journey Analytics. A interface Públicos-alvo é exibida. Selecione **[!UICONTROL Criar público-alvo]** para abrir o [!UICONTROL Construtor de públicos-alvo]. |
   | De uma visualização no Analysis Workspace | Muitas visualizações no Analysis Workspace permitem criar um público-alvo usando o menu de contexto. Por exemplo, você pode selecionar **[!UICONTROL Criar público-alvo]** no menu de contexto de um item em uma [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ou em um nó na [Tela de jornada](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).<p>Usar esse método preenche previamente o segmento no construtor com a dimensão ou item de dimensão que você selecionou.</p><p>As visualizações a seguir permitem criar um público-alvo usando o menu do botão direito do mouse:</p><ul><li>[Tabela de coorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)</li><li>[Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)</li><li>[Fluxo](/help/analysis-workspace/visualizations/c-flow/flow.md)</li><li>[Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)</li><li>[Tela da jornada](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)</li><li>[Venn](/help/analysis-workspace/visualizations/venn.md)</li></ul><p>**Observação:** públicos-alvo não podem incluir métricas calculadas. Se você tentar criar um público-alvo que contenha uma métrica calculada, ela não será incluída na definição do público-alvo.</p> |
   | Na interface de criação e edição de segmentos | Marque a caixa que diz **[!UICONTROL Criar um público-alvo a partir deste segmento]**. Usar esse método preenche previamente o segmento. Consulte [Criar segmentos](/help/components/segments/seg-create.md) para obter mais informações. |

   {style="table-layout:auto"}

1. Crie o público-alvo usando o [Construtor de público-alvo](#audience-builder).

1. Interprete os dados usando o painel [Visualização de data](#data-preview).

1. Selecione **[!UICONTROL [!UICONTROL Exibir IDs de exemplo]]** para exibir uma amostra de IDs neste público-alvo. Na caixa de diálogo **[!UICONTROL IDs de amostra]**, você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) [!UICONTROL *Pesquisar IDs de amostra*] para procurar IDs de exemplo.

1. Verifique novamente a configuração do público-alvo e clique em **[!UICONTROL Publicar]**.
Você receberá uma mensagem de confirmação de que o público-alvo foi publicado. Demora apenas um ou dois minutos para esse público-alvo aparecer na Experience Platform. 

1. Selecione **[!UICONTROL Exibir público-alvo na AEP]** na mesma mensagem e você será levado para a [Interface do segmento](https://experienceleague.adobe.com/pt-br/docs/experience-platform/segmentation/ui/overview) na Adobe Experience Platform. Veja mais informações abaixo.

## Construtor de público-alvo

Defina essas configurações para definir ou atualizar seu público-alvo.

![Captura de tela de como criar um público-alvo mostrando as configurações descritas na próxima seção.](assets/create-audience.png)

| Configuração | Descrição |
| --- | --- |
| ![Dados](/help/assets/icons/Data.svg) | Selecione uma exibição de dados para usar na criação do público-alvo. |
| **[!UICONTROL Nome]** | O nome do público-alvo. Por exemplo, `Really Interested in Potential Car Buyers` |
| **[!UICONTROL Tags]** | Todas as tags que você deseja atribuir ao público-alvo para fins organizacionais. É possível selecionar uma ou mais tags pré-existentes ou inserir uma nova. |
| **[!UICONTROL Descrição]** | Uma descrição do público-alvo, para diferenciá-lo dos demais. Por exemplo, `Build an audience of really interested potential car buyers` |
| **[!UICONTROL Frequência de atualização]** | A frequência na qual você deseja atualizar o público-alvo.<p/>Você pode alternar entre <ul><li>Público-alvo **[!UICONTROL único]**: um público-alvo (padrão) que não precisa de atualização. Por exemplo, essa opção pode ser útil para campanhas específicas e únicas.<br/>É necessário especificar um **[!UICONTROL Intervalo de datas único]**. Você pode usar o ![Calendário](/help/assets/icons/Calendar.svg) para inserir um intervalo de datas.</li><li>Um público-alvo atualizado. Você pode selecionar entre as opções a seguir:<ul><li>**[!UICONTROL A cada 4 horas]**: um público-alvo que é atualizado a cada 4 horas.</li><li>**[!UICONTROL Diariamente]**: um público-alvo que é atualizado diariamente</li><li>**[!UICONTROL Semanalmente]**: um público-alvo que é atualizado semanalmente.</li><li>**[!UICONTROL Mensal]**: um público-alvo que é atualizado mensalmente</li></ul></li>Para atualizar públicos-alvo, é necessário especificar:<ul><li>**[!UICONTROL Atualizar janela de retrospectiva]**. Defina o número de dias da retrospectiva, a partir de hoje, com base na qual o público-alvo será avaliado. Você pode selecionar entre opções ou definir um Tempo personalizado. O máximo é de 90 dias.</li><li>**[!UICONTROL Data de expiração]**: define quando o público-alvo para de atualizar. Você pode usar o ![Calendário](/help/assets/icons/Calendar.svg) para selecionar uma data. O padrão é 1 ano a partir da data de criação. Públicos-alvo que expiram são tratados de forma semelhante aos relatórios agendados que expiram. O administrador recebe um email um mês antes de o público-alvo expirar.</li></ul> Observe que há um limite de 75 a 150 atualizações de público-alvo, dependendo dos seus direitos do Customer Journey Analytics.</li></ul> |
| **[!UICONTROL Filtro]** | Os filtros são a principal entrada para o público. Arraste e solte um ou mais segmentos do painel ![Segmentação](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmento]** à esquerda para a área Segmento. É possível usar a opção ![Pesquisa](/help/assets/icons/Search.svg) [!UICONTROL *Pesquisar segmentos*] para pesquisar segmentos. Você pode adicionar até 20 segmentos. Os segmentos podem ser unidos com operadores **[!UICONTROL E]** ou **[!UICONTROL Ou]**.<p>Ao criar um público-alvo a partir de uma visualização no Analysis Workspace (como uma tabela de forma livre ou uma tela de jornada), todos os segmentos aplicados ao painel ou à coluna são preservados. É possível remover qualquer segmento aplicado automaticamente.</p> |
| **[!UICONTROL Visualização de dados]** | Selecione ![Informações](/help/assets/icons/Info.svg) para mostrar ou ocultar a [Visualização de dados](#data-preview) para o intervalo de datas selecionado. |

## Pré-visualização de dados

O painel Visualização de dados fornece as seguintes informações.

| Elemento | Descrição |
| --- | --- |
| **[!UICONTROL Total de pessoas]** | Um número resumido do número total de pessoas neste público-alvo. O tamanho máximo é de 20 milhões de pessoas. Se o público-alvo exceder 20 milhões de pessoas, você deverá reduzir o tamanho do público-alvo antes de publicá-lo. |
| **[!UICONTROL Limite de tamanho do público]** | Visualização para mostrar a distância que o público-alvo está do limite de 20 milhões. |
| **[!UICONTROL Retorno estimado do público]** | Você pode usar esse valor para redirecionar as pessoas nesse público-alvo que retornam ao seu site, aplicativo móvel ou outro canal.<p>Você pode selecionar o intervalo de tempo (**[!UICONTROL Próximos 7 dias]**, **[!UICONTROL Próximas 2 semanas]** ou **[!UICONTROL Próximo mês]**) para o número estimado de clientes que podem retornar. |
| **[!UICONTROL Estimativa de retorno]** | Esse número fornece uma estimativa do número de clientes recorrentes durante o intervalo de tempo selecionado. Esse número é previsto usando a taxa de churn histórica para esse público-alvo. |
| **[!UICONTROL Visualizar métricas]** | É possível selecionar uma métrica específica para ver como os dados dessa métrica se baseiam no público-alvo definido.  Cada métrica de Visualização exibe um total para a métrica com base no público-alvo e uma porcentagem da métrica com base no público-alvo do total geral da métrica, conforme definido pela visualização de dados. Por exemplo, 381 pessoas (a métrica selecionada) são o resultado da definição do público-alvo, que é 5% do total de pessoas disponíveis na visualização de dados. Você pode selecionar qualquer métrica disponível na visualização de dados. |
| **[!UICONTROL Namespaces incluídos]** | Os namespaces específicos que estão associados às pessoas no seu público-alvo. Os exemplos incluem ECID, CRM ID, endereços de email, etc. |
| **[!UICONTROL Sandbox]** | A [sandbox da Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sandbox/home) em que esse público-alvo está. Ao publicar esse público-alvo na Platform, você só pode trabalhar com ele nos limites dessa sandbox. |

{style="table-layout:auto"}

## O que acontece depois que um público-alvo é criado e publicado? {#after-audience-created}

Depois de criar e publicar um público no Customer Journey Analytics, o público-alvo fica disponível no Experience Platform e pode ser visualizado no [Portal de público-alvo](https://experienceleague.adobe.com/pt-br/docs/experience-platform/segmentation/ui/audience-portal). Com o público-alvo disponível no Experience Platform, ele pode ser usado em outros aplicativos da Experience Platform, como o Adobe Journey Optimizer.

Um segmento de streaming da Adobe Experience Platform só será criado se sua organização estiver configurada para a segmentação de streaming.

Leve em consideração o seguinte ao trabalhar com públicos publicados do Customer Journey Analytics para a Experience Platform:

* O público-alvo no Experience Platform compartilha o mesmo nome e descrição do público-alvo do Customer Journey Analytics. O nome é anexado à ID de público-alvo do Customer Journey Analytics para garantir que o público-alvo seja único.
* Quaisquer alterações feitas no nome ou na descrição do público-alvo no Customer Journey Analytics são refletidas na Experience Platform.
* Se um público-alvo for excluído no Customer Journey Analytics, ele continuará disponível na Experience Platform até que a associação de perfil do público-alvo expire. A associação de perfil expira após 420 dias para públicos-alvo únicos e após 16 dias para públicos-alvo recorrentes.

## Considerações sobre latência {#latency}

Em vários pontos antes, durante e após a publicação do público-alvo, podem ocorrer latências. Esta é uma visão geral de possíveis latências.

![Latências na publicação de público-alvo conforme descrito nesta seção.](assets/latency-diagram.svg)

|  | Ponto de latência | Duração da latência |
| --- | --- | --- |
| Não exibido | Conector de origem do Adobe Analytics para o Analytics (A4T) | Até 30 minutos |
| 1 | Ingestão de dados no Data Lake (do conector de origem do Analytics ou de outras fontes) | Até 90 minutos |
| 2 | Ingestão de dados do Data Lake da Experience Platform para o Customer Journey Analytics | Até 90 minutos |
| 3 | Publicação de público-alvo no perfil do cliente em tempo real, incluindo a criação automática do segmento de streaming e a permissão para que o segmento esteja pronto para receber os dados. | Alguns segundos |
| 4 | Atualizar frequência dos públicos | <ul><li>Atualização única (latência inferior a 5 minutos)</li><li>Atualizar a cada 4 horas, diariamente, semanalmente, mensalmente (a latência acompanha a taxa de atualização) |
| 5 | Criação de destino na Adobe Experience Platform: ativar o novo segmento | 1 a 2 horas |

{style="table-layout:auto"}

## Usar públicos-alvo do Customer Journey Analytics na Experience Platform {#audiences-aep}

O Customer Journey Analytics coleta todas as combinações de namespace e ID do público-alvo publicado e as transmite para a Real-Time Customer Data Platform. O Customer Journey Analytics envia o público-alvo para a Experience Platform com a identidade principal definida, de acordo com o que foi selecionado como a [!UICONTROL ID de pessoa] quando a conexão foi configurada.

Em seguida, a Real-Time Customer Data Platform examina cada combinação de namespace/ID e procura por um perfil do qual possam fazer parte. Um perfil é basicamente um cluster de namespaces, IDs e dispositivos vinculados. Se encontrar um perfil, ela adicionará o namespace e a ID às outras IDs neste perfil como um atributo de associação de segmento. Por exemplo, <user@adobe.com> pode ser direcionado em todos os seus dispositivos e canais. Se um perfil não for encontrado, um novo perfil será criado.

Para exibir os públicos-alvo do Customer Journey Analytics na Platform:

1. Expanda **[!UICONTROL Cliente]** no painel esquerdo e selecione **[!UICONTROL Públicos-alvo]**. <!-- is there a folder called "Customer Journey Analytics? -->

1. Selecione a guia **[!UICONTROL Navegar]**.

1. Para localizar o público-alvo publicado do Customer Journey Analytics, siga um destes procedimentos:

   ![Opção Públicos-alvo no painel esquerdo](assets/aep-audiences.png)

   * Classifique a tabela pela coluna **[!UICONTROL Origem]** para exibir públicos-alvo que mostram o [!UICONTROL **Customer Journey Analytics**] como a origem.

   * Filtre ![Filtro](/help/assets/icons/Filter.svg) em **[!UICONTROL Origem]** e selecione **[!UICONTROL Customer Journey Analytics]**.

   * Use o campo de pesquisa ![Pesquisa](/help/assets/icons/Search.svg).

Para obter mais informações sobre como usar Públicos-alvo na Platform, consulte a seção [Públicos-alvo](https://experienceleague.adobe.com/pt-br/docs/experience-platform/segmentation/ui/segment-builder) do [Guia da interface do Construtor de segmentos](https://experienceleague.adobe.com/pt-br/docs/experience-platform/segmentation/ui/segment-builder) na documentação da Experience Platform.

### Entenda as discrepâncias nas contagens de público-alvo

Podem ocorrer discrepâncias nas contagens de público-alvo entre o Customer Journey Analytics e a Real-Time Customer Data Platform.

<!--
![Infographic on audience differences between Customer Journey Analytics and Real-Time CDP.](/help/components/audiences/assets/infographic-cja-rtcdp.png)
-->

#### Comparação entre contagens estimadas e determinísticas

A metodologia de cálculo dos números de associação do público-alvo difere entre os dois aplicativos, conforme descrito abaixo.

* **Customer Journey Analytics**: a métrica **[!UICONTROL Total de pessoas]** no Customer Journey Analytics é um valor estimado. Isso significa que a contagem é uma estimativa baseada nas regras do público-alvo e pode mudar entre intervalos de atualização.
* **Real-Time Customer Data Platform**: a contagem na Real-Time Customer Data Platform é determinística, com base em trabalhos de avaliação diária, e ela é corrigida ao término da publicação do público-alvo no portal.

#### Intervalo e taxa de publicação

Os públicos-alvo são publicados na Real-Time Customer Data Platform a uma taxa de 1500 registros por segundo (RPS). Por exemplo, um público-alvo de 20 milhões de membros levará aproximadamente 3,7 horas para ser totalmente publicado (20 M/1500 RPS/3600 segundos por hora). Durante esse período, é provável que haja diferenças na associação do público-alvo entre os dois aplicativos.

#### Fragmentação de perfil

Se os perfis importados do Customer Journey Analytics já existirem na Real-Time Customer Data Platform, eles não serão contados como novos perfis. Isso pode fazer com que a contagem de perfis na Real-Time Customer Data Platform seja menor do que o esperado.

#### Comparação entre públicos-alvo em lote e de transmissão

Os públicos-alvo do Customer Journey Analytics não são incluídos no processo de avaliação diária em lote e permanecem fixos até o próximo intervalo de publicação. Em contraste, outros públicos-alvo em lote na Real-Time Customer Data Platform são reavaliados a cada 24 horas.

### Principais pontos a serem lembrados

* **Contagens estimadas no Customer Journey Analytics**: entenda que a contagem **[!UICONTROL Total de pessoas]** no Customer Journey Analytics é uma estimativa e pode variar dependendo dos dados de transmissão e dos comportamentos de identidade.
* **Contagens determinísticas na Real-Time Customer Data Platform**: a contagem na Real-Time Customer Data Platform é fixa e não se altera até o próximo intervalo de publicação.
* **Fragmentação de perfil**: observe que os perfis existentes na Real-Time Customer Data Platform podem não contribuir para novas contagens de perfis ao importar do Customer Journey Analytics.

Por diferenciar claramente esses aspectos, é possível entender e gerenciar melhor os dados de público-alvo no Customer Journey Analytics e na Real-Time Customer Data Platform.--->

## Perguntas frequentes {#faq}

Perguntas frequentes sobre a publicação de público-alvo.

+++**O que acontece se um usuário não é mais membro de um público-alvo Customer Journey Analytics?**

Nesse caso, um evento de saída é enviado à Experience Platform a partir do Customer Journey Analytics.

+++

+++**O que acontece se você excluir um público-alvo no Customer Journey Analytics?**

Quando um público-alvo do Customer Journey Analytics é excluído, ele não será mais exibido na interface da Experience Platform. No entanto, perfis associados a este público-alvo não são excluídos na Experience Platform.

+++

+++**Se um perfil correspondente não existir na Real-Time Customer Data Platform, um novo perfil será criado?**

Sim, será.

+++

+++**O Customer Journey Analytics envia os dados de público-alvo como eventos de pipeline ou como um arquivo simples que também vai para o data lake?**

O Customer Journey Analytics envia os dados para a Real-Time Customer Data Platform por meio do pipeline e esses dados também são coletados em um conjunto de dados do sistema no data lake.

+++

+++**Quais identidades o Customer Journey Analytics envia?**

Qualquer par de identidade/namespace que foi especificado na [Configuração da conexão](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-connections/create-connection). Especificamente, a etapa na qual um usuário seleciona o campo que deseja usar como a ID de pessoa.

+++

+++**Qual ID é escolhida como a identidade principal?**

Veja acima. Somente uma identidade por pessoa do Customer Journey Analytics é enviada.

+++

+++**A Real-Time Customer Data Platform também processa as mensagens do Customer Journey Analytics? O Customer Journey Analytics pode adicionar identidades a um gráfico de identidade de perfil por meio do compartilhamento de público-alvo?**

Não. Somente uma identidade por pessoa é enviada, portanto, não haveria bordas de gráfico para a Real-Time Customer Data Platform consumir.

+++

+++**Que hora do dia ocorrem as atualizações diárias, semanais e mensais? Que dia da semana ocorrem as atualizações semanais?**

O momento da atualização é baseado em quando o público-alvo original foi publicado e se vincula a essa hora do dia (e dia da semana ou mês).

+++

+++**Você pode configurar o horário de atualização diário, semanal e mensal?**

Não, os usuários não podem configurar o horário da atualização.

+++


## Próximas etapas

* Para gerenciar esse público-alvo, acesse a [Interface do usuário de gerenciamento](/help/components/audiences/manage.md).
