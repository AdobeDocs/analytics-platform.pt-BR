---
title: Criar e publicar públicos-alvo no Perfil do cliente em tempo real
description: Saiba como publicar públicos-alvo do Customer Journey Analytics
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
source-git-commit: 60f9c81699f9a8e1657da4bd806d04f9f8adaa99
workflow-type: tm+mt
source-wordcount: '1435'
ht-degree: 94%

---

# Criar e publicar públicos-alvo

Este tópico discute como criar e publicar públicos-alvo identificados no Customer Journey Analytics (CJA) no [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR) na Adobe Experience Platform para direcionamento e personalização de clientes.

Leia esta [visão geral](/help/components/audiences/audiences-overview.md) para familiarizar-se com o conceito de públicos-alvo do CJA.

## Criar público-alvo {#create}

1. Há várias maneiras de começar a criar públicos-alvo:

   | Método de criação | Detalhes |
   | --- | --- |
   | No menu principal **[!UICONTROL Componentes] > [!UICONTROL Públicos-alvo]** | A página do Gerenciador de Audiences se abre. Clique em **[!UICONTROL Criar público-alvo]** e o [!UICONTROL Construtor de público-alvo] se abre. |
   | A partir de uma tabela de forma livre | Clique com o botão direito do mouse em um item na tabela de Forma livre e selecione **[!UICONTROL Criar um público-alvo a partir da seleção]**. O uso desse método preenche o filtro previamente com a dimensão ou o item de dimensão selecionado na tabela. |
   | Na interface de criação/edição do filtro | Marque a caixa que diz **[!UICONTROL Criar um público-alvo com base neste filtro]**. O uso desse método preenche o filtro previamente. |

   {style="table-layout:auto"}

1. Crie o público-alvo.

   Defina essas configurações antes de publicar o público-alvo.

   ![](assets/create-audience.png)

   | Configuração | Descrição |
   | --- | --- |
   | [!UICONTROL Nome] | O nome do público-alvo. |
   | [!UICONTROL Tags] | Todas as tags que você deseja atribuir ao público-alvo para fins organizacionais. Você pode usar uma tag pré-existente ou inserir uma nova. |
   | [!UICONTROL Descrição] | Adicione uma boa descrição do público-alvo para diferenciá-lo dos outros. |
   | [!UICONTROL Frequência de atualização] | A frequência na qual você deseja atualizar o público-alvo.<ul><li>Você pode optar por criar um público-alvo único (padrão) que não precise de atualização. Por exemplo, isso pode ser útil para campanhas específicas, únicas.</li><li>Você pode selecionar outros intervalos de atualização. Para a frequência de atualização de 4 horas, há um limite de 75 a 150 atualizações de público, dependendo do seu direito do CJA.</li></ul> |
   | Data de validade | Quando o público-alvo parará de ser atualizado. O padrão é 1 ano a partir da data de criação. Públicos-alvo que expiram são tratados de forma semelhante aos relatórios agendados que expiram: o administrador recebe um email um mês antes de o público-alvo expirar. |
   | Atualizar janela de retrospectiva | Especifica até que ponto você deseja voltar na janela de dados ao criar esse público-alvo. O máximo é de 90 dias. |
   | [!UICONTROL Intervalo de datas único] | Intervalo de datas quando você deseja que o público-alvo único seja publicado. |
   | [!UICONTROL Filtro] | Os filtros são a principal entrada para o público. Você pode adicionar até 20 filtros. Esses filtros podem ser unidos com operadores `And` ou `Or`. |
   | [!UICONTROL Ver amostras de IDs] | Um exemplo de IDs neste público-alvo. Use a barra de pesquisa para procurar IDs de exemplo. |

   {style="table-layout:auto"}

1. Interpretar a visualização de dados.

   A visualização do público-alvo é exibida no painel direito. Ela permite uma análise resumida do público-alvo criado.

   ![](assets/data-preview.png)

   | Configuração de visualização | Descrição |
   | --- | --- |
   | Janela [!UICONTROL Visualização de dados] | O intervalo de datas do público-alvo. |
   | [!UICONTROL Total de pessoas] | Um número resumido do número total de pessoas neste público-alvo. Pode chegar a 20 milhões de pessoas. Se o público-alvo exceder 20 milhões de pessoas, você deverá reduzir o tamanho do público-alvo antes de publicá-lo. |
   | [!UICONTROL Limite de tamanho do público] | Mostra a distância que está do limite de 20 milhões de pessoas. |
   | [!UICONTROL Retorno estimado do público] | Essa configuração é útil para redirecionar clientes nesse público-alvo que retornam ao site. (Em outras palavras, que são vistas neste conjunto de dados novamente.) <p>Aqui, você pode selecionar o período (próximos 7 dias, próximas 2 semanas, próximo mês) para o número estimado de clientes que podem retornar. |
   | [!UICONTROL Estimativa de retorno] | Esse número oferece um número estimado de clientes recorrentes durante o período selecionado na lista suspensa. Observamos a taxa de churn histórica para esse público-alvo prever esse número. |
   | [!UICONTROL Visualizar métricas] | Essa configuração permite que você observe métricas específicas para ver se esse público-alvo contribui com uma quantidade desproporcional para essa métrica, como “[!UICONTROL Receita]” ou “[!UICONTROL Tempo médio no site]”. Ela fornece a contagem agregada da métrica, bem como a porcentagem do total que ela representa. Você pode selecionar qualquer métrica disponível na visualização de dados. |
   | [!UICONTROL Namespaces incluídos] | Os namespaces específicos que estão associados às pessoas no seu público-alvo. Os exemplos incluem ECID, CRM ID, endereços de email, etc. |
   | [!UICONTROL Sandbox] | A [sandbox da Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=pt-BR) em que esse público-alvo está. Ao publicar esse público-alvo na Platform, você só pode trabalhar com ele nos limites dessa sandbox. |

   {style="table-layout:auto"}

