---
title: Assimilar públicos-alvo da AEP no Customer Journey Analytics
description: Explica como assimilar públicos-alvo da AEP no Customer Journey Analytics para análise adicional.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: af9113f3afced902b385747bceaa9e51b72d83e6
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 99%

---

# Assimilar públicos-alvo da AEP no Customer Journey Analytics (CJA)

Esse caso de uso explora uma maneira temporária e manual de trazer públicos-alvo da Adobe Experience Platform (AEP) para o CJA. Esses públicos-alvo podem ter sido criados no Construtor de segmentos da AEP, no Adobe Audience Manager ou em outras ferramentas e são armazenados no Perfil do cliente em tempo real (RTCP). Os públicos-alvo consistem em um conjunto de IDs de perfil, juntamente com quaisquer atributos/eventos/etc. aplicáveis. e queremos trazê-los para o Espaço de trabalho do CJA para análise.

## Pré-requisitos

* Acesso à Adobe Experience Platform (AEP), especificamente ao Perfil do cliente em tempo real.
* Acesso para criar/gerenciar esquemas e conjuntos de dados da AEP.
* Acesso ao Serviço de consulta da AEP (e a capacidade de gravar SQL) ou a uma ferramenta diferente para executar algumas pequenas transformações.
* Acesso ao Customer Journey Analytics. Você precisa ser um administrador de produto do CJA para criar/modificar conexões e visualizações de dados do CJA.
* Capacidade de usar as APIs da Adobe (Segmentação, opcionalmente outras)

## Etapa 1: Escolher os públicos-alvo no Perfil do cliente em tempo real {#audience}

O [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR) (RTCP) da Adobe Experience Platform oferece uma visão holística de cada cliente individual ao combinar dados de vários canais, incluindo online, offline, CRM e de terceiros.

Você provavelmente já tem públicos-alvo no RTCP que podem ter vindo de várias fontes. Escolha um ou mais públicos-alvo para assimilar no CJA.

## Etapa 2: Criar um conjunto de dados de União de perfil para a exportação

Para exportar o público-alvo para um conjunto de dados que possa ser adicionado a uma conexão no CJA, é necessário criar um conjunto de dados cujo esquema é um Perfil [Esquema de união](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=pt-BR#understanding-union-schemas).

Os esquemas de união são compostos de vários esquemas que compartilham a mesma classe e foram habilitados para o Perfil. O esquema de união permite ver uma combinação de todos os campos contidos em esquemas que compartilham a mesma classe. O Perfil do cliente em tempo real usa o esquema de união para criar uma visualização holística de cada cliente individual.

## Etapa 3: Exportar um público-alvo para o conjunto de dados União de perfis por meio da chamada de API {#export}

Antes de trazer um público para o CJA, é necessário exportá-lo para um conjunto de dados da AEP. Isso só pode ser feito usando a API de segmentação e, especificamente, o [Ponto de extremidade da API de tarefas de exportação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=pt-BR).

Você pode criar um trabalho de exportação usando a ID de público-alvo de sua escolha e colocar os resultados no conjunto de dados da AEP da União de perfis que você criou na Etapa 2. Embora seja possível exportar vários atributos/eventos para o público-alvo, é necessário exportar apenas o campo de ID de perfil específico que corresponde ao campo de ID de pessoa usado na conexão do CJA que você está usando (veja abaixo na Etapa 5).

## Etapa 4: Editar a saída de exportação

Os resultados do trabalho de exportação precisam ser transformados em um conjunto de dados de Perfil separado para serem assimilados no CJA.  Essa transformação pode ser feita com o [Serviço de consulta da AEP](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=pt-BR) ou outra ferramenta de transformação de sua escolha. Somente precisamos da ID de perfil (que corresponderá à ID de pessoa no CJA) e uma ou mais IDs de público-alvo para fazer o relatório no CJA.

No entanto, o trabalho de exportação padrão contém mais dados e, portanto, precisamos editar essa saída para remover dados irrelevantes, bem como mover algumas coisas. Além disso, é necessário criar um esquema/conjunto de dados primeiro antes de adicionar os dados transformados a ele.

Este é um exemplo da saída de exportação no conjunto de dados da união de perfis, **antes** de qualquer edição:

![Saída não editada](../assets/export-unedited.png)

Observe o seguinte:

* A ID de público-alvo está contida em `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* O status deve ser “realizado” ou “inserido”, mas não “fechado”.

Esse é o formato do conjunto de dados do Perfil que você pode enviar para o CJA.

![Saída editada](../assets/export-edited.png)

Estes são os elementos de dados que precisam estar presentes:

* Campo de string do `_aresprodvalidation`: refere-se à ID da organização. O seu será diferente.
* Campo de string do `personID`: é o campo de esquema XDM padrão nos conjuntos de dados do perfil para identificar a pessoa. Use a ID de perfil da exportação.
* Campo de string do `audienceMembershipId`: a ID de público-alvo da exportação.  OBSERVAÇÃO: esse campo pode ser nomeado como você quiser (a partir do seu próprio esquema).
* Adicione um nome intuitivo para o público-alvo (`audienceMembershipIdName`), como

   ![Nome intuitivo do público-alvo](../assets/audience-name.png)

* Adicione outros metadados de público-alvo, se desejar.

## Etapa 5: Adicionar este conjunto de dados de perfil a uma conexão existente no CJA

Você poderia [criar uma nova conexão](/help/connections/create-connection.md), mas a maioria dos clientes desejará adicionar o conjunto de dados do Perfil a uma conexão existente. As IDs de público-alvo “enriquecem” os dados existentes no CJA.

## Etapa 6: Modificar a visualização de dados existente do CJA (ou criar nova)

Adicionar `audienceMembershipId`, `audienceMembershipIdName` e `personID` para a visualização de dados.

## Etapa 7: relatório no Espaço de trabalho

Agora você pode criar relatórios sobre `audienceMembershipId`, `audienceMembershipIdName` e `personID` no Espaço de trabalho.

## Observações adicionais

* Você deve executar esse processo regularmente para que os dados do público-alvo sejam atualizados constantemente no CJA.
* Você pode importar vários públicos-alvo em uma única conexão do CJA. Isso adiciona mais complexidade ao processo, mas é possível. Para que isso funcione, é necessário fazer algumas modificações no processo acima:
   1. Execute esse processo para cada público-alvo desejado em sua coleção de públicos-alvo no RTCP.
   1. O CJA é compatível com arrays/arrays de objetos em conjuntos de dados de perfil. Uso de uma [array de objetos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html) para audienceMembershipId ou audienceMembershipIdName é a melhor opção.
   1. Na visualização de dados, crie uma nova dimensão usando a transformação de Substring no campo `audienceMembershipId` para converter a string de valores separados por vírgula em uma matriz. OBSERVAÇÃO: atualmente, há um limite de 10 valores na matriz.
   1. Agora você pode relatar sobre essa nova dimensão `audienceMembershipIds` no Espaço de trabalho do CJA.
