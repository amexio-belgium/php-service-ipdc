# OpenAPI\Client\InstantieLDESApi

All URIs are relative to https://api.ipdc.tni-vlaanderen.be, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getInstantieLastPageLdesStream()**](InstantieLDESApi.md#getInstantieLastPageLdesStream) | **GET** /id/instantiesnapshot | Fetch the most recent instantie snapshot page of the LDES stream. Redirects to /doc/instantiesnapshot. |
| [**getInstantieSnapshotById()**](InstantieLDESApi.md#getInstantieSnapshotById) | **GET** /doc/instantiesnapshot/{id} | Fetch an instantie snapshot by id. |
| [**getInstantieSnapshotByIdRedirect()**](InstantieLDESApi.md#getInstantieSnapshotByIdRedirect) | **GET** /id/instantiesnapshot/{id} | Fetch an instantie snapshot by id. Redirects to /doc/instantiesnapshot/{id}. |
| [**getInstantiesPageLdesStream()**](InstantieLDESApi.md#getInstantiesPageLdesStream) | **GET** /doc/instantiesnapshot | Fetch an instantie snapshot page of the LDES stream. |


## `getInstantieLastPageLdesStream()`

```php
getInstantieLastPageLdesStream()
```

Fetch the most recent instantie snapshot page of the LDES stream. Redirects to /doc/instantiesnapshot.

**Permissions**: INSTANTIE_SNAPSHOT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieLDESApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $apiInstance->getInstantieLastPageLdesStream();
} catch (Exception $e) {
    echo 'Exception when calling InstantieLDESApi->getInstantieLastPageLdesStream: ', $e->getMessage(), PHP_EOL;
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

## `getInstantieSnapshotById()`

```php
getInstantieSnapshotById($id): \OpenAPI\Client\Model\SnapshotJsonInstantieJson
```

Fetch an instantie snapshot by id.

**Permissions**: INSTANTIE_SNAPSHOT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieLDESApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string | The id of the instantie snapshot

try {
    $result = $apiInstance->getInstantieSnapshotById($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InstantieLDESApi->getInstantieSnapshotById: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| The id of the instantie snapshot | |

### Return type

[**\OpenAPI\Client\Model\SnapshotJsonInstantieJson**](../Model/SnapshotJsonInstantieJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getInstantieSnapshotByIdRedirect()`

```php
getInstantieSnapshotByIdRedirect($id)
```

Fetch an instantie snapshot by id. Redirects to /doc/instantiesnapshot/{id}.

**Permissions**: INSTANTIE_SNAPSHOT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieLDESApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string | The id of the instantie snapshot

try {
    $apiInstance->getInstantieSnapshotByIdRedirect($id);
} catch (Exception $e) {
    echo 'Exception when calling InstantieLDESApi->getInstantieSnapshotByIdRedirect: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| The id of the instantie snapshot | |

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

## `getInstantiesPageLdesStream()`

```php
getInstantiesPageLdesStream($page_number, $limit, $instantie): \OpenAPI\Client\Model\EventStreamSnapshotJsonInstantieJson
```

Fetch an instantie snapshot page of the LDES stream.

**Permissions**: INSTANTIE_SNAPSHOT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\InstantieLDESApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$page_number = 56; // int | Specifies the page the API needs to return. Default last page.
$limit = 56; // int | Specifies the amount of instance snapshots on one page.
$instantie = 'instantie_example'; // string | The instantie-id or productnummer of the instantie snapshot

try {
    $result = $apiInstance->getInstantiesPageLdesStream($page_number, $limit, $instantie);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InstantieLDESApi->getInstantiesPageLdesStream: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_number** | **int**| Specifies the page the API needs to return. Default last page. | [optional] |
| **limit** | **int**| Specifies the amount of instance snapshots on one page. | [optional] |
| **instantie** | **string**| The instantie-id or productnummer of the instantie snapshot | [optional] |

### Return type

[**\OpenAPI\Client\Model\EventStreamSnapshotJsonInstantieJson**](../Model/EventStreamSnapshotJsonInstantieJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
