---
title: Biblioteca JavaScript do Content Analytics
description: Saiba como configurar o Content Analytics sem usar as Tags da coleção de dados da Experience Platform e, em vez disso, use a biblioteca JavaScript do Content Analytics.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
autotag-review: '2026-05-19T06:56:34.440Z'
TQID: 'https://experienceleague.adobe.com/GUYf0ZoTlAkoIIPWzfZTm0-eMvBjN8ieYSu6goHu3GA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 484
ht-degree: 4%

---


# Biblioteca JavaScript do Content Analytics

A biblioteca JavaScript do Adobe Content Analytics permite rastrear eventos relacionados a conteúdo em sites enviando dados de conteúdo para o Adobe Experience Platform por meio do Experience Platform Edge Network. Use essa biblioteca quando quiser implementar o Content Analytics sem tags da Adobe Experience Platform.

>[!NOTE]
>
>Este artigo se aplica ao Content Analytics para o canal da Web.


>[!PREREQUISITES]
>
>* O Adobe Experience Platform Web SDK (Alloy) deve ser inicializado na página antes de chamar `initializeContentLibrary`.
>* Conclua o assistente de configuração guiada do Content Analytics para orientá-lo por todas as etapas necessárias para definir os pré-requisitos de uma configuração do Content Analytics.
>* Após a conclusão da configuração guiada, as configurações do JavaScript ficam disponíveis para uso.


## Instalação

Você pode instalar a biblioteca de duas maneiras:

### pacote npm

Use o `npm` para instalar a biblioteca.

1. Na linha de comando, use:

   ```bash
   npm install @adobe/content-analytics
   ```

1. Importe a biblioteca:

   ```JavaScript
   import initializeContentLibrary from "@adobe/content-analytics";
   ```

### Tag de script (CDN)

Carregue a biblioteca diretamente do CDN.

1. Inicialize a [biblioteca JavaScript Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library) e carregue o pacote Content Analytics:

   ```html
   <!-- 1. Load and configure Alloy first -->
   <script src="https://cdn1.adoberesources.net/alloy/2.x.x/alloy.min.js"></script>
   <script>
   alloy("configure", {
       datastreamId: "YOUR_DATASTREAM_ID",
       orgId: "YOUR_ORG_ID@AdobeOrg",
   });
   </script>
   
   <!-- 2. Load Content Analytics -->
   <script src="https://cdn1.adoberesources.net/content-analytics/1.x.x/content-analytics.min.js"></script>
   <script>
   window.contentAnalytics({
       datastreamId: "YOUR_DATASTREAM_ID",
   });
   </script>
   ```

   em que
   * `alloy/2.x.x` refere-se à versão que você deseja usar da [biblioteca JavaScript do Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library).
   * `content-analytics/1.x.x` refere-se à versão que você deseja usar da biblioteca SDK do Content Analytics.

2. A compilação autônoma expõe `window.contentAnalytics` como a função de inicialização.


## Configuração da sequência de dados

A opção `datastreamId` é necessária e deve fazer referência a uma sequência de dados que tenha o serviço Experience Platform configurado com um conjunto de dados de evento de experiência do Content Analytics habilitado. Verifique se a sandbox associada à sequência de dados ainda não está associada a outra configuração do Content Analytics.

Você pode fornecer IDs de fluxo de dados separadas por ambiente:

```javascript
initializeContentLibrary({
  datastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",          // production
  stagingDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",   // optional
  developmentDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", // optional
});
```

## Captura e definição de experiência

Ative o rastreamento de experiência e controle como as experiências são identificadas no site. As experiências são definidas combinando uma **expressão regular de domínio** com **parâmetros de consulta** opcionais que distinguem uma experiência de outra em páginas correspondentes.

| Opção | Tipo | Padrão | Descrição |
|--------|------|---------|-------------|
| `includeExperiences` | booleano | `false` | Ativar o rastreamento da visualização de página/experiência |
| `experienceConfigurations` | matriz | - | Definir experiências por regex de domínio e parâmetros de consulta |

Cada entrada em `experienceConfigurations` aceita:

| Propriedade | Tipo | Descrição |
|----------|------|-------------|
| `regEx` | string | Expressão regular de domínio correspondente ao URL da página (ex.: `^(?!.*\b(store\|help\|admin)\b)`) |
| `queryParameters` | matriz | Nomes de parâmetros de consulta cujos valores distinguem experiências em páginas correspondentes (por exemplo, `["outdoors", "patio", "kitchen"]`) |

### Exemplo

Consulte abaixo um exemplo de como habilitar o rastreamento de experiência com parâmetros de consulta e regex de domínio.

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  includeExperiences: true,
  experienceConfigurations: [
    {
      regEx: "^https://www\\.example\\.com/products",
      queryParameters: ["category", "collection"],
    },
    {
      regEx: "^https://www\\.example\\.com/blog",
      queryParameters: [],
    },
  ],
});
```

## Filtragem de eventos

Controle quais URLs de página e URLs de ativos são incluídos na coleção de dados usando expressões regulares. Use os exemplos de padrão abaixo como ponto de partida e valide os padrões com um testador regex antes da implantação.

| Opção | Tipo | Padrão | Descrição |
|--------|------|---------|-------------|
| `pageUrlQualifier` | sequência de caracteres (regex) | - | Rastrear somente páginas cujo URL corresponda a este padrão |
| `assetUrlQualifier` | sequência de caracteres (regex) | - | Rastrear somente os ativos cujo URL corresponda a este padrão |
| `excludeURLsFromTracking` | matriz | `[]` | Lista de cadeias de caracteres de URL a serem excluídas do rastreamento |

### Exemplo

Consulte abaixo um exemplo de como excluir páginas de documentação do Content Analytics e considerar apenas imagens de produtos para o Content Analytics.

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  pageUrlQualifier: "^(?!.*\\/documentation).*",
  assetUrlQualifier: ".*\\/products\\/.*\\.(?:jpg|png|webp)",
  excludeURLsFromTracking: [
    "https://www.example.com/internal",
    "https://www.example.com/staging",
  ],
});
```
