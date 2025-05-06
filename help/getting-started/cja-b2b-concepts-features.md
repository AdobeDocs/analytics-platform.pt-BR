---
title: Conceitos e recursos do Customer Journey Analytics B2B edition
description: Conceitos e recursos da B2B edition do Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B edition"
exl-id: df2cc922-d214-49b9-8fdb-443cc1dac05b
source-git-commit: c021dc012f74126c6d0af5cd4ffdf908dd5c696a
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---

# Conceitos e recursos do B2B edition

{{draft-b2b}}

Este artigo explica conceitos como conexões, identificadores, contêineres e conjuntos de dados, normalmente usados no Customer Journey Analytics. E como o Customer Journey Analytics B2B edition adiciona recursos adicionais a esses conceitos.


## Conexões e identificadores

No Customer Journey Analytics, você escolhe um identificador comum, conhecido como ID de pessoa, para conectar seus dados de evento a outros conjuntos de dados, como conjunto de dados de perfil e conjuntos de dados de pesquisa. Esse tipo de conexão é conhecida como conexão com base em pessoas, o que facilita a geração de relatórios e a análise com base em pessoas.

No Customer Journey Analytics B2B edition, você pode selecionar entre uma conexão com base em pessoa ou uma conexão com base em conta. Uma conexão baseada em conta facilita a emissão de relatórios e a análise baseadas em conta.

* Para uma conexão com base em pessoas, você seleciona Pessoa como o identificador principal. Em seguida, você pode configurar e configurar sua conexão, visualização de dados e projetos do espaço de trabalho para relatórios com base em pessoas.
* Para uma conexão baseada em conta, você seleciona Conta como o identificador principal. Opcionalmente, é possível adicionar contêineres adicionais para Conta global, Grupo de compra e Oportunidade. Se você adicionar ou não uma Conta global, seu identificador principal será um identificador de conta ou um identificador de conta global.


## Containers

No Customer Journey Analytics, os containers são gerados como parte da configuração de uma conexão e visualização de dados. Os containers armazenam apenas identificadores para facilitar a execução rápida e eficiente de funcionalidades como segmentação, detalhamentos e muito mais.

### Contêineres padrão

O Customer Journey Analytics é construído com base no conceito de três contêineres: Pessoa, Sessão e Evento. Durante uma configuração, esses containers são gerados implicitamente.

É possível redefinir como esses containers são nomeados ao configurar uma visualização de dados, mas a hierarquia e os relacionamentos entre os containers são predeterminados. O contêiner Sessão é gerado com base em como você define uma sessão nas [Configurações de sessão](/help/data-views/session-settings.md) da sua visualização de dados.

![B2C](assets/b2c-containers.svg){zoomable="yes"}


### Contêineres B2B

No Customer Journey Analytics B2B edition, um contêiner de Conta é adicionado à lista de contêineres gerados. E você tem a opção de configurar a geração de contêineres adicionais, como Conta global, Grupo de compra e Oportunidade.

A hierarquia e os relacionamentos entre os contêineres são predeterminados. Oportunidade, Grupo de Compras e Pessoa são todos contêineres irmãos do contêiner Conta. Nessa hierarquia, o contêiner Sessão entre o contêiner Pessoa e o contêiner Evento é gerado com base em como você define uma sessão nas [Configurações da sessão](/help/data-views/session-settings.md) na sua visualização de dados. Os contêineres de sessão adicionais, por exemplo, entre o contêiner Conta e o contêiner Evento, não são gerados e suportados no momento. Consulte a tabela abaixo para obter uma descrição e a utilização básica dos containers B2B.

![B2B](assets/b2b-containers.svg){zoomable="yes"}

