---
title: Comparar soluções do Customer Journey Analytics às soluções de BI
description: Comparar soluções do Customer Journey Analytics às soluções de BI
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: ae66cd06-7ec1-4174-a3cf-939c3a66b840
source-git-commit: 7991f2be316349fcfaa85c2338e16c41d5b130b1
workflow-type: tm+mt
source-wordcount: '1649'
ht-degree: 65%

---

# Comparar soluções do Customer Journey Analytics às soluções de BI

Com o foco atual na experiência do cliente, as marcas exigem soluções avançadas para entender melhor a jornada integral do cliente. Entender por completo essa jornada do cliente permite analisar e obter informações valiosas sobre como os canais online e offline envolvem os clientes e levam ao aumento da conversão, retenção e fidelidade. Neste contexto, uma jornada do cliente pode ser um simples pedido online de uma refeição em uma franquia de sushi. Ou a compra de um carro novo, onde o cliente combina sua pesquisa online com visitas ao showroom do revendedor, finalizando a compra presencialmente.

Muitas organizações consolidaram seus dados omnicanal em um data lake ou data warehouse. As ferramentas de BI (Business Intelligence) são usadas sobre esses armazenamentos de dados para fornecer os relatórios, visualizações e insights que a empresa necessita para entender a jornada do cliente. Geralmente, essa combinação de soluções e ferramentas é um objetivo geral por natureza e intenção, e não se concentra explicitamente no cliente. O Customer Journey Analytics se concentra em capacitar os responsáveis pela experiência do cliente, como profissionais de marketing, analistas de dados e cientistas de dados. A ferramenta permite que eles visualizem o contexto completo da jornada do cliente em todos os canais em tempo real, sem limitações que muitas outras ferramentas de BI possuem.

Esta seção da documentação explica as diferenças fundamentais entre o Customer Journey Analytics e as ferramentas de BI comumente usadas, primeiro observando o fluxo de trabalho geral usado para alcançar o objetivo mencionado acima: compreender essa jornada do cliente. Em seguida, ele fornece mais detalhes sobre como os dados são armazenados, coletados e consultados de forma diferente entre as ferramentas Customer Journey Analytics e BI. Por fim, ela explica as diferenças nos recursos de visualização.

## Fluxo de trabalho tradicional de BI

Um obstáculo frequente com abordagens tradicionais para analisar jornadas de clientes é que elas não são centradas no cliente. Cada equipe coleta dados em silos, analisando e otimizando experiências com base nos dados aos quais tem acesso.

![Fluxo de trabalho de BI tradicional conforme descrito nesta seção](./assets/biworkflow.png)

Se quiser entender como uma campanha digital específica afeta uma ação offline armazenada em um silo de dados diferente, emita uma solicitação para a fila da equipe de BI. A equipe de BI registra a consulta necessária para adquirir e transformar os dados. Depois que os dados brutos são recuperados, a equipe de BI cria a visualização. Os dados são compartilhados com você, enquanto passa o tempo procurando insights e extraindo dados para ativação em outros sistemas.

Cada uma dessas etapas pode levar horas, dias ou até semanas. Se houver mais perguntas ou problemas com os dados consultados, poderá levar ainda mais tempo até que essas perguntas sejam abordadas e o ciclo continue. Para análise, exploração e compreensão contínuas da jornada do cliente, esse processo não é eficiente nem escalável. Além disso, as equipes de BI geralmente abordam mais do que apenas questões relacionadas à jornada do cliente.

## Customer Journey Analytics: Fluxo de trabalho democratizado para dados online e offline

O Customer Journey Analytics fornece um ambiente para conectar dados entre canais online e offline no nível geral do cliente com o único objetivo de entender a jornada do cliente. Ele exige uma configuração inicial para [conectar](/help/connections/overview.md) e [definir visualizações](/help/data-views/data-views.md) para os dados que você considerar relevantes. No entanto, uma vez concluídos, esses dados estarão prontamente disponíveis para análise e exploração contínuas. Você pode obter insights sobre as jornadas do cliente de maneira progressiva e entendê-las. Ao democratizar dados online e offline combinados, você pode responder perguntas relacionadas à jornada do cliente em segundos.

![fluxo de trabalho Customer Journey Analytics conforme descrito nesta seção](./assets/cjaworkflow.png)

