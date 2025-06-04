# OpenAPI\Client\InstantieApi

All URIs are relative to https://api.ipdc.tni-vlaanderen.be, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**archiveInstantie()**](InstantieApi.md#archiveInstantie) | **DELETE** /doc/instantie/{idOrProductnummer} | Archive the instantie based on instantie-id or instantieIdOrProductnummer. |
| [**createOrUpdateInstantie()**](InstantieApi.md#createOrUpdateInstantie) | **POST** /doc/instantie | Create a new instantie or (if id/instantieIdOrProductnummer in body) update an instantie. |
| [**dearchiveInstantie()**](InstantieApi.md#dearchiveInstantie) | **PUT** /doc/instantie/{idOrProductnummer}/dearchive | Dearchive the instantie based on instantie-id or instantieIdOrProductnummer. |
| [**exportInstanties()**](InstantieApi.md#exportInstanties) | **GET** /doc/instantie/export | Fetch instanties page to export. Filter by using requestparams. |
| [**exportInstantiesFilterByDate()**](InstantieApi.md#exportInstantiesFilterByDate) | **GET** /doc/instantie/export/byLaatstOntvangen | Fetch instanties page to export. Filter by laatstOntvangen in requestParams. |
| [**findInstantieByIdOrProductnummer()**](InstantieApi.md#findInstantieByIdOrProductnummer) | **GET** /doc/instantie/{idOrProductnummer} | Fetch the details of the instantie. |
| [**findInstantieByIdOrProductnummerRedirect()**](InstantieApi.md#findInstantieByIdOrProductnummerRedirect) | **GET** /id/instantie/{idOrProductnummer} | Fetch the details of the instantie. Redirects to /doc/instantie/{idOrProductnummer}. |
| [**findInstantiePage()**](InstantieApi.md#findInstantiePage) | **GET** /doc/instantie | Fetch instantie page. Filter by using requestparams. |
| [**findInstantiesByIdsOrProductnummers()**](InstantieApi.md#findInstantiesByIdsOrProductnummers) | **GET** /doc/instantie/byIds/{ids} | Fetch the details of the instanties. |
| [**getInstantieDelta()**](InstantieApi.md#getInstantieDelta) | **GET** /doc/instantie/{idOrProductnummer}/delta |  |
| [**redirectToFindInstantiePage()**](InstantieApi.md#redirectToFindInstantiePage) | **GET** /id/instantie | Fetch the first instantie page. Redirects to /doc/instantie. |


## `archiveInstantie()`

```php
archiveInstantie($id_or_productnummer)
```

Archive the instantie based on instantie-id or instantieIdOrProductnummer.

**Permissions**: INSTANTIE_ARCHIVE

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id_or_productnummer = 'id_or_productnummer_example'; // string | Pass the instantie-id or instantieIdOrProductnummer for the instantie to archive

try {
    $apiInstance->archiveInstantie($id_or_productnummer);
} catch (Exception $e) {
    echo 'Exception when calling InstantieApi->archiveInstantie: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id_or_productnummer** | **string**| Pass the instantie-id or instantieIdOrProductnummer for the instantie to archive | |

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

## `createOrUpdateInstantie()`

```php
createOrUpdateInstantie($upsert_instantie_json): \OpenAPI\Client\Model\JsonLdWrappedJsonInstantieJson
```

Create a new instantie or (if id/instantieIdOrProductnummer in body) update an instantie.

**Permissions**: INSTANTIE_WRITE_LOCAL, INSTANTIE_WRITE_NON_LOCAL, INSTANTIE_WRITE_WITH_ID, INSTANTIE_WRITE_WITH_PRODUCTNUMMER

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$upsert_instantie_json = new \OpenAPI\Client\Model\UpsertInstantieJson(); // \OpenAPI\Client\Model\UpsertInstantieJson

try {
    $result = $apiInstance->createOrUpdateInstantie($upsert_instantie_json);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InstantieApi->createOrUpdateInstantie: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **upsert_instantie_json** | [**\OpenAPI\Client\Model\UpsertInstantieJson**](../Model/UpsertInstantieJson.md)|  | |

### Return type

[**\OpenAPI\Client\Model\JsonLdWrappedJsonInstantieJson**](../Model/JsonLdWrappedJsonInstantieJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/ld+json`, `application/json`
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `dearchiveInstantie()`

```php
dearchiveInstantie($id_or_productnummer)
```

Dearchive the instantie based on instantie-id or instantieIdOrProductnummer.

**Permissions**: INSTANTIE_DEARCHIVE

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id_or_productnummer = 'id_or_productnummer_example'; // string | Pass the instantie-id or instantieIdOrProductnummer for the instantie to dearchive

try {
    $apiInstance->dearchiveInstantie($id_or_productnummer);
} catch (Exception $e) {
    echo 'Exception when calling InstantieApi->dearchiveInstantie: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id_or_productnummer** | **string**| Pass the instantie-id or instantieIdOrProductnummer for the instantie to dearchive | |

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

## `exportInstanties()`

```php
exportInstanties($page_index, $limit, $laatst_ontvangen_vanaf, $bevoegd_bestuursniveaus, $geografische_toepassingsgebieden, $include_parent_geografische_toepassingsgebieden): \OpenAPI\Client\Model\HydraCollectionJsonLdWrappedJsonInstantieJson
```

Fetch instanties page to export. Filter by using requestparams.

**Permissions**: INSTANTIE_EXPORT

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$page_index = 56; // int | Specifies the page the API needs to return. Default 0 (first page)
$limit = 56; // int | Specifies the amount of instances on one page.
$laatst_ontvangen_vanaf = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | If specified, the API will only return instances that have been received from the given timestamp. Using the ISO specification (yyyy-MM-ddThh:mm:ssZ)
$bevoegd_bestuursniveaus = array('bevoegd_bestuursniveaus_example'); // string[] | If specified, the API will only return instances with the given bevoegdBestuursniveau. E.g. Europees. Possible values can be fetched using the codelijst endpoint.
$geografische_toepassingsgebieden = array('geografische_toepassingsgebieden_example'); // string[] | If specified, the API will only return instances for the given geografische gebieden and/or zip code (List). E.g. BE25838016, 1000(zip code). Possible values can be fetched using the codelijst endpoint.
$include_parent_geografische_toepassingsgebieden = true; // bool | If specified, the API will not only return instances for the given geografische gebieden (List). E.g. BE25838016, but also instances of parent gebieden. E.g. BE258 and BE23, BE2, BE

try {
    $result = $apiInstance->exportInstanties($page_index, $limit, $laatst_ontvangen_vanaf, $bevoegd_bestuursniveaus, $geografische_toepassingsgebieden, $include_parent_geografische_toepassingsgebieden);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InstantieApi->exportInstanties: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_index** | **int**| Specifies the page the API needs to return. Default 0 (first page) | [optional] |
| **limit** | **int**| Specifies the amount of instances on one page. | [optional] |
| **laatst_ontvangen_vanaf** | **\DateTime**| If specified, the API will only return instances that have been received from the given timestamp. Using the ISO specification (yyyy-MM-ddThh:mm:ssZ) | [optional] |
| **bevoegd_bestuursniveaus** | [**string[]**](../Model/string.md)| If specified, the API will only return instances with the given bevoegdBestuursniveau. E.g. Europees. Possible values can be fetched using the codelijst endpoint. | [optional] |
| **geografische_toepassingsgebieden** | [**string[]**](../Model/string.md)| If specified, the API will only return instances for the given geografische gebieden and/or zip code (List). E.g. BE25838016, 1000(zip code). Possible values can be fetched using the codelijst endpoint. | [optional] |
| **include_parent_geografische_toepassingsgebieden** | **bool**| If specified, the API will not only return instances for the given geografische gebieden (List). E.g. BE25838016, but also instances of parent gebieden. E.g. BE258 and BE23, BE2, BE | [optional] |

### Return type

[**\OpenAPI\Client\Model\HydraCollectionJsonLdWrappedJsonInstantieJson**](../Model/HydraCollectionJsonLdWrappedJsonInstantieJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `exportInstantiesFilterByDate()`

```php
exportInstantiesFilterByDate($page_index, $limit, $laatst_ontvangen_vanaf): \OpenAPI\Client\Model\HydraCollectionJsonLdWrappedJsonInstantieJson
```

Fetch instanties page to export. Filter by laatstOntvangen in requestParams.

**Permissions**: INSTANTIE_EXPORT

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$page_index = 56; // int | Specifies the page the API needs to return. Default 0 (first page)
$limit = 56; // int | Specifies the amount of instances on one page.
$laatst_ontvangen_vanaf = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | If specified, the API will only return instances that have been received from the given timestamp. Using the ISO specification (yyyy-MM-ddThh:mm:ssZ)

try {
    $result = $apiInstance->exportInstantiesFilterByDate($page_index, $limit, $laatst_ontvangen_vanaf);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InstantieApi->exportInstantiesFilterByDate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_index** | **int**| Specifies the page the API needs to return. Default 0 (first page) | [optional] |
| **limit** | **int**| Specifies the amount of instances on one page. | [optional] |
| **laatst_ontvangen_vanaf** | **\DateTime**| If specified, the API will only return instances that have been received from the given timestamp. Using the ISO specification (yyyy-MM-ddThh:mm:ssZ) | [optional] |

### Return type

[**\OpenAPI\Client\Model\HydraCollectionJsonLdWrappedJsonInstantieJson**](../Model/HydraCollectionJsonLdWrappedJsonInstantieJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `findInstantieByIdOrProductnummer()`

```php
findInstantieByIdOrProductnummer($id_or_productnummer): \OpenAPI\Client\Model\JsonLdWrappedJsonInstantieJson
```

Fetch the details of the instantie.

**Permissions**: INSTANTIE_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id_or_productnummer = 'id_or_productnummer_example'; // string | Pass the instantie-id or the instantieIdOrProductnummer of the instantie to fetch

try {
    $result = $apiInstance->findInstantieByIdOrProductnummer($id_or_productnummer);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InstantieApi->findInstantieByIdOrProductnummer: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id_or_productnummer** | **string**| Pass the instantie-id or the instantieIdOrProductnummer of the instantie to fetch | |

### Return type

[**\OpenAPI\Client\Model\JsonLdWrappedJsonInstantieJson**](../Model/JsonLdWrappedJsonInstantieJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `findInstantieByIdOrProductnummerRedirect()`

```php
findInstantieByIdOrProductnummerRedirect($id_or_productnummer)
```

Fetch the details of the instantie. Redirects to /doc/instantie/{idOrProductnummer}.

**Permissions**: INSTANTIE_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id_or_productnummer = 'id_or_productnummer_example'; // string | Pass the instantie-id or the productnummer of the instantie to fetch

try {
    $apiInstance->findInstantieByIdOrProductnummerRedirect($id_or_productnummer);
} catch (Exception $e) {
    echo 'Exception when calling InstantieApi->findInstantieByIdOrProductnummerRedirect: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id_or_productnummer** | **string**| Pass the instantie-id or the productnummer of the instantie to fetch | |

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

## `findInstantiePage()`

```php
findInstantiePage($page_index, $limit, $sort_by, $concept, $vertaling, $geografische_toepassingsgebieden, $include_parent_geografische_toepassingsgebieden, $zoekterm, $uitvoerend_bestuursniveaus, $bevoegd_bestuursniveaus, $doelgroepen, $themas, $types, $publicatiekanalen, $cases, $gearchiveerd, $uitvoerende_organisatie, $sociale_kaart_organisatie, $eind_datum_vanaf): \OpenAPI\Client\Model\HydraCollectionJsonLdWrappedJsonInstantieJson
```

Fetch instantie page. Filter by using requestparams.

**Permissions**: INSTANTIE_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$page_index = 56; // int | Specifies the page the API needs to return. Default 0 (first page)
$limit = 56; // int | Specifies the amount of instances on one page.
$sort_by = 'sort_by_example'; // string | On which property to sort
$concept = 'concept_example'; // string | If specified, the API will only return instances that are coupled with the specified conceptId
$vertaling = 'vertaling_example'; // string | If specified, the API will only return instances of that language
$geografische_toepassingsgebieden = array('geografische_toepassingsgebieden_example'); // string[] | If specified, the API will only return instances for the given geografische gebieden and/or zip code (List). E.g. BE25838016, 1000(zip code). Possible values can be fetched using the codelijst endpoint.
$include_parent_geografische_toepassingsgebieden = true; // bool | If specified, the API will not only return instances for the given geografische gebieden (List). E.g. BE25838016, but also instances of parent gebieden. E.g. BE258 and BE23, BE2, BE
$zoekterm = 'zoekterm_example'; // string | If specified, the API will only return instances where the name and/or description and/or search terms matches the value of the zoekterm.  If the 'vertalingen' queryparam is passed, we will only look for a match in instances for the specified language.
$uitvoerend_bestuursniveaus = array('uitvoerend_bestuursniveaus_example'); // string[] | If specified, the API will only return instances with the given uitvoerendBestuursniveau. E.g. Vlaams. Possible values can be fetched using the codelijst endpoint.
$bevoegd_bestuursniveaus = array('bevoegd_bestuursniveaus_example'); // string[] | If specified, the API will only return instances with the given bevoegdBestuursniveau. E.g. Europees. Possible values can be fetched using the codelijst endpoint.
$doelgroepen = array('doelgroepen_example'); // string[] | If specified, the API will only return instances with the given doelgroep. E.g. Burger. Possible values can be fetched using the codelijst endpoint.
$themas = array('themas_example'); // string[] | If specified, the API will only return instances with the given thema. E.g. BurgerOverheid. Possible values can be fetched using the codelijst endpoint.
$types = array('types_example'); // string[] | If specified, the API will only return instances with one of the given types. E.g. AdviesBegeleiding. Possible values can be fetched using the codelijst endpoint.
$publicatiekanalen = array('publicatiekanalen_example'); // string[] | If specified, the API will only return instances with the given publicatiekanalen. E.g. YourEurope. Possible values can be fetched using the codelijst endpoint.
$cases = array('cases_example'); // string[] | If specified, the API will only return instances with the given cases. E.g. Rechtenverkenner.
$gearchiveerd = True; // bool | If true, the API will also return instances that have been archived
$uitvoerende_organisatie = 'uitvoerende_organisatie_example'; // string | If specified the result will only contain instances with the given uitvoerende organisatie
$sociale_kaart_organisatie = 'sociale_kaart_organisatie_example'; // string | If specified the result will only contain instances with the given sociale kaart organisatie
$eind_datum_vanaf = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | If specified, the result wil only contain the instances having an end Date that is larger than the specified date, or has an empty end date. This Using the ISO specification ISO specification (yyyy-MM-ddThh:mm:ssZ).

try {
    $result = $apiInstance->findInstantiePage($page_index, $limit, $sort_by, $concept, $vertaling, $geografische_toepassingsgebieden, $include_parent_geografische_toepassingsgebieden, $zoekterm, $uitvoerend_bestuursniveaus, $bevoegd_bestuursniveaus, $doelgroepen, $themas, $types, $publicatiekanalen, $cases, $gearchiveerd, $uitvoerende_organisatie, $sociale_kaart_organisatie, $eind_datum_vanaf);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InstantieApi->findInstantiePage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_index** | **int**| Specifies the page the API needs to return. Default 0 (first page) | [optional] |
| **limit** | **int**| Specifies the amount of instances on one page. | [optional] |
| **sort_by** | **string**| On which property to sort | [optional] |
| **concept** | **string**| If specified, the API will only return instances that are coupled with the specified conceptId | [optional] |
| **vertaling** | **string**| If specified, the API will only return instances of that language | [optional] |
| **geografische_toepassingsgebieden** | [**string[]**](../Model/string.md)| If specified, the API will only return instances for the given geografische gebieden and/or zip code (List). E.g. BE25838016, 1000(zip code). Possible values can be fetched using the codelijst endpoint. | [optional] |
| **include_parent_geografische_toepassingsgebieden** | **bool**| If specified, the API will not only return instances for the given geografische gebieden (List). E.g. BE25838016, but also instances of parent gebieden. E.g. BE258 and BE23, BE2, BE | [optional] |
| **zoekterm** | **string**| If specified, the API will only return instances where the name and/or description and/or search terms matches the value of the zoekterm.  If the &#39;vertalingen&#39; queryparam is passed, we will only look for a match in instances for the specified language. | [optional] |
| **uitvoerend_bestuursniveaus** | [**string[]**](../Model/string.md)| If specified, the API will only return instances with the given uitvoerendBestuursniveau. E.g. Vlaams. Possible values can be fetched using the codelijst endpoint. | [optional] |
| **bevoegd_bestuursniveaus** | [**string[]**](../Model/string.md)| If specified, the API will only return instances with the given bevoegdBestuursniveau. E.g. Europees. Possible values can be fetched using the codelijst endpoint. | [optional] |
| **doelgroepen** | [**string[]**](../Model/string.md)| If specified, the API will only return instances with the given doelgroep. E.g. Burger. Possible values can be fetched using the codelijst endpoint. | [optional] |
| **themas** | [**string[]**](../Model/string.md)| If specified, the API will only return instances with the given thema. E.g. BurgerOverheid. Possible values can be fetched using the codelijst endpoint. | [optional] |
| **types** | [**string[]**](../Model/string.md)| If specified, the API will only return instances with one of the given types. E.g. AdviesBegeleiding. Possible values can be fetched using the codelijst endpoint. | [optional] |
| **publicatiekanalen** | [**string[]**](../Model/string.md)| If specified, the API will only return instances with the given publicatiekanalen. E.g. YourEurope. Possible values can be fetched using the codelijst endpoint. | [optional] |
| **cases** | [**string[]**](../Model/string.md)| If specified, the API will only return instances with the given cases. E.g. Rechtenverkenner. | [optional] |
| **gearchiveerd** | **bool**| If true, the API will also return instances that have been archived | [optional] |
| **uitvoerende_organisatie** | **string**| If specified the result will only contain instances with the given uitvoerende organisatie | [optional] |
| **sociale_kaart_organisatie** | **string**| If specified the result will only contain instances with the given sociale kaart organisatie | [optional] |
| **eind_datum_vanaf** | **\DateTime**| If specified, the result wil only contain the instances having an end Date that is larger than the specified date, or has an empty end date. This Using the ISO specification ISO specification (yyyy-MM-ddThh:mm:ssZ). | [optional] |

### Return type

[**\OpenAPI\Client\Model\HydraCollectionJsonLdWrappedJsonInstantieJson**](../Model/HydraCollectionJsonLdWrappedJsonInstantieJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `findInstantiesByIdsOrProductnummers()`

```php
findInstantiesByIdsOrProductnummers($ids): \OpenAPI\Client\Model\JsonLdWrappedJsonInstantieJson[]
```

Fetch the details of the instanties.

**Permissions**: INSTANTIE_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$ids = 'ids_example'; // string | Pass the instantie-ids or productnummers of the instanties to fetch. This should be encoded as a comma-separated list.

try {
    $result = $apiInstance->findInstantiesByIdsOrProductnummers($ids);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InstantieApi->findInstantiesByIdsOrProductnummers: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ids** | **string**| Pass the instantie-ids or productnummers of the instanties to fetch. This should be encoded as a comma-separated list. | |

### Return type

[**\OpenAPI\Client\Model\JsonLdWrappedJsonInstantieJson[]**](../Model/JsonLdWrappedJsonInstantieJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getInstantieDelta()`

```php
getInstantieDelta($id_or_productnummer, $from, $to): \OpenAPI\Client\Model\InstantieDeltaJson
```



**Permissions**: INSTANTIE_DELTA_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id_or_productnummer = 'id_or_productnummer_example'; // string
$from = 'from_example'; // string
$to = 'to_example'; // string

try {
    $result = $apiInstance->getInstantieDelta($id_or_productnummer, $from, $to);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InstantieApi->getInstantieDelta: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id_or_productnummer** | **string**|  | |
| **from** | **string**|  | |
| **to** | **string**|  | |

### Return type

[**\OpenAPI\Client\Model\InstantieDeltaJson**](../Model/InstantieDeltaJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `redirectToFindInstantiePage()`

```php
redirectToFindInstantiePage()
```

Fetch the first instantie page. Redirects to /doc/instantie.

**Permissions**: INSTANTIE_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->redirectToFindInstantiePage();
} catch (Exception $e) {
    echo 'Exception when calling InstantieApi->redirectToFindInstantiePage: ', $e->getMessage(), PHP_EOL;
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
