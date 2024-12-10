---
title: Visão geral da compilação
description: Visão geral de compilação
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 15%

---

# Visão geral da compilação

>[!NOTE]
>
>Você deve ter o pacote **Select** ou superior (para a [compilação em campo](fbs.md)) ou o pacote **Prime** ou superior (para a [compilação em gráfico](gbs.md)) para usar a funcionalidade descrita nesta seção. Entre em contato com sua administração se não tiver certeza de qual pacote do Customer Journey Analytics você possui.

A compilação de identidade (ou simplesmente, compilação) é um recurso poderoso que eleva a adequação de um conjunto de dados de evento para análise entre canais. A análise entre canais é um caso de uso principal que o Customer Journey Analytics pode manipular, permitindo combinar e executar relatórios de maneira contínua em vários conjuntos de dados de diferentes canais, com base em um identificador comum (ID de pessoa).

Quando você combina conjuntos de dados com IDs de pessoa semelhantes, a atribuição é transportada entre dispositivos e canais. Por exemplo, um usuário visita o site pela primeira vez por meio de um anúncio no computador desktop. Esse usuário encontra um problema com seu pedido e, em seguida, faz uma chamada à equipe de atendimento ao cliente para ajudá-lo a resolver o problema. Com a análise entre canais, você pode atribuir eventos da central de atendimento ao anúncio em que eles clicaram originalmente.

Infelizmente, nem todos os conjuntos de dados baseados em eventos que fazem parte da sua conexão no Customer Journey Analytics estão preenchidos com dados suficientes para dar suporte a essa atribuição pronta para uso. Especialmente, os conjuntos de dados de experiência baseados na Web ou em dispositivos móveis geralmente não têm informações reais de ID de pessoa disponíveis em todos os eventos.

A compilação permite rechavear identidades em linhas de um conjunto de dados, garantindo que a ID de pessoa (ID compilada) esteja disponível em cada evento. A compilação analisa os dados do usuário de sessões autenticadas e não autenticadas para determinar o valor da ID transitória comum (ID de pessoa) que pode ser usada como ID compilada. Esse rechaveamento permite resolver registros desiguais em uma única ID compilada para análise no nível da pessoa, em vez de no nível do dispositivo ou do cookie.

O Customer Journey Analytics oferece suporte a dois tipos de compilação: [compilação em campo](fbs.md) e [compilação em gráfico](gbs.md).

## Pré-requisitos

>[!IMPORTANT]
>
>O não cumprimento de todos os pré-requisitos pode resultar na incapacidade de realizar a análise entre canais corretamente.

Antes de usar a compilação, verifique se sua organização está preparada com o seguinte:

- A compilação inclui a mesclagem de dados de usuário autenticados e não autenticados. Cumpra as leis e regulamentos aplicáveis e obtenha as permissões necessárias do usuário final antes de ativar a compilação em um conjunto de dados de evento. Consulte [Definir campos de identidade na interface](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/ui/fields/identity) para obter mais informações.

- Importe os dados desejados para o Adobe Experience Platform:

   - Para dados do Adobe Analytics, consulte [Utilização dos dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Para outros tipos de dados, consulte [Criar um esquema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) e [Assimilar dados](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) na documentação da Adobe Experience Platform.

Você se beneficia da análise entre canais se combinar um ou mais conjuntos de dados compilados com outros conjuntos de dados, como dados da central de atendimento, como parte da definição da conexão Customer Journey Analytics. Essa configuração de conexão pressupõe que esses outros conjuntos de dados já contenham uma ID de pessoa em cada linha, semelhante à ID compilada.


## Limitações

>[!IMPORTANT]
>
>- Não há suporte para o uso de `identityMap` como ID persistente. Você precisa definir um identificador específico no conjunto de dados (por exemplo, `ECID`) como a ID persistente.
>
>- Aplique qualquer alteração feita ao esquema do conjunto de dados do evento de origem também ao novo esquema do conjunto de dados compilado, caso contrário, ela quebrará o conjunto de dados compilado.
>
>- Se você remover o conjunto de dados de origem, o conjunto de dados compilado parará de ser processado e será removido pelo sistema.
>
>- Os rótulos de uso de dados não são propagados automaticamente para o esquema do conjunto de dados compilado. Se você tiver rótulos de uso de dados aplicados ao esquema do conjunto de dados de origem, será necessário aplicar esses rótulos de uso de dados manualmente ao esquema do conjunto de dados compilado. Consulte [Gerenciamento de rótulos de uso de dados no Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) para obter mais informações.

A costura é um recurso inovador e robusto, mas tem limitações na forma de uso.

- Somente conjuntos de dados de evento são suportados. Outros conjuntos de dados, como conjuntos de dados de pesquisa, não são suportados.
- A compilação não transforma de maneira alguma o campo usado para compilação. A compilação usa o valor no campo especificado, como ele existe no conjunto de dados não compilado no data lake.
- O processo de compilação diferencia maiúsculas de minúsculas. Por exemplo, se às vezes aparecer no campo a palavra &quot;Bob&quot; e, às vezes, a palavra &quot;BOB&quot;, essas IDs serão tratadas como duas pessoas separadas.

Não confunda a compilação com:

- A mesclagem de dois ou mais conjuntos de dados. A compilação se aplica a apenas um conjunto de dados. A mesclagem de conjuntos de dados ocorre como resultado da configuração de uma conexão Customer Journey Analytics e da seleção da mesma ID de pessoa nos conjuntos de dados selecionados na conexão.

- A associação de dois conjuntos de dados. No Customer Journey Analytics, uma junção é frequentemente usada para pesquisas ou classificações no Analysis Workspace. Embora a compilação use a funcionalidade de associação, o próprio processo envolve mais do que associações.

>[!MORELIKETHIS]
>
>[Compilação baseada em campo](fbs.md)
>[Compilação baseada em gráfico](gbs.md)
>[Usar compilação](use-stitching.md)
>[Perguntas frequentes sobre compilação](faq.md)

