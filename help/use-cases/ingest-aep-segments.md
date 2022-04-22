---
title: Assimilar públicos da AEP no Customer Journey Analytics
description: Explica como assimilar públicos-alvo do AEP no Customer Journey Analytics para análise adicional.
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: cd1d639ad698c188c506881b2b17103b0a3559f2
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 2%

---


# Assimilar públicos da AEP no Customer Journey Analytics (CJA)

(Brandon, para sua informação, &quot;Perfil unificado&quot; é um termo obsoleto para &quot;Perfil do cliente em tempo real&quot; - de acordo com o gerente de documentação da AEP. Você não encontrará nenhum documento no UP no conjunto de documentos do AEP.)

Esse caso de uso explora uma maneira temporária e manual de trazer públicos-alvo da Adobe Experience Platform (AEP) para o CJA. Esses públicos-alvo podem ter sido criados no Construtor de segmentos da AEP, no Adobe Audience Manager ou em outras ferramentas e são armazenados no Perfil do cliente em tempo real (RTCP). Os públicos-alvo consistem em listas de IDs de pessoa, IDs de perfil, etc. e queremos trazê-los para o CJA Workspace para análise.

## Pré-requisitos

* Acesso ao Adobe Experience Platform (AEP), especificamente Perfil do cliente em tempo real.
* Acesso ao Customer Journey Analytics
* Capacidade de gravar código personalizado?
* O que mais.

## Etapa 1: Escolha o(s) público(s) no Perfil do cliente em tempo real {#audience}

Adobe Experience Platform [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR) (RTCP) permite ver uma visão holística de cada cliente individual ao combinar dados de vários canais, incluindo online, offline, CRM e de terceiros. Você provavelmente já tem públicos-alvo em RTCP que podem ter vindo de várias fontes. Escolha um ou mais públicos-alvo.

## Etapa 2: Criar um conjunto de dados de União de perfil para a exportação

Para exportar o público-alvo para um conjunto de dados que pode fazer uma conexão com o CJA, é necessário criar um conjunto de dados cujo esquema é um Perfil [Schema da União](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).
Os esquemas de união são compostos de vários esquemas que compartilham a mesma classe e foram habilitados para o Perfil. O schema union permite ver uma combinação de todos os campos contidos em schemas que compartilham a mesma classe. O Perfil do cliente em tempo real usa o schema de união para criar uma visualização holística de cada cliente individual.

## Etapa 3: Exportar um público-alvo para um conjunto de dados por meio de uma chamada de API {#export}

Antes de trazer um público-alvo para o CJA, é necessário exportá-lo para um conjunto de dados no AEP. Isso só pode ser feito usando a API de segmentação e, especificamente, o [Exporte o Ponto de Extremidade da API de Tarefas](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en). Você pode criar um trabalho de exportação e colocar os resultados no conjunto de dados AEP da União de perfis que você criou na Etapa 2.

## Etapa 4: Editar a saída de exportação

Ao criar o trabalho de exportação para um público-alvo, precisamos apenas da ID de pessoa e da ID de público-alvo para fazer os relatórios no CJA. No entanto, o trabalho de exportação padrão contém mais dados e, portanto, precisamos editar essa saída para remover dados irrelevantes.

Este é um exemplo da saída de exportação no conjunto de dados da união de perfis, **before** qualquer edição:

![Saída não permitida](assets/export-unedited.png)

Observe o seguinte:

* A ID de público-alvo está contida em `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* O status deve ser &quot;realizado&quot; ou &quot;inserido&quot;, mas não &quot;fechado&quot;. Substitua &quot;sair&quot; por &quot;em branco&quot;.

Esse é o formato do conjunto de dados do Perfil que você pode enviar para o CJA.

![Saída editada](assets/export-edited.png)

Estes são os elementos de dados que precisam estar presentes:

* `_aresprodvalidation`: Refere-se à ID da organização. O seu será diferente.
* `personID`: Nesse caso, um nome amigável
* `audienceMembershipIdList` campo de string: A ID de público-alvo
* Adicione um nome amigável para o público-alvo (`audienceMembershipIdName`), como

   ![Nome amigável do público](assets/audience-name)

## Etapa 5: Criar uma conexão no CJA com este conjunto de dados de perfil

[Criar uma conexão](/help/connections/create-connection.md)

## Etapa 6: Criar uma visualização de dados

Adicionar `audienceMembershipIdName` e `personID` à exibição de dados.

## Etapa 7: Relatório no Workspace

Agora você pode criar relatórios sobre `audienceMembershipIdName` e `personID` no Workspace.
A imagem seria ótima.

Para fazer:

crie mais etapas para quando estiver lidando com pessoas que são membros de vários públicos-alvo.




