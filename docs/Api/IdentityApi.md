# OpenAPI\Client\IdentityApi

All URIs are relative to https://api.ipdc.tni-vlaanderen.be, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getMe()**](IdentityApi.md#getMe) | **GET** /me | Get information about your user such as permissions and rate limits. |


## `getMe()`

```php
getMe(): \OpenAPI\Client\Model\MeJson
```

Get information about your user such as permissions and rate limits.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\IdentityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getMe();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling IdentityApi->getMe: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\OpenAPI\Client\Model\MeJson**](../Model/MeJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `*/*`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
