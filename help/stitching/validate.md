---
title: Validar A Compilação De Identidade No Customer Journey Analytics
description: Saiba como validar a compilação de identidade no Customer Journey Analytics. Meça as taxas de autenticação e a identificação antes e depois da compilação.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: b9b73926-6502-4a48-ba73-c784f80950d3
source-git-commit: 0eb3fec2e52fe0850c5f42777edbdb5d981988fb
workflow-type: tm+mt
source-wordcount: '1726'
ht-degree: 0%

---

# Validar compilação

O objetivo da [compilação de identidade](/help/stitching/overview.md) (ou simplesmente, compilação) é elevar a adequação de um conjunto de dados de evento para análise entre canais. Essa elevação é obtida quando todas as linhas de dados no conjunto de dados contêm a identidade de ordem mais alta desejada disponível. Essa elevação permite:

* Crie relatórios centrados em pessoas, sem deixar de fora pessoas anônimas.
* Conecte vários dispositivos a uma única pessoa.
* Conectar uma pessoa através de canais.

Este artigo descreve métodos de análise para medir a elevação de um ou mais conjuntos de dados compilados recém-criados e para fornecer confiança de que a compilação está oferecendo esses benefícios.

Os métodos de análise envolvem [configurações do componente de Visualização de dados](/help/data-views/component-settings/overview.md) que normalmente são acessíveis para administradores. Os métodos também exigem que os analistas, que trabalham em um projeto do Analysis Workspace, criem métricas calculadas e visualizações.

Embora esses métodos de análise possam ser usados para a compilação em campo e a compilação em gráfico, alguns elementos podem não estar presentes no conjunto de dados, especialmente em um cenário de compilação em gráfico. Esses elementos ausentes podem dificultar o cálculo do aumento diretamente no Analysis Workspace.

