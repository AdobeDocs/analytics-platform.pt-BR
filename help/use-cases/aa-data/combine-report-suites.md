---
title: Combinar conjuntos de relatórios com esquemas diferentes
description: Saiba como usar o Preparo de dados para combinar conjuntos de relatórios com esquemas diferentes
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
source-git-commit: 69356510596d047d80af63338fccca71e8af53cd
workflow-type: ht
source-wordcount: '1335'
ht-degree: 100%

---

# Combinar conjuntos de relatórios com esquemas diferentes

O [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) traz dados do conjunto de relatórios do Adobe Analytics para a Adobe Experience Platform (AEP) para uso por aplicativos da AEP, como a Real-time Customer Data Platform e o Customer Journey Analytics (CJA). Cada conjunto de relatórios trazido para a AEP é configurado como um fluxo de dados de conexão de origem individual e cada fluxo de dados chega como um conjunto de dados no data lake da AEP. O Conector de origem do Analytics cria um conjunto de dados por conjunto de relatórios.

Clientes do CJA usam [conexões](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR) para integrar conjuntos de dados do dat lake da AEP ao Analysis Workspace do CJA. No entanto, ao combinar conjuntos de relatórios em uma conexão, as diferenças de esquema entre conjuntos de relatórios precisam ser resolvidas usando a funcionalidade [Preparo de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR). O objetivo é garantir que variáveis do Adobe Analytics, como props e eVars, tenham um significado consistente no CJA.

## As diferenças de esquema entre conjuntos de relatórios são problemáticas

Suponha que sua empresa queira trazer dados de dois conjuntos de relatórios diferentes para a AEP para uso pelo CJA e suponha que os esquemas dos dois conjuntos de relatórios tenham diferenças:

| Conjunto de relatórios A | Conjunto de relatórios B |
| --- | --- |
| eVar1 = Termo de pesquisa | eVar1 = Unidade de negócios |
| eVar2 = Categoria do cliente | eVar2 = Termo de pesquisa |

Por uma questão de simplicidade, considere que essas são as únicas eVars definidas para ambos os conjuntos de relatórios.

Além disso, suponha que você execute as seguintes ações:

- Crie uma conexão de origem do Analytics (sem usar o preparo de dados) que assimila o **Conjunto de relatórios A** no data lake da AEP como **Conjunto de dados A**.
- Crie uma conexão de origem do Analytics (sem usar o preparo de dados) que assimila o **Conjunto de relatórios B** no data lake da AEP como o **Conjunto de dados B**.
- Crie uma [Conexão do CJA](/help/connections/create-connection.md) chamada **Todos os conjuntos de relatórios** que combina o conjunto de dados A e o conjunto de dados B.
- Crie um [Exibição de dados do CJA](/help/data-views/create-dataview.md) chamada **Exibição global** que se baseia na conexão Todos os conjuntos de relatórios.

Sem o uso do Preparo de dados para resolver as diferenças de esquema entre o Conjunto de dados A e o Conjunto de dados B, as eVars na exibição de dados da Exibição global conterão uma mistura de valores:

| Exibição de dados global no CJA |
| --- |
| eVar1 => uma combinação de termos de pesquisa e unidades de negócios |
| eVar2 => uma combinação de categorias de clientes e termos de pesquisa |

Essa situação resulta em relatórios sem sentido para a eVar1 e a eVar2:

- Os campos de eVar contêm uma mistura de valores com significados semânticos diferentes.
- Os termos de pesquisa são distribuídos entre a eVar1 e a eVar2.
- Não é possível usar modelos de atribuição diferentes para cada um dos termos de pesquisa, unidades de negócios e categorias de clientes.

## Usar o Preparo de dados da AEP para resolver diferenças de esquema entre conjuntos de relatórios

A funcionalidade Preparo de dados da Experience Platform é integrada ao Conector de origem do Analytics e pode ser usada para resolver as diferenças de esquema descritas no cenário acima. Isso resulta em eVars com significados consistentes na visualização de dados do CJA. (As convenções de nomenclatura usadas abaixo podem ser personalizadas para atender às suas necessidades.)

1. Antes de criar os fluxos de dados da conexão de origem para o Conjunto de relatórios A e o Conjunto de relatórios B, [crie um novo esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=pt-BR) na AEP (vamos chamá-lo de **Esquema unificado** em nosso exemplo.) Adicione o seguinte ao esquema:

   | “Esquema unificado” |
   | --- |
   | Classe **XDM ExperienceEvent** |
   | Grupo de campos **Modelo ExperienceEvent do Adobe Analytics** |