Você pode usar o Customer Journey Analytics para fazer perguntas usando o ambiente visual do Analysis Workspace e obter insights quase instantaneamente. Os dados e relatórios entre canais são imediatamente disponibilizados, sem necessidade de um código SQL. Consultas e análises adicionais podem ser realizadas com uma simples operação de arrastar e soltar na interface, com dados totalmente correlacionados. Você pode continuar fazendo perguntas e explorando mais detalhes progressivamente, conforme necessário. Em seguida, é possível realizar ações imediatas sobre os insights descobertos, como compartilhar públicos para ativação e orquestração.

## Mecanismo avançado de relatórios do Customer Journey Analytics

O Customer Journey Analytics usa uma poderosa arquitetura proprietária que distribui análises em centenas ou até milhares de servidores para exibir dados no Analysis Workspace em segundos. Algumas propriedades notáveis dessa arquitetura de processamento incluem:

* **Otimizado para consultas individuais relacionadas ao cliente**: Tecnicamente, o Customer Journey Analytics armazena os dados em um mecanismo de relatórios distribuído que usa amplamente o armazenamento em cache. Esse mecanismo é ajustado para consultas responsivas em dados de eventos de nível individual e, como tal, é perfeitamente otimizado para consultas relacionadas ao cliente. O mecanismo de relatórios armazena dados em índices de bitmap orientados por coluna que permitem um cálculo rápido e preciso de métricas agregadas. Ele tem um mecanismo de filtragem abrangente que possibilita segmentação e análise de público eficientes. Ele também possui um entendimento geral da sequência dos pontos de dados, o que é útil para analisar o comportamento desses pontos de dados (a ordem em que as coisas ocorreram) e realizar atribuições usando vários modelos complexos.

* **Aplicação rápida de caminhos e filtros complexos**: o mecanismo de relatórios trabalha em conjuntos de dados hierárquicos parcialmente ordenados (por exemplo, pessoa -> sessões -> eventos). Todos os dados de um objeto de nível superior (perfis individuais) residem em um único nó de processamento para obter resultados precisos. Esse particionamento permite a aplicação rápida de caminhos e filtros complexos. Operações complexas, como criação de sessões, atribuição, persistência de atributos de dados com monitoramento de estado e opções complexas de manipulação de dados são executadas em escala com uma rápida geração de relatórios. No contexto de BI, esses tipos de operações normalmente exigem a criação de novos cubos OLAP para cada caso de uso. O mecanismo de relatórios Customer Journey Analytics permite acesso irrestrito a todo o conjunto de dados em cada query, resultando em dados totalmente correlacionados sem exigir cubos antecipadamente.

* **Consulta eficiente de fluxos de dados complexos**: uma das maiores diferenças do mecanismo de relatórios com relação ao uso de bancos de dados SQL e NoSQL tradicionais é sua capacidade de determinar predicados com base em relacionamentos orientados por sequência em um nível fundamental. Essas operações fundamentais de consulta podem observar o fluxo de registro, que é composto por muitas sequências intercaladas (e até aninhadas). Eles executam uma consulta em relação a todos esses fluxos de dados interligados com a eficiência de uma única operação de sequência contígua.

* **Desenvolvido para responder rapidamente a consultas grandes**: o mecanismo de relatórios não possui um propósito tão geral quanto os tradicionais sistemas de “big data”. No entanto, ele foi desenvolvido especificamente para responder consultas que abrangem milhões ou até bilhões de registros (dados de evento/eventos de experiência), geralmente em menos de um segundo. Ao contrário de outros sistemas “big data”, ele não faz isso amostrando os dados ou pré-calculando as respostas para todas as perguntas que acha que você pode fazer. Em vez disso, ele é capaz de computar as respostas com rapidez suficiente para dar suporte a casos de uso de consulta interativa. Esse design específico do mecanismo de relatórios do Customer Journey Analytics facilita a disponibilização imediata dos dados e a alta velocidade para a análise e exploração contínuas, permitindo, portanto, que você obtenha progressivamente insights e entenda as jornadas do cliente.

* **Atua como uma solução de BI headless**: Você define suas dimensões, métricas, filtros em um local e, em seguida, qualquer cliente Customer Journey Analytics (incluindo nossa API de Customer Journey Analytics pública) pode acessar esses componentes. Isso oculta as consultas complexas dos usuários finais e garante que os resultados sejam os mesmos, independentemente do cliente de relatório ou visualização usado.

