---
title: Assimilar públicos-alvo da Adobe Experience Platform no Customer Journey Analytics
description: Explica como assimilar públicos-alvo da Adobe Experience Platform no Customer Journey Analytics para análise adicional.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 51%

---

# Assimilar públicos da Adobe Experience Platform na Adobe Customer Journey Analytics

Esse caso de uso explora uma maneira temporária e manual de trazer públicos-alvo da Adobe Experience Platform (Adobe Experience Platform) para o Customer Journey Analytics. Esses públicos-alvo podem ter sido criados no Construtor de segmentos do Adobe Experience Platform, no Adobe Audience Manager ou em outras ferramentas e são armazenados no Perfil do cliente em tempo real (RTCP). Os públicos-alvo consistem em um conjunto de IDs de perfil, juntamente com quaisquer atributos/eventos/etc. aplicáveis. e queremos trazê-los ao Customer Journey Analytics Workspace para análise.

## Pré-requisitos 

* Acesso ao Adobe Experience Platform (Adobe Experience Platform), especificamente ao Perfil do cliente em tempo real.
* Acesso para criar/gerenciar esquemas e conjuntos de dados da Adobe Experience Platform.
* Acesso ao Adobe Experience Platform Query Service (e a capacidade de gravar SQL) ou a uma ferramenta diferente para executar algumas pequenas transformações.
* Acesso ao Customer Journey Analytics. Você precisa ser um administrador de produto do Customer Journey Analytics para criar/modificar conexões Customer Journey Analytics e visualizações de dados.
* Capacidade de usar as APIs da Adobe (Segmentação, opcionalmente outras)

## Etapa 1: Escolher os públicos-alvo no Perfil do cliente em tempo real {#audience}

O [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR) (RTCP) da Adobe Experience Platform oferece uma visão holística de cada cliente individual ao combinar dados de vários canais, incluindo online, offline, CRM e de terceiros.

Você provavelmente já tem públicos-alvo no RTCP que podem ter vindo de várias fontes. Escolha um ou mais públicos-alvo para assimilar no Customer Journey Analytics.

## Etapa 2: Criar um conjunto de dados de União de perfil para a exportação

Para exportar o público-alvo para um conjunto de dados que possa ser adicionado a uma conexão no Customer Journey Analytics, é necessário criar um conjunto de dados cujo esquema é um Perfil [Esquema de união](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=pt-BR#understanding-union-schemas).

Os esquemas de união são compostos de vários esquemas que compartilham a mesma classe e foram habilitados para o Perfil. O esquema de união permite ver uma combinação de todos os campos contidos em esquemas que compartilham a mesma classe. O Perfil do cliente em tempo real usa o esquema de união para criar uma visualização holística de cada cliente individual.

## Etapa 3: Exportar um público-alvo para o conjunto de dados União de perfis por meio da chamada de API {#export}

Antes de trazer um público para o Customer Journey Analytics, é necessário exportá-lo para um conjunto de dados do Adobe Experience Platform. Isso só pode ser feito usando a API de segmentação e, especificamente, o [Ponto de extremidade da API de tarefas de exportação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=pt-BR).

Você pode criar um trabalho de exportação usando a ID de público-alvo de sua escolha e colocar os resultados no conjunto de dados da Adobe Experience Platform da União de perfis que você criou na Etapa 2. Embora seja possível exportar vários atributos/eventos para o público-alvo, é necessário exportar apenas o campo de ID de perfil específico que corresponde ao campo de ID de pessoa usado na conexão Customer Journey Analytics que você está usando (veja abaixo na Etapa 5).

## Etapa 4: Editar a saída de exportação

Os resultados do trabalho de exportação precisam ser transformados em um conjunto de dados de Perfil separado para serem assimilados no Customer Journey Analytics.  Esta transformação pode ser feita com o [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=pt-BR) ou outra ferramenta de transformação de sua escolha. Somente precisamos da ID de perfil (que corresponderá à ID de pessoa no Customer Journey Analytics) e uma ou mais IDs de público-alvo para fazer o relatório no Customer Journey Analytics.

No entanto, o trabalho de exportação padrão contém mais dados e, portanto, precisamos editar essa saída para remover dados irrelevantes, bem como mover algumas coisas. Além disso, é necessário criar um esquema/conjunto de dados primeiro antes de adicionar os dados transformados a ele.

Este é um exemplo da saída de exportação no conjunto de dados da união de perfis, **antes** de qualquer edição:

![Saída não editada](../assets/export-unedited.png)

Observe o seguinte:

* A ID de público-alvo está contida em `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* O status deve ser “realizado” ou “inserido”, mas não “fechado”.

Esse é o formato do conjunto de dados do Perfil que você pode enviar para o Customer Journey Analytics.

![Saída editada](../assets/export-edited.png)

Estes são os elementos de dados que precisam estar presentes:

* Campo de string do `_aresprodvalidation`: refere-se à ID da organização. O seu será diferente.
* Campo de string do `personID`: é o campo de esquema XDM padrão nos conjuntos de dados do perfil para identificar a pessoa. Use a ID de perfil da exportação.
* Campo de string do `audienceMembershipId`: a ID de público-alvo da exportação.  OBSERVAÇÃO: esse campo pode ser nomeado como você quiser (a partir do seu próprio esquema).
* Adicione um nome intuitivo para o público-alvo (`audienceMembershipIdName`), como

  ![Nome intuitivo do público-alvo](../assets/audience-name.png)

* Adicione outros metadados de público-alvo, se desejar.

## Etapa 5: Adicionar este conjunto de dados de perfil a uma conexão existente no Customer Journey Analytics

Você poderia [criar uma nova conexão](/help/connections/create-connection.md), mas a maioria dos clientes desejará adicionar o conjunto de dados do Perfil a uma conexão existente. As IDs de público-alvo &quot;enriquecem&quot; os dados existentes no Customer Journey Analytics.

## Etapa 6: Modificar a visualização de dados de Customer Journey Analytics existente (ou criar nova)

Adicionar `audienceMembershipId`, `audienceMembershipIdName` e `personID` para a visualização de dados.

## Etapa 7: relatório no Espaço de trabalho

Agora você pode criar relatórios sobre `audienceMembershipId`, `audienceMembershipIdName` e `personID` no Espaço de trabalho.

## Observações adicionais

* Você deve executar esse processo regularmente para que os dados do público-alvo sejam atualizados constantemente no Customer Journey Analytics.
* Você pode importar vários públicos-alvo em uma única conexão Customer Journey Analytics. Isso adiciona mais complexidade ao processo, mas é possível. Para que isso funcione, é necessário fazer algumas modificações no processo acima:
   1. Execute esse processo para cada público-alvo desejado em sua coleção de públicos-alvo no RTCP.
   1. O Customer Journey Analytics oferece suporte a matrizes/matrizes de objetos em conjuntos de dados de perfil. Uso de uma [array de objetos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html?lang=pt-BR) para audienceMembershipId ou audienceMembershipIdName é a melhor opção.
   1. Na visualização de dados, crie uma nova dimensão usando a transformação de Substring no campo `audienceMembershipId` para converter a string de valores separados por vírgula em uma matriz. OBSERVAÇÃO: atualmente, há um limite de 10 valores na matriz.
   1. Agora você pode relatar sobre esta nova dimensão `audienceMembershipIds` no Customer Journey Analytics Workspace.
