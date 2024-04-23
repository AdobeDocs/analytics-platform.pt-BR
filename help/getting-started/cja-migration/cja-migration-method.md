---
title: Escolha seu método de migração Customer Journey Analytics
description: Conheça as vantagens e desvantagens dos possíveis métodos de migração ao migrar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 3e362a62d2ffd6d15e3028706e3704264df80222
workflow-type: tm+mt
source-wordcount: '2026'
ht-degree: 2%

---

# Etapa 2: escolha seu método de migração de Customer Journey Analytics

+++Expanda esta seção para ver onde as informações desta página se encaixam no processo de migração geral. Verifique se todas as etapas de migração anteriores foram concluídas.

Antes de continuar com esta seção, primeiro verifique se você concluiu todas as tarefas de migração anteriores.

As informações nesta página abrangem a Etapa 2, conforme destacado na tabela abaixo:

| Tarefa de migração | Detalhes |
|---------|----------|
| **Etapa 1: [Introdução à migração](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Saiba mais sobre os benefícios da migração para o Adobe Analytics e o processo de migração básico. |
| <span class="preview">**Etapa 2: [Escolha o método de migração](/help/getting-started/cja-migration/cja-migration-method.md)**</span> | <span class="preview">Vários métodos estão disponíveis para migrar para o Customer Journey Analytics. Escolha o método que é melhor para sua organização, dependendo do ambiente Adobe Analytics atual da organização e das metas de longo prazo.</span> |
| **Etapa 3: [Enviar dados para o Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | O processo de envio de dados para o Adobe Experience Platform difere, dependendo do método de migração escolhido na Etapa 1. |
| **Etapa 4: [Mapear dados para o esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) são usados no Adobe Experience Platform para descrever a estrutura dos dados de forma consistente e reutilizável. Ao definir os dados de forma consistente em todos os sistemas, fica mais fácil manter o significado e, portanto, obter valor dos dados.<p>A maioria dos métodos de migração exige a criação de um novo esquema XDM ou o mapeamento do esquema existente do Adobe Analytics para o XDM usando o mapeamento do fluxo de dados.</p> |
| **Etapa 5: [Reter dados históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | A maioria das organizações precisa manter seus dados históricos do Adobe Analytics por um determinado período. Várias opções estão disponíveis para fazer isso. |
| **Etapa 6: [Planejar a integração do usuário](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Você deve dar aos seus usuários tempo suficiente (de 3 a 6 meses) para se familiarizar com as principais diferenças do Analysis Workspace no Customer Journey Analytics. |
| **Etapa 7: [Portar o uso da API de relatórios](/help/getting-started/cja-migration/cja-migration-api.md)** | A API de relatórios de Customer Journey Analytics está no mesmo formato, mas usa um endpoint diferente. Porte o uso da API de relatórios da API de relatórios do Adobe Analytics para a API de relatórios do Customer Journey Analytics. |
| **Etapa 8: [Substituir Feeds de dados e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decida como você usará as opções de exportação disponíveis no Customer Journey Analytics para substituir os Feeds de dados e os recursos do Data Warehouse que você estava usando no Adobe Analytics. |
| **Etapa 9: [Migrar projetos e componentes](/help/getting-started/cja-migration/cja-migration-projects.md)** | A área Migração de componentes no Adobe Analytics permite migrar projetos e seus componentes associados do Adobe Analytics para o Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Depois de decidir migrar para o Customer Journey Analytics, é necessário determinar o método de migração ideal para sua organização.

O método escolhido para migrar do Adobe Analytics para o Customer Journey Analytics depende dos seguintes fatores:

* Sua implementação existente do Adobe Analytics

* Suas metas para o futuro

Use as informações desta página para determinar qual método de migração Customer Journey Analytics se alinha melhor à implementação atual e às metas futuras de sua organização.

As seguintes seções devem ser lidas sequencialmente para determinar o método de migração ideal para sua organização:

1. Primeiro, [compreender os métodos de migração disponíveis](#understand-migration-methods).

1. Em seguida, [avalie quais métodos de migração estão disponíveis para você](#assess-the-migration-methods-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. E finalmente, [avaliar as vantagens e desvantagens de cada método de migração](#weigh-the-advantages-and-disadvantages-of-the-migration-methods-available-to-you).

## Entender os métodos de migração

Existem vários métodos de migração para migrar do Adobe Analytics para o Customer Journey Analytics.

Em geral, cada método de migração difere no nível de esforço necessário para executá-la, bem como na viabilidade a longo prazo alcançada após a conclusão da migração.

A tabela a seguir lista cada método de migração, seu nível de esforço e sua viabilidade a longo prazo:

| Método de migração | Nível de esforço | Viabilidade a longo prazo |
|---------|----------|---------|
| **Nova implementação do SDK da Web**</br> Você pode fazer uma nova implementação do SDK da Web da Adobe Experience Platform para começar a enviar dados para o Edge Network da Adobe Experience Platform <!-- what is the correct branding -->. <p>Para organizações que ainda não estão no SDK da Web, esse método de migração talvez seja o mais simples de obter dados para o Edge Network (exigindo o menor número de etapas). No entanto, como todo o trabalho é feito antecipadamente (como a criação do esquema XDM), ele requer mais um esforço inicial maior.</p><p>As etapas básicas são:</p><ol><li>Crie um esquema XDM para sua organização.</li><li>Implemente o SDK da Web.</li><li>Enviar dados para a Platform.</li></ol> | Alta | Alta |
| **Migrar sua implementação do Adobe Analytics para usar o SDK da Web**</br> Se a implementação do Adobe Analytics for o AppMeasurement ou a extensão do Analytics, você poderá migrá-la para usar o SDK da Web da Adobe Experience Platform para começar a enviar dados para o Edge Network antes de enviá-los para o Customer Journey Analytics. <!-- what else? --><p>Esta é a maneira mais fácil e suave de obter dados para o Edge Network; requer mais etapas, mas oferece uma transição mais metódica com marcos mais tangíveis.</p><p>As etapas básicas são:</p><ol><li>Mova sua implementação existente do Adobe Analytics para o SDK da Web e valide se tudo está funcionando lá.</li><li>Crie um esquema XDM para sua organização à medida que tiver tempo.</li><li>Use o Mapeamento de fluxo de dados para mapear todos os campos no objeto de dados para o esquema XDM.</li><li>Enviar dados para a Platform.</li></ol> | Moderado | Alta |
| **Configurar a implementação existente do Adobe Analytics Web SDK para enviar dados ao Customer Journey Analytics**</br> Se sua implementação do Adobe Analytics já estiver usando o SDK da Web, você poderá começar a enviar dados para o Customer Journey Analytics com o mínimo esforço.<p>Antes de enviar dados para o Customer Journey Analytics, considere atualizar seu esquema do Adobe Analytics para as necessidades específicas de sua organização e quaisquer outros aplicativos da plataforma que você usará.</p><p>As etapas básicas são:</p><ol><li>Começar a enviar dados para o Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Opcional) Crie um esquema XDM para sua organização à medida que tiver tempo.</li><li>(Condicional) Se você criou um esquema XDM, use o mapeamento de fluxo de dados para mapear todos os campos no objeto de dados para o esquema XDM.</li></ol> | Baixa | Alta |
| **Conector de origem do Analytics**</br> Se a implementação do Adobe Analytics for o AppMeasurement ou a extensão do Analytics, você poderá começar a enviar dados para uma visualização de dados no Customer Journey Analytics.<p>Essa é a maneira mais fácil de obter dados para o Customer Journey Analytics, mas é o método menos viável a longo prazo.</p> | Baixa | Baixa |

{style="table-layout:auto"}

Use o diagrama a seguir para ajudar a visualizar onde cada método de migração se enquadra no espectro em termos de nível de esforço e viabilidade a longo prazo:

![métodos de migração do cja](assets/cja-migration-methods.png)

## Avalie os métodos de migração disponíveis para você com base em sua implementação atual do Adobe Analytics

Nem todos os métodos de migração estão disponíveis para cada tipo de implementação do Adobe Analytics.

Use as informações abaixo para entender qual método de migração é mais apropriado para sua organização.

Entre em contato com o representante da Adobe se precisar de conselhos, orientações ou suporte mais específicos.

| Implementação do Adobe Analytics | Métodos de migração disponíveis |
|---------|----------|
| AppMeasurement | <ul><li>Nova implementação do SDK da Web</li><li>Migrar o Adobe Analytics para o SDK da Web</li><li>Conector de origem do Analytics</li></ul> |
| Extensão do Adobe Analytics | <ul><li>Nova implementação do SDK da Web</li><li>Migrar o Adobe Analytics para o SDK da Web</li><li>Conector de origem do Analytics</li></ul> |
| SDK da Web | <ul><li>Configurar a implementação do SDK da Web da Adobe Analytics para enviar dados para o Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## Analise as vantagens e desvantagens dos métodos de migração disponíveis para você

As vantagens e desvantagens de um determinado método de migração diferem dependendo da implementação existente do Adobe Analytics.

Antes de usar as informações abaixo para determinar qual é o método de migração adequado para você, consulte as informações em [Entender os métodos de migração](#understand-migration-methods) se você ainda não tiver feito.

### Para implementações do Adobe Analytics que usam: AppMeasurement e extensão Adobe Analytics

A tabela a seguir mostra os métodos de migração disponíveis para organizações que implementaram o Adobe Analytics com AppMeasurement ou a extensão Adobe Analytics:

| Método de migração | Benefícios | Desvantagens |
|---------|----------|---------|
| **Nova implementação do SDK da Web** | <ul><li>Usa um esquema XDM, um esquema flexível para definir todos os campos necessários e somente os campos relevantes (permite que você se afaste do grupo de Campos de evento de experiência do Adobe Analytics)</li><li>Não depende da nomenclatura do Adobe Analytics (propriedades, eVar, evento e assim por diante)</li><li>Nenhum problema de limite de caracteres (100 caracteres para propriedades)</li><li>Geração de relatórios com alto desempenho e disponibilidade de dados porque o Adobe Experience Platform foi desenvolvido para potencializar [casos de uso de personalização em tempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=pt-BR)</li><li>À prova de obsolescência (receberá todos os recursos e funcionalidades mais recentes)</li><li>Consolidar tags para a coleta de dados da Adobe Experience Cloud entre outros produtos Experience Cloud (AJO, RTCDP e assim por diante)</li><li>[IDs de dispositivo próprio](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=pt-BR) para melhorar a precisão da identificação do visitante</li></ul> | <ul><li>O método de migração mais demorado e exigente<p>É necessário recriar o esquema completo no XDM antes de começar a implementar o SDK da Web</p></li></ul> |
| **Migrar o Adobe Analytics para o SDK da Web** | <ul><li>Mantém regras e elementos de dados já configurados na implementação do Adobe Analytics.</li><li>Permite migrar para o SDK da Web sem afetar os relatórios existentes do Adobe Analytics.</li><li>Fornece flexibilidade para criar um esquema XDM para sua organização posteriormente: um esquema flexível para definir todos os campos necessários e somente os campos relevantes.</br>Não exige o grupo de campos de evento de experiência do Adobe Analytics no Customer Journey Analytics. <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>Não depende da nomenclatura do Adobe Analytics (propriedades, eVar, evento e assim por diante)</li><li>Nenhum problema de limite de caracteres (100 caracteres para propriedades)</li><li>Geração de relatórios com alto desempenho e disponibilidade de dados porque o Adobe Experience Platform foi desenvolvido para potencializar [casos de uso de personalização em tempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=pt-BR)</li><li>À prova de obsolescência (receberá todos os recursos e funcionalidades mais recentes)</li><li>Consolidar tags para a coleta de dados da Adobe Experience Cloud entre outros produtos Experience Cloud (AJO, RTCDP e assim por diante)</li><li>[IDs de dispositivo próprio](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=pt-BR) para melhorar a precisão da identificação do visitante</li></ul> | <ul><li>Deve estar em conformidade com um esquema XDM em algum ponto no futuro, usando o mapeamento de fluxo de dados.</li><li>Incorre em alguma dívida técnica. Por exemplo, o código de extensão herdado do AppMeasurement ou do Analytics pode permanecer. </li></ul> |
| **Conector de origem do Analytics** | <ul><li>Método de migração menos demorado e exigente. <p>Os dados são migrados para Customer Journey Analytics rapidamente com o mínimo de investimento</p></li></ul> | <ul><li>Os dados não são enviados para o Edge Network e não podem ser compartilhados com outros aplicativos da Adobe Experience Platform; estão restritos somente ao Customer Journey Analytics<li>Dificuldade em migrar para o SDK da Web no futuro</li><li>Usa o grupo de campos Evento de experiência do Analytics no esquema.</br>Esse grupo de campos adiciona muitos eventos Adobe Analytics que não são necessários no esquema Customer Journey Analytics.  Isso pode levar a um esquema mais desorganizado e complexo do que o necessário para o Customer Journey Analytics.</li><li>Nível mais alto de [latência](/help/admin/guardrails.md#latencies) em todos os métodos de implementação</li></ul> |

{style="table-layout:auto"}

### Para implementações do Adobe Analytics usando: SDK da Web

A tabela a seguir mostra os métodos de migração disponíveis para organizações que implementaram o Adobe Analytics com o SDK da Web:

| Método de migração | Benefícios | Desvantagens |
|---------|----------|---------|
| **Configurar a implementação do SDK da Web da Adobe Analytics para enviar dados para o Customer Journey Analytics** | Este é o método de migração preferido se a implementação do Adobe Analytics já estiver usando o SDK da Web. <p>Ao usar esse método de implementação, você pode escolher se deseja usar seu esquema existente do Adobe Analytics ou pode atualizar para o esquema XDM para se alinhar melhor às necessidades da organização à medida que você começa a usar outros aplicativos da Platform.</p><p>**Uso do schema Adobe Analytics**</p><p>As vantagens de usar o esquema do Adobe Analytics incluem:</p><ul><li>Facilidade de migração<p>Se você já estiver enviando dados para a Adobe Analytics com o SDK da Web da Adobe Experience Platform, poderá adicionar um serviço adicional ao fluxo de dados para enviar dados para a Adobe Experience Platform (que, em seguida, pode ser usado na configuração do Customer Journey Analytics).</p></li></ul><p>As desvantagens de usar o esquema do Adobe Analytics incluem:</p><ul><li>Embora o uso do esquema do Adobe Analytics não limite você em termos de como ele pode ser usado com outros aplicativos da Platform, ele resulta em um esquema que é mais complexo do que poderia ser. Isso ocorre porque o esquema do Adobe Analytics contém muitos objetos específicos do Adobe Analytics que provavelmente não serão usados pela organização.<p>Quando são necessárias alterações no esquema, é necessário analisar milhares de campos não utilizados para localizar o campo que requer atualização.</p></li></ul><p>**Uso do schema XDM**</p><p>As vantagens de atualizar o esquema XDM incluem:</p><ul><li>Um esquema simplificado adaptado às necessidades da sua organização e aos aplicativos específicos da Platform que você usa.</li><p>Quando são necessárias alterações no esquema, não é necessário percorrer milhares de campos não utilizados para localizar o campo que requer atualização.</p></ul><p>As desvantagens da atualização do esquema XDM incluem:</p><ul><li>A atualização do esquema é um processo demorado e necessário antes de você começar a enviar dados para o Customer Journey Analytics.</li></ul> | Nenhum |

{style="table-layout:auto"}

## Em seguida, envie dados para o Adobe Experience Platform

Depois de usar as informações acima para escolher um método de migração, saiba como [enviar dados para o Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) dependendo do método de migração escolhido.