## Recursos de visualização exclusivos do Customer Journey Analytics

O mecanismo de relatórios é fundamental para o Customer Journey Analytics, permitindo que você interaja e aja progressivamente em todos os dados de jornada do cliente nesse mecanismo de relatórios. O Customer Journey Analytics vem com um extenso conjunto de componentes que o capacitam a fazer isso visualmente e por meio do recurso de arrastar e soltar. As ferramentas de visualização de BI permitem explorar os limites dos dados preparados por SQL (conforme definido pela equipe de TI). O Customer Journey Analytics permite que você decomponha e divida os dados o quanto quiser, sem precisar voltar para a TI para criar outra visualização SQL.

&quot;Progressivamente&quot; é um conceito importante aqui: ao contrário da maioria das visualizações em ferramentas de BI, a interface visual de arrastar e soltar no Customer Journey Analytics permite detalhar continuamente seus dados para necessidades específicas: você pode criar consultas visuais interativamente usando métricas, dimensões, filtros (segmentos), cálculos, linhas de tempo, anotações e outros valores de análise relevantes.

Integrados a esses componentes de visualização, estão recursos inteligentes como:

* **Recursos de análise virtual**, como a [Detecção de anomalias](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) que usa algoritmos preditivos e aprendizado de máquina para fornecer insights sobre o que estaria gerando comportamentos incomuns em seus dados.

* **Recursos avançados de análise** que se concentram especificamente nos insights de jornada do cliente, como [diagramas de fluxo](/help/analysis-workspace/visualizations/c-flow/flow.md), [Painel de atribuição](/help/analysis-workspace/c-panels/attribution.md), [diagramas de fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), e [detalhamentos de dimensão](/help/components/dimensions/t-breakdown-fa.md). Exemplos de visualizações prontas para uso são:

   * [Análise de retenção do cliente por meio de tabelas de coorte/latência](/help/analysis-workspace/visualizations/cohort-table/cohort-use-cases.md), que permitem simplesmente arrastar e soltar métricas/dimensões em um construtor, gerando resultados em menos de 30 segundos,

   * Visualizações de [fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)/[fluxo](/help/analysis-workspace/visualizations/c-flow/create-flow.md). Configurado em menos de um minuto.

* **Recurso de segmentação em cada etapa da exploração progressiva**: sempre que achar relevante, publique novamente o seu público na Experience Platform e, em seguida, em um dos destinos compatíveis.

* **Criação de sessões** completamente [personalizáveis](/help/data-views/component-settings/persistence.md): determine quando uma sessão, como parte de um canal em uma jornada do cliente, começa e termina.

* **Curadoria e democratização**: os painéis criados no Customer Journey Analytics podem ser:

   * [Preparados](/help/analysis-workspace/curate-share/curate.md) para exploração contínua por outros indivíduos da organização,
   * Exportados para o Excel usando o [Report Builder](/help/report-builder/report-buider-overview.md) (um plug-in dedicado),
   * [Compartilhados](/help/analysis-workspace/curate-share/share-projects.md) em vários formatos, incluindo [PDF](/help/analysis-workspace/curate-share/download-send.md), [CSV](/help/analysis-workspace/curate-share/download-send.md) e através de um [aplicativo móvel dedicado](/help/mobile-app/home.md), com aqueles que estão interessados nos relatórios finais e/ou visualizações.

Comparar os recursos de visualização de Customer Journey Analytics com o que as ferramentas de BI oferecem é difícil devido à variedade de visualizações disponíveis. Algumas ferramentas de BI têm visualizações mais avançadas, mas o Customer Journey Analytics se concentra em visualizações interativas e interoperáveis de jornada do cliente, que permitem dividir os dados em segundos e não &quot;cobrar&quot; por cada consulta adicional.


## Resumo

O Customer Journey Analytics difere das ferramentas de BI na forma como integra um mecanismo de relatórios altamente otimizado focado na jornada do cliente perfeitamente com ferramentas e componentes amigáveis para realizar análises e criar relatórios e visualizações avançadas. Tudo isso por meio de uma única interface, sem que seja necessário alternar entre o mecanismo de consulta e o ambiente de visualização.
