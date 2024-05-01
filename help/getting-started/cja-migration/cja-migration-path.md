---
title: Escolha o caminho de migração do Customer Journey Analytics
description: Saiba mais sobre as vantagens e desvantagens dos possíveis caminhos de migração ao migrar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: tm+mt
source-wordcount: '2422'
ht-degree: 0%

---

# Etapa 2: escolha o caminho de migração

+++Expanda esta seção para ver onde as informações desta página se encaixam no processo de migração geral. Verifique se todas as etapas de migração anteriores foram concluídas.

Antes de continuar com esta seção, primeiro verifique se você concluiu todas as tarefas de migração anteriores.

As informações nesta página abordam a Etapa 2 da migração, conforme destacado na tabela abaixo:

| Tarefa de migração | Detalhes |
|---------|----------|
| **Etapa 1: [Introdução à migração](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Saiba mais sobre os benefícios da migração para o Adobe Analytics e o processo de migração básico. |
| <span class="preview">**Etapa 2: Escolher o caminho de migração**</span> | <span class="preview">Vários métodos estão disponíveis para migrar para o Customer Journey Analytics. Escolha o método que é melhor para sua organização, dependendo do ambiente Adobe Analytics atual da organização e das metas de longo prazo.</span> |
| **Etapa 3: [Enviar dados para o Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | O processo de envio de dados para o Adobe Experience Platform difere, dependendo do caminho de migração escolhido na Etapa 2. |
| **Etapa 4: [Reter dados históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | A maioria das organizações precisa manter seus dados históricos do Adobe Analytics por um determinado período. Várias opções estão disponíveis para fazer isso. |
| **Etapa 5: [Executar tarefas de implementação adicionais](/help/getting-started/cja-getting-started.md)** | Nesse ponto do processo de migração, é necessário executar várias tarefas antes que o ambiente de Customer Journey Analytics esteja pronto para uso.<p>Essas tarefas adicionais se aplicam às migrações do Adobe Analytics, bem como às novas implementações de Customer Journey Analytics.</p><p>Essas tarefas incluem:</p><ul><li>Trazendo outros dados para o Experience Platform</li><li>Criação de conexões entre conjuntos de dados da plataforma e Customer Journey Analytics</li><li>Criação de visualizações de dados</li><li>Transferência do uso da API de relatórios</li><li>Contabilização de feeds de dados e Data Warehouse</li><li>Migração de projetos e componentes</li><li>Integração do usuário do Planning</li></ul> <p>Para obter mais informações, consulte [Customer Journey Analytics Introdução](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Depois de decidir migrar para o Customer Journey Analytics, é necessário determinar o caminho de migração ideal para sua organização.

O caminho escolhido para migrar do Adobe Analytics para o Customer Journey Analytics depende dos seguintes fatores:

* Sua implementação existente do Adobe Analytics

* Suas metas para o futuro

Use as informações desta página para determinar qual caminho de migração de Customer Journey Analytics se alinha melhor à implementação atual e às metas futuras de sua organização.

Para determinar o caminho de migração ideal para sua organização, as seguintes seções devem ser lidas sequencialmente:

1. Primeiro, [compreender os caminhos de migração disponíveis](#understand-migration-methods).

1. Em seguida, [avalie quais caminhos de migração estão disponíveis para você](#assess-the-migration-methods-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. E finalmente, [avalie as vantagens e desvantagens de cada caminho de migração](#weigh-the-advantages-and-disadvantages-of-the-migration-methods-available-to-you).

## Entender os caminhos de migração

Existem vários caminhos de migração para migrar do Adobe Analytics para o Customer Journey Analytics.

Em geral, cada caminho de migração difere no nível de esforço necessário para executá-la, bem como na viabilidade a longo prazo obtida após a conclusão da migração.

A tabela a seguir lista cada caminho de migração, seu nível de esforço e sua viabilidade a longo prazo:

| Caminho de migração | Nível de esforço | Viabilidade a longo prazo |
|---------|----------|---------|
| **Nova implementação do SDK da Web do Experience Platform**</br> Embora tecnicamente não seja uma migração, você pode começar a usar o Customer Journey Analytics fazendo uma nova implementação do SDK da Web do Experience Platform. Isso permite que você comece a enviar dados para o Edge Network e Customer Journey Analytics da Adobe Experience Platform. <p>Para organizações que ainda não estão no SDK da Web, esse caminho de migração talvez seja o mais simples para enviar dados para o Edge Network, pois requer o menor número de etapas. No entanto, como todo o trabalho é feito antecipadamente (como a criação do esquema XDM), ele requer um esforço inicial maior.</p><p>As etapas básicas são:</p><ol><li>Crie um esquema XDM para sua organização.</li><li>Implemente o SDK da Web.</li><li>Enviar dados para a Platform.</li></ol> | Alta | Alta |
| **Migrar sua implementação do Adobe Analytics para usar o SDK da Web**</br> Se a implementação do Adobe Analytics for o AppMeasurement ou a extensão do Analytics, você poderá migrá-la para usar o SDK da Web da Adobe Experience Platform para começar a enviar dados para o Edge Network e o Adobe Analytics, antes de enviá-los para o Customer Journey Analytics.<p>Para organizações que ainda não estão no SDK da Web, essa é a maneira mais fácil e simples de obter dados para o Edge Network. Ela requer mais etapas, mas oferece uma transição mais metódica do Adobe Analytics para o Customer Journey Analytics, com marcos mais tangíveis.</p><p>As etapas básicas são:</p><ol><li>Mova sua implementação do Adobe Analytics existente para o SDK da Web e valide se tudo está funcionando no Adobe Analytics.</li><li>Crie um esquema XDM para sua organização à medida que tiver tempo.</li><li>Use o mapeamento da sequência de dados para mapear todos os campos no objeto de dados para o esquema XDM.</li><li>Enviar dados para a Platform.</li></ol> | Moderado | Alta |
| **Configurar a implementação existente do SDK da Web da Adobe Analytics**</br> Se sua implementação do Adobe Analytics já estiver usando o SDK da Web da Adobe Experience Platform, você poderá começar a enviar dados para o Customer Journey Analytics com o mínimo esforço.<p>Antes de enviar dados para o Customer Journey Analytics, considere atualizar seu esquema do Adobe Analytics para as necessidades específicas de sua organização e quaisquer outros aplicativos da plataforma que você use.</p><p>As etapas básicas são:</p><ol><li>Começar a enviar dados para o Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Opcional) Crie um esquema XDM para sua organização à medida que tiver tempo.</li><li>(Condicional) Se você criou um esquema XDM, use o mapeamento de sequência de dados para mapear todos os campos no objeto de dados para o esquema XDM.</li></ol> | Baixa | Alta |
| **Usar o Conector de origem do Analytics**</br> Se a implementação do Adobe Analytics for o AppMeasurement ou a extensão do Analytics, você poderá começar a enviar dados para uma visualização de dados no Customer Journey Analytics.<p>Essa é a maneira mais fácil de obter dados para o Customer Journey Analytics, mas é o método menos viável a longo prazo.</p> | Baixa | Baixa |

{style="table-layout:auto"}

Use o diagrama a seguir para ajudar a visualizar onde cada caminho de migração se encaixa no espectro em termos de nível de esforço e viabilidade a longo prazo:

![caminhos de migração do cja](assets/cja-migration-methods.png)

## Avalie os caminhos de migração disponíveis para você com base em sua implementação atual do Adobe Analytics

Nem todos os caminhos de migração estão disponíveis para cada tipo de implementação do Adobe Analytics.

Use as informações abaixo para entender qual caminho de migração é mais apropriado para sua organização.

Entre em contato com o representante da Adobe se precisar de conselhos, orientações ou suporte mais específicos.

| Implementação existente do Adobe Analytics | Caminhos de migração disponíveis |
|---------|----------|
| AppMeasurement | <ul><li>Nova implementação do SDK da Web do Experience Platform</li><li>Migrar o Adobe Analytics para o SDK da Web</li><li>Conector de origem do Analytics</li></ul> |
| Extensão do Adobe Analytics | <ul><li>Nova implementação do SDK da Web do Experience Platform</li><li>Migrar o Adobe Analytics para o SDK da Web</li><li>Conector de origem do Analytics</li></ul> |
| SDK da Web | <ul><li>Configurar a implementação do SDK da Web da Adobe Analytics para enviar dados para o Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## Analise as vantagens e desvantagens dos caminhos de migração disponíveis para você

As vantagens e desvantagens de um determinado caminho de migração diferem dependendo da implementação existente do Adobe Analytics.

Antes de usar as informações abaixo para determinar qual é o caminho de migração adequado para você, reveja as informações em [Entender os caminhos de migração](#understand-migration-methods) se você ainda não tiver feito.

### Para implementações do Adobe Analytics que usam: AppMeasurement e extensão Adobe Analytics

A seguir estão os caminhos de migração disponíveis para organizações que implementaram o Adobe Analytics com o AppMeasurement ou a extensão do Adobe Analytics. Expanda cada seção para visualizar as vantagens e desvantagens de cada caminho de migração.

#### Caminhos de migração

+++Nova implementação do SDK da Web do Experience Platform

| Benefícios | Desvantagens |
|----------|---------|
| <ul><li>**Oferece todas as vantagens de hospedar dados no Experience Edge Network**: <p>Essas vantagens incluem:</p><ul><li>Geração de relatórios com alto desempenho e disponibilidade de dados porque o Adobe Experience Platform foi desenvolvido para potencializar [casos de uso de personalização em tempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=pt-BR)</li><li>Consolidar a implementação da coleta de dados da Adobe Experience Cloud entre outros produtos Experience Cloud (AJO, RTCDP e assim por diante)</li><li>Não depende da nomenclatura do Adobe Analytics (propriedades, eVar, evento e assim por diante)</li></ul></li><li>**À prova de obsolescência**: as atualizações de implementação futuras são mais fáceis.</li></ul> | <ul><li>**Requer uma nova implementação do zero**: O requisito de fazer uma nova implementação do zero significa as seguintes desvantagens: </li><ul><li>**Demorado**: este é o caminho de migração mais demorado e demorado porque requer que você comece novamente com uma nova implementação.</li><li>**É necessário recriar o esquema completo no XDM**: antes de começar a implementar o SDK da Web, é necessário recriar o esquema completo no XDM.</li><li>**É necessário recriar regras e elementos de dados**: antes de começar a implementar o SDK da Web, é necessário recriar quaisquer condições de regra e elementos de dados da implementação do Adobe Analytics.</li></ul></ul> |

{style="table-layout:auto"}

+++

+++Migrar Adobe Analytics para o SDK da Web do Experience Platform

| Benefícios | Desvantagens |
|----------|---------|
| <ul><li>**Oferece todas as vantagens de hospedar dados no Experience Edge Network**: <p>Essas vantagens incluem:</p><ul><li>Geração de relatórios com alto desempenho e disponibilidade de dados porque o Adobe Experience Platform foi desenvolvido para potencializar [casos de uso de personalização em tempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=pt-BR)</li><li>Consolidar a implementação da coleta de dados da Adobe Experience Cloud entre outros produtos Experience Cloud (AJO, RTCDP e assim por diante)</li><li>Não depende da nomenclatura do Adobe Analytics (propriedades, eVar, evento e assim por diante)</li></ul><li>**Usa sua implementação existente**: Embora essa abordagem exija algumas alterações de implementação, ela não requer uma implementação totalmente nova do zero. Você pode usar sua camada de dados e código existentes com alterações mínimas na lógica de implementação sem afetar seus relatórios existentes do Adobe Analytics.</li><li>**Fornece flexibilidade para criar um esquema XDM para sua organização posteriormente**: é possível migrar sua implementação existente do Adobe Analytics para usar o SDK da Web, validar se tudo está funcionando no Adobe Analytics e criar o esquema XDM. Essa flexibilidade permite uma migração mais metódica e ponderada.</li></ul> | <ul><li>**Requer mapeamento para enviar dados para a Plataforma**: quando sua organização estiver pronta para usar o Customer Journey Analytics, você deverá enviar dados para um conjunto de dados na Adobe Experience Platform. Essa ação requer que cada campo no objeto de dados seja uma entrada na ferramenta de mapeamento de fluxo de dados que o atribui a um campo de esquema XDM. O mapeamento só precisa ser feito uma vez para esse fluxo de trabalho e não envolve fazer alterações de implementação. No entanto, essa é uma etapa extra que não é necessária ao enviar dados em um objeto XDM.</li><li>**Dívida técnica**: como essa abordagem usa uma forma modificada da implementação existente, pode ser mais difícil rastrear a lógica de implementação e executar alterações no futuro, quando necessário. </li></ul> |

{style="table-layout:auto"}

+++

+++Uso do Conector de origem do Analytics

| Benefícios | Desvantagens |
|----------|---------|
| <ul><li>Caminho de migração menos demorado e exigente. <p>Os dados são migrados para Customer Journey Analytics rapidamente com o mínimo de investimento</p></li></ul> | <ul><li>**Os dados não são enviados para o Edge Network**: <p>Isso resulta nas seguintes desvantagens:</p><ul><li>Nível mais alto de [latência](/help/technotes/guardrails.md#latencies) nos relatórios em todos os caminhos de migração; não otimizado para casos de uso de personalização em tempo real.</li><li>Os dados não podem ser compartilhados com outros aplicativos Adobe Experience Platform; estão restritos somente ao Customer Journey Analytics</li><li>Dependente da nomenclatura do Adobe Analytics (propriedades, eVar, evento e assim por diante)</li></ul><li>**Dificuldade em migrar para o SDK da Web no futuro**: </li><li>**Usa o grupo de campos Evento de experiência do Analytics no esquema**: Esse grupo de campos adiciona muitos eventos Adobe Analytics que não são necessários no esquema Customer Journey Analytics.  Isso pode levar a um esquema mais desorganizado e complexo do que o necessário para o Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}

+++

### Para implementações do Adobe Analytics usando: SDK da Web

O seguinte caminho de migração está disponível para organizações que implementaram o Adobe Analytics com o SDK da Web do Experience Platform.

Ao escolher esse caminho de migração, você também precisa escolher seu esquema.

#### Caminho de migração

+++Configure a implementação do SDK da Web da Adobe Analytics para enviar dados ao Customer Journey Analytics

| Benefícios | Desvantagens |
|----------|---------|
| Esse é o caminho de migração preferencial se a implementação do Adobe Analytics já estiver usando o SDK da Web.<ul><li>**Oferece todas as vantagens de hospedar dados no Experience Edge Network**: <p>Essas vantagens incluem:</p><ul><li>Geração de relatórios com alto desempenho e disponibilidade de dados porque o Adobe Experience Platform foi desenvolvido para potencializar [casos de uso de personalização em tempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=pt-BR)</li><li>Consolidar a implementação da coleta de dados da Adobe Experience Cloud entre outros produtos Experience Cloud (AJO, RTCDP e assim por diante)</li><li>Não depende da nomenclatura do Adobe Analytics (propriedades, eVar, evento e assim por diante)</li></ul><li>**Usa sua implementação existente**: Embora essa abordagem exija algumas alterações de implementação, ela não requer uma implementação totalmente nova do zero. Você pode usar sua camada de dados e código existentes com alterações mínimas na lógica de implementação sem afetar seus relatórios existentes do Adobe Analytics.</li><li>**Fornece uma opção para usar um esquema XDM**: você pode optar por usar seu esquema do Adobe Analytics existente ou criar um esquema XDM e mapear campos no objeto de dados para seu esquema XDM. [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) são um esquema flexível para definir quaisquer campos necessários e somente os campos relevantes. <p>Consulte &quot;Usar seu próprio esquema XDM&quot; abaixo para obter mais informações sobre as vantagens de usar seu próprio esquema XDM.</p></li><li>**Mantém regras e elementos de dados**: embora isso exija novas ações de regra, você pode reutilizar os elementos de dados existentes e as condições da regra com alterações mínimas.</li><li>**À prova de obsolescência**: se você optar por usar seu próprio esquema XDM, as atualizações de implementação futuras serão mais fáceis.</li></ul> | Nenhum |

{style="table-layout:auto"}

+++

#### Escolha seu esquema

Se você escolher o caminho de migração que permite configurar a implementação do SDK da Web da Adobe Analytics para enviar dados para o Customer Journey Analytics, poderá escolher o esquema que deseja usar.

Você pode escolher se deseja usar seu esquema do Adobe Analytics existente ou atualizar para seu próprio esquema XDM para se alinhar melhor às necessidades de sua organização à medida que começa a usar outros serviços da plataforma.

+++Use o esquema do Adobe Analytics com a implementação do SDK da Web da Adobe Analytics

| Benefícios | Desvantagens |
|----------|---------|
| <p>As vantagens de usar o esquema do Adobe Analytics incluem:</p><ul><li>Facilidade de migração<p>Se você já estiver enviando dados para a Adobe Analytics com o SDK da Web da Adobe Experience Platform, poderá adicionar um serviço adicional ao fluxo de dados para enviar dados para a Adobe Experience Platform (que, em seguida, pode ser usado na configuração do Customer Journey Analytics).</p></li></ul> | <p>As desvantagens de usar o esquema do Adobe Analytics incluem:</p><ul><li>Embora o uso do esquema do Adobe Analytics não limite você em termos de como ele pode ser usado com outros aplicativos da Platform, ele resulta em um esquema que é mais complexo do que poderia ser. Isso ocorre porque o esquema do Adobe Analytics contém muitos objetos específicos do Adobe Analytics que provavelmente não serão usados por sua organização.<p>Quando são necessárias alterações no esquema, é necessário analisar milhares de campos não utilizados para localizar o campo que requer atualização.</p></li></ul> |

+++

+++Use seu próprio esquema XDM com a implementação do SDK da Web da Adobe Analytics

| Benefícios | Desvantagens |
|----------|---------|
| <ul><p>As vantagens de atualizar para seu próprio esquema XDM incluem:</p><ul><li>Um esquema simplificado adaptado às necessidades da sua organização e aos aplicativos específicos da Platform que você usa.</li><p>Quando são necessárias alterações no esquema, não é necessário percorrer milhares de campos não utilizados para localizar o campo que requer atualização.</p></ul> | <p>As desvantagens de atualizar para seu próprio esquema XDM incluem:</p><ul><li>A atualização do esquema é um processo demorado e necessário antes de você começar a enviar dados para o Customer Journey Analytics.</li></ul> |

+++

## Em seguida, envie dados para o Adobe Experience Platform

Depois de usar as informações acima para escolher um caminho de migração, saiba como [enviar dados para o Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) dependendo do caminho de migração escolhido.
