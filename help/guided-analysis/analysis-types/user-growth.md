---
title: Crescimento de usuários
description: Acompanhe o crescimento da base de usuários do seu produto.
source-git-commit: c47c4364cbf027c24a355bb306ee786c3e2446a9
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 2%

---

# Crescimento de usuários

{{release-limited-testing}}

A variável **Crescimento do usuário** [Tipo de análise](overview.md) O fornece insights sobre o crescimento e a aquisição de usuários em um período específico. O eixo horizontal é sempre uma granularidade de tempo, enquanto o eixo vertical é sempre uma medida de usuários. Os usuários são analisados desde o início do intervalo de datas, divididos em quatro categorias:

* **Novo**: é a primeira vez que o usuário aparece no intervalo de datas especificado. O primeiro ponto de dados em um relatório é sempre 100% de usuários novos, já que o relatório não considera datas fora do intervalo de relatórios.
* **Repetir**: o usuário apareceu no ponto de dados imediatamente anterior e no ponto de dados atual.
* **Retornar**: o usuário não apareceu no ponto de dados imediatamente anterior, mas não é um novo usuário. Os usuários recorrentes não podem aparecer no primeiro ou no segundo ponto de dados, pois devem aparecer primeiro como um novo usuário e depois como um usuário inativo.
* **Inativo**: o usuário não apareceu no ponto de dados atual, mas apareceu no ponto de dados imediatamente anterior. Os usuários inativos não contam para o número total de usuários ativos.

Todos os usuários ativos (novo + repetição + retorno) aparecem como uma sombra de azul-petróleo acima do eixo horizontal, enquanto todos os usuários inativos aparecem em laranja abaixo do eixo horizontal.

Os casos de uso para esse tipo de análise incluem:

* **Avaliação de desempenho**: o crescimento do usuário permite avaliar o desempenho geral do produto em termos de aquisição de novos usuários. Ao rastrear as tendências de crescimento, é possível entender melhor se o seu produto está atraindo e retendo usuários no ritmo desejado.
* **Retenção e churn de usuário:** Este relatório fornece uma visualização clara dos períodos de alta ou baixa retenção de usuários. Reconhecer esses períodos de alta ou baixa retenção pode ajudar você a tomar decisões sobre o produto para incentivar alta retenção ou ajudar a minimizar o abandono.
* **Avaliação de campanha**: visualizar um relatório de crescimento do usuário específico para uma campanha específica pode ajudar você a entender não apenas quanto tráfego ele gerou, mas também quão bem a campanha ajudou os usuários a permanecerem envolvidos.

[Captura de tela do crescimento de usuários]

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **Eventos**: define o evento que você deseja medir no relatório. Como esse relatório é baseado no usuário, um usuário pode tocar no evento uma vez dentro da granularidade de data definida para ser contado como um usuário ativo. Somente um evento é compatível.
* **Pessoas**: define o segmento que você deseja medir no relatório. Somente um segmento é compatível.

## Exibir tipos

O crescimento de usuários oferece os seguintes tipos de exibição. Você pode alterar o tipo de visualização usando o menu suspenso na parte superior esquerda do gráfico.

* **Ativo:** Meça o crescimento da sua base de usuários.

## Configurações de gráficos

O crescimento de usuários oferece as seguintes configurações de gráfico. Você pode ajustar as configurações do gráfico usando o menu entre o tipo de exibição e o seletor de calendário.

* **Métrica**: define a métrica que você deseja medir. As opções incluem Número de usuários e Porcentagem de usuários.
* **Tipo de gráfico**: define o tipo de visualização que você deseja usar. As opções incluem Barra empilhada e Área empilhada.

## Intervalo de datas

Define o intervalo de datas desejado. Há dois componentes importantes nessa configuração:

* **Interval**: a granularidade de data em que você deseja exibir os dados. As opções válidas incluem Por hora, Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes que afetam o número de pontos de dados no gráfico e o número de colunas na tabela. Por exemplo, visualizar um relatório que abrange três dias com granularidade diária mostraria apenas três pontos de dados, enquanto um relatório que abrange três dias com granularidade horária mostraria 72 pontos de dados.
* **Data**: a data inicial e final do projeto. As predefinições de intervalo de datas estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para definir a data exata desejada.
