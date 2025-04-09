---
title: Conceitos e recursos do Customer Journey Analytics B2B edition
description: Conceitos e recursos da B2B edition do Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: true
hidefromtoc: true
badgePremium: label="B2B edition"
exl-id: df2cc922-d214-49b9-8fdb-443cc1dac05b
source-git-commit: 3812b10e558c1b8a3ee4fe474405543c68433d8e
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 0%

---

# Conceitos e recursos do B2B edition

{{draft-b2b}}

Este artigo explica os conceitos e recursos gerais sobre conjuntos de dados e containers e como eles diferem entre o padrão e o B2B edition do Customer Journey Analytics.

Os conjuntos de dados são as fontes de uma conexão. Como parte da configuração de uma conexão, você define conjuntos de dados como parte dessa conexão.

Os contêineres são usados no Customer Journey Analytics para oferecer suporte e facilitar recursos como filtros, métricas calculadas e recursos de análise avançados.




## Contêineres padrão

A versão *standard* do Customer Journey Analytics é criada com base no conceito de três contêineres: Pessoa, Sessão e Evento. Em uma configuração padrão do Customer Journey Analytics, esses contêineres relevantes são gerados implicitamente com base na sua configuração.

É possível redefinir como esses contêineres são nomeados ao configurar uma Visualização de dados, mas conceitualmente a versão padrão usa uma hierarquia de contêiner baseada em pessoas.

![B2C](assets/b2c-containers.svg){zoomable="yes"}

Na conexão, você adiciona os conjuntos de dados Evento, Perfil e Pesquisa e seleciona identidades a serem usadas para definir a conexão entre esses conjuntos de dados. Como parte da conexão, uma hierarquia de contêiner com base em pessoa é gerada automaticamente. Nessa hierarquia, o contêiner Sessão é definido pelas [Configurações de sessão](/help/data-views/session-settings.md) na visualização de dados.


## Contêineres B2B

No Customer Journey Analytics B2B edition, um contêiner de Conta é adicionado à lista de contêineres gerados.  E você tem a opção de configurar a geração de contêineres adicionais, como Conta global, Grupo de compra e Oportunidade.

![B2B](assets/b2b-containers.svg){zoomable="yes"}

Na conexão, você adiciona Evento, Conta, Conta global, Oportunidade, Grupo de compras e outros conjuntos de dados de Pesquisa. Você seleciona Conta como a ID primária da conexão para que possa usar identidades baseadas em conta para definir a conexão entre os conjuntos de dados. Como parte da conexão, uma hierarquia de container baseada em conta é gerada automaticamente. Nessa hierarquia, o contêiner Sessão entre o contêiner Pessoa e o contêiner Evento é definido pelas [configurações Sessão](/help/data-views/session-settings.md) na visualização de Dados. Além disso, os contêineres Sessão, por exemplo, entre Conta e Evento, não são suportados no momento.

Oportunidade, Grupo de Compras e Pessoa são todos contêineres irmãos do contêiner Conta. Consulte a tabela abaixo para obter uma descrição e um uso básico.

| Contêiner B2B | Descrição<br/>Caso de uso básico |
|---|---|
| Conta | Uma empresa que é um cliente ou um cliente potencial de seu negócio. Pode ser uma subsidiária ou divisão de uma organização maior. Conta representa a organização para a qual você está vendendo e que deseja rastrear nesse nível de organização. |
| Conta global (opcional) | A principal empresa-mãe de um grupo de empresas relacionadas. Uma conta global não tem uma empresa principal, mas pode ter subsidiárias ou divisões pertencentes à conta global. Uma conta que não tenha pais ou subsidiárias deve ser listada nos campos conta e conta global, se ambos estiverem ativados como parte da configuração de uma conexão. |
| Oportunidade (opcional) | Uma coleção de produtos e serviços que são vendidos juntos. Uma oportunidade geralmente envolvia vários estágios no ciclo de vendas para fechar como uma venda.<br>Você usaria os dados da oportunidade para medir a progressão da oportunidade no funil de vendas. Por exemplo, um relatório que fornece detalhes sobre as principais oportunidades que passaram do estágio 3 para o estágio 4. |
| Grupo de compras (opcional) | Uma coleção de pessoas em uma organização que está envolvida no processo de tomada de decisão para comprar um produto ou serviço. <br/>Você usaria os dados do grupo de compras para acompanhar grupos de compras através do gerenciamento de campanhas. Por exemplo, criou um segmento de público-alvo dos principais grupos de compra.<br/> Provavelmente você deseja realizar uma pesquisa a partir do grupo de compras para os dados do perfil, para poder relatar as pessoas de um grupo de compras. |
| Pessoa | Um indivíduo, geralmente identificado por um endereço de e-mail exclusivo que interagiu com a empresa. <br/>Você usaria os dados do perfil para identificar as pessoas que trabalham em uma conta. Por exemplo: direcione a todas as pessoas em uma conta que se inscreveram para uma conferência. |


## Corresponder por contêiner ou campo

Ao definir uma conexão no Customer Journey Analytics, você pode definir para cada conjunto de dados de registro (perfil ou pesquisa) se esse conjunto de dados é correspondido pelo contêiner ou pelo campo.

### Corresponder por container

Se um conjunto de dados de registro for correspondido por um contêiner, por exemplo, Grupo de compras, o conjunto de dados de registro será tratado como um tipo de conjunto de dados de perfil e como um conjunto de dados de perfil na interface do usuário.

### Corresponder por campo

Se um conjunto de dados de registro for correspondido pelo campo, por exemplo, Membro da lista de marketing, o conjunto de dados do registro será tratado como um tipo de conjunto de dados de pesquisa e como um conjunto de dados de Pesquisa na interface do usuário.



## Relatório sobre dados baseados em pessoa e conta

Se quiser criar relatórios sobre contêineres com base em pessoas (e identidades de pessoas) e contêineres com base em contas (e identidades de contas), configure duas conexões separadas no Customer Journey Analytics. Uma conexão em que você seleciona Pessoa como a ID principal e uma conexão em que você seleciona Conta como a ID principal. O Customer Journey Analytics não oferece suporte a relatórios com base em pessoas e em contas do mesmo contêiner.
