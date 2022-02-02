---
title: Configurações do componente de desduplicação de métrica
description: Conte somente a primeira ocorrência de uma métrica nos relatórios.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 100%

---

# Configurações do componente de desduplicação de métrica

A desduplicação de métrica permite configurar uma métrica para contar apenas valores de forma não repetitiva.

| Configuração | Descrição |
| --- | --- |
| Desduplicação de métrica | Uma caixa de seleção que permite ativar a desduplicação de métrica. Desabilitado por padrão. |
| Escopo de desduplicação | Permite determinar até que ponto a verificação única vai.<br>**Sessão**: somente a primeira ocorrência de métrica da sessão é contada.<br>**Pessoa**: somente a primeira ocorrência de métrica na janela de relatório é contada. |
| ID de desduplicação | Em vez de aplicar a desduplicação na própria métrica, é possível aplicá-la com base em uma dimensão. Importante para que dimensões como a ID de compra possam aplicar a desduplicação. |
