---
title: Configurações do componente de desduplicação de métrica
description: Conte somente a primeira ocorrência de uma métrica em relatórios.
source-git-commit: 86522f1ea5ae241351514d954672ec5fd7990944
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 9%

---


# Configurações do componente de desduplicação de métrica

A desduplicação de métrica permite configurar uma métrica para contar apenas valores de forma não repetitiva.

| Configuração | Descrição |
| --- | --- |
| Desduplicação de métrica | Uma caixa de seleção que permite ativar a desduplicação de métrica. Desabilitado por padrão. |
| Escopo de desduplicação | Permite determinar até que ponto a verificação única vai.<br>**Sessão**: Somente a primeira ocorrência de métrica da sessão é contada.<br>**Pessoa**: Somente a primeira ocorrência de métrica na janela de relatório é contada. |
| ID de desduplicação | Em vez de aplicar a desduplicação na própria métrica, o permite aplicar a desduplicação de métrica com base em uma dimensão. Valioso para dimensões como ID de compra para aplicar desduplicação. |
