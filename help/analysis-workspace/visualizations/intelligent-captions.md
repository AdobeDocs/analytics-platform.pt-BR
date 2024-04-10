---
description: Use legendas inteligentes para gerar insights em linguagem natural e exibir tendências rapidamente nas visualizações.
title: Legendas inteligentes
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 542cbb35d3870b8eef6fe252d1ac20962a1b2b8f
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 2%

---

# Legendas inteligentes

As legendas inteligentes usam aprendizagem de máquina avançada e IA gerativa para fornecer insights valiosos de linguagem natural para visualizações do Workspace. A versão inicial fornece insights gerados automaticamente para o [Linha](line.md) visualização. (Outras visualizações se seguirão.)

As legendas inteligentes são voltadas para:

* Analistas que precisam de narrativas para compartilhar com outros usuários. Os analistas precisam desses insights para fornecer contexto aos usuários.
* Usuários empresariais que desejam descobrir rapidamente as principais vantagens.

As legendas estão disponíveis para todos os usuários de Customer Journey Analytics e não exigem permissões especiais.

## Iniciar legendas inteligentes {#launch}

Para iniciar legendas geradas automaticamente para uma visualização de linha, clique no **[!UICONTROL Legendas inteligentes]** ícone na parte superior direita da visualização.

![Janela Análise do Launch mostrando as legendas inteligentes para a tendência de Exibições de produto. ](assets/intell-caps-1.png)

Os insights de linguagem natural estão sendo gerados agora.

Lembre-se

* É necessário ter no mínimo 3 pontos de dados para que as legendas sejam geradas com êxito. Caso contrário, você poderá receber um erro com a frase &quot;Dados insuficientes para analisar&quot;.

* As legendas são geradas sempre que os dados subjacentes selecionados mudam na tabela que possibilita a visualização.

* Se houver várias métricas na tabela, as legendas serão geradas apenas para a primeira métrica ou para a métrica selecionada no momento pelo usuário.

* Se você salvar o projeto neste ponto e recarregá-lo posteriormente, as legendas serão atualizadas automaticamente com novos dados. O mesmo se aplica a projetos agendados e arquivos PDF exportados deste projeto.

## Exibir e interpretar legendas {#view}

Esta é uma amostra de como as legendas podem ser:

![Legendas inteligentes para visualização de Linha, incluindo Sazonalidade, Mín, Máx, Pico e Declínio.](assets/captions.png)

## Copiar para a área de transferência {#copy}

Você pode copiar as legendas para uma área de transferência e colá-las em um PowerPoint ou outra ferramenta. Localize o **[!UICONTROL Copiar legendas para a área de transferência]** ícone na parte superior direita da caixa de diálogo de legendas.

## Editar legendas {#edit}

É possível editar as legendas, como ocultar ou reexibir uma categoria específica de insights. Por exemplo, se você não quiser obter informações sobre a ordem mínima, oculte-a e clique em Aplicar para que ela não seja exibida novamente.

1. Clique em **[!UICONTROL Editar exibição inteligente de legendas]** ícone ao lado do ícone da área de transferência.

1. Na caixa de diálogo de edição, clique no ícone de olho ao lado do insight que você deseja ocultar.

1. Clique em **[!UICONTROL Aplicar]**.

Use o mesmo processo para exibir legendas.

## Exportar legendas {#export}

Você pode **exportar legendas via PDF**, desde que o projeto seja salvo com as legendas geradas.

## Ativar/desativar legendas {#toggle}

Se você preferir não gerar legendas inteligentes, é possível desativar esse recurso acessando as Preferências de visualização e desmarcando **[!UICONTROL Mostrar legendas inteligentes]**.

![Opções de visualização de linha que mostram a opção de desmarcar Mostrar legendas inteligentes.](assets/toggle-captions.png)

## Legendas inteligentes em cartões de pontuação móveis

As legendas inteligentes também estão disponíveis no Customer Journey Analytics [cartões de pontuação móveis](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions).