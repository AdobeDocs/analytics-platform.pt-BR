---
title: Considerações sobre o Data Mirror
description: Entenda as considerações adicionais a serem consideradas quando quiser sincronizar dados entre as soluções nativas de data warehouse e a Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
autotag-review: '2026-05-19T06:55:09.938Z'
TQID: 'https://experienceleague.adobe.com/uZjXZUKUMeXLxxpTRrkCZrPsGhxseSxOtJ9X0ZjG5wU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: bfef374d-acfd-4c57-bf74-a2b36053c545id: e1471301-a189-438e-8d48-264a8db508a6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d00e9f03-e50b-4162-b143-0c0817c937c2id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 832
ht-degree: 1%

---

# Considerações sobre o Experience Platform Data Mirror

Este artigo descreve fatores que você deve considerar ao configurar conjuntos de dados do Data Mirror.

## Nova coluna para tabela de origem

Quando uma nova coluna é adicionada a uma tabela de origem em um conjunto de dados espelhado de dados habilitado para CDC, essa alteração pode acionar atualizações para todas as linhas existentes. Essas atualizações são processadas como alterações por meio do CDC, que:

* Pode se comportar como uma regravação completa de tabela de uma perspectiva de progresso.
* Pode aumentar drasticamente o volume de assimilação, o que pode fazer com que a atualização exceda seu direito de assimilação.

A estratégia recomendada para colunas na tabela de origem:

* Verifique se todas as colunas relevantes estão definidas inicialmente.
* Mapeie cada coluna que você pode achar necessária inicialmente.

Se quiser adicionar uma nova coluna, há duas opções, dependendo se o preenchimento retroativo é obrigatório:

* Preenchimento retroativo:

   * Remover o conjunto de dados atual.
   * Configure o conector novamente com a coluna atualizada.

  Isso garante que os dados sejam preenchidos retroativamente de forma mais eficiente e oportuna.

* Sem preenchimento retroativo:

   * Adicione a coluna na tabela de origem.
   * Adicione a coluna no esquema do conjunto de dados de destino.
   * Atualize o mapeamento para incluir o novo campo (coluna) da tabela de origem para o conjunto de dados de destino.

Esta estratégia:

* Evita a evolução dispendiosa do esquema posteriormente (atualizações em massa ao adicionar colunas).
* Mantém o volume de alterações mais previsível do que quando as colunas são adicionadas ou modificadas posteriormente.
* Ajuda a limitar possíveis custos de computação no lado do banco de dados externo, já que o data warehouse pode interpretar a nova coluna como uma atualização para todas as linhas.


## Privacy Service

As solicitações de privacidade precisam ocorrer da mesma forma que as solicitações de privacidade são tratadas hoje para esquemas não relacionais, já que as solicitações de privacidade são indiferentes à forma como os dados são estruturados.

Os dados espelhados de um esquema relacional externo se tornam parte do ecossistema do Adobe e podem ser compartilhados em todo esse ecossistema, como por meio da Publicação de público-alvo da Customer Journey Analytics. O envio de uma solicitação de privacidade garante que as identidades e os dados associados sejam tratados corretamente em todo o ecossistema da Adobe.

Portanto, as solicitações de privacidade não devem se limitar ao conjunto de dados espelhado, mas também devem envolver atualizações nos dados de origem no banco de dados externo.

## Comportamento de higiene

O serviço de limpeza opera em *identidades primárias*, mas as tabelas no banco de dados externo espelhadas têm *chaves primárias*, não identidades primárias.

As consequências da diferença entre as identidades primárias e as chaves primárias são que as exclusões de higiene não podem ser executadas diretamente nessas tabelas relacionais. Como resultado, você deve:

* Exclua os dados em suas próprias tabelas de origem na solução de data warehouse e verifique se as operações de exclusão fluem pelo CDC (ou pela coluna de alteração manual).
* Envie solicitações de higiene e privacidade na Adobe para qualquer conjunto de dados downstream baseado em XDM com informações de identidade (por exemplo: visualizações do Customer Journey Analytics, conjuntos de dados do Real-Time Customer Data Platform, conjuntos de dados específicos do Adobe Journey Optimizer e muito mais).

A diferença entre a identidade primária e a chave primária introduz um modelo de responsabilidade compartilhada:

* A Adobe processa a higiene onde as identidades estão presentes.
* Você, como cliente, é responsável por alinhar seus próprios processos de higiene no banco de dados de origem às solicitações de higiene enviadas à Adobe.

## Diferenças de governança

Em [esquemas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/schema/composition) do XDM e em conceitos subjacentes como [grupos de campos](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field-group), um [campo](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field) definido em um grupo de campos propaga seus rótulos em todos os conjuntos de dados em que o grupo de campos é usado. Por exemplo, um campo de email `emailID` em um grupo de campos `identities`, é rotulado da mesma forma em todos os conjuntos de dados em que o grupo de campos `identities` é usado.

Em um esquema relacional, um nome de coluna é independente. Uma coluna chamada `email` na tabela `customers` é independente e distinta de uma coluna chamada `email` em uma tabela `prospects`. Esse comportamento implica que rótulos (como rótulos de uso DULE, políticas) devem ser aplicados individualmente aos campos nos conjuntos de dados espelhados. Com base no exemplo acima, você precisa aplicar rótulos tanto ao campo `email` no conjunto de dados `customers` quanto ao campo `email` no conjunto de dados `prospects`.

A diferença de governança tem o seguinte impacto:

* Mais controle manual e trabalho de configuração para você como cliente.
* Você pode precisar de orientação explícita, de modo que não presuma que a rotulagem única por meio de grupos de campos é suficiente para a governança adequada.

## Compilação

Os esquemas relacionais têm as seguintes considerações, pois estão relacionados à compilação:

* A compilação baseada em gráfico é parcialmente compatível. Esquemas relacionais não podem ser habilitados para perfil/contribuição para o gráfico.
* A compilação em campo é totalmente compatível.


## Chaves e campos do sistema

As seguintes considerações se aplicam a chaves e campos do sistema:

* A chave primária, o descritor de versão e o descritor de carimbo de data e hora precisam ser campos de nível raiz no esquema XDM relacional. Use o [mapeamento de campo](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema) durante a assimilação para dar suporte a este requisito.
* Você pode omitir campos de origem apropriados durante a [fase de mapeamento](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema).
