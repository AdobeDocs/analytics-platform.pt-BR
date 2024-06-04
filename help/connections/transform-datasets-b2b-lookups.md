---
title: Transformar conjuntos de dados para pesquisas B2B
description: Descreve como transformar dados em conjuntos de dados de esquemas de pesquisa B2B específicos
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: ffa57c19174bf1618957efe7191c8486c8e3a900
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 5%

---

# Transformar conjuntos de dados para pesquisas B2B

Para oferecer suporte a pesquisas com base em pessoas em dados B2B (incluindo contas, oportunidades, listas de marketing e campanhas), é necessária a transformação de conjuntos de dados de pesquisa B2B.

Essa transformação só está disponível para conjuntos de dados com dados para esquemas de pesquisa B2B, com base nas seguintes classes:

* Relação pessoal da conta de negócios XDM
* Relação pessoal de oportunidade de negócios XDM
* Membros da lista de marketing de negócios XDM
* Membros da campanha de negócios XDM

Para ativar a transformação desse conjunto de dados:

![Habilitar conjunto de dados de transformação](assets/transform-dataset.gif)

* Selecione o identificador apropriado para **[!UICONTROL Chave]** e **[!UICONTROL Chave correspondente]**, por exemplo `personKey.sourceKey`.

* Selecione as opções para importar novos dados e preenchimento retroativo de conjunto de dados.

* Selecionar **[!UICONTROL Transformar conjunto de dados para pesquisas B2B]**.

  Essa opção transforma o conjunto de dados para que ele possa ser usado para pesquisas baseadas em pessoas em cenários B2B.


  >[!IMPORTANT]
  >
  >Uma vez ativada e quando a conexão é salva, a transformação é irreversível. Não é possível modificar a configuração de transformação de um conjunto de dados depois que uma conexão é salva, a não ser removendo e adicionando o conjunto de dados mais uma vez à conexão.

Para habilitar a transformação para um ou mais conjuntos de dados que já fazem parte de uma conexão existente:

1. Remova os conjuntos de dados da conexão.
1. Salve a conexão.
1. Adicionar os conjuntos de dados à conexão ao ativar a transformação para os conjuntos de dados

## Informações de fundo

Os conjuntos de dados não transformados para esquemas baseados nas quatro classes de esquema mencionadas acima podem conter várias linhas para um único identificador de pessoa. As pesquisas com base em pessoas correspondem apenas à ocorrência mais recente desse identificador de pessoa, impedindo uma pesquisa adequada com base em ID de pessoa de contas, oportunidades, listas de marketing ou campanhas.

A transformação modifica o conjunto de dados de cada uma das quatro classes de esquema (laranja na ilustração abaixo) para que cada identificador de pessoa crie uma matriz (objeto) para os dados relevantes (contas, oportunidades, listas de marketing ou campanhas) nos conjuntos de dados de pesquisa (rosa na ilustração abaixo). Essa transformação permite o funcionamento correto de pesquisas baseadas em ID de pessoa.

![Esquemas B2B](./assets/b2b-schemas.svg)