1. Verifique novamente a configuração do público-alvo e clique em **[!UICONTROL Publicar]**.

   Se tudo correr bem, você receberá uma mensagem de confirmação de que o público-alvo foi publicado. Demora apenas um ou dois minutos para esse público aparecer na Experience Platform. (Mesmo para públicos-alvo com milhões de membros, deve levar menos de 5 minutos.)

1. Clique em **[!UICONTROL Exibir público-alvo na AEP]** na mesma mensagem e você será direcionado para a [Interface do usuário do segmento](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=pt-BR) na Adobe Experience Platform. Veja mais informações abaixo.

## O que acontece depois que um público é criado? {#after-audience-created}

Depois de criar um público, a Adobe cria um segmento de streaming da Experience Platform para cada novo público do CJA. Um segmento de streaming da AEP só será criado se sua organização estiver configurada para a segmentação de streaming.

* O segmento da AEP compartilha o mesmo nome/descrição do público do CJA, mas o nome será anexado à ID de público do CJA para garantir que seja exclusivo.
* Se o nome/descrição do público do CJA mudar, o nome/descrição do segmento da AEP também refletirá essa alteração.
* Se um público do CJA for excluído por um usuário, o segmento da AEP NÃO será excluído. O motivo é que o público do CJA pode ser recuperado posteriormente.

## Considerações sobre latência {#latency}

Em vários pontos antes, durante e após a publicação do público-alvo, podem ocorrer latências. Esta é uma visão geral de possíveis latências.

![latência de AEP para CJA](assets/latency-diagram.png)

| # | Ponto de latência | Duração da latência |
| --- | --- | --- |
| Não exibido | Conector de origem Adobe Analytics para Analytics (A4T) | Até 30 minutos |
| 1 | Assimilação de dados no Data Lake (do Conector de origem do Analytics ou outras fontes) | Até 90 minutos |
| 2 | Assimilação de dados do Experience Platform Data Lake para CJA | Até 90 minutos |
| 3 | Publicação de público no perfil do cliente em tempo real, incluindo a criação automática do segmento de streaming e permitindo que o segmento esteja pronto para receber os dados. | Cerca de 60 minutos |
| 4 | Atualizar frequência dos públicos | <ul><li>Atualização única (latência inferior a 5 minutos)</li><li>Atualizar a cada 4 horas, diariamente, semanalmente, mensalmente (a latência acompanha a taxa de atualização) |
| 5 | Criação de destino na AEP: ativar o novo segmento | 1 a 2 horas |

{style="table-layout:auto"}

## Usar públicos do CJA na Experience Platform {#audiences-aep}

O CJA coleta todas as combinações de namespace e ID do público que foi publicado e as transmite para o Perfil do cliente em tempo real (RTCP). O CJA envia o público para a Experience Platform com a identidade principal definida, de acordo com o que foi selecionado como [!UICONTROL ID de pessoa] quando a conexão foi configurada.

Em seguida, o RTCP examina cada combinação de namespace/ID e procura por um perfil do qual possa fazer parte. Um perfil é basicamente um cluster de namespaces, IDs e dispositivos vinculados. Se encontrar um perfil, ele adicionará o namespace e a ID às outras IDs neste perfil como um atributo de associação de segmento. Agora, por exemplo, “user@adobe.com” pode ser direcionado para todos os dispositivos e canais. Se um perfil não for encontrado, um novo perfil será criado.

Você pode visualizar públicos-alvo do CJA na Platform acessando a guia **[!UICONTROL Segmentos]** > **[!UICONTROL Criar segmentos]** > **[!UICONTROL Públicos-alvo]** > **[!UICONTROL Públicos-alvo do CJA]**.

Você pode arrastar os públicos-alvo do CJA para a definição de segmentos da AEP.

![](assets/audiences-aep.png)

## Perguntas frequentes {#faq}

Perguntas frequentes sobre a publicação de público-alvo.

+++**O que acontece se um usuário não é mais membro de um público no CJA?**

Nesse caso, um evento de saída é enviado à Experience Platform do CJA.

+++

+++**O que acontece se você excluir um público no CJA?**

Quando um público-alvo do CJA é excluído, ele não será mais exibido na interface da Experience Platform. No entanto, nenhum perfil associado a esse público-alvo é realmente excluído na Platform.

+++

+++**Se um perfil correspondente não existir na RTCDP, um novo perfil será criado?**

Sim, será.

+++

+++**O CJA envia os dados do público-alvo como eventos de pipeline ou como um arquivo simples que também vai para o lago de dados?**

O CJA envia os dados para o RTCP por meio do pipeline e esses dados também são coletados em um conjunto de dados do sistema no data lake.

+++

+++**Quais identidades o CJA envia?**

Qualquer par de identidade/namespace especificado no [Configuração de conexão](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR#create-connection). Especificamente, a etapa na qual um usuário seleciona o campo que deseja usar como “ID de pessoa”:

+++

+++**Qual ID é escolhida como a identidade principal?**

Veja acima. Enviamos apenas uma identidade por “pessoa” do CJA.

+++

+++**O RTCP também processa as mensagens do CJA? O CJA pode adicionar identidades a um gráfico de identidade de perfil por meio do compartilhamento de público?**

Não. Enviamos apenas uma identidade por “pessoa”, de modo que não haveria bordas de gráfico para a RTCP consumir.

+++

## Próximas etapas

* Para gerenciar esse público-alvo, acesse a [Interface do usuário de gerenciamento](/help/components/audiences/manage.md).