| Contêiner B2B | Descrição<br/>Caso de uso básico |
|---|---|
| Conta | Uma empresa que é um cliente ou um cliente potencial de seu negócio. A empresa pode ser uma subsidiária ou divisão de uma organização maior. Conta representa a organização para a qual você está vendendo e que deseja rastrear nesse nível de organização. |
| Conta global (opcional) | A principal empresa-mãe de um grupo de empresas relacionadas. Uma conta global não tem uma empresa principal, mas pode ter subsidiárias ou divisões pertencentes à conta global. Quando você tem o contêiner de Conta global configurado em sua conexão, uma conta que não tem pai ou subsidiárias deve ser listada nos campos conta e conta global. |
| Oportunidade (opcional) | Uma coleção de produtos e serviços que são vendidos juntos. Uma oportunidade frequentemente envolvia várias etapas do ciclo de vendas até o fechamento da venda.<br>Você usaria os dados para medir a progressão da oportunidade pelo funil de vendas. Por exemplo, um relatório que fornece detalhes sobre as principais oportunidades que passaram do estágio 3 para o estágio 4. |
| Grupo de compras (opcional) | Uma coleção de pessoas em uma organização que está envolvida no processo de tomada de decisão para comprar um produto ou serviço. <br/>Você usaria os dados do grupo de compras para acompanhar grupos de compras através do gerenciamento de campanhas. Por exemplo, crie um segmento de público-alvo de grupos-chave de compra.<br/> Provavelmente você deseja realizar uma pesquisa a partir do grupo de compras para os dados do perfil, para poder relatar as pessoas de um grupo de compras. |
| Pessoa | Um indivíduo, geralmente identificado por um endereço de e-mail exclusivo que interagiu com a empresa. <br/>Você usaria os dados do perfil para identificar as pessoas que trabalham em uma conta. Por exemplo: direcione a todas as pessoas em uma conta que se inscreveram para uma conferência. |

>[!IMPORTANT]
>
>* Se você tiver **habilitado** o contêiner de Conta Global em uma conexão baseada em conta, cada registro nos conjuntos de dados do evento deverá conter uma ID de Conta e uma ID de Conta Global. Caso contrário, o registro será ignorado.
>* Se você **não habilitou** o contêiner de Conta Global em uma conexão baseada em conta, cada registro nos conjuntos de dados do evento deve conter uma ID de Conta. Caso contrário, o registro será ignorado.

## Conjuntos de dados

Ao definir [configurações de conjuntos de dados](/help/connections/create-connection.md#dataset-settings) para sua conexão baseada em conta no Customer Journey Analytics B2B edition, as opções disponíveis para algumas das configurações dependem do [tipo de conjunto de dados](/help/connections/create-connection.md#dataset-types). Por exemplo, é necessário:

* Especifique identificadores para cada um dos containers configurados para seus conjuntos de dados de eventos.
* Defina um campo de conta ou um campo de conta global para seus conjuntos de dados de perfil.
* Defina chaves e como correspondê-las (por contêiner de campo) para conjuntos de dados de pesquisa.

## Corresponder por contêiner ou campo

Você pode definir para cada conjunto de dados de pesquisa, se você corresponder o conjunto de dados por campo ou por container.

### Corresponder por container

Se um conjunto de dados de registro usar uma correspondência por contêiner, ele será tratado como um tipo de conjunto de dados de perfil e como um conjunto de dados de perfil na interface do usuário. Use a correspondência por contêiner em conjuntos de dados que oferecem suporte aos contêineres configurados. Por exemplo, um conjunto de dados do Grupo de compra.

### Corresponder por campo

Se um conjunto de dados de registro usar um campo Corresponder por, o conjunto de dados de registro será tratado como um tipo de conjunto de dados de pesquisa e como um conjunto de dados de Pesquisa na interface do usuário. Use a correspondência por campo em conjuntos de dados que oferecem suporte a detalhes adicionais por meio de pesquisa. Por exemplo, um conjunto de dados Membro da lista de marketing ou um conjunto de dados Detalhes do produto.


## Relatório sobre dados baseados em pessoa e conta

Se quiser criar relatórios sobre contêineres com base em pessoas (e identidades de pessoas) e contêineres com base em contas (e identidades de contas), configure duas conexões separadas no Customer Journey Analytics. Uma conexão em que você seleciona Pessoa como a ID principal e uma conexão em que você seleciona Conta como a ID principal. O Customer Journey Analytics não oferece suporte a relatórios com base em pessoas e em contas de uma única hierarquia de contêiner.

