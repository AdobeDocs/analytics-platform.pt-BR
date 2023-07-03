---
title: Crescimento de usuários
description: Acompanhe o crescimento da base de usuários do seu produto.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
feature: Guided Analysis
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 2%

---

# Crescimento de usuários

{{release-limited-testing}}

A variável **Crescimento do usuário** [Tipo de análise](overview.md) O fornece insights sobre o crescimento e a aquisição de usuários em um período específico. O eixo horizontal é sempre uma granularidade de tempo, enquanto o eixo vertical é sempre uma medida de usuários. Os usuários são analisados desde o início do intervalo de datas, divididos em quatro categorias:

* **Novo**: é a primeira vez que o usuário aparece no intervalo de datas especificado. O primeiro ponto de dados é sempre de 100% de usuários novos, já que a análise não parece fora do intervalo de datas.
* **Repetir**: o usuário apareceu no ponto de dados imediatamente anterior e no ponto de dados atual.
* **Retornar**: o usuário não apareceu no ponto de dados imediatamente anterior, mas não é um novo usuário. Os usuários recorrentes não podem aparecer no primeiro ou no segundo ponto de dados, pois devem aparecer primeiro como um novo usuário e depois como um usuário inativo.
* **Inativo**: o usuário não apareceu no ponto de dados atual, mas apareceu no ponto de dados imediatamente anterior. Os usuários inativos não contam para o número total de usuários ativos.

Todos os usuários ativos (novo + repetição + retorno) aparecem como uma sombra de azul-petróleo acima do eixo horizontal, enquanto todos os usuários inativos aparecem em laranja abaixo do eixo horizontal.

Os casos de uso para esse tipo de análise incluem:

* **Avaliação de desempenho**: o crescimento do usuário permite avaliar o desempenho geral do produto em termos de aquisição de novos usuários. Ao rastrear as tendências de crescimento, é possível entender melhor se o seu produto está atraindo e retendo usuários no ritmo desejado.
* **Retenção e churn de usuário:** O crescimento do usuário fornece uma visualização clara em torno de períodos de alta ou baixa retenção do usuário. Reconhecer esses períodos de alta ou baixa retenção pode ajudar você a tomar decisões sobre o produto para incentivar alta retenção ou ajudar a minimizar o abandono.
* **Avaliação de campanha**: visualizar o crescimento dos usuários em torno de uma campanha específica pode ajudar você a entender não apenas o tráfego gerado, mas também o quão bem a campanha ajudou os usuários a permanecerem envolvidos.

[Captura de tela do crescimento de usuários]

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **Eventos**: o evento que você deseja medir. Como esse tipo de análise se baseia no usuário, ele pode tocar no evento uma vez dentro da granularidade de data definida para ser contado como um usuário ativo. Você pode incluir apenas um evento em uma query.
* **Pessoas**: o segmento que você deseja medir. Você pode incluir apenas um segmento em uma consulta.

## Exibir tipos

O crescimento de usuários oferece os seguintes tipos de exibição. Você pode alterar o tipo de visualização usando o menu suspenso na parte superior esquerda do gráfico.

* **Ativo:** Meça o crescimento da sua base de usuários.

## Configurações de gráficos

O crescimento de usuários oferece as seguintes configurações de gráfico. Você pode ajustar as configurações do gráfico usando o menu entre o tipo de exibição e o seletor de calendário.

* **Métrica**: A métrica que você deseja medir. As opções incluem Número de usuários e Porcentagem de usuários.
* **Tipo de gráfico**: o tipo de visualização que você deseja usar. As opções incluem Barra empilhada e Área empilhada.

## Intervalo de datas

O período desejado. Há dois componentes importantes nessa configuração:

* **Interval**: a granularidade de data em que você deseja exibir os dados. As opções válidas incluem Por hora, Diariamente, Semanalmente, Mensalmente e Trimestralmente. O mesmo intervalo de datas pode ter intervalos diferentes que afetam o número de pontos de dados no gráfico e o número de colunas na tabela. Por exemplo, a visualização de uma análise abrangendo três dias com granularidade diária mostraria apenas três pontos de dados, enquanto uma análise abrangendo três dias com granularidade horária mostraria 72 pontos de dados.
* **Data**: a data inicial e final. As predefinições de intervalo de datas estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para definir a data exata desejada.
