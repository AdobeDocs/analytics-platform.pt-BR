---
title: Criar e publicar públicos-alvo no Perfil do cliente em tempo real
description: Saiba como publicar públicos-alvo do Customer Journey Analytics
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: 905d8e0bfe2e0dbc9c6a03d9eb9a6efd4926fbbf
workflow-type: tm+mt
source-wordcount: '1767'
ht-degree: 48%

---

# Criar e publicar públicos-alvo {#create-and-publish-audiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_audiences_refreshfrequency"
>title="Frequência de atualização"
>abstract="Veja com que frequência a associação de um público-alvo será reavaliada.<br/>Públicos-alvo únicos são avaliados apenas uma vez."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_audiences_audiencelimit"
>title="Atualizar público"
>abstract="As atualizações de públicos são limitadas com base na frequência com que são atualizadas."

<!-- markdownlint-enable MD034 -->

Este tópico discute como criar e publicar públicos-alvo identificados no Customer Journey Analytics no [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR) no Adobe Experience Platform para direcionamento e personalização de clientes.

Leia esta [visão geral](/help/components/audiences/audiences-overview.md) para familiarizar-se com o conceito de públicos-alvo do Customer Journey Analytics.

## Criar e publicar um público-alvo {#create}

1. Para começar a criar e publicar um público-alvo, siga um destes procedimentos:

   | Método de criação | Detalhes |
   | --- | --- |
   | No menu principal **[!UICONTROL Componentes] > [!UICONTROL Públicos-alvo]** | A página do Gerenciador de Audiences se abre. Clique em **[!UICONTROL Criar público-alvo]** e o [!UICONTROL Construtor de público-alvo] se abre. |
   | De uma visualização no Analysis Workspace | Muitas visualizações no Analysis Workspace permitem criar um público-alvo usando o menu do botão direito do mouse. Por exemplo, você pode clicar com o botão direito do mouse em um item em uma tabela de forma livre ou clicar com o botão direito em um nó na tela de Jornada e selecionar **[!UICONTROL Criar público-alvo]**. <p>O uso desse método preenche o filtro previamente com a dimensão ou o item de dimensão selecionado na tabela.</p><p>As visualizações a seguir permitem criar um público-alvo usando o menu do botão direito do mouse:</p><ul><li>Coorte</li><li>Fallout</li><li>Fluxo</li><li>Tabela de forma livre</li><li>Tela da jornada</li><li>Venn</li></ul><p>**Observação:** públicos-alvo não podem incluir métricas calculadas. Se você tentar criar um público-alvo que contenha uma métrica calculada, a métrica calculada não será incluída na definição do público-alvo.</p> |
   | Na interface de criação/edição do filtro | Marque a caixa que diz **[!UICONTROL Criar um público-alvo com base neste filtro]**. O uso desse método preenche o filtro previamente. |

   {style="table-layout:auto"}

1. Crie o público-alvo.

   Defina essas configurações antes de publicar o público-alvo.

   ![Captura de tela de como criar um público-alvo enviando as configurações descritas na próxima seção.](assets/create-audience.png)

   | Configuração | Descrição |
   | --- | --- |
   | [!UICONTROL Nome] | O nome do público-alvo. |
   | [!UICONTROL Tags] | Todas as tags que você deseja atribuir ao público-alvo para fins organizacionais. Você pode usar uma tag pré-existente ou inserir uma nova. |
   | [!UICONTROL Descrição] | Adicione uma boa descrição do público-alvo para diferenciá-lo dos outros. |
   | [!UICONTROL Frequência de atualização] | A frequência na qual você deseja atualizar o público-alvo.<ul><li>Você pode optar por criar um público-alvo único (padrão) que não precise de atualização. Por exemplo, isso pode ser útil para campanhas específicas, únicas.</li><li>Você pode selecionar outros intervalos de atualização. Para a frequência de atualização de 4 horas, há um limite de 75 a 150 atualizações de público, dependendo do seu direito ao Customer Journey Analytics.</li></ul> |
   | Data de validade | Quando o público-alvo parará de ser atualizado. O padrão é 1 ano a partir da data de criação. Públicos-alvo que expiram são tratados de forma semelhante aos relatórios agendados que expiram: o administrador recebe um email um mês antes de o público-alvo expirar. |
   | Atualizar janela de retrospectiva | Especifica até que ponto você deseja voltar na janela de dados ao criar esse público-alvo. O máximo é de 90 dias. |
   | [!UICONTROL Intervalo de datas único] | Intervalo de datas quando você deseja que o público-alvo único seja publicado. |
   | [!UICONTROL Filtro] | Os filtros são a principal entrada para o público. Você pode adicionar até 20 filtros. Esses filtros podem ser unidos com operadores `And` ou `Or`.<p>Ao criar um público-alvo a partir de uma visualização no Analysis Workspace (como uma tabela de forma livre ou tela de Jornada), todos os filtros aplicados ao painel ou à coluna são preservados. É possível remover qualquer filtro aplicado automaticamente.</p> |
   | [!UICONTROL Ver amostras de IDs] | Um exemplo de IDs neste público-alvo. Use a barra de pesquisa para procurar IDs de exemplo. |

   {style="table-layout:auto"}

