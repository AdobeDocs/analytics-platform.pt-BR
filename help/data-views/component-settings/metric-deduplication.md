---
title: Configurações do componente de desduplicação de métrica
description: Conte somente a primeira ocorrência de uma métrica nos relatórios.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 9a31b1dcba4015f00dd7ae8c43b317e1c5679a2c
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 41%

---

# Configurações do componente de desduplicação de métrica

A desduplicação de métrica permite configurar uma métrica para contar apenas valores de forma não repetitiva.

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Desduplicação de métrica] | Uma caixa de seleção que permite ativar a desduplicação de métrica. Desabilitado por padrão. |
| [!UICONTROL Escopo de desduplicação] | Permite determinar até que ponto a verificação única vai.<br>**Sessão**: somente a primeira ocorrência de métrica da sessão é contada.<br>**Pessoa**: somente a primeira ocorrência de métrica na janela de relatório é contada. |
| [!UICONTROL ID de desduplicação] | Em vez de aplicar a desduplicação na própria métrica, é possível aplicá-la com base em uma dimensão. Importante para que dimensões como a ID de compra possam aplicar a desduplicação. |
| [!UICONTROL Valor a manter] | <ul><li>**Manter primeira instância**: Use isso em situações em que a instância inicial da métrica é válida. O mais comum provavelmente seria uma confirmação de compra. Mesmo que alguém recarregue inadvertidamente a página e obtenhamos outra instância de uma confirmação de compra, o evento inicial é válido.</li><li>**Manter última instância**: Use essa opção em situações em que a última instância faça mais sentido coletar. Exemplo: Alguém faz uma atualização no seu perfil online. Queremos contar apenas uma dessas atualizações por sessão. No entanto, eles podem atualizar seu perfil várias vezes durante a sessão. Se mantivermos a primeira instância, pode haver atividades que não se vinculariam ao evento. Nesse caso, faz mais sentido manter a última instância.</li></ul> |

{style=&quot;table-layout:auto&quot;}

>[!CAUTION]
>
>Desduplicação em uma _pessoa_ o escopo é avaliado por meses completos no horário UTC. Uma janela de relatório parcial de mês pode não exibir todas as primeiras ou últimas instâncias, se algumas ocorreram dentro do mês completo, mas fora das datas de relatório.
