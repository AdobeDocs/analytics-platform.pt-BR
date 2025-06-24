---
title: Comparar soluções do Customer Journey Analytics às soluções de BI
description: Comparar soluções do Customer Journey Analytics às soluções de BI
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: ae66cd06-7ec1-4174-a3cf-939c3a66b840
source-git-commit: 720751130d0f66bddffd13c6f160a85fcc7a7206
workflow-type: ht
source-wordcount: '1648'
ht-degree: 100%

---

# Comparar soluções do Customer Journey Analytics às soluções de BI

Com o foco atual na experiência do cliente, as marcas exigem soluções avançadas para entender melhor a jornada integral do cliente. Entender por completo essa jornada do cliente permite analisar e obter informações valiosas sobre como os canais online e offline envolvem os clientes e levam ao aumento da conversão, retenção e fidelidade. Neste contexto, uma jornada do cliente pode ser um simples pedido online de uma refeição em uma franquia de sushi. Ou a compra de um carro novo, onde o cliente combina sua pesquisa online com visitas ao showroom do revendedor, finalizando a compra presencialmente.

Muitas organizações consolidaram seus dados omnicanal em um data lake ou data warehouse. As ferramentas de BI (Business Intelligence) são usadas sobre esses armazenamentos de dados para fornecer os relatórios, visualizações e insights que a empresa necessita para entender a jornada do cliente. Geralmente, essa combinação de soluções e ferramentas é um objetivo geral por natureza e intenção, e não se concentra explicitamente no cliente. O Customer Journey Analytics tem como foco capacitar os responsáveis pela experiência de cliente, como profissionais de marketing, analistas de dados e cientistas de dados. A ferramenta permite que visualizem o contexto completo da jornada de cliente em todos os canais e em tempo real, sem limitações que muitas outras ferramentas de BI possuem.

Esta seção da documentação explica as diferenças fundamentais entre o Customer Journey Analytics e as ferramentas de BI comumente usadas, primeiro analisando o fluxo de trabalho geral usado para realizar o objetivo mencionado acima: entender a jornada de cliente. Em seguida, são fornecidos mais detalhes sobre como os dados são armazenados, coletados e consultados de maneiras diferentes no Customer Journey Analytics e nas ferramentas de BI. Por fim, ela explica as diferenças nos recursos de visualização.

## Fluxo de trabalho tradicional de BI

Um obstáculo frequente com abordagens tradicionais para analisar jornadas de clientes é que elas não são centradas no cliente. Cada equipe coleta dados em silos, analisando e otimizando experiências com base nos dados aos quais tem acesso.

![Fluxo de trabalho tradicional de BI conforme descrito nesta seção](./assets/biworkflow.png)

Se quiser entender como uma campanha digital específica afeta uma ação offline armazenada em um silo de dados diferente, emita uma solicitação para a fila da equipe de BI. A equipe de BI registra a consulta necessária para adquirir e transformar os dados. Depois que os dados brutos são recuperados, a equipe de BI cria a visualização. Os dados são compartilhados com você, enquanto passa o tempo procurando insights e extraindo dados para ativação em outros sistemas.

Cada uma dessas etapas pode levar horas, dias ou até semanas. Se houver mais perguntas ou problemas com os dados consultados, poderá levar ainda mais tempo até que essas perguntas sejam abordadas e o ciclo continue. Para análise, exploração e compreensão contínuas da jornada do cliente, esse processo não é eficiente nem escalável. Além disso, as equipes de BI geralmente abordam mais do que apenas questões relacionadas à jornada do cliente.

## Customer Journey Analytics: fluxo de trabalho democratizado para dados online e offline

O Customer Journey Analytics fornece um ambiente para conectar dados online e offline de vários canais no nível geral de cliente com o objetivo único de entender a jornada de clientes. Ele exige uma configuração inicial para [conectar](/help/connections/overview.md) e [definir visualizações](/help/data-views/data-views.md) para os dados que você considerar relevantes. No entanto, uma vez concluídos, esses dados estarão prontamente disponíveis para análise e exploração contínuas. Você pode obter insights sobre as jornadas do cliente de maneira progressiva e entendê-las. Ao democratizar dados online e offline combinados, você pode responder perguntas relacionadas à jornada do cliente em segundos.

![Fluxo de trabalho do Customer Journey Analytics conforme descrito nesta seção](./assets/cjaworkflow.png)

