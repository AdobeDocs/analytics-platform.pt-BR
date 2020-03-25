---
title: Visão geral das métricas calculadas
description: 'Saiba mais sobre '
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Visão geral das métricas calculadas

Métricas calculadas e calculadas avançadas (ou derivadas) são métricas personalizadas que podem ser criadas a partir de métricas existentes. Nossas ferramentas de Métricas calculadas ofertas uma maneira altamente flexível de criar, gerenciar e preparar métricas. Elas permitem que os profissionais de marketing, gerentes de produtos e analistas façam perguntas sobre os dados sem precisarem alterar a implementação do [!DNL Analytics]. 

É possível

* Crie métricas filtradas derivadas do tempo de execução do relatório, [sem precisar alterar a implementação](https://youtu.be/CuQTm9RaUpY). Estes podem ser vistos historicamente porque são baseados em filtros.
* Compartilhe métricas em conjuntos de relatórios. Isso significa que todas as métricas recém-criadas se aplicam a todos os conjuntos de relatórios na mesma empresa de logon.
* (Somente métricas calculadas avançadas) Filtrar em métricas. Por exemplo, você pode criar uma métrica para &quot;Novos visitantes&quot;, com uma contagem de pessoas para as quais esta é a primeira sessão.
* (Somente métricas calculadas avançadas) Incorpore funções estatísticas para ajudar a descrever melhor seus dados. Por exemplo, é possível contar o número de itens em um relatório ou adicionar o número de desvios padrão para cada item.

## Métricas calculadas versus métricas calculadas avançadas

Esta é uma comparação dos recursos de Métricas calculadas e Métricas calculadas avançadas:

| Opções do Construtor | Métricas calculadas | Métricas calculadas avançadas (derivadas) |
|---|---|---|
| Tipos de formatos (decimal, hora, percentual, moeda | Sim | Sim |
| Alterações de atribuição (padrão, linear, participação etc. | Sim | Sim |
| Tipos de métrica (padrão, total | Sim | Sim |
| Operadores básicos (adicionar, subtrair, multiplicar, dividir) | Sim | Sim |
| Aplicar filtros | Não | Sim |
| [Funções básicas (contagem, valor absoluto, meio etc.)](/help/components/calc-metrics/cm-functions.md) | Não | Sim |
| [Funções avançadas (regressão, if/then, t-score etc.)](/help/components/calc-metrics/cm-adv-functions.md) | Não | Sim |

## Ferramentas

| Ferramenta | Capacidades  |
|--- |--- |
| Criador de métricas calculada | <ul><li>Crie métricas calculadas e calculadas avançadas usando modelos de alocação avançados.</li><li>Adicionar filtros em linha às fórmulas de métricas.</li><li>Comparar filtros no mesmo relatório. Por exemplo, compare visitantes locais versus visitantes internacionais.</li><li>Use funções estatísticas.</li><li> Forneça descrições detalhadas da métrica (mostre o que ela faz, onde usá-la, onde NÃO usá-la).</li><li>Copie definições em novas métricas.</li><li>Forneça uma pré-visualização de métrica em linha.</li><li>Defina a polaridade da métrica, que indica se ela é boa ou ruim se um determinado evento personalizado (métrica) aumentar.</li><li>Marcar métricas.</li></ul> |
| Gerenciador de métricas calculadas | <ul><li>Compartilhe métricas com outras pessoas.</li><li>Aprovar e preparar métricas.</li><li>Organizar (marcar) suas métricas para que as pessoas possam encontrá-las.</li><li>Excluir métricas.</li><li>Renomear métricas.</li></ul> |
| API para métricas calculadas | Parte do conjunto de APIs do Adobe Analytics 2.0. |

