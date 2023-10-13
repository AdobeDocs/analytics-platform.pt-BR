---
title: Cancelar solicitações de relatórios no Gerenciador de atividades de relatórios
description: Saiba mais sobre como usar o Gerente de atividade de relatórios para diagnosticar e corrigir problemas de capacidade durante o pico dos relatórios.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 23509d26e08b50a6b7a133fdc9a3e2d2d3e8fe43
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 7%

---

# Cancelar solicitações de relatórios no Gerenciador de atividades de relatórios

{{release-limited-testing}}

A variável [!UICONTROL Gerenciador de atividades de relatórios] O permite que os administradores diagnostiquem e cancelem rapidamente as solicitações de relatórios para corrigir problemas de capacidade durante o pico dos relatórios.

Considere o seguinte ao cancelar solicitações de relatórios:

* Você pode cancelar solicitações específicas, cancelar todas as solicitações de um usuário específico ou cancelar todas as solicitações relacionadas a um projeto específico.

* Ao cancelar solicitações, você também pode optar por restringir solicitações subsequentes por um determinado período.

* Não é possível cancelar uma solicitação se a variável [!UICONTROL **Usuário**] a coluna de uma solicitação é exibida como [!UICONTROL **Não reconhecido**]. Quando isso ocorre, significa que o usuário está em uma empresa de logon na qual você não tem permissões administrativas.

Para obter mais informações sobre o Gerente de atividades de relatórios, incluindo os principais benefícios e requisitos de permissão, consulte [Visão geral do Gerenciador de atividades de relatórios](/help/reporting-activity-manager/reporting-activity-overview.md).

## Cancelar solicitações específicas

Você pode cancelar solicitações individuais que estão consumindo uma grande quantidade de capacidade de relatório.

1. No Customer Journey Analytics, acesse **[!UICONTROL Ferramentas]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione a conexão na qual deseja cancelar solicitações de relatórios. <!--double-check this step-->

   Para obter mais informações sobre os dados disponíveis nesta página, consulte [Exibir atividade de relatórios no Gerenciador de atividades de relatórios](/help/reporting-activity-manager/reporting-activity.md).

1. Selecione o [!UICONTROL **Solicitações**] e selecione uma ou mais solicitações.

   <!-- add screenshot -->

1. Selecionar [!UICONTROL **Cancelar solicitações**].

   A variável [!UICONTROL **Cancelar _x_ solicitações de relatório**] é exibida.

1. O campo de mensagem Cancelamento mostra a mensagem que o exibe aos usuários quando as solicitações são canceladas. Uma mensagem padrão é fornecida. Você pode atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras por um determinado período, habilite a opção para [!UICONTROL **Restringir solicitações subsequentes**], em seguida, escolha entre as seguintes opções:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Usuário e projeto**] | Os usuários associados às solicitações selecionadas estarão temporariamente impedidos de executar solicitações de relatórios para os projetos associados. |
   | [!UICONTROL **Usuário**] | Usuários(as) associados(as) às solicitações selecionadas serão temporariamente restringidos(as) de fazer solicitações de relatórios. |
   | [!UICONTROL **Projeto**] | Os projetos associados às solicitações selecionadas ficarão temporariamente fechados a todas as solicitações de relatórios. |
   | [!UICONTROL **Restrito para**] | Escolha por quanto tempo as solicitações serão restritas. Você pode escolher 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!-- double-check this --><p>Não é possível remover uma restrição antecipadamente depois que ela é definida.</p> |

   {style="table-layout:auto"}

