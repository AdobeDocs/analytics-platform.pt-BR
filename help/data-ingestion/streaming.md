---
title: Assimilar e usar dados de transmissão
description: Explique como assimilar e usar dados de transmissão no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: 9984200a-71e6-4697-b46f-f53e8d4c507f
role: Admin
source-git-commit: bc2c959497230d7672d43d5cd409ca62d4627d6a
workflow-type: tm+mt
source-wordcount: '2002'
ht-degree: 83%

---

# Assimilar e usar dados de transmissão

Este guia de início rápido explica como você pode assimilar dados de transmissão na Adobe Experience Platform e usar esses dados no Customer Journey Analytics.

Para isso, é necessário:

- **Configurar um esquema e um conjunto de dados** na Adobe Experience Platform para definir o modelo (esquema) dos dados que você deseja coletar e onde realmente coletar os dados (conjunto de dados).

- **Usar conector de origem da API HTTP** para transmitir facilmente seus dados para o conjunto de dados configurado na Adobe Experience Platform.

- **Configurar uma conexão** no Customer Journey Analytics. Essa conexão deve (pelo menos) incluir o conjunto de dados da Adobe Experience Platform.

- **Configurar uma visualização de dados** no Customer Journey Analytics para definir métricas e dimensões que você deseja usar no Analysis Workspace.

- **Configurar um projeto** no Customer Journey Analytics para criar relatórios e visualizações.


>[!NOTE]
>
>Este guia de início rápido é um guia simplificado sobre como assimilar dados de transmissão na Adobe Experience Platform e usar no Customer Journey Analytics. É altamente recomendável estudar as informações adicionais quando referidas.

## Configurar um esquema e um conjunto de dados

Para assimilar dados na Adobe Experience Platform, primeiro é necessário definir quais dados você deseja coletar. Todos os dados assimilados na Adobe Experience Platform devem estar em conformidade com uma estrutura padrão e desnormalizada para que sejam reconhecidos e utilizados pelos recursos e capacidades downstream. O Experience Data Model (XDM) é a estrutura padrão que fornece essa estrutura no formato de esquemas.

Após definir um esquema, use um ou mais conjuntos de dados para armazenar e gerenciar a coleta de dados. Um conjunto de dados é uma construção de armazenamento e gerenciamento para uma coleção de dados (normalmente uma tabela) que contém um esquema (colunas) e campos (linhas).

Todos os dados assimilados na Adobe Experience Platform devem estar em conformidade com um esquema predefinido antes que possam ser mantidos como um conjunto de dados.

### Configurar um esquema

Para esse início rápido, você deseja coletar alguns dados de fidelidade, por exemplo, id de fidelidade, pontos de fidelidade e status de fidelidade.
Primeiro, você deve definir um esquema que modele esses dados.

Para configurar o esquema:

1. Na interface do usuário da Adobe Experience Platform, no painel esquerdo, selecione **[!UICONTROL Esquemas]** no [!UICONTROL GERENCIAMENTO DE DADOS].

