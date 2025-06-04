# OpenAPI\Client\ConceptApi

All URIs are relative to https://api.ipdc.tni-vlaanderen.be, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**archiveConcept()**](ConceptApi.md#archiveConcept) | **DELETE** /doc/concept/{idOrProductnummer} | Archive the concept based on concept-id or productnummer. |
| [**createOrUpdateConcept()**](ConceptApi.md#createOrUpdateConcept) | **POST** /doc/concept | Create a new concept or (if id/productnummer in body) update a concept. |
| [**dearchiveConcept()**](ConceptApi.md#dearchiveConcept) | **PUT** /doc/concept/{idOrProductnummer}/dearchive | Dearchive the concept based on concept-id or productnummer. |
| [**export()**](ConceptApi.md#export) | **GET** /doc/concept/export | Fetch concept page to export. Filter by laatstOntvangen in requestParams. |
| [**findConceptByIdOrProductnummer()**](ConceptApi.md#findConceptByIdOrProductnummer) | **GET** /doc/concept/{idOrProductnummer} | Fetch the details of the concept. |
| [**findConceptsByIdsOrProductnummers()**](ConceptApi.md#findConceptsByIdsOrProductnummers) | **GET** /doc/concept/byIds/{ids} | Fetch the details of the concepten. |
| [**findPage()**](ConceptApi.md#findPage) | **GET** /doc/concept | Fetch concepten page. Filter by using requestparams. |
| [**getConceptDelta()**](ConceptApi.md#getConceptDelta) | **GET** /doc/concept/{idOrProductnummer}/delta |  |
| [**redirectToFindConceptByIdOrProductnummer()**](ConceptApi.md#redirectToFindConceptByIdOrProductnummer) | **GET** /id/concept/{idOrProductnummer} | Fetch de details of the concept. Redirects to /doc/concept/{idOrProductnummer}. |
| [**redirectToFindConceptPage()**](ConceptApi.md#redirectToFindConceptPage) | **GET** /id/concept | Fetch the first concept page. Redirects to /doc/concept. |


## `archiveConcept()`

```php
archiveConcept($id_or_productnummer)
```

Archive the concept based on concept-id or productnummer.

**Permissions**: CONCEPT_ARCHIVE

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ConceptApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id_or_productnummer = 'id_or_productnummer_example'; // string | Pass the concept-id or the productnummer for the concept to archive

try {
    $apiInstance->archiveConcept($id_or_productnummer);
} catch (Exception $e) {
    echo 'Exception when calling ConceptApi->archiveConcept: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id_or_productnummer** | **string**| Pass the concept-id or the productnummer for the concept to archive | |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createOrUpdateConcept()`

```php
createOrUpdateConcept($upsert_concept_json): \OpenAPI\Client\Model\JsonLdWrappedJsonConceptJson
```

Create a new concept or (if id/productnummer in body) update a concept.

**Permissions**: CONCEPT_WRITE, CONCEPT_WRITE_WITH_PRODUCTNUMMER

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ConceptApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$upsert_concept_json = new \OpenAPI\Client\Model\UpsertConceptJson(); // \OpenAPI\Client\Model\UpsertConceptJson

try {
    $result = $apiInstance->createOrUpdateConcept($upsert_concept_json);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConceptApi->createOrUpdateConcept: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **upsert_concept_json** | [**\OpenAPI\Client\Model\UpsertConceptJson**](../Model/UpsertConceptJson.md)|  | |

### Return type

[**\OpenAPI\Client\Model\JsonLdWrappedJsonConceptJson**](../Model/JsonLdWrappedJsonConceptJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/ld+json`, `application/json`
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `dearchiveConcept()`

```php
dearchiveConcept($id_or_productnummer)
```

Dearchive the concept based on concept-id or productnummer.

**Permissions**: CONCEPT_DEARCHIVE

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ConceptApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id_or_productnummer = 'id_or_productnummer_example'; // string | Pass the concept-id or the productnummer for the concept to dearchive

try {
    $apiInstance->dearchiveConcept($id_or_productnummer);
} catch (Exception $e) {
    echo 'Exception when calling ConceptApi->dearchiveConcept: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id_or_productnummer** | **string**| Pass the concept-id or the productnummer for the concept to dearchive | |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `export()`

```php
export($page_index, $limit, $laatst_ontvangen_vanaf): \OpenAPI\Client\Model\HydraCollectionJsonLdWrappedJsonConceptJson
```

Fetch concept page to export. Filter by laatstOntvangen in requestParams.

**Permissions**: CONCEPT_EXPORT

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ConceptApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$page_index = 56; // int | Specifies the page the API needs to return. Default 0 (first page)
$limit = 56; // int | Specifies the amount of concepts on one page.
$laatst_ontvangen_vanaf = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | If specified, the API will only return concepten that have been received from the given timestamp. Using the ISO specification (yyyy-MM-ddThh:mm:ssZ)

try {
    $result = $apiInstance->export($page_index, $limit, $laatst_ontvangen_vanaf);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConceptApi->export: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_index** | **int**| Specifies the page the API needs to return. Default 0 (first page) | [optional] |
| **limit** | **int**| Specifies the amount of concepts on one page. | [optional] |
| **laatst_ontvangen_vanaf** | **\DateTime**| If specified, the API will only return concepten that have been received from the given timestamp. Using the ISO specification (yyyy-MM-ddThh:mm:ssZ) | [optional] |

### Return type

[**\OpenAPI\Client\Model\HydraCollectionJsonLdWrappedJsonConceptJson**](../Model/HydraCollectionJsonLdWrappedJsonConceptJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `findConceptByIdOrProductnummer()`

```php
findConceptByIdOrProductnummer($id_or_productnummer): \OpenAPI\Client\Model\JsonLdWrappedJsonConceptJson
```

Fetch the details of the concept.

**Permissions**: CONCEPT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ConceptApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id_or_productnummer = 'id_or_productnummer_example'; // string | Pass the concept-id or productnummer for the concept to fetch

try {
    $result = $apiInstance->findConceptByIdOrProductnummer($id_or_productnummer);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConceptApi->findConceptByIdOrProductnummer: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id_or_productnummer** | **string**| Pass the concept-id or productnummer for the concept to fetch | |

### Return type

[**\OpenAPI\Client\Model\JsonLdWrappedJsonConceptJson**](../Model/JsonLdWrappedJsonConceptJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `findConceptsByIdsOrProductnummers()`

```php
findConceptsByIdsOrProductnummers($ids): \OpenAPI\Client\Model\JsonLdWrappedJsonConceptJson[]
```

Fetch the details of the concepten.

**Permissions**: CONCEPT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ConceptApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$ids = 'ids_example'; // string | Pass the concept-ids or productnummers of the concepten to fetch. This should be encoded as a comma-separated list.

try {
    $result = $apiInstance->findConceptsByIdsOrProductnummers($ids);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConceptApi->findConceptsByIdsOrProductnummers: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ids** | **string**| Pass the concept-ids or productnummers of the concepten to fetch. This should be encoded as a comma-separated list. | |

### Return type

[**\OpenAPI\Client\Model\JsonLdWrappedJsonConceptJson[]**](../Model/JsonLdWrappedJsonConceptJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `findPage()`

```php
findPage($page_index, $limit, $sort_by, $vertaling, $zoekterm, $uitvoerend_bestuursniveaus, $bevoegd_bestuursniveaus, $doelgroepen, $themas, $types, $gearchiveerd, $eind_datum_vanaf): \OpenAPI\Client\Model\HydraCollectionJsonLdWrappedJsonConceptJson
```

Fetch concepten page. Filter by using requestparams.

**Permissions**: CONCEPT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ConceptApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$page_index = 56; // int | Specifies the page that the API will return. Default 0 (first page)
$limit = 56; // int | Specifies the amount of concepts on one page.
$sort_by = 'sort_by_example'; // string | On which property to sort
$vertaling = 'vertaling_example'; // string | If specified, the API will only return concepts of that language
$zoekterm = 'zoekterm_example'; // string | If specified, the API will only return concepts where the name and/or description and/or search terms matches the value of the zoekterm.  If the 'vertalingen' queryparam is passed, we will only look for a match in concepts for the specified language.
$uitvoerend_bestuursniveaus = array('uitvoerend_bestuursniveaus_example'); // string[] | If specified, the API will only return concepts with the given uitvoerendBestuursniveau. E.g. Vlaams. Possible values can be fetched using the codelijst endpoint.
$bevoegd_bestuursniveaus = array('bevoegd_bestuursniveaus_example'); // string[] | If specified, the API will only return concepts with the given bevoegdBestuursniveau. E.g. Europees. Possible values can be fetched using the codelijst endpoint.
$doelgroepen = array('doelgroepen_example'); // string[] | If specified, the API will only return concepts with the given doelgroep. E.g. Burger. Possible values can be fetched using the codelijst endpoint.
$themas = array('themas_example'); // string[] | If specified, the API will only return concepts with the given thema. E.g. BurgerOverheid. Possible values can be fetched using the codelijst endpoint.
$types = array('types_example'); // string[] | If specified, the API will only return concepts with one of the given types. E.g. AdviesBegeleiding. Possible values can be fetched using the codelijst endpoint.
$gearchiveerd = True; // bool | If true, the API will also return concepts that have been archived
$eind_datum_vanaf = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | If specified, the result wil only contain the concepts having an end Date larger than the specified date, or has an empty end date. This Using the ISO specification ISO specification (yyyy-MM-ddThh:mm:ssZ).

try {
    $result = $apiInstance->findPage($page_index, $limit, $sort_by, $vertaling, $zoekterm, $uitvoerend_bestuursniveaus, $bevoegd_bestuursniveaus, $doelgroepen, $themas, $types, $gearchiveerd, $eind_datum_vanaf);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConceptApi->findPage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_index** | **int**| Specifies the page that the API will return. Default 0 (first page) | [optional] |
| **limit** | **int**| Specifies the amount of concepts on one page. | [optional] |
| **sort_by** | **string**| On which property to sort | [optional] |
| **vertaling** | **string**| If specified, the API will only return concepts of that language | [optional] |
| **zoekterm** | **string**| If specified, the API will only return concepts where the name and/or description and/or search terms matches the value of the zoekterm.  If the &#39;vertalingen&#39; queryparam is passed, we will only look for a match in concepts for the specified language. | [optional] |
| **uitvoerend_bestuursniveaus** | [**string[]**](../Model/string.md)| If specified, the API will only return concepts with the given uitvoerendBestuursniveau. E.g. Vlaams. Possible values can be fetched using the codelijst endpoint. | [optional] |
| **bevoegd_bestuursniveaus** | [**string[]**](../Model/string.md)| If specified, the API will only return concepts with the given bevoegdBestuursniveau. E.g. Europees. Possible values can be fetched using the codelijst endpoint. | [optional] |
| **doelgroepen** | [**string[]**](../Model/string.md)| If specified, the API will only return concepts with the given doelgroep. E.g. Burger. Possible values can be fetched using the codelijst endpoint. | [optional] |
| **themas** | [**string[]**](../Model/string.md)| If specified, the API will only return concepts with the given thema. E.g. BurgerOverheid. Possible values can be fetched using the codelijst endpoint. | [optional] |
| **types** | [**string[]**](../Model/string.md)| If specified, the API will only return concepts with one of the given types. E.g. AdviesBegeleiding. Possible values can be fetched using the codelijst endpoint. | [optional] |
| **gearchiveerd** | **bool**| If true, the API will also return concepts that have been archived | [optional] |
| **eind_datum_vanaf** | **\DateTime**| If specified, the result wil only contain the concepts having an end Date larger than the specified date, or has an empty end date. This Using the ISO specification ISO specification (yyyy-MM-ddThh:mm:ssZ). | [optional] |

### Return type

[**\OpenAPI\Client\Model\HydraCollectionJsonLdWrappedJsonConceptJson**](../Model/HydraCollectionJsonLdWrappedJsonConceptJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getConceptDelta()`

```php
getConceptDelta($id_or_productnummer, $from, $to): \OpenAPI\Client\Model\ConceptDeltaJson
```



**Permissions**: CONCEPT_DELTA_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ConceptApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id_or_productnummer = 'id_or_productnummer_example'; // string
$from = 'from_example'; // string
$to = 'to_example'; // string

try {
    $result = $apiInstance->getConceptDelta($id_or_productnummer, $from, $to);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConceptApi->getConceptDelta: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id_or_productnummer** | **string**|  | |
| **from** | **string**|  | |
| **to** | **string**|  | |

### Return type

[**\OpenAPI\Client\Model\ConceptDeltaJson**](../Model/ConceptDeltaJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `redirectToFindConceptByIdOrProductnummer()`

```php
redirectToFindConceptByIdOrProductnummer($id_or_productnummer)
```

Fetch de details of the concept. Redirects to /doc/concept/{idOrProductnummer}.

**Permissions**: CONCEPT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ConceptApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id_or_productnummer = 'id_or_productnummer_example'; // string | You can pass the uuid or the productnumber for a concept to fetch it by id

try {
    $apiInstance->redirectToFindConceptByIdOrProductnummer($id_or_productnummer);
} catch (Exception $e) {
    echo 'Exception when calling ConceptApi->redirectToFindConceptByIdOrProductnummer: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id_or_productnummer** | **string**| You can pass the uuid or the productnumber for a concept to fetch it by id | |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `*/*`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `redirectToFindConceptPage()`

```php
redirectToFindConceptPage()
```

Fetch the first concept page. Redirects to /doc/concept.

**Permissions**: CONCEPT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ConceptApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->redirectToFindConceptPage();
} catch (Exception $e) {
    echo 'Exception when calling ConceptApi->redirectToFindConceptPage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `*/*`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