1. Interpretar a visualização de dados.

   A pré-visualização do público-alvo é exibida no painel direito. Ela permite uma análise resumida do público-alvo criado.

   ![Captura de tela da visualização de dados mostrando uma análise resumida do público-alvo.](assets/data-preview.png)

   | Configuração de visualização | Descrição |
   | --- | --- |
   | Janela [!UICONTROL Visualização de dados] | O intervalo de datas do público-alvo. |
   | [!UICONTROL Total de pessoas] | Um número resumido do número total de pessoas neste público-alvo. Pode chegar a 20 milhões de pessoas. Se o público-alvo exceder 20 milhões de pessoas, você deverá reduzir o tamanho do público-alvo antes de publicá-lo. |
   | [!UICONTROL Limite de tamanho do público] | Mostra a distância que está do limite de 20 milhões de pessoas. |
   | [!UICONTROL Retorno estimado do público] | Essa configuração é útil para redirecionar clientes nesse público-alvo que retornam ao site, aplicativo móvel ou outro canal (ou seja, que são vistos nesse conjunto de dados novamente). <p>Aqui, você pode selecionar o período (próximos 7 dias, próximas 2 semanas, próximo mês) para o número estimado de clientes que podem retornar. |
   | [!UICONTROL Estimativa de retorno] | Esse número oferece um número estimado de clientes recorrentes durante o período selecionado na lista suspensa. Observamos a taxa de churn histórica para esse público-alvo prever esse número. |
   | [!UICONTROL Visualizar métricas] | Essa configuração permite que você observe métricas específicas para ver se esse público-alvo contribui com uma quantidade desproporcional para essa métrica, como “[!UICONTROL Receita]” ou “[!UICONTROL Tempo médio no site]”. Ela fornece a contagem agregada da métrica, bem como a porcentagem do total que ela representa. Você pode selecionar qualquer métrica disponível na visualização de dados. |
   | [!UICONTROL Namespaces incluídos] | Os namespaces específicos que estão associados às pessoas no seu público-alvo. Os exemplos incluem ECID, CRM ID, endereços de email, etc. |
   | [!UICONTROL Sandbox] | A [sandbox da Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=pt-BR) em que esse público-alvo está. Ao publicar esse público-alvo na Platform, você só pode trabalhar com ele nos limites dessa sandbox. |

   {style="table-layout:auto"}

1. Verifique novamente a configuração do público-alvo e clique em **[!UICONTROL Publicar]**.

   Se tudo correr bem, você receberá uma mensagem de confirmação de que o público-alvo foi publicado. Demora apenas um ou dois minutos para esse público aparecer na Experience Platform. (Mesmo para públicos-alvo com milhões de membros, deve levar menos de 5 minutos.)

1. Clique em **[!UICONTROL Exibir público-alvo na AEP]** na mesma mensagem e você será direcionado para a [Interface do usuário do segmento](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=pt-BR) na Adobe Experience Platform. Veja mais informações abaixo.

## O que acontece depois que um público-alvo é criado e publicado? {#after-audience-created}

Depois de criar e publicar um público-alvo no Customer Journey Analytics, o público-alvo fica disponível no Experience Platform. Um segmento de transmissão do Adobe Experience Platform só será criado se sua organização estiver configurada para segmentação de transmissão.

* O público-alvo na Platform compartilha o mesmo nome/descrição do público-alvo da Customer Journey Analytics, mas o nome será anexado com a ID de público-alvo da Customer Journey Analytics para garantir que seja exclusivo.
* Quaisquer alterações feitas no nome ou na descrição do público-alvo no Customer Journey Analytics são refletidas na Platform.
* Se um público-alvo for excluído no Customer Journey Analytics, ele continuará disponível na Platform.

## Considerações sobre latência {#latency}

Em vários pontos antes, durante e depois da publicação do público-alvo, podem ocorrer latências. Esta é uma visão geral de possíveis latências.

![Latências na publicação de público-alvo conforme descrito nesta seção.](assets/latency-diagram.svg)

