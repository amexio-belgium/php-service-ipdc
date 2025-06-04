# OpenAPIClient-php

### Access

The Product API is a public API. If you want to make use of this api, contact someone on the team to get an API key.

Each endpoint also lists the necessary permissions to call it. You can view your own permissions by calling the `/me`
endpoint.  
In a few cases some of the listed permissions are optional and depend upon the specific data requested.

### Tracing

The API uses X-request-ID and X-correlation-ID headers.  
Every request that hits the API without these headers, gets a new random UUID as request-ID and correlation-ID.

If you as a client pass these id's yourself, the API will use your values, but only when they are in UUID format.  
If you provide a value that is not a UUID, the api will fail to handle your request.

Providing these values enables distributed request correlation & tracing.

### Rate limiting

GET calls to this API are rate limited.  
This rate limit is configured per client. You can request a higher rate limit if needed.

The rate limit uses a token bucket that is refilled within a fixed timeframe.  
Each request can use multiple tokens, depending on the number of items requested.

Information about your current limit is conveyed via the response headers of each response: 
| Header                | Description                                                                                                    | Example                |
|-----------------------|----------------------------------------------------------------------------------------------------------------|------------------------|
| X-RateLimit-Reset     | The time at which the rate limit will reset                                                                    | 2025-07-14T15:23:45Z   |
| X-RateLimit-Limit     | The maximum number of tokens to be used in the current time window                                             | 2000                   |
| X-RateLimit-Remaining | The number of tokens remaining in the current time window                                                      | 670                    |
| Retry-After           | Indicates how many seconds the client should wait before making a new request (only when response code is 429) | 42                     |

### Contact



## Installation & Usage

### Requirements

