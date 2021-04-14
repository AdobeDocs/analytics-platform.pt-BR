---
title: (B2B) Adicionar dados a nível de conta como um conjunto de dados de pesquisa
description: Saiba como adicionar dados baseados em conta como um conjunto de dados de pesquisa ao CJA
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
translation-type: tm+mt
source-git-commit: 2b6ef07963d648d757f9c1baef123bff416a871a
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 89%

---

# (B2B) Adicionar dados a nível de conta como um conjunto de dados de pesquisa

Este caso de uso B2B mostra como especificar seus dados em um nível de conta, em vez de em um nível de pessoa para análise. A análise a nível de conta pode responder perguntas como

* Que nome de empresa corresponde a esta conta?
* Quantos funcionários estão associados a esta conta/empresa?
* Que funções estão representadas nesta conta?
* Como essa conta funciona no geral, com relação a uma campanha de marketing específica, em comparação a outra conta?
* Algumas funções (como o Gerente de TI) em uma conta estão se comportando de forma diferente da mesma função em outra conta?

Você consegue tudo isso trazendo as informações no nível da conta como um conjunto de dados de [pesquisa](/help/getting-started/cja-glossary.md).

Primeiro, você cria um esquema de pesquisa na Adobe Experience Platform e depois cria um conjunto de dados de tabela de pesquisa assimilando dados de nível de conta baseados em .csv. Em seguida, você cria uma conexão no Customer Journey Analytics (CJA0) que combina diferentes conjuntos de dados, incluindo o conjunto de pesquisa criado. Posteriormente, você cria uma visualização de dados e, por fim, pode utilizar todos esses dados no Workspace.

>[!NOTE]
>
>As tabelas de pesquisa podem ter até 1 GB.

## 1. Criar esquema de pesquisa (Experience Platform)

