---
title: Interface de análise guiada
description: Saiba mais sobre a estrutura geral da interface do projeto de análise guiada.
source-git-commit: d73dc0eb1740f28c0cd0b7b64fee86069c402b63
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---

# Interface da análise do guia

{{release-limited-testing}}

A interface de um projeto de Análise guiada, independentemente do tipo de análise, inclui os seguintes elementos principais da interface do usuário:

* **Painel de consulta**: use esse painel à esquerda do projeto para criar a análise.
* **Gráfico**: após selecionar os eventos, as pessoas ou as etapas desejados, um gráfico é exibido à direita que visualiza os dados.
* **Tabela**: uma tabela abaixo do gráfico que mostra os números usados na visualização.
* **Configurações e insights**: vários elementos de interface acima do gráfico que permitem personalizar os dados retornados.

[Captura de tela da interface]

## Painel de consulta

[Captura de tela do painel de consulta]

O painel de consulta é onde você configura os componentes desejados que compõem um relatório. Tipos de análise diferentes compartilham várias opções de consulta; se dois tipos de análise compartilham opções de consulta, elas são transferidas ao alternar tipos de análise. Consulte [Tipos de análise](analysis-types/overview.md) para obter mais informações sobre as opções de consulta para cada tipo de análise respectivo.

## Gráfico

[Captura de tela do gráfico]

Uma visualização dos dados retornados com base na entrada do painel de consulta e nas configurações. A visualização exibida depende do tipo de exibição acima do gráfico. Os tipos de visualização disponíveis dependem do [Tipo de análise](analysis-types/overview.md) acima do painel de consulta.

## Tabela

[Captura de tela da tabela]

Uma representação em tabela dos dados retornados com base na entrada do painel de consulta e nas configurações. As colunas na tabela dependem do tipo de exibição acima do gráfico. Os tipos de visualização disponíveis dependem do [Tipo de análise](analysis-types/overview.md) acima do painel de consulta.

## Configurações 

[Captura de tela das configurações]

Várias opções acima do gráfico que permitem personalizar como o gráfico e a tabela retornam dados.

* **Tipo de visualização**: um seletor suspenso que permite apresentar dados para um determinado [Tipo de análise](analysis-types/overview.md) de forma diferente. Cada tipo de análise tem pelo menos dois tipos de visualização.
* **Configurações do gráfico**: ajuste a aparência do gráfico e os eventos que deseja usá-lo. As opções disponíveis dependem do tipo de visualização selecionado.
* **Intervalo de datas**: um seletor de calendário que permite determinar o intervalo de datas do relatório. Alguns tipos de análise também permitem intervalos, como diário, semanal ou mensal.
* **Insights**: fornece insights contextuais dependendo do relatório que você visualiza. Você pode mostrar ou ocultar esses insights usando o ícone de lâmpada na parte superior direita.

## Menu Projeto

[Captura de tela do menu Projeto]

Comandos na parte superior direita do projeto que fornecem ações abrangentes.

* **Seletor de visualização de dados**: altere a visualização de dados que esse projeto usa. Ao alterar a visualização de dados, os componentes disponíveis no painel de consulta também são alterados.
* **Salvar**: salva o projeto. Se você estiver salvando um novo projeto, será exibida uma janela modal que solicita um nome e uma descrição.
* **Salvar como**: salva o projeto separadamente do projeto atual, criando uma cópia. Uma janela modal é exibida solicitando um novo nome e descrição.
* **Abrir no Espaço de trabalho**: recria o projeto de análise guiada atual no Analysis Workspace. O projeto do espaço de trabalho é criado em uma nova guia, que evita a interrupção enquanto você trabalha no projeto de Análise guiada. Use esse comando quando a Análise guiada não oferecer a flexibilidade ou o insight específico que você está procurando. Por exemplo, você deseja uma [Tendências](analysis-types/trends.md) relatório que usa Sessões para um segmento e Pessoas para outro segmento.
* **Baixar PNG**: baixa o gráfico como um `.png`. O painel de consulta e a tabela não estão incluídos no gráfico.
* **Baixar SVG**: baixa o gráfico como um `.svg`. O painel de consulta e a tabela não estão incluídos no gráfico.