PHP 8.1 and later.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/GIT_USER_ID/GIT_REPO_ID.git"
    }
  ],
  "require": {
    "GIT_USER_ID/GIT_REPO_ID": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/OpenAPIClient-php/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');




$apiInstance = new OpenAPI\Client\Api\CodelijstenApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string
$only_roots = True; // bool | Some codelijsten contain hierarchy. With this property you can control whether to only fetch the first level or the whole codelijst.
$include_inactive = false; // bool | If true, the API will also return inactive nodes

try {
    $result = $apiInstance->getCodelijst($id, $only_roots, $include_inactive);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CodelijstenApi->getCodelijst: ', $e->getMessage(), PHP_EOL;
}

```

## API Endpoints

All URIs are relative to *https://api.ipdc.tni-vlaanderen.be*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*CodelijstenApi* | [**getCodelijst**](docs/Api/CodelijstenApi.md#getcodelijst) | **GET** /api/codelijsten/{id} | Fetch a codelijst based on codelijst-id.
*CodelijstenApi* | [**getCodelijstByParentId**](docs/Api/CodelijstenApi.md#getcodelijstbyparentid) | **GET** /api/codelijsten/{id}/{parentId} | Fetch a codelijst based on codelijst-id and parent-id.
*ConceptApi* | [**archiveConcept**](docs/Api/ConceptApi.md#archiveconcept) | **DELETE** /doc/concept/{idOrProductnummer} | Archive the concept based on concept-id or productnummer.
*ConceptApi* | [**createOrUpdateConcept**](docs/Api/ConceptApi.md#createorupdateconcept) | **POST** /doc/concept | Create a new concept or (if id/productnummer in body) update a concept.
*ConceptApi* | [**dearchiveConcept**](docs/Api/ConceptApi.md#dearchiveconcept) | **PUT** /doc/concept/{idOrProductnummer}/dearchive | Dearchive the concept based on concept-id or productnummer.
*ConceptApi* | [**export**](docs/Api/ConceptApi.md#export) | **GET** /doc/concept/export | Fetch concept page to export. Filter by laatstOntvangen in requestParams.
*ConceptApi* | [**findConceptByIdOrProductnummer**](docs/Api/ConceptApi.md#findconceptbyidorproductnummer) | **GET** /doc/concept/{idOrProductnummer} | Fetch the details of the concept.
*ConceptApi* | [**findConceptsByIdsOrProductnummers**](docs/Api/ConceptApi.md#findconceptsbyidsorproductnummers) | **GET** /doc/concept/byIds/{ids} | Fetch the details of the concepten.
*ConceptApi* | [**findPage**](docs/Api/ConceptApi.md#findpage) | **GET** /doc/concept | Fetch concepten page. Filter by using requestparams.
*ConceptApi* | [**getConceptDelta**](docs/Api/ConceptApi.md#getconceptdelta) | **GET** /doc/concept/{idOrProductnummer}/delta | 
*ConceptApi* | [**redirectToFindConceptByIdOrProductnummer**](docs/Api/ConceptApi.md#redirecttofindconceptbyidorproductnummer) | **GET** /id/concept/{idOrProductnummer} | Fetch de details of the concept. Redirects to /doc/concept/{idOrProductnummer}.
*ConceptApi* | [**redirectToFindConceptPage**](docs/Api/ConceptApi.md#redirecttofindconceptpage) | **GET** /id/concept | Fetch the first concept page. Redirects to /doc/concept.
*ConceptLDESApi* | [**getConceptSnapshotById**](docs/Api/ConceptLDESApi.md#getconceptsnapshotbyid) | **GET** /doc/conceptsnapshot/{id} | Fetch a concept snapshot by id.
*ConceptLDESApi* | [**getConceptSnapshotByIdRedirect**](docs/Api/ConceptLDESApi.md#getconceptsnapshotbyidredirect) | **GET** /id/conceptsnapshot/{id} | Fetch a concept snapshot by id. Redirects to /doc/conceptsnapshot/{id}.
*ConceptLDESApi* | [**getConceptenLastPageLdesStream**](docs/Api/ConceptLDESApi.md#getconceptenlastpageldesstream) | **GET** /id/conceptsnapshot | Fetch the most recent concept snapshot page of the LDES stream. Redirects to /doc/conceptsnapshot.
*ConceptLDESApi* | [**getConceptenPageLdesStream**](docs/Api/ConceptLDESApi.md#getconceptenpageldesstream) | **GET** /doc/conceptsnapshot | Fetch a concept snapshot page of the LDES stream.
*IdentityApi* | [**getMe**](docs/Api/IdentityApi.md#getme) | **GET** /me | Get information about your user such as permissions and rate limits.
*InstantieApi* | [**archiveInstantie**](docs/Api/InstantieApi.md#archiveinstantie) | **DELETE** /doc/instantie/{idOrProductnummer} | Archive the instantie based on instantie-id or instantieIdOrProductnummer.
*InstantieApi* | [**createOrUpdateInstantie**](docs/Api/InstantieApi.md#createorupdateinstantie) | **POST** /doc/instantie | Create a new instantie or (if id/instantieIdOrProductnummer in body) update an instantie.
*InstantieApi* | [**dearchiveInstantie**](docs/Api/InstantieApi.md#dearchiveinstantie) | **PUT** /doc/instantie/{idOrProductnummer}/dearchive | Dearchive the instantie based on instantie-id or instantieIdOrProductnummer.
*InstantieApi* | [**exportInstanties**](docs/Api/InstantieApi.md#exportinstanties) | **GET** /doc/instantie/export | Fetch instanties page to export. Filter by using requestparams.
*InstantieApi* | [**exportInstantiesFilterByDate**](docs/Api/InstantieApi.md#exportinstantiesfilterbydate) | **GET** /doc/instantie/export/byLaatstOntvangen | Fetch instanties page to export. Filter by laatstOntvangen in requestParams.
*InstantieApi* | [**findInstantieByIdOrProductnummer**](docs/Api/InstantieApi.md#findinstantiebyidorproductnummer) | **GET** /doc/instantie/{idOrProductnummer} | Fetch the details of the instantie.
*InstantieApi* | [**findInstantieByIdOrProductnummerRedirect**](docs/Api/InstantieApi.md#findinstantiebyidorproductnummerredirect) | **GET** /id/instantie/{idOrProductnummer} | Fetch the details of the instantie. Redirects to /doc/instantie/{idOrProductnummer}.
*InstantieApi* | [**findInstantiePage**](docs/Api/InstantieApi.md#findinstantiepage) | **GET** /doc/instantie | Fetch instantie page. Filter by using requestparams.
*InstantieApi* | [**findInstantiesByIdsOrProductnummers**](docs/Api/InstantieApi.md#findinstantiesbyidsorproductnummers) | **GET** /doc/instantie/byIds/{ids} | Fetch the details of the instanties.
*InstantieApi* | [**getInstantieDelta**](docs/Api/InstantieApi.md#getinstantiedelta) | **GET** /doc/instantie/{idOrProductnummer}/delta | 
*InstantieApi* | [**redirectToFindInstantiePage**](docs/Api/InstantieApi.md#redirecttofindinstantiepage) | **GET** /id/instantie | Fetch the first instantie page. Redirects to /doc/instantie.
*InstantieLDESApi* | [**getInstantieLastPageLdesStream**](docs/Api/InstantieLDESApi.md#getinstantielastpageldesstream) | **GET** /id/instantiesnapshot | Fetch the most recent instantie snapshot page of the LDES stream. Redirects to /doc/instantiesnapshot.
*InstantieLDESApi* | [**getInstantieSnapshotById**](docs/Api/InstantieLDESApi.md#getinstantiesnapshotbyid) | **GET** /doc/instantiesnapshot/{id} | Fetch an instantie snapshot by id.
*InstantieLDESApi* | [**getInstantieSnapshotByIdRedirect**](docs/Api/InstantieLDESApi.md#getinstantiesnapshotbyidredirect) | **GET** /id/instantiesnapshot/{id} | Fetch an instantie snapshot by id. Redirects to /doc/instantiesnapshot/{id}.
*InstantieLDESApi* | [**getInstantiesPageLdesStream**](docs/Api/InstantieLDESApi.md#getinstantiespageldesstream) | **GET** /doc/instantiesnapshot | Fetch an instantie snapshot page of the LDES stream.
*ProductApi* | [**findProductByIdOrProductnummer**](docs/Api/ProductApi.md#findproductbyidorproductnummer) | **GET** /id/product/{idOrProductnummer} | Fetch the details of a instantie or concept. Redirects to /doc/product/{idOrProductnummer}.
*ProductApi* | [**findProductPage**](docs/Api/ProductApi.md#findproductpage) | **GET** /doc/product | Fetch product page. Filter by using requestparams.
*ProductApi* | [**findProductenByIdsOrProductnummers**](docs/Api/ProductApi.md#findproductenbyidsorproductnummers) | **GET** /doc/product/byIdsOrProductnummers/{ids} | Fetch the details of the producten.
*ProductApi* | [**getProduct**](docs/Api/ProductApi.md#getproduct) | **GET** /doc/product/{idOrProductnummer} | Fetch the details of a instantie or concept
*VerrijkingApi* | [**findById**](docs/Api/VerrijkingApi.md#findbyid) | **GET** /verrijking/{caseId} | Fetch a verrijking case based on case-id. A Verrijking case contains all conditions with all possible options.
*VerrijkingApi* | [**getVerrijkingVoorwaardeOptieUsage**](docs/Api/VerrijkingApi.md#getverrijkingvoorwaardeoptieusage) | **GET** /verrijking/{caseId}/voorwaarde/{voorwaardeId}/optie/{optieId}/usage | 
*VerrijkingApi* | [**getVerrijkingVoorwaardeUsage**](docs/Api/VerrijkingApi.md#getverrijkingvoorwaardeusage) | **GET** /verrijking/{caseId}/voorwaarde/{voorwaardeId}/usage | 

## Models

- [Bewijs](docs/Model/Bewijs.md)
- [BooleanVoorwaardeJson](docs/Model/BooleanVoorwaardeJson.md)
- [CaseId](docs/Model/CaseId.md)
- [CodelijstJson](docs/Model/CodelijstJson.md)
- [CodelijstWaardeJson](docs/Model/CodelijstWaardeJson.md)
- [ConceptDeltaJson](docs/Model/ConceptDeltaJson.md)
- [ContactOrganisatie](docs/Model/ContactOrganisatie.md)
- [ContactOrganisatieJson](docs/Model/ContactOrganisatieJson.md)
- [ErrorDto](docs/Model/ErrorDto.md)
- [EventStreamSnapshotJsonConceptJson](docs/Model/EventStreamSnapshotJsonConceptJson.md)
- [EventStreamSnapshotJsonInstantieJson](docs/Model/EventStreamSnapshotJsonInstantieJson.md)
- [FieldDeltaJson](docs/Model/FieldDeltaJson.md)
- [HydraCollectionJsonLdWrappedJsonConceptJson](docs/Model/HydraCollectionJsonLdWrappedJsonConceptJson.md)
- [HydraCollectionJsonLdWrappedJsonInstantieJson](docs/Model/HydraCollectionJsonLdWrappedJsonInstantieJson.md)
- [HydraCollectionProductJson](docs/Model/HydraCollectionProductJson.md)
- [HydraPartialCollectionView](docs/Model/HydraPartialCollectionView.md)
- [InputVertalingen](docs/Model/InputVertalingen.md)
- [InstantieDeltaJson](docs/Model/InstantieDeltaJson.md)
- [JsonLdTypedAdres](docs/Model/JsonLdTypedAdres.md)
- [JsonLdTypedBewijs](docs/Model/JsonLdTypedBewijs.md)
- [JsonLdWrappedJsonConceptJson](docs/Model/JsonLdWrappedJsonConceptJson.md)
- [JsonLdWrappedJsonInstantieJson](docs/Model/JsonLdWrappedJsonInstantieJson.md)
- [MeJson](docs/Model/MeJson.md)
- [ProductJson](docs/Model/ProductJson.md)
- [ProductMetadataJson](docs/Model/ProductMetadataJson.md)
- [PubliekeOrganisatie](docs/Model/PubliekeOrganisatie.md)
- [PubliekeOrganisatieJson](docs/Model/PubliekeOrganisatieJson.md)
- [RateLimitConfigurationJson](docs/Model/RateLimitConfigurationJson.md)
- [Relation](docs/Model/Relation.md)
- [ShaclOrderedFinancieelVoordeel](docs/Model/ShaclOrderedFinancieelVoordeel.md)
- [ShaclOrderedJsonLdTypedContactgegevensJson](docs/Model/ShaclOrderedJsonLdTypedContactgegevensJson.md)
- [ShaclOrderedJsonLdTypedFinancieelVoordeel](docs/Model/ShaclOrderedJsonLdTypedFinancieelVoordeel.md)
- [ShaclOrderedJsonLdTypedKost](docs/Model/ShaclOrderedJsonLdTypedKost.md)
- [ShaclOrderedJsonLdTypedProcedureJson](docs/Model/ShaclOrderedJsonLdTypedProcedureJson.md)
- [ShaclOrderedJsonLdTypedRegelgevingJson](docs/Model/ShaclOrderedJsonLdTypedRegelgevingJson.md)
- [ShaclOrderedJsonLdTypedUpsertWebsite](docs/Model/ShaclOrderedJsonLdTypedUpsertWebsite.md)
- [ShaclOrderedJsonLdTypedVoorwaardeJson](docs/Model/ShaclOrderedJsonLdTypedVoorwaardeJson.md)
- [ShaclOrderedJsonLdTypedWebsite](docs/Model/ShaclOrderedJsonLdTypedWebsite.md)
- [ShaclOrderedKost](docs/Model/ShaclOrderedKost.md)
- [ShaclOrderedRegelgeving](docs/Model/ShaclOrderedRegelgeving.md)
- [ShaclOrderedUpsertContactgegevens](docs/Model/ShaclOrderedUpsertContactgegevens.md)
- [ShaclOrderedUpsertFinancieelVoordeel](docs/Model/ShaclOrderedUpsertFinancieelVoordeel.md)
- [ShaclOrderedUpsertKost](docs/Model/ShaclOrderedUpsertKost.md)
- [ShaclOrderedUpsertProcedureJson](docs/Model/ShaclOrderedUpsertProcedureJson.md)
- [ShaclOrderedUpsertRegelgeving](docs/Model/ShaclOrderedUpsertRegelgeving.md)
- [ShaclOrderedUpsertVerwantProductJson](docs/Model/ShaclOrderedUpsertVerwantProductJson.md)
- [ShaclOrderedUpsertVoorwaarde](docs/Model/ShaclOrderedUpsertVoorwaarde.md)
- [ShaclOrderedUpsertWebsite](docs/Model/ShaclOrderedUpsertWebsite.md)
- [ShaclOrderedVerwantProduct](docs/Model/ShaclOrderedVerwantProduct.md)
- [ShaclOrderedWebsite](docs/Model/ShaclOrderedWebsite.md)
- [SnapshotJsonConceptJson](docs/Model/SnapshotJsonConceptJson.md)
- [SnapshotJsonInstantieJson](docs/Model/SnapshotJsonInstantieJson.md)
- [SocialeKaartOrganisatie](docs/Model/SocialeKaartOrganisatie.md)
- [TaalString](docs/Model/TaalString.md)
- [UpsertAdres](docs/Model/UpsertAdres.md)
- [UpsertConceptJson](docs/Model/UpsertConceptJson.md)
- [UpsertInstantieJson](docs/Model/UpsertInstantieJson.md)
- [VerrijkingCaseJson](docs/Model/VerrijkingCaseJson.md)
- [VerrijkingUsage](docs/Model/VerrijkingUsage.md)
- [VerrijkingVoorwaardeJson](docs/Model/VerrijkingVoorwaardeJson.md)
- [VerrijkingVoorwaardeOptieId](docs/Model/VerrijkingVoorwaardeOptieId.md)
- [VerrijkingVoorwaardeOptieJson](docs/Model/VerrijkingVoorwaardeOptieJson.md)
- [View](docs/Model/View.md)
- [VoorwaardeJson](docs/Model/VoorwaardeJson.md)
- [VoorwaardenSetJson](docs/Model/VoorwaardenSetJson.md)
- [Website](docs/Model/Website.md)

## Authorization

Authentication schemes defined for the API:
### apiKey

- **Type**: API key
- **API key parameter name**: x-api-key
- **Location**: HTTP header


## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```

## Author

iom@groepen.vlaanderen.be

## About this package

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `1.0.2`
    - Generator version: `7.14.0-SNAPSHOT`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
