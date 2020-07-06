---
description: Modelos no Workspace
title: Modelos
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '1420'
ht-degree: 95%

---


# Modelos

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html)tradicional. [Saiba mais...](/help/getting-started/cja-aa.md)

Você pode criar um projeto a partir de:

* **Projeto em branco (padrão)**: para obter instruções, consulte [Criar um projeto no Analysis Workspace](/help/analysis-workspace/home.md).
* **Modelo padrão**: esses modelos são criados pela Adobe e fornecidos com o produto.
* **Modelo** personalizado: Esses modelos podem ser criados, compartilhados ou excluídos por usuários com direitos de administrador ou por não administradores, desde que tenham recebido a [!UICONTROL Analysis Workspace: A permissão Salvar como modelo] no Admin Console. [Saiba mais...](https://docs.adobe.com/content/help/pt-BR/analytics/admin/admin-console/permissions/product-profile.html)

![](assets/start_modal.png)

## Criar um modelo personalizado {#create-custom-template}

Os usuários com direitos de administrador podem tornar qualquer projeto criado por ele um modelo personalizado. Veja como:

1. Abrir o projeto.
1. Vá até **[!UICONTROL Projeto]** > **[!UICONTROL Salvar como modelo]**.

   ![](assets/save_project_template.png)

   O projeto será salvo com o nome do projeto atual, seguido da palavra (Modelo) entre parênteses. Os administradores podem alterar esse nome ao editar o modelo.

   >[!NOTE]
   >
   >Por padrão, os modelos de projeto estão visíveis para todos em sua organização. Você pode organizá-los aplicando tags. (Vá até **[!UICONTROL Projeto]** > **[!UICONTROL Informações e configurações do projeto]** para editar tags e descrições.)

### Ações executáveis nos modelos personalizados

![](assets/custom_templates.png)

| Ação | Descrição |
|--- |--- |
| Editar modelo | Permite que um administrador edite o modelo ao alterar a fonte de dados, modificar componentes, exibições, intervalos de data etc.  Para editar um modelo personalizado,<ul><li>abra a lista de modelos personalizados do Analysis Workspace, selecione um e clique em Editar modelo, ou</li><li>no Analytics, clique em Componentes > Projetos e filtre por Modelos. Clique no nome do modelo que deseja editar.</li></ul>**Observação:** após editar um modelo, dependendo da situação, você terá duas opções: Salvar, Salvar como. Elas se diferem da seguinte forma:<ul><li>**Salvar:** atualiza o modelo personalizado para todos os usuários. Quando outra pessoa cria um projeto a partir deste modelo personalizado, ela verá suas alterações.</li><li>**Salvar como:** cria uma cópia do modelo personalizado com suas alterações. (Você saberá que está no modo de edição quando o item de menu Compartilhar > Compartilhar projeto estiver desativado.)</li></ul> |
| Pesquisar nos modelos | Na caixa de diálogo Modelos personalizados, clique em Pesquisar modelos. |
| Classificar modelos | É possível classificar modelos por ordem alfabética, relevância e data de criação.  Na caixa de diálogo Modelos personalizados, clique em Classificar. |
| Aplicar tags ao modelo | Abra o modelo e vá até Projeto > Informações e configurações do projeto. Clique em Adicionar tags. |
| Modificar descrição do modelo | Abra o modelo e vá até Projeto > Informações e configurações do projeto. Clique duas vezes na descrição e edite-a. |


## Modelos padrão

Quando você abre um Workspace pela primeira vez, os modelos ficam disponíveis no painel esquerdo. Os modelos do Analysis Workspace abrangem casos usuais. São agrupados pela vertical à qual pertencem e são preenchidos com diferentes dimensões, segmentos, métricas e visualizações, dependendo do conjunto de relatórios selecionado.

Você pode usar esses modelos pré-preenchidos como estão ou adaptá-los às suas necessidades (adicionando ou substituindo métricas ou visualizações, por exemplo) e salvá-los com um novo nome.

[Modelos padrão do Analysis Workspace no YouTube](https://www.youtube.com/watch?v=aRgYwPneVXg&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=6) (2:46)

Estes são os modelos disponíveis e as perguntas que cada modelo ajuda a responder.

### Treinamento

Esses modelos padrão orientam você pela terminologia e etapas comuns para criar sua primeira análise no Workspace. Eles estão disponíveis como modelo padrão no modal Novo projeto e substituem o projeto de amostra atual para novos usuários que não têm outros projetos na lista.

* **Tutorial de treinamento - Análise de pesquisa interna**: o tutorial de Pesquisa interna ajuda você a entender o que seus visitantes estão procurando no site ou aplicativo, mas não estão achando. A análise desse tipo de dados pode exibir oportunidades de otimização de conteúdo.

* **Tutorial de treinamento - Análise de marketing**: este tutorial mostra como fazer uma análise de marketing para seus executivos, incluindo quais dimensões e métricas personalizadas são importantes.

### Publicidade

>[!IMPORTANT]
>
>Os modelos de publicidade estão disponíveis somente se o seu conjunto de relatórios estiver habilitado para a Advertising Cloud.

* **Mecanismos de pesquisa paga**: esse modelo detalha tendências de publicidade, plataformas de publicidade, palavras-chave, contas, campanhas e muito mais.

### Comércio

* **Magento: marketing e comércio**: esse modelo detalha sua conversão de comércio eletrônico por atribuição de canal de marketing, além de fornecer informações por palavra-chave de pesquisa, página de aterrissagem, localização geográfica e muito mais. Para ter uma visão geral, assista ao vídeo > [!VIDEO](https://www.youtube.com/watch?v=AQOViVLEMHw)

### Mídia

* **Consumo de áudio**: que conteúdo está sendo mais consumido pelos usuários, resultando em interações?
* **Recenticidade - Frequência - Fidelidade**: quem são meus leitores fiéis?

### Dispositivos móveis

>[!IMPORTANT]
>
>Os modelos para dispositivos móveis estão disponíveis somente se o seu conjunto de relatórios estiver habilitado para dispositivos móveis.

* **Mensagens:** focaliza o desempenho das mensagens no aplicativo e por push.
* **Localização:** inclui um mapa que exibe os dados de localização.
* **Métricas principais:** permite o controle das métricas principais do seu aplicativo.
* **Uso do aplicativo:** quantos usuários, inicializações e primeiras inicializações o aplicativo teve e qual foi a duração média das sessões?
* **Aquisição:** você pode ver o desempenho dos links de aquisição para dispositivos móveis.
* **Desempenho:** como está o desempenho do aplicativo e que problemas os usuários estão tendo?
* **Retenção:** quem são meus usuários fiéis e o que eles fazem?
* **Jornadas:** quais são os principais padrões de uso do meu aplicativo?

### Varejo

* **Desempenho da campanha:** que campanhas estão gerando mais receita?
* **Produtos:** que produtos estão tendo o melhor desempenho?

### Web

* **Aquisição:** quais são os principais impulsionadores de tráfego do meu site?
* **Consumo de conteúdo:** quais são os lugares mais acessados do meu site?
* **Retenção:** que tipo de usuário tem maior probabilidade de se tornar um usuário fiel do meu site?
* **Tecnologia:** que tecnologia as pessoas estão usando para acessar o meu site?

### Pessoas

>[!NOTE]
>
>O modelo Pessoas e sua respectiva métrica Pessoas estão disponíveis para uso somente como parte do [Device Co-op da Adobe Experience Cloud](https://docs.adobe.com/content/help/pt-BR/device-co-op/using/data/people.html).

O modelo é baseado na métrica de Pessoas, que é uma versão deduplicada da métrica Visitantes únicos. A métrica de Pessoas oferece uma medida da frequência que os clientes que usam vários dispositivos interagem com a sua marca. O modelo permite

* Segmentar seus dados por EUA/Canadá vs. o resto do mundo. No momento, o Device Co-op está disponível somente para a América do Norte.
* Comparar as métricas de Pessoas e de Visitantes únicos lado a lado.
* Ver a &quot;taxa de compressão&quot;, uma métrica calculada que calcula o quão menor a métrica de Pessoas é como uma porcentagem de Visitantes únicos.
* Comparar os totais de tipos de dispositivos que seus clientes usam.
* Ver a média de quantos dispositivos por pessoa são usados.
* Descobrir como usar o empilhamento de segmentos com a métrica de Pessoas.
* Saber mais sobre como usar a Experience Cloud ID em seu ambiente melhora a eficácia da métrica Pessoas.

### QI da jornada: modelo de Análise entre dispositivos

<!-->This content is mirrored in the CDA doc.<-->

Esse modelo permite que você veja dados essenciais de desempenho entre dispositivos. Ele está disponível somente para clientes que têm acesso ao [Cross-Device Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/components/cda/cda-home.html) (CDA).

* **Nota especial para os membros do Gráfico cooperativo**: mostra qual parte do conjunto de relatórios contém visitantes em regiões nas quais o gráfico cooperativo é suportado e em regiões nas quais ele não é suportado.
* **Identificação de usuários**: mostra a frequência com que os visitantes do site são identificados usando métodos com base na Análise entre dispositivos.
* **Medição do tamanho do público-alvo**: mostra uma comparação entre &quot;Dispositivos únicos&quot; e &quot;Pessoas&quot;. A proporção desses dois números é conhecida como &quot;compactação entre dispositivos&quot;, uma métrica calculada visível neste painel. Essa métrica de compactação depende de vários fatores:
   * **Uso do gráfico Cooperativo ou Privado**: em geral, as organizações que usam a cooperação de dispositivos tendem a ver melhores taxas de compactação, em relação às organizações que usam o gráfico privado.
   * **Taxa de logon**: quanto mais usuários entrarem no site, mais a Adobe poderá identificar e compilar visitantes entre dispositivos. Os sites com uma taxa de logon baixa também têm taxas de compactação baixas.
   * **Cobertura da Experience Cloud ID**: somente os visitantes com uma ECID podem ser compilados. Uma porcentagem menor de visitantes do site que usam uma ECID está correlacionada a taxas de compactação mais baixas.
   * **Uso de vários dispositivos**: se os visitantes do site não usarem vários dispositivos, você poderá ver taxas de compactação mais baixas.
   * **Granularidade do relatório**: a compactação por dia geralmente é menor do que a compactação por mês ou ano. As chances de um indivíduo usar vários dispositivos se tornam menores em um único dia do que em mais de um mês inteiro. A segmentação, a filtragem ou o uso de dimensões de detalhamento também podem mostrar uma taxa de compactação menor.
* **Segmentos com base em pessoas**: contêm uma lista suspensa de segmentos que permitem visualizar dados específicos do dispositivo. Esse painel incentiva a experimentação com segmentos para ver como a inclusão ou exclusão de tipos de dispositivos afetam os relatórios.
* **Análise da jornada entre dispositivos**: fornece relatórios de fluxo e fallout de acordo com o tipo de dispositivo.
* **Atribuição entre dispositivos**: combine os recursos de Journey IQ e Attribution IQ.
* **Outras dicas e truques**: tópicos úteis sobre o CDA que permitem que você o aproveite ao máximo.