---
title: Considerações sobre o Data Mirror
description: Entenda as considerações adicionais a serem consideradas quando quiser sincronizar dados entre as soluções nativas de data warehouse e a Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
hide: true
source-git-commit: 19351a7155eda77d1768b486c7e39dcf7cdba935
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 1%

---

# Considerações sobre o Experience Platform Data Mirror

Este artigo descreve fatores que você deve considerar ao configurar conjuntos de dados do Data Mirror.

## Nova coluna para tabela de origem

Quando uma nova coluna é adicionada a uma tabela de origem em um conjunto de dados espelhado de dados habilitado para CDC, essa alteração pode acionar atualizações para todas as linhas existentes. Essas atualizações são processadas como alterações por meio do CDC, que:

* Podem se comportar como uma reescrita completa de tabela a partir de uma perspectiva de custo.
* Pode aumentar drasticamente o volume de assimilação, especialmente com qualquer preço futuro de *multiplicador de alteração* (por exemplo, as operações de mesclagem podem ser cobradas a taxas mais altas).

A estratégia recomendada para colunas na tabela de origem:

* Certifique-se de que a maioria, se não todas, das colunas relevantes seja definida inicialmente.
* Mapeie cada coluna que você pode achar necessária inicialmente.

Esta estratégia:

* Evita a evolução dispendiosa do esquema posteriormente (atualizações em massa ao adicionar colunas).
* Mantém o volume de alterações mais previsível do que quando as colunas são adicionadas ou modificadas posteriormente.
* Pode incorrer em alguns custos de computação adicionais no lado do banco de dados externo, já que o data warehouse pode interpretar todas as colunas como atualizações.

Para lidar com novas colunas em tabelas de data warehouse externas, siga estas etapas:

1. Crie um novo schema com a coluna adicionada.
1. Configure um novo conector de origem que traga os dados para o.
1. Carregue o preenchimento retroativo adequadamente.
1. Usar alterações do CDC a partir de agora.

Essa abordagem minimiza o impacto em ambos os lados.

## Privacy Service

As solicitações de privacidade precisam ocorrer da mesma forma que as solicitações de privacidade são tratadas hoje para esquemas não relacionais, já que as solicitações de privacidade são indiferentes à forma como os dados são estruturados.

Os dados espelhados em um conjunto de dados externo com base em um esquema relacional se tornam parte do ecossistema do Adobe e podem ser compartilhados de várias maneiras. Por exemplo, por meio da publicação de público-alvo.

Portanto, as solicitações de privacidade não devem se limitar ao conjunto de dados espelhado, mas também devem envolver atualizações nos dados de origem no banco de dados externo.

## Comportamento de higiene

O serviço de limpeza opera em *identidades primárias*, mas as tabelas no banco de dados externo espelhadas têm *chaves primárias*, não identidades primárias.

As consequências da diferença entre as identidades primárias e as chaves primárias são que as exclusões de higiene não podem ser executadas diretamente nas tabelas relacionais. Como resultado, você deve:

* Exclua os dados em suas próprias tabelas de origem na solução de data warehouse e verifique se as operações de exclusão fluem pelo CDC (ou pela coluna de alteração manual).
* Envie solicitações de higiene e privacidade na Adobe para qualquer conjunto de dados downstream baseado em XDM com informações de identidade (por exemplo: visualizações do Customer Journey Analytics, conjuntos de dados do Real-Time Customer Data Platform, conjuntos de dados específicos do Adobe Journey Optimizer e muito mais).

A diferença entre a identidade primária e a chave primária introduz um modelo de responsabilidade compartilhada:

* A Adobe processa a higiene onde as identidades estão presentes.
* Você, como cliente, é responsável por alinhar seus próprios processos de higiene no banco de dados de origem com as solicitações de higiene enviadas ao Adobe.

## Diferenças de governança

Em [esquemas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/schema/composition) do XDM e em conceitos subjacentes como [grupos de campos](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/schema/composition#field-group), um [campo](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/schema/composition#field) definido em um grupo de campos propaga seus rótulos em todos os conjuntos de dados em que o grupo de campos é usado. Por exemplo, um campo de email `emailID` em um grupo de campos `identities`, é rotulado da mesma forma em todos os conjuntos de dados em que o grupo de campos `identities` é usado.

Em um esquema relacional, um nome de coluna é independente. Uma coluna chamada `email` na tabela `customers` é independente e distinta de uma coluna chamada `email` em uma tabela `prospects`. Esse comportamento implica que rótulos (como rótulos de uso DULE, políticas) devem ser aplicados individualmente aos campos nos conjuntos de dados espelhados. Com base no exemplo acima, você precisa aplicar rótulos tanto ao campo `email` no conjunto de dados `customers` quanto ao campo `email` no conjunto de dados `prospects`.

A diferença de governança tem o seguinte impacto:

* Mais controle manual e trabalho de configuração para você como cliente.
* Você pode precisar de orientação explícita, de modo que não presuma que a rotulagem única por meio de grupos de campos é suficiente para a governança adequada.
