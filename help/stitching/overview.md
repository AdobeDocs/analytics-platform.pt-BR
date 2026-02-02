---
title: Visão geral da compilação
description: Saiba mais sobre os conceitos, benefícios, pré-requisitos e limitações da compilação de identidade.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: a94f3fe6821d96c76b759efa3e7eedc212252c5f
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 71%

---

# Visão geral da compilação

>[!NOTE]
>
>Você deve ter o pacote Customer Journey Analytics **Select** ou superior (para [compilação em campo](fbs.md)) ou o pacote Customer Journey Analytics **Prime** ou superior (para [compilação em gráfico](gbs.md)) para usar a funcionalidade descrita nesta seção. Entre em contato com seu administrador se não tiver certeza de qual pacote do Customer Journey Analytics você tem.

A compilação de identidade (ou simplesmente, compilação) é um recurso eficiente que aumenta a adequação de um conjunto de dados de eventos com a análise entre canais. A análise entre canais é um caso de uso principal do Customer Journey Analytics. Essa funcionalidade permite combinar e executar relatórios de forma integrada em vários conjuntos de dados de diferentes canais, com base em um identificador comum (ID da pessoa).

Quando você combina conjuntos de dados com IDs de pessoa semelhantes, a atribuição é transportada entre dispositivos e canais. Por exemplo, um usuário visita seu site por meio de um anúncio em seu computador. O usuário compra um produto, mas depois encontra um problema com o pedido. O usuário então entra em contato com sua equipe de atendimento ao cliente para obter ajuda na resolução do problema. Com a análise entre canais, você pode atribuir eventos da central de atendimento ao anúncio em que o usuário clicou originalmente.

Infelizmente, nem todos os conjuntos de dados baseados em eventos que fazem parte da sua conexão no Customer Journey Analytics são preenchidos por padrão com dados suficientes para oferecer suporte a essa atribuição. Em particular, os conjuntos de dados de experiência baseados na web ou em dispositivos móveis geralmente não têm informações reais de identificação pessoal disponíveis para todos os eventos.

A compilação rechavea identidades em linhas de um conjunto de dados para garantir que a ID de pessoa (ID compilada) esteja disponível em cada evento. A compilação analisa dados de usuários de sessões autenticadas e não autenticadas para determinar o valor da ID de pessoa comum que pode ser usado como ID compilada. Esse rechaveamento resolve registros desiguais para uma única ID compilada para análise no nível da pessoa, em vez de no nível do dispositivo ou do cookie.

O Customer Journey Analytics oferece suporte a dois tipos de compilação: [compilação baseada em campos](fbs.md) e [compilação baseada em gráficos](gbs.md).

## Pré-requisitos

>[!IMPORTANT]
>
>Se algum pré-requisito não for atendido, isso pode resultar na incapacidade de realizar a análise entre canais corretamente.

Antes de usar a compilação, verifique se a sua organização está preparada com o seguinte:

- A compilação inclui a mesclagem de dados de usuário autenticados e não autenticados. Cumpra as leis e regulamentos aplicáveis e obtenha as permissões necessárias do usuário final antes de ativar a compilação em um conjunto de dados de evento.

- Importe os dados desejados para a Adobe Experience Platform:

   - Para dados do Adobe Analytics, consulte [Uso de dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Para outros tipos de dados, consulte [Criar um esquema](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/tutorials/create-schema-ui) e [Assimilar dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/ingestion/home) na documentação da Adobe Experience Platform.

Ao definir sua conexão do Customer Journey Analytics, você se beneficiará da análise entre canais por combinar um ou mais conjuntos de dados compilados com outros conjuntos de dados, como dados da central de atendimento. Essa configuração de conexão pressupõe que esses outros conjuntos de dados já possuem uma ID de pessoa em cada linha, semelhante à ID compilada.

## Habilitar compilação

É possível habilitar a compilação de duas formas:

- [Solicitação para habilitar a compilação](/help/stitching/use-stitching.md) (desaprovado). Depois de aprovado, um conjunto de dados duplicado é criado para o conjunto de dados para o qual você solicitou a compilação. Esse conjunto de dados duplicado contém uma coluna adicional com o identificador compilado. É necessário criar uma nova conexão ou editar uma conexão existente que inclua o conjunto de dados compilado para usar os dados compilados no Customer Journey Analytics.
- [Habilite a compilação na interface de Conexões](/help/stitching/use-stitching-ui.md). Ao configurar a compilação de um conjunto de dados na interface Conexões, a compilação ocorre em tempo real, durante a assimilação de dados desse conjunto de dados no Customer Journey Analytics.

## Limitações

A compilação é um recurso inovador e robusto, mas possui algumas limitações de uso.

- Somente conjuntos de dados de evento são suportados. Outros conjuntos de dados, como conjuntos de dados de pesquisa, não são suportados.
- A compilação não transforma de maneira alguma o campo usado para compilação. A compilação usa o valor no campo especificado de acordo com a sua versão no conjunto de dados não compilado no data lake.
- O processo de compilação diferencia maiúsculas de minúsculas. Por exemplo, os valores de identidade `Bob` e `BOB` são tratados como duas pessoas separadas.

Não confunda a compilação com:

- A mesclagem de dois ou mais conjuntos de dados. A compilação se aplica a apenas um conjunto de dados. A mesclagem de conjuntos de dados ocorre ao configurar uma conexão do Customer Journey Analytics e selecionar a mesma ID de pessoa nos conjuntos de dados selecionados na conexão.

- A associação de dois conjuntos de dados. No Customer Journey Analytics, uma associação é frequentemente usada para pesquisas ou classificações no Analysis Workspace. Embora a compilação use a funcionalidade de associação, o próprio processo envolve mais do que associações.


## Conjuntos de dados do Journey Optimizer

A compilação oferece suporte aos seguintes conjuntos de dados do Journey Optimizer gerados automaticamente:

- Eventos de etapa da jornada do AJO
- Conjunto de dados do evento de atividade de entrada do AJO
- Conjunto de dados de superfícies do AJO
- Conjunto de dados do evento de feedback de mensagens do AJO* Conjunto de dados do evento de experiência de rastreamento de push do AJO
- Conjunto de dados de evento de experiência de rastreamento de email do AJO
- Conjunto de dados do evento de feedback BCC do AJO
- Conjunto de dados do evento de feedback de atividades em tempo real do AJO
- Conjunto de dados de evento de decisão ExD do AJO

>[!MORELIKETHIS]
>
>[Compilação em campo](fbs.md)
>[Compilação baseada em gráfico](gbs.md)
>[Usar compilação](use-stitching.md)
>[Validar compilação](validate.md)
>[Perguntas frequentes sobre compilação](faq.md)

