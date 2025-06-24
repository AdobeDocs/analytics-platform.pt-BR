---
title: Visão geral da compilação
description: Visão geral de compilação
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 1a697ce0372d1cb544940778850714a198a000ec
workflow-type: ht
source-wordcount: '741'
ht-degree: 100%

---

# Visão geral da compilação

>[!NOTE]
>
>Você deve ter o pacote **Select** ou superior (para a [compilação baseada em campo](fbs.md)) ou o pacote **Prime** ou superior (para a [compilação baseada em gráfico](gbs.md)) para usar a funcionalidade descrita nesta seção. Entre em contato com seu administrador se não tiver certeza de qual pacote do Customer Journey Analytics você tem.

A compilação de identidade (ou simplesmente, compilação) é um recurso eficiente que aumenta a adequação de um conjunto de dados de eventos com a análise entre canais. A análise entre canais é um dos casos de uso principais que o Customer Journey Analytics pode processar, permitindo combinar e executar relatórios em vários conjuntos de dados de diferentes canais com base em um identificador comum (ID de pessoa).

Quando você combina conjuntos de dados com IDs de pessoa semelhantes, a atribuição é transportada entre dispositivos e canais. Por exemplo, um usuário visita o site pela primeira vez por meio de um anúncio no computador desktop. Esse usuário encontra um problema com seu pedido e, em seguida, faz uma chamada à equipe de atendimento ao cliente para ajudá-lo a resolver o problema. Com a análise entre canais, você pode atribuir eventos da central de atendimento ao anúncio clicado originalmente.

Infelizmente, nem todos os conjuntos de dados baseados em eventos que fazem parte da sua conexão no Customer Journey Analytics estão preenchidos por padrão com dados suficientes para oferecer suporte a essa atribuição. Em especial, os conjuntos de dados de experiência baseados na web ou em dispositivos móveis geralmente não têm informações reais de ID de pessoa disponíveis em todos os eventos.

A compilação permite rechavear identidades em linhas de um conjunto de dados, garantindo que a ID de pessoa (ID compilada) esteja disponível em cada evento. A compilação analisa os dados do usuário de sessões autenticadas e não autenticadas para determinar o valor da ID transitória comum (ID de pessoa) que pode ser usada como ID compilada. Esse rechaveamento permite resolver registros distintos em uma única ID compilada para realizar uma análise no nível da pessoa, em vez de no nível do dispositivo ou do cookie.

O Customer Journey Analytics oferece suporte a dois tipos de compilação: [compilação baseada em campos](fbs.md) e [compilação baseada em gráficos](gbs.md).

## Pré-requisitos

>[!IMPORTANT]
>
>Se algum pré-requisito não for atendido, isso pode resultar na incapacidade de realizar a análise entre canais corretamente.

Antes de usar a compilação, verifique se a sua organização está preparada com o seguinte:

- A compilação inclui a mesclagem de dados de usuário autenticados e não autenticados. Certifique-se de cumprir as leis e regulamentações aplicáveis, incluindo obter as permissões necessárias do usuário final, antes de ativar a compilação em um conjunto de dados de eventos. Consulte [Definir campos de identidade na interface](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/ui/fields/identity) para obter mais informações.

- Importe os dados desejados para a Adobe Experience Platform:

   - Para dados do Adobe Analytics, consulte [Uso de dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Para outros tipos de dados, consulte [Criar um esquema](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/tutorials/create-schema-ui) e [Assimilar dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/ingestion/home) na documentação da Adobe Experience Platform.

Ao definir sua conexão do Customer Journey Analytics, você se beneficiará da análise entre canais por combinar um ou mais conjuntos de dados compilados com outros conjuntos de dados, como dados da central de atendimento. Essa configuração de conexão pressupõe que esses outros conjuntos de dados já possuem uma ID de pessoa em cada linha, semelhante à ID compilada.


## Limitações

>[!IMPORTANT]
>
>
>- Aplique também qualquer alteração feita ao esquema do conjunto de dados do evento de origem no novo esquema do conjunto de dados compilado, caso contrário, o conjunto de dados compilado será corrompido.
>
>- Se você remover o conjunto de dados de origem, o processamento do conjunto de dados compilado será interrompido e ele será removido pelo sistema.
>
>- Os rótulos de uso de dados não são propagados automaticamente para o esquema do conjunto de dados compilado. Se você tiver rótulos de uso de dados aplicados ao esquema do conjunto de dados de origem, será necessário aplicá-los manualmente ao esquema do conjunto de dados compilado. Consulte [Gerenciamento de rótulos de uso de dados na Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-governance/labels/overview) para obter mais informações.

A compilação é um recurso inovador e robusto, mas possui algumas limitações de uso.

- Somente conjuntos de dados de evento são suportados. Outros conjuntos de dados, como conjuntos de dados de pesquisa, não são suportados.
- A compilação não transforma de maneira alguma o campo usado para compilação. A compilação usa o valor no campo especificado de acordo com a sua versão no conjunto de dados não compilado no data lake.
- O processo de compilação diferencia maiúsculas de minúsculas. Por exemplo, se tanto a palavra “Bob” quanto a palavra “BOB” aparecerem em algumas instâncias do campo, essas IDs serão tratadas como duas pessoas separadas.

Não confunda a compilação com:

- A mesclagem de dois ou mais conjuntos de dados. A compilação se aplica a apenas um conjunto de dados. A mesclagem de conjuntos de dados ocorre ao configurar uma conexão do Customer Journey Analytics e selecionar a mesma ID de pessoa nos conjuntos de dados selecionados na conexão.

- A associação de dois conjuntos de dados. No Customer Journey Analytics, uma associação é frequentemente usada para pesquisas ou classificações no Analysis Workspace. Embora a compilação use a funcionalidade de associação, o próprio processo envolve mais do que associações.

>[!MORELIKETHIS]
>
>[Compilação baseada em campos](fbs.md)
>>[Compilação baseada em gráficos](gbs.md)
>>[Usar compilação](use-stitching.md)
>>[Validar compilação](validate.md)
>>[Perguntas frequentes sobre compilação](faq.md)

