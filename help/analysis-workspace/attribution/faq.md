---
title: Perguntas frequentes sobre Atribuição
description: Obtenha respostas para perguntas frequentes sobre atribuição.
feature: Attribution
exl-id: 3153d8c9-4ca8-4189-8a2f-511a87e8ac17
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 88%

---

# Perguntas frequentes sobre Atribuição

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). [Saiba mais...](/help/getting-started/cja-aa.md)

**O que é o item de linha “Nenhum” na atribuição?**

O item de linha “Nenhum” é um item “catch-all” (global) que representa todas as conversões que ocorreram sem nenhum ponto de contato na janela de retrospectiva. Tente incluir um intervalo de tempo maior na janela de relatórios.

**Por que às vezes vejo datas fora da minha janela de relatórios ao usar modelos de atribuição?**

Essas datas extras aparecem devido à janela de retrospectiva do visitante. Consulte [Dados que aparecem fora da janela de relatórios](https://helpx.adobe.com/br/analytics/kb/data-appearing-outside-reporting-window.html) na base de conhecimento (KB) do Analytics para obter mais informações. O Adobe excluirá essas linhas adicionais nas próximas versões.

**Quando devo usar retrospectiva de atribuição de visita e quando devo usar retrospectiva de atribuição de visitante?**

A escolha da retrospectiva de atribuição depende do seu caso de uso. Se as conversões normalmente levam mais tempo do que uma visita única, recomenda-se a retrospectiva de visitante. Criar uma visualização de dados com uma definição de visita mais longa também é uma solução possível.

**Como funciona a comparação de props e eVars na atribuição?**

A atribuição é recalculada no tempo de execução do relatório, portanto, não há diferença entre prop e eVar (ou qualquer outra dimensão) para fins de modelagem de atribuição. As props podem persistir usando qualquer janela de retrospectiva ou modelo de atribuição, e as configurações de alocação/expiração de eVar são ignoradas.

**Que dimensões e métricas são incompatíveis?**

O painel de atribuição é compatível com todas as dimensões. As métricas não compatíveis incluem as seguintes:

* Visitantes únicos
* Visitas
* Ocorrências
* Exibições de página
* Métricas do A4T
* Métricas de tempo gasto
* Rejeições
* Taxa de rejeição
* Entradas
* Saídas
* Páginas não encontradas
* Pesquisas
* Visitas em única página
* Acesso único

**Como a atribuição funciona com filtros?**

A atribuição sempre é executada antes dos filtros e os filtros globais são executados antes de qualquer outro filtro de relatório ser aplicado.