Você pode usar o Customer Journey Analytics para fazer perguntas usando o ambiente visual do Analysis Workspace e obter insights quase instantaneamente. Os dados e relatórios entre canais são imediatamente disponibilizados, sem necessidade de um código SQL. Consultas e análises adicionais podem ser realizadas com uma simples operação de arrastar e soltar na interface, com dados totalmente correlacionados. Você pode continuar fazendo perguntas e explorando mais detalhes progressivamente, conforme necessário. Em seguida, é possível realizar ações imediatas sobre os insights descobertos, como compartilhar públicos para ativação e orquestração.

## O avançado mecanismo de relatórios do Customer Journey Analytics

O Customer Journey Analytics usa uma avançada arquitetura própria que distribui a análise em centenas ou até milhares de servidores para exibir dados no Analysis Workspace em segundos. Algumas propriedades notáveis dessa arquitetura de processamento incluem:

* **Otimização para consultas individuais relacionadas a clientes**: tecnicamente, o Customer Journey Analytics armazena os dados em um mecanismo de relatório distribuído que faz uso extensivo do armazenamento em cache. Esse mecanismo é ajustado para consultas responsivas em dados de eventos de nível individual e, como tal, é perfeitamente otimizado para consultas relacionadas ao cliente. O mecanismo de relatórios armazena dados em índices de bitmap orientados por coluna que permitem um cálculo rápido e preciso de métricas agregadas. Ele tem um amplo mecanismo de segmentação que permite uma análise eficiente da segmentação e do público-alvo. Ele também possui um entendimento geral da sequência dos pontos de dados, o que é útil para analisar o comportamento desses pontos de dados (a ordem em que as coisas ocorreram) e realizar atribuições usando vários modelos complexos.

* **Aplicação rápida de segmentos e caminhos complexos**: o mecanismo de relatórios funciona em conjuntos de dados hierárquicos parcialmente ordenados (por exemplo, pessoa -> sessões -> eventos). Todos os dados de um objeto de nível superior (perfis individuais) residem em um único nó de processamento para garantir resultados precisos. Esse particionamento permite a aplicação rápida de caminhos e segmentos complexos. Operações complexas, como criação de sessões, atribuição, persistência de atributos de dados com monitoramento de estado e opções complexas de manipulação de dados são executadas em escala com uma rápida geração de relatórios. No contexto de BI, esses tipos de operações normalmente exigem a criação de novos cubos OLAP para cada caso de uso. O mecanismo de relatórios do Customer Journey Analytics permite acesso irrestrito a todo o conjunto de dados em cada consulta, resultando em dados totalmente correlacionados sem a necessidade de formação antecipada de cubos.

* **Consulta eficiente de sequências de dados complexas**: uma das maiores diferenças do mecanismo de relatórios se comparado a bancos de dados SQL e NoSQL tradicionais é sua capacidade de determinar predicados com base em relações orientadas por sequências em um nível fundamental. Essas operações fundamentais de consulta podem observar o fluxo de registro, que é composto por muitas sequências intercaladas (e até aninhadas). Eles executam uma consulta em relação a todos esses fluxos de dados interligados com a eficiência de uma única operação de sequência contígua.

* **Desenvolvido para responder rapidamente a consultas grandes**: o mecanismo de relatórios não possui um propósito tão geral quanto os tradicionais sistemas de “big data”. No entanto, ele foi desenvolvido especificamente para responder consultas que abrangem milhões ou até bilhões de registros (dados de evento/eventos de experiência), geralmente em menos de um segundo. Ao contrário de outros sistemas “big data”, ele não faz isso amostrando os dados ou pré-calculando as respostas para todas as perguntas que acha que você pode fazer. Em vez disso, ele é capaz de computar as respostas com rapidez suficiente para dar suporte a casos de uso de consulta interativa. Esse design específico do mecanismo de relatórios do Customer Journey Analytics facilita a disponibilização dos dados em alta velocidade para análise e exploração contínuas, permitindo assim obter insights de maneira progressiva e entender as jornadas de cliente.

* **Atua como uma solução de BI sem interface**: é possível definir dimensões, métricas e segmentos de um só lugar, e qualquer cliente do Customer Journey Analytics (incluindo nossa API pública do Customer Journey Analytics) pode acessar esses componentes. Isso oculta as consultas complexas dos usuários finais e garante que os resultados sejam os mesmos, independentemente do cliente de relatório ou visualização usado.

