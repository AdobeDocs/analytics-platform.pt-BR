---
description: Perguntas frequentes sobre o espaço de trabalho e dicas para solução de problemas.
title: Perguntas frequentes
translation-type: tm+mt
source-git-commit: d14817f28e757e94435c3b1059765fabe7cec54b
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 84%

---


# Perguntas frequentes

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

| Pergunta | Resposta |
|--- |--- |
| **Quais são os pré-requisitos para usar o Analysis Workspace?** | O uso da Analysis Workspace requer uma implementação de Customer Journey Analytics funcional. Certifique-se de que sua organização esteja enviando dados para a Adobe Experience Platform antes de usar a ferramenta. |
| **Quais são os requisitos de administração e acesso para o Analysis Workspace?** | Consulte [Requisitos de administração](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **O uso do Analysis Workspace afetará a coleta de dados?** | Como o Analysis Workspace é uma ferramenta de relatórios, ela não exerce impacto na coleta de dados. Se você arrastar componentes indiscriminadamente para um projeto para ver o que acontece, não haverá nenhuma repercussão. Arraste diferentes combinações de dimensões e métricas para o projeto do seu espaço de trabalho para ver o que está disponível. Se você arrastar acidentalmente um componente inválido para o projeto do seu espaço de trabalho ou quiser voltar uma etapa, pressione ctrl+Z (Windows) ou cmd+Z (Mac) para desfazer a última ação realizada. Você também pode começar com uma tabulação limpa clicando em *[!UICONTROL Projeto] > [!UICONTROL Novo]* no menu superior esquerdo. |
| **Como implementar o Analysis Workspace?** | Não é necessária nenhuma implementação específica. A Analysis Workspace está disponível para todas as Customer Journey Analytics empresa. No entanto, as permissões padrão para o conteúdo (como componentes do projeto) se aplicam e para preparar e compartilhar projetos. Consulte [Requisitos de administração e acesso](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **Como posso otimizar o desempenho do Analysis Workspace?** | Consulte [Otimizar o desempenho](/help/analysis-workspace/workspace-faq/optimizing-performance.md). |

## Solução de problemas

**Quando eu arrasto uma métrica, vejo “Dados inválidos”.**

Dados inválidos significa que a Adobe não pode retornar dados usando a combinação de dimensões e métricas usadas no relatório. Por exemplo, duas métricas empilhadas uma sobre a outra não podem retornar como dados, pois não há como exibir duas métricas desse modo. Em vez disso, coloque as métricas lado a lado.

**Quando arrasto uma métrica, não vejo nenhum dado real, apenas zeros.**

Se você criar um relatório de espaço de trabalho com êxito, mas não houver dados, você pode realizar as seguintes verificações:

* Verifique novamente o conjunto de relatórios e veja se ele está preenchido com dados.
* Se você aplicar um segmento no seu relatório, os critérios do segmento podem não corresponder a nenhum dado. Tente remover o segmento ou ajustar a definição do segmento.
* Verifique o intervalo de datas no canto superior direito e verifique se ele está definido como um valor que você esperaria.
* Acesse seu site e use o [Depurador](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=pt-BR) para verificar se os dados estão sendo coletados.