---
title: IDs inválidas do Customer Journey Analytics
description: Entenda as IDs inválidas (BAVIDs) no Customer Journey Analytics. Saiba como identificar IDs inválidas em seus dados, por que elas afetam os relatórios e como investigar e resolver a exposição a ID inválida em suas conexões.
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: b7b2a1f3eb1c149caf65ab3e4321e4f4347695cc
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 0%

---


# IDs inválidas

Este artigo fornece contexto sobre IDs inválidas e como detectar a presença ou risco de ocorrência em seus dados usando o Serviço de consulta.


>[!INFO]
>
>IDs inválidas também são chamadas de BAVIDs na interface do Customer Journey Analytics (originadas do [Analytics BAVID](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16444)).
>

## Definição

No Customer Journey Analytics, como parte de todos os dados definidos em uma conexão, uma ID incorreta é um identificador:

* com um valor de ID específico que se origina
   * de um campo de ID de pessoa (conjuntos de dados não compilados), **ou**
   * de uma ID persistente ou um campo de ID de pessoa (conjuntos de dados habilitados para compilação),

  **e**
* está em mais de um milhão (1.000.000) eventos nos dados de conexão (contados para todos os conjuntos de dados na conexão), no prazo de um mês.

Quando um valor de ID é marcado como uma ID incorreta, os eventos futuros que contêm esse valor de ID são descartados dos dados de conexão e não são exibidos no relatório.

### Exemplo

Um exemplo de um cenário de IDs inválidas é que você tem valores personalizados ou de espaço reservado no campo de ID de pessoa (por exemplo, `undefined` para tráfego anônimo). Para um conjunto de dados habilitado para compilação, essa situação pode ter um impacto ainda maior nos dados do relatório, pois a qualidade da compilação provavelmente será afetada. Para resolver isso, pode ser necessário limpar e reativar a configuração de compilação, incluindo a exclusão de dados históricos de conjuntos de dados na conexão.


## Métricas

A interface Customer Journey Analytics Connection oferece **[!UICONTROL IDs inválidas]** informações de métricas em vários locais da interface.

* Você pode ver **[!UICONTROL IDs inválidas]** (ou **[!UICONTROL BAVIDs]**) como possíveis motivos para ignorar registros na caixa de diálogo **[!UICONTROL Verificar detalhes ignorados]**. Use o **[!UICONTROL Detalhes da verificação]** (se disponível) abaixo de **[!UICONTROL Registros ignorados]** na [tela de detalhes de uma conexão](/help/connections/create-connection.md).
* Para um conjunto de dados habilitado para compilação, a [**[!UICONTROL visualização do conjunto de dados]**](/help/stitching/use-stitching-ui.md#bad-ids) mostra **[!UICONTROL IDs inválidas]** como parte das **[!UICONTROL Métricas de compilação]**. Essa métrica pode ajudar a identificar possíveis casos de IDs inválidas. No entanto, esteja ciente de que essa métrica é calculada com base em um conjunto limitado de dados.

Consulte [Exposição a IDs inválidas](#bad-ids-exposure) para ajudar a identificar a presença de IDs inválidas para um conjunto de dados que você planeja usar em uma conexão (independentemente de a compilação estar habilitada ou não).


## Exposição

Para investigar a exposição de IDs inválidas em um determinado campo do conjunto de dados, considere executar a seguinte consulta no Serviço de consulta da Experience Platform. Verifique os principais valores de ID retornados para ver se há candidatos para IDs inválidas. Esteja ciente de que a [definição de ID incorreta](#definition) leva em consideração todos os conjuntos de dados na conexão.


### Identificar (risco de) IDs inválidas em um campo

Você pode usar o Experience Platform Query para serviço a fim de identificar o risco potencial de IDs inválidas em um campo.

A consulta abaixo retorna os primeiros 20 valores de ID de um campo. Em ordem decrescente por contagem do total de eventos. E em que cada valor é detectado em um determinado intervalo (por exemplo, nos últimos 30 dias).

Execute esta consulta para um campo de ID de pessoa específico que você deseja analisar. Para um conjunto de dados que precisa de compilação, você também pode executar a consulta para um campo de ID persistente.

```sql
SELECT
    /* INSERT FIELD HERE */,
    COUNT(*) AS occurrences
FROM /* INSERT DATASET TABLE NAME HERE */
WHERE timestamp >= NOW() - INTERVAL '30 days' 
GROUP BY /* INSERT FIELD HERE */
ORDER BY occurrences DESC
LIMIT 20; 
```

Na consulta, substitua `INSERT FIELD HERE` dependendo do tipo de campo que você investiga para IDs inválidas:

* `full.field.path.from.XDM.schema` (para campos de cadeia de caracteres definidos no esquema XDM)
* `identityMap['namespace_value'][0].id` (para campos definidos com `namespace_value` em `identityMap`)

Verifique os resultados para ver se há valores de ID problemáticos. Como valores personalizados ou de espaço reservado, ou valores com alta ocorrência que chegam ou podem chegar perto de 1 milhão em um mês no nível de dados da conexão.
Mesmo que sua implementação ainda esteja na fase de desenvolvimento, você deve avaliar o risco da presença de IDs inválidas assim que a configuração estiver estável e pronta para produção.