## Recursos de visualização exclusivos do Customer Journey Analytics

O mecanismo de relatórios é fundamental para o Customer Journey Analytics, permitindo que você interaja progressivamente e atue em todos os dados de jornada de cliente desse mecanismo. O Customer Journey Analytics vem com um conjunto extenso de componentes que capacitam você a fazer isso visualmente e por meio de uma interface de arrastar e soltar. As ferramentas de visualização de BI permitem explorar os limites dos dados preparados por SQL (conforme definido pela equipe de TI). O Customer Journey Analytics permite detalhar e destrinchar os dados o quanto quiser, sem precisar recorrer a equipe de TI para criar mais uma visualização de SQL.

A “progressividade” é um conceito-chave aqui, pois diferentemente da maioria das visualizações nas ferramentas de BI, a interface de arrastar e soltar do Customer Journey Analytics permite detalhar seus dados continuamente para suas necessidades específicas: é possível criar consultas visuais de forma interativa usando métricas, dimensões, segmentos, cálculos, linhas de tempo, anotações e outros componentes de análise relevantes.

Integrados a esses componentes de visualização, estão recursos inteligentes como:

* **Recursos de análise virtual**, como a [Detecção de anomalias](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) que usa algoritmos preditivos e aprendizado de máquina para fornecer insights sobre o que estaria gerando comportamentos incomuns em seus dados.

* **Recursos de análise avançada** que se concentram especificamente em insights de jornada de cliente, como [diagramas de fluxo](/help/analysis-workspace/visualizations/c-flow/flow.md), [painel de atribuição](/help/analysis-workspace/c-panels/attribution.md), [diagramas de fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) e [detalhamentos de dimensão](/help/components/dimensions/t-breakdown-fa.md). Exemplos de visualizações prontas para uso são:

   * [Análise de retenção do cliente por meio de tabelas de coorte/latência](/help/analysis-workspace/visualizations/cohort-table/cohort-use-cases.md), que permitem simplesmente arrastar e soltar métricas/dimensões em um construtor, gerando resultados em menos de 30 segundos,

   * Visualizações de [fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)/[fluxo](/help/analysis-workspace/visualizations/c-flow/create-flow.md). Configurado em menos de um minuto.

* **Recurso de segmentação em cada etapa da exploração progressiva**: sempre que achar relevante, publique novamente o seu público na Experience Platform e, em seguida, em um dos destinos compatíveis.

* **Criação de sessões** completamente [personalizáveis](/help/data-views/component-settings/persistence.md): determine quando uma sessão, como parte de um canal em uma jornada do cliente, começa e termina.

* **Curadoria e democratização**: os painéis criados no Customer Journey Analytics podem ser:

   * [Preparados](/help/analysis-workspace/curate-share/curate.md) para exploração contínua por outras pessoas da organização,
   * Exportados para o Excel usando o [Report Builder](/help/report-builder/rb-overview.md) (um plug-in dedicado),
   * [Compartilhados](/help/analysis-workspace/curate-share/share-projects.md) em vários formatos, incluindo [PDF](/help/analysis-workspace/export/download-send.md), [CSV](/help/analysis-workspace/export/download-send.md) e através de um [aplicativo móvel dedicado](/help/mobile-app/home.md), com aqueles que estão interessados nos relatórios finais e/ou visualizações.

Comparar os recursos de visualização do Customer Journey Analytics com o que as ferramentas de BI oferecem é uma tarefa difícil devido à variedade de visualizações disponíveis. Algumas ferramentas de BI têm visualizações mais avançadas, mas o Customer Journey Analytics se concentra em visualizações de jornada de cliente interativas e interoperáveis que permitem detalhar os dados em segundos, sem “cobrar” por cada consulta adicional.


## Resumo

O Customer Journey Analytics se diferencia das ferramentas de BI na forma como integra perfeitamente um mecanismo de relatórios altamente otimizado e voltado para a jornada de cliente, o que é obtido por meio de ferramentas e componentes práticos para a realização de análises e criação de relatórios e visualizações avançadas. Tudo isso por meio de uma única interface, sem que seja necessário alternar entre o mecanismo de consulta e o ambiente de visualização.
