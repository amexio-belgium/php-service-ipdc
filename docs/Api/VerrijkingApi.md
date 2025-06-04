# OpenAPI\Client\VerrijkingApi

All URIs are relative to https://api.ipdc.tni-vlaanderen.be, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**findById()**](VerrijkingApi.md#findById) | **GET** /verrijking/{caseId} | Fetch a verrijking case based on case-id. A Verrijking case contains all conditions with all possible options. |
| [**getVerrijkingVoorwaardeOptieUsage()**](VerrijkingApi.md#getVerrijkingVoorwaardeOptieUsage) | **GET** /verrijking/{caseId}/voorwaarde/{voorwaardeId}/optie/{optieId}/usage |  |
| [**getVerrijkingVoorwaardeUsage()**](VerrijkingApi.md#getVerrijkingVoorwaardeUsage) | **GET** /verrijking/{caseId}/voorwaarde/{voorwaardeId}/usage |  |


## `findById()`

```php
findById($case_id): \OpenAPI\Client\Model\VerrijkingCaseJson
```

Fetch a verrijking case based on case-id. A Verrijking case contains all conditions with all possible options.

**Permissions**: VERRIJKING_CASE_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\VerrijkingApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$case_id = 'case_id_example'; // string

try {
    $result = $apiInstance->findById($case_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VerrijkingApi->findById: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **case_id** | **string**|  | |

### Return type

[**\OpenAPI\Client\Model\VerrijkingCaseJson**](../Model/VerrijkingCaseJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `*/*`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getVerrijkingVoorwaardeOptieUsage()`

```php
getVerrijkingVoorwaardeOptieUsage($case_id, $voorwaarde_id, $optie_id): \OpenAPI\Client\Model\VerrijkingUsage
```



**Permissions**: VERRIJKING_CASE_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\VerrijkingApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$case_id = 'case_id_example'; // string
$voorwaarde_id = 'voorwaarde_id_example'; // string
$optie_id = 'optie_id_example'; // string

try {
    $result = $apiInstance->getVerrijkingVoorwaardeOptieUsage($case_id, $voorwaarde_id, $optie_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VerrijkingApi->getVerrijkingVoorwaardeOptieUsage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **case_id** | **string**|  | |
| **voorwaarde_id** | **string**|  | |
| **optie_id** | **string**|  | |

### Return type

[**\OpenAPI\Client\Model\VerrijkingUsage**](../Model/VerrijkingUsage.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `*/*`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getVerrijkingVoorwaardeUsage()`

```php
getVerrijkingVoorwaardeUsage($case_id, $voorwaarde_id): \OpenAPI\Client\Model\VerrijkingUsage
```



**Permissions**: VERRIJKING_CASE_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\VerrijkingApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$case_id = 'case_id_example'; // string
$voorwaarde_id = 'voorwaarde_id_example'; // string

try {
    $result = $apiInstance->getVerrijkingVoorwaardeUsage($case_id, $voorwaarde_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VerrijkingApi->getVerrijkingVoorwaardeUsage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **case_id** | **string**|  | |
| **voorwaarde_id** | **string**|  | |

### Return type

[**\OpenAPI\Client\Model\VerrijkingUsage**](../Model/VerrijkingUsage.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `*/*`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
