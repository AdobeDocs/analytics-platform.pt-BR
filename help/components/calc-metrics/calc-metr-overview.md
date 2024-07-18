---
title: Visão geral das métricas calculadas
description: Saiba mais sobre métricas filtradas derivadas do tempo de execução do relatório.
feature: Calculated Metrics
exl-id: c9205c95-8b01-4177-a89c-038886f41d3d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 100%

---

# Visão geral das métricas calculadas

Métricas calculadas e calculadas avançadas (ou derivadas) são métricas personalizadas que podem ser criadas a partir de métricas existentes. Nossas ferramentas para métricas calculadas oferecem uma maneira muito mais flexível para criar, gerenciar e preparar métricas. Elas permitem que os profissionais de marketing, gerentes de produtos e analistas façam perguntas sobre os dados sem precisarem alterar a implementação do.

É possível

* Criar métricas filtradas derivadas do tempo de execução do relatório, sem precisar alterar a implementação. Essas métricas podem ser exibidas historicamente, pois se baseiam em filtros.
* (Somente métricas calculadas avançadas) Filtrar as métricas. Por exemplo, é possível criar uma métrica de “Novas pessoas”, com uma contagem de pessoas para as quais esta é a primeira sessão.
* (Somente métricas calculadas avançadas) Incorpore funções estatísticas para ajudar a descrever melhor seus dados. Por exemplo, é possível contar o número de itens em um relatório ou adicionar o número de desvios padrão para cada item.

## Métricas calculadas versus métricas calculadas avançadas

Veja uma comparação entre os recursos de Métricas calculadas e Métricas calculadas avançadas:

| Opções do criador | Métricas calculadas | Métricas calculadas avançadas (derivadas) |
|---|---|---|
| Tipos de formatos (decimal, hora, percentual, moeda) | Sim | Sim |
| Alterações de atribuição (padrão, linear, participação etc.) | Sim | Sim |
| Tipos de métrica (padrão, total) | Sim | Sim |
| Operadores básicos (adição, subtração, multiplicação, divisão) | Sim | Sim |
| Aplicar filtros | Não | Sim |
| [Funções básicas (contagem, valor absoluto, meio etc.)](/help/components/calc-metrics/cm-functions.md) | Não | Sim |
| [Funções avançadas (regressão, if/then, t-score etc.)](/help/components/calc-metrics/cm-adv-functions.md) | Não | Sim |

## Ferramentas

| Ferramenta | Capacidades |
|--- |--- |
| Construtor de métrica calculada | <ul><li>Crie métricas calculadas e calculadas avançadas usando modelos de alocação avançados.</li><li>Adicionar filtros em linha às fórmulas de métricas.</li><li>Comparar filtros em um mesmo relatório. Por exemplo, compare pessoas locais com pessoas internacionais.</li><li>Usar funções estatísticas.</li><li> Fornecer descrições de métricas detalhadas (mostrar o que ela faz, quando usá-la, quando NÃO usá-la).</li><li>Copiar definições em novas métricas.</li><li>Fornecer uma visualização da métrica em linha.</li><li>Definir a polaridade da métrica, que indica se ela é boa ou ruim caso um determinado evento personalizado (métrica) apresente uma tendência para cima.</li><li>Adicionar tags às métricas.</li></ul> |
| Gerenciador de métricas calculadas | <ul><li>Compartilhar métricas com outras pessoas.</li><li>Aprovar e controlar métricas.</li><li>Organizar (marcar com tags) suas métricas de forma que as pessoas possam encontrá-las.</li><li>Excluir métricas.</li><li>Renomear as métricas.</li></ul> |
| API para métricas calculadas | Parte do conjunto de APIs do Customer Journey Analytics. |

## Modelos de métricas calculadas no Customer Journey Analytics

| Nome da métrica calculada | Descrição da métrica calculada |
| --- | --- |
| Sessões por pessoa | Número médio de sessões por pessoa |
| Taxa de início da sessão | A porcentagem de tempo em que qualquer item de dimensão ocorreu no primeiro evento de uma sessão. |
| Taxa de término da sessão | A porcentagem de tempo em que qualquer item de dimensão ocorreu no último evento de uma sessão. |
| Tempo gasto por pessoa | A quantidade média de tempo que uma pessoa gastou em determinado item de dimensão. |
| Tempo gasto por sessão | A quantidade média de tempo que uma pessoa gastou por sessão em qualquer item de dimensão. |