1. Adicione outro grupo de campos ao esquema ou [crie um grupo de campos personalizado](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=pt-BR#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail) e adicione-o ao esquema. Criaremos um novo grupo de campos e o chamaremos de **Campos unificados**. Em seguida, adicionaremos os seguintes campos ao novo grupo de campos:

   | Grupo de campos personalizado “Campos unificados”  |
   | --- |
   | Termo de pesquisa |
   | Unidade de negócios |
   | Categoria do cliente |

1. Crie o fluxo de dados da conexão de origem para o **Conjunto de relatórios A**, selecionando **Esquema unificado** para uso no fluxo de dados. Adicione mapeamentos personalizados ao fluxo de dados da seguinte maneira:

   | Conjunto de origem do Conjunto de relatórios A | Campo de grupos Campo de destino de campos unificados |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >O caminho XDM para os campos de destino dependerá de como você estruturar o grupo de campos personalizados.

1. Crie o fluxo de dados da conexão de origem para o **Conjunto de relatórios B**, selecionando novamente **Esquema unificado** para uso no fluxo de dados. O fluxo de trabalho mostrará que dois campos têm um conflito de nome de descritor. Isso ocorre porque os descritores da eVar1 e da eVar2 são diferentes no Conjunto de relatórios B do que eram no Conjunto de relatórios A. Mas já sabemos disso, para que possamos ignorar com segurança o conflito e usar mapeamentos personalizados da seguinte maneira:

   | Campo de origem do Conjunto de relatórios B | Campo de grupos Campo de destino de campos unificados |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. Agora crie uma conexão **Todos os conjuntos de relatórios** para o CJA, combinando o Conjunto de dados A e o Conjunto de dados B.

1. Crie uma visualização de dados **Exibição global** no CJA. Ignore os campos de eVar originais e inclua apenas os campos do grupo Campos unificados.

   Visualização de dados **Exibição global** no CJA:

   | Campo de origem | Incluir na visualização de dados? |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | Não |
   | \_experience.analytics.customDimensions.eVars.eVar2 | Não |
   | _\&lt;path>_.Search_term | Sim |
   | _\&lt;path>_.Customer_category  | Sim |
   | _\&lt;path>_.Business_unit | Sim |

Agora você mapeou a eVar1 e a eVar2 dos conjuntos de relatórios de origem para três novos campos. Observe que outra vantagem de usar os mapeamentos do Preparo de dados é que os campos de destino agora se baseiam em nomes semanticamente significativos (termo de pesquisa, unidade de negócios, categoria de cliente) em vez dos nomes de eVar menos significativos (eVar1, eVar2).

>[!NOTE]
>
>O grupo de campos personalizados Campos unificados e os mapeamentos de campo associados podem ser adicionados aos fluxos de dados e conjuntos de dados existentes do Conector de origem do Analytics a qualquer momento. No entanto, isso afeta apenas os dados futuros.

## Mais do que apenas conjuntos de relatórios

Os recursos do Preparo de dados para combinar conjuntos de dados com esquemas diferentes vão além dos conjuntos de relatórios do Analytics. Suponha que você tenha dois conjuntos de dados com os seguintes dados:

| Conjunto de dados A = Conjunto de relatórios do Analytics via Conector de origem do Analytics |
| --- |
| `eVar1` => Categoria do cliente |

| Conjunto de dados B = Dados da central de atendimento |
| --- |
| Some_field => Categoria do cliente |

Usando o Preparo de dados, você pode combinar a Categoria do cliente na eVar 1 nos dados do Analytics com a Categoria do cliente no campo Some_field na central de atendimento. Aqui está uma maneira de fazer isso. Novamente, a convenção de nomenclatura pode ser alterada para atender às suas necessidades.

1. Crie um esquema na AEP. Adicione o seguinte ao esquema:

   | “Esquema estendido” |
   | --- | 
   | Classe **Evento de experiência do XDM** |
   | Grupo de campos **Modelo de evento de experiência do Adobe Analytics** |

1. Crie um novo grupo de campos e adicione-o ao esquema. Adicionar campos ao grupo de campos:

   | Grupo de campos personalizados “Informações do cliente”  |
   | --- |
   | Customer_category |

1. Crie o fluxo de dados para **Conjunto de dados A**, selecionando **Esquema estendido** como esquema. Adicione mapeamentos personalizados ao fluxo de dados da seguinte maneira:

   | Campo de origem do conjunto de dados A | Campo de destino do grupo de campos de informações do cliente |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. Crie o fluxo de dados para o **Conjunto de dados B**, selecionando novamente o **Esquema estendido** como esquema. Adicione mapeamentos personalizados ao fluxo de dados da seguinte maneira:

   | Campo de origem do conjunto de dados B | Campo de destino do grupo de campos de informações do cliente |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

1. Crie uma conexão do CJA que combine o Conjunto de dados A e o Conjunto de dados B.

1. Crie uma visualização de dados no CJA usando a conexão CJA recém-criada. Ignore os campos de eVar originais e inclua apenas os campos do grupo de campos Informações do cliente.

   Exibição de dados no CJA:

   | Campo de origem | Incluir na visualização de dados? |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | Não |
   | \_experience.analytics.customDimensions.eVars.eVar2 | Não |
   | _\&lt;path>_.Customer_category | Sim |

## Preparo de dados vs. ID de componente

Conforme descrito acima, o Preparo de dados permite mapear campos diferentes em conjunto em vários conjuntos de relatórios do Adobe Analytics. Isso é útil no CJA quando você deseja combinar dados de vários conjuntos de dados em uma única conexão do CJA. No entanto, se você pretende manter os conjuntos de relatórios em conexões do CJA separadas, mas deseja usar um conjunto de relatórios nessas conexões e visualizações de dados, alterar a ID do componente subjacente no CJA fornece uma maneira de tornar os relatórios compatíveis, mesmo que os esquemas sejam diferentes. Consulte [Configurações do componente](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=pt-BR) para obter mais informações.

A alteração da ID do componente é uma função somente do CJA e não afeta dados do Conector de origem do Analytics enviados para o Perfil do cliente em tempo real e para a RTCDP.