Criar seu próprio esquema para a tabela de [pesquisa](/help/getting-started/cja-glossary.md) garante que o conjunto de dados usado estará disponível no CJA com a configuração correta (tipo de registro). Uma prática recomendada é [criar uma classe de esquema personalizada](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/tutorials/create-schema-ui.html#create-new-class) chamada &quot;Pesquisa&quot;, sem elementos, que pode ser reutilizada para todas as tabelas de pesquisa.

![](assets/create-new-class.png)

## 2. Criar conjunto de dados de pesquisa (Experience Platform)

Depois de criar o esquema, é necessário criar um conjunto de dados de pesquisa a partir dele, na Experience Platform. Esse conjunto de dados de pesquisa contém informações de marketing a nível de conta, como: nome da empresa, número total de funcionários, nome do domínio, a que setor pertencem, receita anual, se são clientes atuais da Experience Platform ou não, em que estágio de vendas estão, qual equipe dentro da conta está usando o CJA etc.

>[!IMPORTANT]
>
>O CJA não aceita números inteiros em conjuntos de dados de pesquisa. Se você adicionar os campos inteiros no esquema XDM para o conjunto de dados de pesquisa, não será possível usar esses números inteiros como métricas ou métricas calculadas. Por exemplo, se annualRevenue ou totalEmployees forem definidos como inteiros, eles serão exibidos como “0” nos relatórios no CJA. No entanto, se você atribuí-los como strings, poderá usá-los como informações de pesquisa.

Por exemplo, annualRevenue ou totalEmployees são definidos como um inteiro no exemplo a seguir - é por isso que estão mostrando &quot;0&quot; no CJA.

1. Na Adobe Experience Platform, acesse **[!UICONTROL Gerenciamento de dados > Conjuntos de dados]**.
1. Clique em **[!UICONTROL + Criar conjunto de dados]**.
1. Clique em **[!UICONTROL Criar conjunto de dados a partir do esquema]**.
1. Selecione a classe Esquema de pesquisa criada.
1. Clique em **[!UICONTROL Próximo]**.
1. Nomeie o conjunto de dados (em nosso exemplo, Informações B2B) e forneça uma descrição.
1. Clique em **[!UICONTROL Concluir]**.

## 3. Assimilar dados na Experience Platform

As instruções sobre como [Mapear um arquivo CSV para um esquema XDM](https://docs.adobe.com/content/help/pt-BR/experience-platform/ingestion/tutorials/map-a-csv-file.html) devem ajudar se você estiver usando um arquivo CSV.

[Outros métodos](https://docs.adobe.com/content/help/pt-BR/experience-platform/ingestion/home.html) também estão disponíveis.

A assimilação de dados e o estabelecimento da pesquisa levam de 2 a 4 horas, dependendo do tamanho da tabela de pesquisa.

## 4. Combinar conjuntos de dados em uma conexão (Customer Journey Analytics)

Neste exemplo, estamos combinando 3 conjuntos de dados em uma conexão do CJA:

| Nome do conjunto de dados | Descrição | Classe de esquema da AEP | Detalhes do conjunto de dados |
| --- | --- | --- | --- |
| Impressão B2B | Contém dados de sequência de cliques e nível de evento no nível de conta. Por exemplo, contém a ID de email e a ID de conta correspondente, além do nome de marketing, para a execução de anúncios de marketing. Também inclui as impressões desses anúncios, por usuário. | Com base na classe de esquema XDM ExperienceEvent | O `emailID` é usado como a identidade primária e recebe um namespace `Customer ID`. Como resultado, será exibido como a **[!UICONTROL ID de pessoa]** padrão no Customer Journey Analytics. ![Impressões](assets/impressions-mixins.png) |
| Perfil B2B | Este conjunto de dados de perfil informa mais sobre os usuários em uma conta, como o cargo, a qual conta eles pertencem, o perfil do LinkedIn etc. | Com base na classe de esquema Perfil individual XDM | Não é necessário selecionar `emailID` como a ID primária neste esquema. Certifique-se de ativar o **[!UICONTROL Perfil]**; caso contrário, o CJA não será capaz de conectar a `emailID` ao Perfil B2B com a `emailID` nos dados de impressão B2B. ![Perfil](assets/profile-mixins.png) |
| Informações B2B | Consulte &quot;Criar conjunto de dados de pesquisa&quot; acima. | B2BAccount (classe de esquema de pesquisa personalizada) | A relação entre `accountID` e o conjunto de dados Impressões B2B foi criada automaticamente ao conectar o conjunto de dados Informações B2B ao conjunto de dados Impressões B2B no CJA, conforme descrito nas etapas abaixo. ![Pesquisa](assets/lookup-mixins.png) |

Veja como combinar conjuntos de dados:

1. No Customer Journey Analytics, selecione a guia **[!UICONTROL Conexões]**.
1. Selecione os conjuntos de dados (no nosso exemplo, os três acima) que deseja combinar.
1. Para o conjunto de dados de Informações B2B, selecione a chave `accountID` que será usada na tabela de pesquisa. Em seguida, selecione a chave correspondente (dimensão correspondente), também `accountID` no conjunto de dados do evento.
1. Clique em **[!UICONTROL Próximo]**.
1. Nomeie e descreva a conexão e configure-a de acordo com [estas instruções](/help/connections/create-connection.md).
1. Clique em **[!UICONTROL Salvar]**.

## 5. Criar uma visualização de dados a partir desta conexão

Siga as instruções em [criação de visualizações de dados](/help/data-views/create-dataview.md).

* Adicione todos os componentes (dimensões e métricas) necessários dos conjuntos de dados.

## 6. Analisar os dados no Workspace

Agora é possível criar projetos do Workspace com base nos dados de todos os três conjuntos de dados.

Por exemplo, encontre respostas para as perguntas apresentadas na introdução:

* Detalhe a emailID por accountID para descobrir a empresa à qual uma ID de email pertence.
* Quantos funcionários estão mapeados para uma ID de conta específica?
* A que setor uma ID de conta pertence?

![](assets/project-lookup.png)