| # | Ponto de latência | Duração da latência |
| --- | --- | --- |
| Não exibido | Conector de origem do Adobe Analytics para o Analytics (A4T) | Até 30 minutos |
| 1 | Assimilação de dados no Data Lake (do conector de origem do Analytics ou de outras fontes) | Até 90 minutos |
| 2 | Assimilação de dados do Experience Platform Data Lake no Customer Journey Analytics | Até 90 minutos |
| 3 | Publicação de público-alvo no perfil do cliente em tempo real, incluindo a criação automática do segmento de transmissão e permitindo que o segmento esteja pronto para receber os dados. | Alguns segundos |
| 4 | Atualizar frequência dos públicos | <ul><li>Atualização única (latência inferior a 5 minutos)</li><li>Atualizar a cada 4 horas, diariamente, semanalmente, mensalmente (a latência acompanha a taxa de atualização) |
| 5 | Criação de destino no Adobe Experience Platform: ativação do novo segmento | 1 a 2 horas |

{style="table-layout:auto"}

## Usar públicos-alvo do Customer Journey Analytics no Experience Platform {#audiences-aep}

O Customer Journey Analytics pega todas as combinações de namespace e ID de seu público publicado e as transmite para o Perfil do cliente em tempo real (RTCP). O Customer Journey Analytics envia o público-alvo para o Experience Platform com a identidade primária definida, de acordo com o que foi selecionado como a [!UICONTROL ID de pessoa] quando a conexão foi configurada.

Em seguida, o RTCP examina cada combinação de namespace/ID e procura por um perfil do qual possa fazer parte. Um perfil é basicamente um cluster de namespaces, IDs e dispositivos vinculados. Se encontrar um perfil, ele adicionará o namespace e a ID às outras IDs neste perfil como um atributo de associação de segmento. Por exemplo, <user@adobe.com> pode ser direcionado em todos os seus dispositivos e canais. Se um perfil não for encontrado, um novo perfil será criado.

Para exibir públicos-alvo do Customer Journey Analytics na Platform:

1. Expanda [!UICONTROL **Cliente**] no painel esquerdo e selecione [!UICONTROL **Públicos-alvo**]. <!-- is there a folder called "Customer Journey Analytics? -->

1. Selecione a guia [!UICONTROL **Procurar**].

   ![Opção Públicos-alvo no painel esquerdo](assets/audiences-aep.png)

1. Para localizar o público-alvo publicado pelo Customer Journey Analytics, siga um destes procedimentos:

   * Classifique a tabela pela coluna [!UICONTROL **Origin**] para exibir públicos-alvo que mostram [!UICONTROL **Customer Journey Analytics**] como a origem.

   * Selecione o ícone de filtro.

   * Use o campo de pesquisa.

Para obter mais informações sobre como usar o Audiences na Platform, consulte a seção [Audiences](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#audiences) no [guia da interface do usuário do Construtor de segmentos](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html), na documentação do Experience Platform.


## Perguntas frequentes {#faq}

Perguntas frequentes sobre a publicação de público-alvo.

+++**O que acontece se um usuário não é mais membro de um público no Customer Journey Analytics?**

Nesse caso, um evento de saída é enviado para o Experience Platform do Customer Journey Analytics.

+++

+++**O que acontece se você excluir um público-alvo no Customer Journey Analytics?**

Quando um público-alvo do Customer Journey Analytics é excluído, ele não será mais exibido na interface do Experience Platform. No entanto, nenhum perfil associado a esse público-alvo é realmente excluído na Platform.

+++

+++**Se um perfil correspondente não existir na RTCDP, um novo perfil será criado?**

Sim, será.

+++

+++**O Customer Journey Analytics envia os dados do público-alvo como eventos de pipeline ou como um arquivo simples que também vai para o data lake?**

O Customer Journey Analytics transmite os dados para o RTCP por meio do pipeline e esses dados também são coletados em um conjunto de dados do sistema no data lake.

+++

+++**Sobre quais identidades o Customer Journey Analytics envia?**

Qualquer par de identidade/namespace que tenha sido especificado na [Configuração de conexão](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR#create-connection). Especificamente, a etapa na qual um usuário seleciona o campo que deseja usar como “ID de pessoa”:

+++

+++**Qual ID é escolhida como a identidade principal?**

Veja acima. Só enviamos uma identidade por Customer Journey Analytics &quot;pessoa&quot;.

+++

+++**O RTCP também processa as mensagens Customer Journey Analytics? O Customer Journey Analytics pode adicionar identidades a um gráfico de identidade de perfil por meio do compartilhamento de público-alvo?**

Não. Enviamos apenas uma identidade por “pessoa”, de modo que não haveria bordas de gráfico para a RTCP consumir.

+++

+++**Que hora do dia ocorrem as atualizações diárias, semanais e mensais? Que dia da semana ocorrem as atualizações semanais?**

O momento da atualização é baseado em quando o público original foi publicado e ancora esse horário do dia (e dia da semana ou mês).

+++

+++**O horário de atualização diário, semanal e mensal pode ser configurado pelos usuários?**

Não, eles não podem ser configurados por usuários.

+++


## Próximas etapas

* Para gerenciar esse público-alvo, acesse a [Interface do usuário de gerenciamento](/help/components/audiences/manage.md).