>[!NOTE]
>
>A (validação da) compilação de um ou mais conjuntos de dados contribui, em última análise, para melhorar a análise e os insights. No entanto, este artigo não discute o valor geral de uma configuração do Customer Journey Analytics que tem todos os conjuntos de dados no Experience Platform alinhados ao mesmo namespace de identidade. E que todos esses conjuntos de dados estejam bem unidos para realizar análises em toda a jornada do cliente.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Habilitação e validação de compilação](https://video.tv.adobe.com/v/3478125?captions=por_br&quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]



## Configuração na validação de conexões

Esta seção detalha como validar a compilação que você ativou na interface de Conexões.

### Recomendações de conexão

Para validar a compilação habilitada na interface de Conexões, selecione um período curto e representativo para **[!UICONTROL preenchimento retroativo de conjunto de dados]**. Por exemplo, uma semana.

No exemplo abaixo, você deseja compilar o conjunto de dados do evento. Você configurou uma conexão de teste na qual você adiciona o conjunto de dados do evento. Para esse conjunto de dados, você define o **[!UICONTROL ECID]** **[!UICONTROL Namespace]** como a **[!UICONTROL ID Persistente]** e o **[!UICONTROL Endereço de Email com Hash do Visitante (directMarketing.hashEmail)]** como a **[!UICONTROL ID de Pessoa]**. Para validar essa compilação, você define um **[!UICONTROL preenchimento retroativo de conjunto de dados]** para uma pequena janela de tempo (24 de janeiro de 2026 a 10 de fevereiro de 2026). Use essa pequena janela para validar se a compilação funciona conforme o esperado.

![Configuração de compilação](/help/stitching/assets/stitching-config.png)

### Pré-requisitos da visualização de dados

Para a validação da compilação, é necessário garantir que você tenha todas as dimensões e métricas necessárias do seu conjunto de dados compilado definidas em uma visualização de dados. Crie uma visualização de dados com base na conexão definida anteriormente. Na etapa **[!UICONTROL Componentes]** da configuração da visualização de dados, é necessário:

* Adicionar **[!UICONTROL Namespace de Identidade]** de **[!UICONTROL Métricas e Dimensões]** como uma dimensão à lista **[!UICONTROL Dimensões]**.

  ![Namespace de identidade](/help/stitching/assets/identity-namespace.png)


* Selecione o **[!UICONTROL Identificador de Endereço de Email com Hash do Visitante]** que você definiu como a ID de pessoa para seus eventos em **[!UICONTROL Campos de esquema]**. Adicione o campo como uma dimensão à lista **[!UICONTROL Dimensões]** e como uma métrica à lista **[!UICONTROL Métricas]**. Modifique o **[!UICONTROL Nome do componente]** da métrica para `Email set`.

  ![Identificador de email](/help/stitching/assets/email-identifier.png)

Certifique-se de salvar a visualização de dados.

### Criar projeto do Workspace

No Workspace, crie um novo projeto e use uma tabela de forma livre para mostrar a métrica **[!UICONTROL Conjunto de emails]** para o intervalo de datas definido para testar a configuração de compilação. Esta tabela de forma livre mostra os eventos que têm um endereço de email antes da compilação.

![Tabela de forma livre de visão geral da compilação - Conjunto de emails](/help/stitching/assets/workspace-emailset.png)

Para ver os eventos que têm um endereço de email definido após o processo de compilação, defina uma métrica calculada `Email stitched namespace`. Essa métrica calculada procura em **[!UICONTROL Eventos]** que tenham **[!UICONTROL Namespace de identidade]** igual ao namespace de email com hash `email_lc_sha256`.

![Visão geral da compilação - Métrica calculada do namespace compilado por email](/help/stitching/assets/cm-email-stitched-namespace.png)

Se você adicionar a nova métrica calculada **[!UICONTROL Namespace de email compilado]** à tabela de forma livre, verá o aumento no número de eventos que agora têm um endereço de email após o processo de compilação.

![Tabela de forma livre de visão geral da compilação - Email definido e compilado](/help/stitching/assets/workspace-emailset-stitched.png)

Você pode obter mais insights ao definir duas métricas calculadas adicionais.

* **[!UICONTROL Taxa de autenticação de email]**. Essa métrica calculada determina a taxa de autenticação antes do processo de compilação.

  ![Definição de métrica calculada da taxa de autenticação de email](/help/stitching/assets/cm-email-authentication-rate.png)

* **[!UICONTROL Taxa de autenticação compilada]**. Essa métrica calculada determina a taxa de autenticação após o processo de compilação.

  ![Definição de métrica calculada da taxa de autenticação compilada](/help/stitching/assets/cm-stitched-authentication-rate.png)

Adicione essas duas métricas calculadas adicionais à tabela de forma livre para ver o aumento de eventos compilados.

![Tabela de forma livre de visão geral da compilação - Autenticada](/help/stitching/assets/workspace-authenticated.png)

Para obter mais informações, você pode adicionar mais duas métricas calculadas (**[!UICONTROL Aumento percentual]** e **[!UICONTROL Aumento]**) à tabela de forma livre para ver o impacto da configuração de compilação.

![Tabela de forma livre de visão geral da compilação - Aumento autenticado](/help/stitching/assets/workspace-authenticated-lift.png)



## Solicitar validação de compilação

Esta seção detalha como validar a compilação solicitada no Adobe. Esse método está obsoleto, mas ainda pode ser que você tenha conjuntos de dados que foram compilados usando esse método.

### Pré-requisitos da visualização de dados

Para o plano de medição de validação de compilação, é necessário garantir que você tenha todas as dimensões e métricas necessárias do seu conjunto de dados compilado definidas em uma visualização de dados. Verifique se os campos `stitchedID.id` e `stitchedID.namespace.code` foram adicionados como dimensões. Embora o conjunto de dados compilado seja uma cópia exata do conjunto de dados original, o processo de compilação adiciona essas duas novas colunas ao conjunto de dados:

* Use `stitchedID.namespace.code` para definir uma dimensão de **[!UICONTROL Namespace compilado]**. Esta dimensão contém o namespace da identidade para a qual a linha foi elevada, por exemplo `Email` ou `Phone`. Ou o namespace para o qual o processo de compilação retorna, como `ECID`.
  ![Dimensão de namespace compilada](/help/stitching/assets/stitchednamespace-dimension.png)

* Use `stitchedID.id` para definir uma dimensão de **[!UICONTROL Valor de ID compilado]**. Essa dimensão contém o valor bruto da identidade. Por exemplo: email com hash, telefone com hash, ECID. Este valor é usado com **[!UICONTROL Namespace Compilado]**.
  ![Dimensão de ID compilada](/help/stitching/assets/stitchedid-dimension.png)


Além disso, é necessário adicionar duas métricas de compilação que são baseadas na presença de valores em uma dimensão.

1. Use o campo que contém a ID de pessoa do conjunto de dados compilado para configurar uma métrica que define se uma ID de pessoa está definida. Adicione essa ID de pessoa mesmo se estiver usando a compilação baseada em gráfico, pois a ID de pessoa ajuda a estabelecer uma linha de base. Caso a ID da pessoa não esteja contida no conjunto de dados, sua linha de base é 0%.

   No exemplo abaixo, `personalEmail.address` serve como a identidade e é usado para criar a métrica **[!UICONTROL _Conjunto de emails]**.
   ![Métrica do conjunto de emails](/help/stitching/assets/emailset-metric.png)

1. Use o campo `stitchedID.namespace.code` para criar uma métrica **[!UICONTROL Namespace compilado por email]**. Certifique-se de especificar [Incluir valores de exclusão nas configurações de componente](/help/data-views/component-settings/include-exclude-values.md), de modo que considere apenas valores do namespace para o qual você está tentando elevar linhas de dados.
   1. Selecione **[!UICONTROL Definir inclusão/exclusão de valores]**.
   1. Selecione **[!UICONTROL Se todos os critérios forem atendidos]** como **[!UICONTROL Correspondência]**.
   1. Especifique **[!UICONTROL Igual]** `email` como o **[!UICONTROL Critério]** para selecionar eventos que foram elevados para o namespace de email.

   ![Métrica de namespace compilada por email](/help/stitching/assets/emailstitchednamespace-metric.png)

### Dimensões compiladas

Com ambas as dimensões adicionadas à visualização de dados, use as [tabelas de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) no Analysis Workspace para verificar os dados que cada dimensão tem.

Na tabela de dimensões **[!UICONTROL Namespace compilado]**, você normalmente vê duas linhas para cada conjunto de dados. Uma linha representa quando o processo de compilação precisou usar o método de fallback (ECID). A outra linha mostra eventos associados ao namespace de identidade desejado (email).

Para a tabela de dimensões **[!UICONTROL ID com título]**, você verá os valores brutos provenientes dos eventos. Nessa tabela, você vê que os valores oscilam entre a ID persistente e a ID de pessoa desejada.

![Verificar dimensões compiladas](/help/stitching/assets/check-data-on-stitching.png)


### Relatórios centrados em dispositivos ou pessoas

Ao criar uma conexão, você precisa definir qual campo ou identidade é usada para a ID de pessoa. Por exemplo, em um conjunto de dados da Web, se você escolher uma ID de dispositivo como a ID de pessoa, você criará relatórios centrados em dispositivos e perderá a capacidade de unir esses dados a outros canais offline. Se você selecionar um campo ou uma identidade entre canais, por exemplo, email, você perderá todos os eventos não autenticados. Para entender esse impacto, você precisa descobrir quanto do tráfego não é autenticado e quanto do tráfego é autenticado.

1. Criar uma métrica calculada **[!UICONTROL Eventos não autenticados no total]**. Defina a regra no construtor de regras conforme mostrado abaixo:
   ![Total de eventos não autenticados](/help/stitching/assets/calcmetric-unauthenticatedeventsovertotal.png)

1. Crie uma métrica calculada **[!UICONTROL Taxa de autenticação de email]**, com base na métrica **[!UICONTROL _Conjunto de email]** definida anteriormente. Defina a regra no construtor de regras conforme mostrado abaixo:
   ![Taxa de autenticação de email](/help/stitching/assets/calcmetric-emailauthenticationrate.png)

1. Use a métrica calculada **[!UICONTROL Eventos não autenticados no total]**, juntamente com a métrica calculada **[!UICONTROL Taxa de autenticação de email]**, para criar uma visualização de [Rosca](/help/analysis-workspace/visualizations/donut.md). A visualização mostra o número de eventos no conjunto de dados que não foram autenticados e estão autenticados.

   ![Detalhes de identificação](/help/stitching/assets/identification-details.png)



### Costura das taxas de identificação

Você deseja medir o desempenho de identificação antes e depois da compilação. Para fazer isso, crie três métricas calculadas adicionais:

1. Uma **[!UICONTROL métrica calculada da taxa de autenticação compilada]** que calcula o número de eventos em que o namespace compilado é definido como a identidade desejada sobre o número total de eventos. Ao configurar a visualização de dados, você criou uma métrica **[!UICONTROL Namespace compilado por email]** que incluía um filtro para contar somente quando um evento tivesse um namespace definido como email. A métrica calculada usa esta métrica de **[!UICONTROL Namespace compilado de email]** para fornecer uma indicação de qual porcentagem dos dados tem a identidade desejada.
   ![Métrica calculada da taxa de autenticação compilada](/help/stitching/assets/calcmetric-stitchedauthenticationrate.png)

1. Uma métrica calculada de **[!UICONTROL Aumento percentual]** que calcula a alteração percentual bruta entre a taxa de identificação atual e a compilada.
   ![Métrica calculada de aumento percentual](/help/stitching/assets/calcmetric-percentincrease.png)

1. Uma métrica calculada **[!UICONTROL Lift]** que calcula o aumento entre a taxa de identificação atual e a taxa de identificação compilada.
   ![Aumentar métrica calculada](/help/stitching/assets/calcmetric-lift.png)


### Conclusão

Se você combinar todos os dados em uma tabela de forma livre do Analysis Workspace, poderá começar a ver o impacto e o valor fornecidos pela compilação, incluindo:

* Taxa de autenticação atual: a linha de base do número de eventos que já tinham a ID de pessoa correta em relação ao número total de eventos.
* Taxa de autenticação compilada: o novo número de eventos que têm a ID de pessoa correta em relação ao número total de eventos.
* Aumento percentual: o aumento percentual bruto da taxa de autenticação compilada menos a taxa de autenticação atual da linha de base.
* Aumento: a alteração percentual sobre a taxa de autenticação atual da linha de base.

![Desempenho de identificação](/help/stitching/assets/identification-performance.png)


## Principais lições

Os principais argumentos deste artigo são que a compilação da validação e da análise ajuda a:

* Forneça uma visualização personalizada abrangente da eficácia da autenticação comparando as taxas atuais e as compiladas.
* Permita uma medição clara da melhoria por meio de aumentos de porcentagem e métricas de aumento.
* Ajude a identificar o verdadeiro impacto da implementação da compilação na autenticação de usuário.
* Crie uma maneira padronizada para comunicar o desempenho de autenticação entre equipes.
* Permita decisões orientadas por dados sobre estratégia e otimização de autenticação.

Essas métricas juntas fornecem às partes interessadas uma imagem completa de como a compilação do Customer Journey Analytics afeta as taxas de sucesso de autenticação e o desempenho geral da identificação de pessoas.
