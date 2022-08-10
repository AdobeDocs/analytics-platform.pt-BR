---
title: Criar e publicar públicos-alvo no Perfil do cliente em tempo real
description: Saiba como publicar públicos-alvo do Customer Journey Analytics
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
source-git-commit: 235f08b275fd2f5706024823005e732b61af1c07
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 96%

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

   {style=&quot;table-layout:auto&quot;}

1. Crie o público-alvo.

   Defina essas configurações antes de publicar o público-alvo.

   ![](assets/create-audience.png)

   | Configuração | Descrição |
   | --- | --- |
   | [!UICONTROL Nome] | O nome do público-alvo. |
   | [!UICONTROL Tags] | Todas as tags que você deseja atribuir ao público-alvo para fins organizacionais. Você pode usar uma tag pré-existente ou inserir uma nova. |
   | [!UICONTROL Descrição] | Adicione uma boa descrição do público-alvo para diferenciá-lo dos outros. |
   | [!UICONTROL Frequência de atualização] | A frequência na qual você deseja atualizar o público-alvo.<ul><li>Você pode optar por criar um público-alvo único (padrão) que não precise de atualização. Por exemplo, isso pode ser útil para campanhas específicas, únicas.</li><li>Você pode selecionar outros intervalos de atualização. Para a frequência de 4 horas, há um limite de 75 ou 150 públicos-alvo, dependendo do seu direito ao CJA. Para outros intervalos, não há número máximo de públicos-alvo.</li></ul> |
   | Data de validade | Quando o público-alvo parará de ser atualizado. O padrão é 1 ano a partir da data de criação. Públicos-alvo que expiram são tratados de forma semelhante aos relatórios agendados que expiram: o administrador recebe um email um mês antes de o público-alvo expirar. |
   | Atualizar janela de retrospectiva | Especifica até que ponto você deseja voltar na janela de dados ao criar esse público-alvo. O máximo é de 90 dias. |
   | [!UICONTROL Intervalo de datas único] | Intervalo de datas quando você deseja que o público-alvo único seja publicado. |
   | [!UICONTROL Filtro] | Os filtros são a principal entrada para o público. Você pode adicionar até 20 filtros. Esses filtros podem ser unidos com operadores `And` ou `Or`. |
   | [!UICONTROL Ver amostras de IDs] | Um exemplo de IDs neste público-alvo. Use a barra de pesquisa para procurar IDs de exemplo. |

   {style=&quot;table-layout:auto&quot;}

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

   {style=&quot;table-layout:auto&quot;}

1. Verifique novamente a configuração do público-alvo e clique em **[!UICONTROL Publicar]**.

   Se tudo correr bem, você receberá uma mensagem de confirmação de que o público-alvo foi publicado. Demora apenas um ou dois minutos para esse público aparecer na Experience Platform. (Mesmo para públicos-alvo com milhões de membros, deve levar menos de 5 minutos.)

1. Clique em **[!UICONTROL Exibir público-alvo na AEP]** na mesma mensagem e você será direcionado para a [Interface do usuário do segmento](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=pt-BR) na Adobe Experience Platform. Veja mais informações abaixo.

## Usar públicos-alvo do CJA na Experience Platform {#audiences-aep}

O CJA agora pega todas as combinações de namespace e ID de seu público publicado e as transmite para o Perfil do cliente em tempo real (RTCP). O CJA envia o público-alvo para a Experience Platform com a identidade primária definida como qualquer ID de pessoa selecionada quando a conexão foi configurada.

Em seguida, o RTCP examina cada combinação de namespace/ID e procura por um perfil do qual possa fazer parte. Um perfil é basicamente um cluster de namespaces, IDs e dispositivos vinculados. Se encontrar um perfil, ele adicionará o namespace e a ID às outras IDs neste perfil como um atributo de associação de segmento. Agora, por exemplo, “user@adobe.com” pode ser direcionado para todos os dispositivos e canais. Se um perfil não for encontrado, um novo perfil será criado.

Você pode visualizar públicos-alvo do CJA na Platform acessando a guia **[!UICONTROL Segmentos]** > **[!UICONTROL Criar segmentos]** > **[!UICONTROL Públicos-alvo]** > **[!UICONTROL Públicos-alvo do CJA]**.

Você pode arrastar os públicos-alvo do CJA para a definição de segmentos da AEP.

![](assets/audiences-aep.png)

## O que acontece se um usuário não é mais membro de um público-alvo no CJA? {#no-member}

Nesse caso, um evento de saída é enviado à Experience Platform do CJA.

## O que acontece se você excluir um público-alvo no CJA? {#delete}

Quando um público-alvo do CJA é excluído, esse público-alvo não será mais exibido na interface do usuário do Experience Platform. No entanto, nenhum perfil associado a esse público-alvo é realmente excluído na Platform.

## Próximas etapas

* Para gerenciar esse público-alvo, acesse a [Interface do usuário de gerenciamento](/help/components/audiences/manage.md).