1. Selecione **[!UICONTROL Criar esquema]**.
.
1. Na etapa Selecionar uma classe do assistente Criar esquema:

   1. Selecione **[!UICONTROL Perfil Individual]**.

      ![Criar um esquema](./assets/create-pr-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Um esquema de evento de experiência é usado para modelar o _comportamento_ de um perfil (como nome do cenário, pressione o botão para adicionar ao carrinho). Um esquema de Perfil individual é usado para modelar os _atributos_ de perfil (como nome, email, gênero).

   1. Selecione **[!UICONTROL Próximo]**.


1. No [!UICONTROL Nome e etapa de revisão] do assistente [!UICONTROL Criar esquema]:

   1. Insira um **[!UICONTROL nome de exibição]** para o esquema e uma **[!UICONTROL descrição]** (opcional).

      ![Dê um nome ao esquema](./assets/create-pr-schema-wizard-step-2.png)

   1. Selecione **[!UICONTROL Concluir]**.

1. Na guia Estrutura de Esquema de Exemplo:

   1. Selecione **[!UICONTROL + Adicionar]** em [!UICONTROL Grupos de campos].

      ![Adicione um grupo de campos](./assets/add-field-group-button.png)

      Grupos de campos são coleções reutilizáveis de objetos e atributos que permitem estender seus esquemas facilmente.

   1. Na caixa de diálogo [!UICONTROL Adicionar grupos de campos], selecione o grupo de campos **[!UICONTROL Detalhes de fidelidade]** na lista.

      ![Grupo de campos ExperienceEvent do SDK da Web da AEP](./assets/loyalty-fieldgroup.png)

      Você pode selecionar o botão de visualização para ver uma visualização dos campos que fazem parte desse grupo de campos.

      ![Visualização do campo de grupos ExperienceEvent do SDK da Web da AEP](./assets/loyalty-fieldgroup-preview.png)

      Selecione **[!UICONTROL Voltar]** para fechar a visualização.

   1. Selecione **[!UICONTROL Adicionar grupos de campos]**.

1. Selecione **[!UICONTROL +]** ao lado do nome do esquema no painel [!UICONTROL Estrutura].

   ![Botão Adicionar campo de esquema de exemplo](./assets/example-loalty-schema-plus.png)

1. No painel [!UICONTROL Propriedades do campo], digite `Identification` como nome, **[!UICONTROL Identificação]** como [!UICONTROL Nome de exibição], selecione **[!UICONTROL Objeto]** como [!UICONTROL Tipo] e selecione **[!UICONTROL Perfil Core v2]** como [!UICONTROL Grupo de campos].

   ![Objeto de identificação](./assets/identifcation-loyalty-field.png)

   Esse objeto de identificação adiciona recursos de identificação ao esquema. No seu caso, você deseja identificar as informações de fidelidade usando o endereço de email nos dados em lote.

   Selecione **[!UICONTROL Aplicar]** para adicionar esse objeto ao esquema.

1. Selecione o campo **[!UICONTROL email]** no objeto de identificação que você acabou de adicionar e selecione **[!UICONTROL Identidade]** e **[!UICONTROL Email]** do [!UICONTROL Namespace de identidade] no painel [!UICONTROL Propriedades do campo].

   ![Especificar email como identidade](./assets/specify-email-loyalty-id.png)

   Você está especificando o endereço de email como a identidade que o serviço Adobe Experience Platform Identity pode usar para combinar (compilar) o comportamento de perfis.

   Selecione **[!UICONTROL Aplicar]**. Você vê que um ícone de impressão digital aparece no atributo de email.

1. Selecione o nível raiz do esquema (com o nome do esquema) e selecione a opção **[!UICONTROL Perfil]**.

   Você deve habilitar o esquema para o perfil. Depois de ativados, quando os dados são assimilados em conjuntos de dados com base nesse esquema, esses dados são mesclados ao Perfil do cliente em tempo real.

   Consulte [Ativar o esquema para usar no Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=pt-BR#profile) para obter mais informações.

   >[!IMPORTANT]
   >
   >    Depois de salvar um esquema ativado para perfil, ele não pode mais ser desativado para perfil.

   ![Habilitar esquema para perfil](./assets/enable-for-profile.png)

1. Selecione **[!UICONTROL Salvar]** para salvar o esquema.

Você criou um esquema mínimo que modela os dados de fidelidade que podem ser assimilados na Adobe Experience Platform. O esquema permite que os perfis sejam identificados usando o endereço de email. Ao ativar o esquema para perfil, você garante que os dados da fonte de transmissão sejam adicionados ao Perfil do cliente em tempo real.

Consulte [Criar e editar esquemas na interface do usuário](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=pt-BR) para obter mais informações sobre a adição e remoção de grupos de campos e campos individuais a um esquema.

### Configurar um conjunto de dados

Com seu esquema, você definiu seu modelo de dados. Agora é necessário definir a construção para armazenar e gerenciar esses dados, o que é feito por meio de conjuntos de dados.

Para configurar seu conjunto de dados:

1. Na interface do usuário da Adobe Experience Platform, no painel esquerdo, selecione **[!UICONTROL Conjuntos de dados]** no [!UICONTROL GERENCIAMENTO DE DADOS].

2. Selecione **[!UICONTROL Criar conjunto de dados]**.

   ![Criar conjunto de dados](./assets/create-dataset.png)

3. Selecione **[!UICONTROL Criar conjunto de dados a partir do esquema]**.

   ![Criar conjunto de dados a partir do esquema](./assets/create-dataset-from-schema.png)

4. Selecione o esquema criado anteriormente e selecione **[!UICONTROL Próximo]**.

5. Nomeie seu conjunto de dados e (opcional) forneça uma descrição.

   ![Nome do conjunto de dados](./assets/name-your-datatest.png)

6. Selecione **[!UICONTROL Concluir]**.

7. Selecione a opção **[!UICONTROL Perfil]**.

   Você deve habilitar o conjunto de dados para perfil. Depois de habilitado, o conjunto de dados enriquece os perfis do cliente em tempo real com seus dados assimilados.

   >[!IMPORTANT]
   >
   >    Você só pode habilitar um conjunto de dados para perfil quando o esquema, ao qual o conjunto de dados corresponde, também estiver habilitado para perfil.

   ![Habilitar esquema para perfil](./assets/loyalty-dataset-profile.png)

Consulte [Guia da interface do usuário de conjuntos de dados](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=pt-BR) para obter muito mais informações sobre como visualizar, visualizar, criar, excluir um conjunto de dados. E como ativar um conjunto de dados para o Perfil do cliente em tempo real.


## Configurar uma conexão de transmissão da API HTTP

Seu aplicativo de origem envia dados que estão em conformidade com o esquema criado e se parece com ele.

```json
{
    ...
    "_demosystem4": {
        "identification": {
            "core": {
                "email": "abrocking0@blog.com",
                "loyaltyId": "793406",
            }
        }
    },
    "loyalty": {
        "loyaltyID": [
            "793406"
        ],
        "points": 82.16,
        "status": "Silver"
    }
    ...
}
```

Para transmitir esses dados para o conjunto de dados criado, você deve definir um terminal de transmissão para onde esses dados serão enviados. Um ponto de extremidade de transmissão é criado usando um conector de origem da API HTTP.

Para criar um conector de origem da API HTTP:

1. Na interface do usuário da Experience Platform, selecione **[!UICONTROL Fontes]** em [!UICONTROL CONEXÕES] no painel esquerdo.

2. Selecione **[!UICONTROL Transmissão]** na lista em [!UICONTROL CATEGORIAS].

3. Selecione **Configurar** no bloco [!UICONTROL API HTTP].

   ![Configurar bloco API HTTP](./assets/httpapi-tile.png)

4. Na etapa [!UICONTROL Autenticação] da tela [!UICONTROL Adicionar dados]:

   Insira um nome e uma descrição para a conexão da API HTTP.

   Selecione **[!UICONTROL Compatível com XDM]** para indicar que os dados de transmissão são compatíveis com um esquema XDM existente.

   Selecione **[!UICONTROL Conectar-se à origem]**. Após uma conexão bem-sucedida, você verá [!UICONTROL Conectado].

   ![Autenticação da API HTTP](./assets/httpapi-authentication.png)

   Clique em **[!UICONTROL Avançar]** para continuar.

5. Na etapa [!UICONTROL Detalhes do fluxo de dados] da tela [!UICONTROL Adicionar dados]:

   Selecione **[!UICONTROL Conjunto de dados existente]**, selecione o conjunto de dados na lista do conjunto de dados e estabeleça o [!UICONTROL Nome do fluxo de dados].

   ![Detalhes do fluxo de dados](./assets/httpapi-dataflowdetail.png)

   Selecione **[!UICONTROL Próximo]**.

6. A etapa [!UICONTROL Revisão] da tela [!UICONTROL Adicionar dados] fornece uma visão geral da conexão da API HTTP.

   ![Detalhes do fluxo de dados](./assets/httpapi-review.png)

   Selecione **[!UICONTROL Concluir]**.

7. Você vê a definição final do seu ponto de acesso de transmissão da API HTTP.

   ![Ponto de acesso de transmissão da API HTTP](./assets/httpapi-streamingendpoint.png)

Você pode copiar o URL do ponto de acesso de transmissão e usá-lo para configurar seu aplicativo de fidelidade para transmitir dados para o conjunto de dados de fidelidade da Adobe Experience Platform.

Consulte [Criar uma conexão de transmissão da API HTTP usando a interface do usuário](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/streaming/http.html?lang=pt-BR) para obter um tutorial muito mais abrangente que explique:

- como usar autenticação,
- como mapear dados quando os dados recebidos não são compatíveis com o esquema XDM e
- como criar um conjunto de dados como parte da configuração do conector de transmissão.


## Configurar uma conexão

Para usar os dados da Adobe Experience Platform no Customer Journey Analytics, crie uma conexão que inclua os dados resultantes da configuração do esquema, do conjunto de dados e do fluxo de trabalho.

Uma conexão permite integrar conjuntos de dados da Adobe Experience Platform ao Espaço de trabalho. Para criar relatórios sobre esses conjuntos de dados, primeiro é necessário estabelecer uma conexão entre os conjuntos de dados na Adobe Experience Platform e no Workspace.

Para criar sua conexão:

1. Na interface do usuário do Customer Journey Analytics, selecione **[!UICONTROL Conexões]**, opcionalmente em **[!UICONTROL Gerenciamento de dados]**, no menu superior.

2. Selecione **[!UICONTROL Criar nova conexão]**.

3. Na tela [!UICONTROL Conexão sem título]:

   Nomeie e descreva sua conexão em [!UICONTROL Configurações de conexão].

   Selecione a sandbox correta na lista [!UICONTROL Sandbox] em [!UICONTROL Configurações de dados] e selecione o número de eventos diários na lista [!UICONTROL Número médio de eventos diários].

   ![Configurações de conexão](./assets/cja-connections-1.png)

   Selecione **[!UICONTROL Adicionar conjuntos de dados]**.

   Na etapa [!UICONTROL Selecionar conjuntos de dados] em [!UICONTROL Adicionar conjuntos de dados]:

   - Selecione o conjunto de dados criado anteriormente (`Example Loyalty Dataset`) e qualquer outro conjunto de dados que você deseja incluir em sua conexão.

     ![Adicionar conjuntos de dados](./assets/cja-connections-2.png)

   - Selecione **[!UICONTROL Próximo]**.

   Na etapa [!UICONTROL Configurações de conjuntos de dados] em [!UICONTROL Adicionar conjuntos de dados]:

   - Para cada conjunto de dados:

      - Selecione uma [!UICONTROL ID de pessoa] a partir das identidades disponíveis definidas nos esquemas de conjunto de dados da Adobe Experience Platform.

      - Selecione a fonte de dados correta na lista [!UICONTROL Tipo de fonte de dados]. Se você especificar **[!UICONTROL Outros]**, em seguida, adicione uma descrição para a fonte de dados.

      - Definir **[!UICONTROL Importar todos os novos dados]** e **[!UICONTROL Preenchimento retroativo de conjunto de dados com dados existentes]** de acordo com suas preferências.

     ![Configurar conjuntos de dados](./assets/cja-connections-3.png)

   - Selecione **[!UICONTROL Adicionar conjuntos de dados]**.

   Selecione **[!UICONTROL Salvar]**.

Consulte [Visão geral das conexões](../connections/overview.md) para obter mais informações sobre como criar e gerenciar uma conexão e como selecionar e combinar conjuntos de dados.

## Configurar uma visualização de dados

Uma visualização de dados é um container específico do Customer Journey Analytics que permite determinar como interpretar dados de uma conexão. Ele especifica todas as dimensões e métricas disponíveis no Analysis Workspace e de quais colunas elas obtêm seus dados. As visualizações de dados são definidas na preparação de relatórios no Analysis Workspace.

Para criar a visualização de dados:

1. Na interface do usuário do Customer Journey Analytics, selecione **[!UICONTROL Visualizações de dados]**, opcionalmente em **[!UICONTROL Gerenciamento de dados]**, no menu superior.

2. Selecione **[!UICONTROL Criar nova visualização de dados]**.

3. Na etapa [!UICONTROL Configurar]:

   Selecione a conexão na lista [!UICONTROL Conexão].

   Nomeie e (opcionalmente) descreva a conexão.

   ![Configuração da visualização de dados](./assets/cja-dataview-1.png)

   Selecione **[!UICONTROL Salvar e continuar]**.

4. Na etapa [!UICONTROL Componentes]:

   Adicione qualquer campo de esquema e/ou componente padrão que deseja incluir às caixas de componentes [!UICONTROL MÉTRICAS] ou [!UICONTROL DIMENSÃO].

   ![Componentes da visualização de dados](./assets/cja-dataview-2.png)

   Selecione **[!UICONTROL Salvar e continuar]**.

5. Na etapa [!UICONTROL Configurações]:

   Configurações de ![visualização de dados](./assets/cja-dataview-3.png)

   Deixe as configurações como estão e selecione **[!UICONTROL Salvar e concluir]**.

Consulte [Visão geral das visualizações de dados](../data-views/data-views.md) para obter mais informações sobre como criar e editar uma visualização de dados, quais componentes estão disponíveis para você usar na visualização de dados e como usar as configurações de segmento e sessões.


## Configurar um projeto

O Analysis Workspace é uma ferramenta de navegador flexível que permite criar análises e compartilhar insights rapidamente com base em dados. Os projetos do Espaço de trabalho permitem combinar componentes de dados, tabelas e visualizações para criar a análise e compartilhar com qualquer pessoa na organização.

Para criar o projeto:

1. Na interface do usuário do Customer Journey Analytics, selecione **[!UICONTROL Projetos]** no menu superior.

2. Selecione **[!UICONTROL Projetos]** no painel de navegação esquerdo.

3. Selecione **[!UICONTROL Criar projeto]**.

   ![Projeto do Espaço de trabalho](./assets/cja-projects-1.png)

   Selecione **[!UICONTROL Projeto em branco]**.

   ![Espaço de trabalho - Projeto em branco](./assets/cja-projects-2.png)

4. Selecione a visualização de dados na lista.

   ![Visualização de dados de seleção do Espaço de trabalho](./assets/cja-projects-3.png).

5. Para criar seu primeiro relatório, comece a arrastar e soltar dimensões e métricas na [!UICONTROL Tabela de forma livre] do [!UICONTROL Painel]. Como exemplo, arraste `Program Points Balance` e `Page View` como métricas e `email` como dimensão para obter uma visão geral rápida dos perfis que visitaram seu site e fazem parte do programa de fidelidade que coleta pontos.

   ![Espaço de trabalho - Primeiro relatório](./assets/cja-projects-5.png)

Consulte [Visão geral do Analysis Workspace](../analysis-workspace/home.md) para obter mais informações sobre como criar projetos e sua análise usando componentes, visualizações e painéis.

>[!SUCCESS]
>
>Você concluiu todas as etapas. A partir da definição de quais dados de fidelidade você deseja coletar (esquema) e onde armazená-los (conjunto de dados) na Adobe Experience Platform, você configurou um conector de origem da API HTTP para transmitir dados de fidelidade diretamente no conjunto de dados. A definição da visualização de dados permite especificar qual dimensão e métricas usar e, por fim, criar seu primeiro projeto visualizando e analisando seus dados.