1. Selecionar [!UICONTROL **Continuar com o cancelamento**].

   Uma notificação é exibida no Analysis Workspace, informando aos usuários que a solicitação foi cancelada. Para obter mais informações sobre como isso é exibido no Analysis Workspace, consulte [Experiência quando usuários acessam um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Cancelar solicitações por usuário

Você pode cancelar todas as solicitações associadas a um ou mais usuários.

1. No Customer Journey Analytics, acesse **[!UICONTROL Ferramentas]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione a conexão na qual deseja cancelar solicitações de relatórios. <!--double-check this step-->

   Para obter mais informações sobre os dados disponíveis nesta página, consulte [Exibir atividade de relatórios no Gerenciador de atividades de relatórios](/help/reporting-activity-manager/reporting-activity.md).

1. Selecione o [!UICONTROL **Usuários**] e selecione um ou mais usuários.

   <!-- add screenshot -->

1. Selecionar [!UICONTROL **Cancelar solicitações**].

   A variável [!UICONTROL **Cancelar _x_ solicitações de relatório de x usuários**] é exibida.

1. O campo de mensagem Cancelamento mostra a mensagem que o exibe aos usuários quando as solicitações são canceladas. Uma mensagem padrão é fornecida. Você pode atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras por um determinado período, habilite a opção para [!UICONTROL **Restringir solicitações subsequentes**], em seguida, escolha entre as seguintes opções:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Usuário e projeto**] | Os usuários selecionados serão temporariamente impedidos de fazer qualquer solicitação de relatório para os projetos associados. |
   | [!UICONTROL **Usuário**] | Os usuários selecionados serão temporariamente impedidos de fazer qualquer solicitação de relatório. |
   | [!UICONTROL **Projeto**] | Os projetos associados aos usuários selecionados serão impedidos de qualquer solicitação de relatório feita por qualquer usuário. |
   | [!UICONTROL **Restrito para**] | Escolha por quanto tempo as solicitações serão restritas. Você pode escolher 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!--double-check this--> <p>Não é possível remover uma restrição antecipadamente depois que ela é definida.</p> |

   {style="table-layout:auto"}

1. Selecionar [!UICONTROL **Continuar com o cancelamento**].

   Uma notificação é exibida no Analysis Workspace, informando aos usuários que a solicitação foi cancelada. Para obter mais informações sobre como isso é exibido no Analysis Workspace, consulte [Experiência quando usuários acessam um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Cancelar solicitações por projeto

Você pode cancelar todas as solicitações associadas a um ou mais projetos.

1. No Customer Journey Analytics, acesse **[!UICONTROL Ferramentas]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione a conexão na qual deseja cancelar solicitações de relatórios. <!--double-check this step-->

   Para obter mais informações sobre os dados disponíveis nesta página, consulte [Exibir atividade de relatórios no Gerenciador de atividades de relatórios](/help/reporting-activity-manager/reporting-activity.md).

1. Selecione o [!UICONTROL **Projetos**] e selecione um ou mais projetos.

   <!-- add screenshot -->

1. Selecionar [!UICONTROL **Cancelar solicitações**].

   A variável [!UICONTROL **Cancelar _x_ solicitações de relatório de x projetos**] é exibida.

1. O campo de mensagem Cancelamento mostra a mensagem que o exibe aos usuários quando as solicitações são canceladas. Uma mensagem padrão é fornecida. Você pode atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras por um determinado período, habilite a opção para [!UICONTROL **Restringir solicitações subsequentes**], em seguida, escolha entre as seguintes opções:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Usuário e projeto**] | Os projetos selecionados estarão temporariamente restritos a quaisquer solicitações de relatórios feitas pelos usuários associados. |
   | [!UICONTROL **Usuário**] | Os usuários associados aos projetos selecionados não poderão fazer solicitações de relatórios. |
   | [!UICONTROL **Projeto**] | Os projetos selecionados estarão temporariamente restritos a quaisquer solicitações de relatórios feitas por qualquer usuário do. |
   | [!UICONTROL **Restrito para**] | Escolha por quanto tempo as solicitações serão restritas. Você pode escolher 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!--double-check this--> <p>Não é possível remover uma restrição antecipadamente depois que ela é definida.</p> |

   {style="table-layout:auto"}

1. Selecionar [!UICONTROL **Continuar com o cancelamento**].

   Uma notificação é exibida no Analysis Workspace, informando aos usuários que a solicitação foi cancelada. Para obter mais informações sobre como isso é exibido no Analysis Workspace, consulte [Experiência quando usuários acessam um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Experiência quando usuários acessam um relatório cancelado

No Analysis Workspace, os usuários veem a seguinte mensagem ao tentar acessar um relatório que foi cancelado por um administrador:

![cancel-user-notice](assets/cancel-user-facing.png)