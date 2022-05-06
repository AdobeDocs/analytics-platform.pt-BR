---
title: Assimilar públicos da AEP no Customer Journey Analytics
description: Explica como assimilar públicos-alvo do AEP no Customer Journey Analytics para análise adicional.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: 490a754270922481ebd893514c530a0667d9d6e4
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 1%

---

# Assimilar públicos da AEP no Customer Journey Analytics (CJA)

Esse caso de uso explora uma maneira temporária e manual de trazer públicos-alvo da Adobe Experience Platform (AEP) para o CJA. Esses públicos-alvo podem ter sido criados no Construtor de segmentos da AEP, no Adobe Audience Manager ou em outras ferramentas e são armazenados no Perfil do cliente em tempo real (RTCP). Os públicos-alvo consistem em um conjunto de IDs de perfil, juntamente com quaisquer atributos/eventos/etc. aplicáveis. e queremos trazê-los para o CJA Workspace para análise.

## Pré-requisitos

* Acesso ao Adobe Experience Platform (AEP), especificamente Perfil do cliente em tempo real.
* Acesso para criar/gerenciar esquemas e conjuntos de dados do AEP.
* Acesso ao AEP Query Service (e a capacidade de gravar SQL) ou a uma ferramenta diferente para executar algumas transformações de luz.
* Acesso ao Customer Journey Analytics. Você precisa ser um administrador de produto do CJA para criar/modificar conexões e visualizações de dados do CJA.
* Capacidade de usar as APIs do Adobe (Segmentação, opcionalmente outras)

## Etapa 1: Escolha o(s) público(s) no Perfil do cliente em tempo real {#audience}

Adobe Experience Platform [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR) (RTCP) permite ver uma visão holística de cada cliente individual ao combinar dados de vários canais, incluindo online, offline, CRM e de terceiros.

Você provavelmente já tem públicos-alvo em RTCP que podem ter vindo de várias fontes. Escolha um ou mais públicos-alvo para assimilar no CJA.

## Etapa 2: Criar um conjunto de dados de União de perfil para a exportação

Para exportar o público-alvo para um conjunto de dados que possa ser adicionado a uma conexão no CJA, é necessário criar um conjunto de dados cujo esquema é um Perfil [Schema da União](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).

Os esquemas de união são compostos de vários esquemas que compartilham a mesma classe e foram habilitados para o Perfil. O schema union permite ver uma combinação de todos os campos contidos em schemas que compartilham a mesma classe. O Perfil do cliente em tempo real usa o schema de união para criar uma visualização holística de cada cliente individual.

## Etapa 3: Exportar um público-alvo para o conjunto de dados da União de perfis por meio da chamada de API {#export}

Antes de trazer um público para o CJA, é necessário exportá-lo para um conjunto de dados da AEP. Isso só pode ser feito usando a API de segmentação e, especificamente, o [Exporte o Ponto de Extremidade da API de Tarefas](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en).

Você pode criar um trabalho de exportação usando a ID de público-alvo de sua escolha e colocar os resultados no conjunto de dados da AEP da União de perfis que você criou na Etapa 2. Embora seja possível exportar vários atributos/eventos para o público-alvo, é necessário exportar apenas o campo de ID de perfil específico que corresponde ao campo de ID de pessoa usado na conexão do CJA que você está aproveitando (veja abaixo na Etapa 5).

## Etapa 4: Editar a saída de exportação

Os resultados do trabalho de exportação precisam ser transformados em um conjunto de dados de Perfil separado para serem assimilados no CJA.  Essa transformação pode ser feita com o AEP Query Service ou outra ferramenta de transformação de sua escolha.  Somente precisamos da ID de perfil (que corresponderá à ID de pessoa no CJA) e uma ou mais IDs de público-alvo para fazer o relatório no CJA. No entanto, o trabalho de exportação padrão contém mais dados e, portanto, precisamos editar essa saída para remover dados irrelevantes, bem como mover algumas coisas.  Além disso, é necessário criar um esquema/conjunto de dados primeiro antes de adicionar os dados transformados a ele.

Este é um exemplo da saída de exportação no conjunto de dados da união de perfis, **before** qualquer edição:

![Saída não permitida](assets/export-unedited.png)

Observe o seguinte:

* A ID de público-alvo está contida em `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* O status deve ser &quot;realizado&quot; ou &quot;inserido&quot;, mas não &quot;fechado&quot;.

Esse é o formato do conjunto de dados do Perfil que você pode enviar para o CJA.

![Saída editada](assets/export-edited.png)

Estes são os elementos de dados que precisam estar presentes:

* `_aresprodvalidation` campo de string: Refere-se à ID da organização. O seu será diferente.
* `personID` campo de string: Este é o campo de esquema XDM padrão nos conjuntos de dados do perfil para identificar a pessoa. Use a ID de perfil da exportação.
* `audienceMembershipId` campo de string: A ID de público-alvo da exportação.  OBSERVAÇÃO: Esse campo pode ser nomeado conforme desejar (de seu próprio schema).
* Adicione um nome amigável para o público-alvo (`audienceMembershipIdName`), como

   ![Nome amigável do público](assets/audience-name.png)

* Adicione outros metadados de público-alvo, se desejar.

## Etapa 5: Adicionar este conjunto de dados de perfil a uma conexão existente no CJA

Você pode criar uma nova conexão, mas a maioria dos clientes deseja adicioná-la a uma conexão existente. As IDs de público-alvo &quot;enriquecem&quot; os dados existentes no CJA.

[Criar uma conexão](/help/connections/create-connection.md)

## Etapa 6: Modificar a visualização de dados CJA existente (ou criar nova)

Adicionar `audienceMembershipId`, `audienceMembershipIdName` e `personID` para a visualização de dados.

## Etapa 7: Relatório no Workspace

Agora você pode criar relatórios sobre `audienceMembershipId`, `audienceMembershipIdName` e `personID` no Workspace.

## Observações adicionais

* Você deve executar esse processo regularmente, para que os dados do público-alvo sejam atualizados constantemente no CJA.
* Você pode importar vários públicos-alvo em uma única conexão do CJA. Isso adiciona complexidade adicional ao processo, mas é possível. Para que isso funcione, é necessário fazer algumas modificações no processo acima:
   1. Execute esse processo para cada público-alvo desejado em sua coleção de público-alvo dentro do RTCP.
   1. Ao executar as transformações da saída do trabalho de exportação, será necessário criar uma lista de `audienceMembershipId(s)`, pois uma única ID de pessoa do CJA pode pertencer a vários públicos. Em algum ponto no futuro, o CJA oferecerá suporte a arrays/arrays de objetos em conjuntos de dados de perfil. Quando esses objetos forem suportados, usando uma matriz de objetos para a variável `audienceMembershipId` ou `audienceMembershipIdName` será a melhor opção. Entretanto, extraia todas as IDs de público-alvo atuais para cada ID de perfil na saída do trabalho de exportação (com o status &quot;realizado&quot; ou &quot;inserido&quot;) e as coloca em uma cadeia de caracteres de valores separados por vírgula (ou seja, `<id1>,<id2>,...`).  Se houver uma ID de público-alvo com o status de &quot;encerrado&quot;, verifique se ela NÃO está na lista.  Se quiser manter a associação do nome amigável com a ID, é possível anexá-la ao final de cada ID na lista (juntamente com quaisquer outros metadados).
   1. Na visualização de dados, crie uma nova dimensão usando a transformação de Substring na `audienceMembershipId` para converter a string de valores separados por vírgula em uma matriz. OBSERVAÇÃO: atualmente, há um limite de 10 valores na matriz.
   1. Agora você pode relatar sobre essa nova dimensão `audienceMembershipIds` no CJA Workspace.
