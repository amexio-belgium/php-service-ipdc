# OpenAPI\Client\ConceptLDESApi

All URIs are relative to https://api.ipdc.tni-vlaanderen.be, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getConceptSnapshotById()**](ConceptLDESApi.md#getConceptSnapshotById) | **GET** /doc/conceptsnapshot/{id} | Fetch a concept snapshot by id. |
| [**getConceptSnapshotByIdRedirect()**](ConceptLDESApi.md#getConceptSnapshotByIdRedirect) | **GET** /id/conceptsnapshot/{id} | Fetch a concept snapshot by id. Redirects to /doc/conceptsnapshot/{id}. |
| [**getConceptenLastPageLdesStream()**](ConceptLDESApi.md#getConceptenLastPageLdesStream) | **GET** /id/conceptsnapshot | Fetch the most recent concept snapshot page of the LDES stream. Redirects to /doc/conceptsnapshot. |
| [**getConceptenPageLdesStream()**](ConceptLDESApi.md#getConceptenPageLdesStream) | **GET** /doc/conceptsnapshot | Fetch a concept snapshot page of the LDES stream. |


## `getConceptSnapshotById()`

```php
getConceptSnapshotById($id): \OpenAPI\Client\Model\SnapshotJsonConceptJson
```

Fetch a concept snapshot by id.

**Permissions**: CONCEPT_SNAPSHOT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ConceptLDESApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string | The id of the concept snapshot

try {
    $result = $apiInstance->getConceptSnapshotById($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConceptLDESApi->getConceptSnapshotById: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| The id of the concept snapshot | |

### Return type

[**\OpenAPI\Client\Model\SnapshotJsonConceptJson**](../Model/SnapshotJsonConceptJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getConceptSnapshotByIdRedirect()`

```php
getConceptSnapshotByIdRedirect($id)
```

Fetch a concept snapshot by id. Redirects to /doc/conceptsnapshot/{id}.

**Permissions**: CONCEPT_SNAPSHOT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ConceptLDESApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string | The id of the concept snapshot

try {
    $apiInstance->getConceptSnapshotByIdRedirect($id);
} catch (Exception $e) {
    echo 'Exception when calling ConceptLDESApi->getConceptSnapshotByIdRedirect: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| The id of the concept snapshot | |

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

## `getConceptenLastPageLdesStream()`

```php
getConceptenLastPageLdesStream()
```

Fetch the most recent concept snapshot page of the LDES stream. Redirects to /doc/conceptsnapshot.

**Permissions**: CONCEPT_SNAPSHOT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ConceptLDESApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->getConceptenLastPageLdesStream();
} catch (Exception $e) {
    echo 'Exception when calling ConceptLDESApi->getConceptenLastPageLdesStream: ', $e->getMessage(), PHP_EOL;
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

## `getConceptenPageLdesStream()`

```php
getConceptenPageLdesStream($page_number, $limit, $concept): \OpenAPI\Client\Model\EventStreamSnapshotJsonConceptJson
```

Fetch a concept snapshot page of the LDES stream.

**Permissions**: CONCEPT_SNAPSHOT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ConceptLDESApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$page_number = 56; // int | Specifies the page the API needs to return. Default last page.
$limit = 56; // int | Specifies the amount of instance snapshots on one page.
$concept = 'concept_example'; // string | The concept-id or productnummer of the concept snapshot

try {
    $result = $apiInstance->getConceptenPageLdesStream($page_number, $limit, $concept);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ConceptLDESApi->getConceptenPageLdesStream: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_number** | **int**| Specifies the page the API needs to return. Default last page. | [optional] |
| **limit** | **int**| Specifies the amount of instance snapshots on one page. | [optional] |
| **concept** | **string**| The concept-id or productnummer of the concept snapshot | [optional] |

### Return type

[**\OpenAPI\Client\Model\EventStreamSnapshotJsonConceptJson**](../Model/EventStreamSnapshotJsonConceptJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
