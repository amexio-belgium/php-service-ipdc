# OpenAPI\Client\CodelijstenApi

All URIs are relative to https://api.ipdc.tni-vlaanderen.be, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getCodelijst()**](CodelijstenApi.md#getCodelijst) | **GET** /api/codelijsten/{id} | Fetch a codelijst based on codelijst-id. |
| [**getCodelijstByParentId()**](CodelijstenApi.md#getCodelijstByParentId) | **GET** /api/codelijsten/{id}/{parentId} | Fetch a codelijst based on codelijst-id and parent-id. |


## `getCodelijst()`

```php
getCodelijst($id, $only_roots, $include_inactive): \OpenAPI\Client\Model\CodelijstJson
```

Fetch a codelijst based on codelijst-id.

**Permissions**: CODELIJST_READ

### Example

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

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **only_roots** | **bool**| Some codelijsten contain hierarchy. With this property you can control whether to only fetch the first level or the whole codelijst. | [optional] |
| **include_inactive** | **bool**| If true, the API will also return inactive nodes | [optional] |

### Return type

[**\OpenAPI\Client\Model\CodelijstJson**](../Model/CodelijstJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getCodelijstByParentId()`

```php
getCodelijstByParentId($id, $parent_id, $include_inactive): \OpenAPI\Client\Model\CodelijstJson
```

Fetch a codelijst based on codelijst-id and parent-id.

**Permissions**: CODELIJST_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\CodelijstenApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id = 'id_example'; // string
$parent_id = Reizen; // string | When a codelijst contains hierarchy, you can fetch all the nodes of a certain parentId by specifying the parentId. 'Reizen' is an example node in the codelijst 'your-europe' that has child nodes you can fetch.
$include_inactive = false; // bool | If true, the API will also return inactive nodes

try {
    $result = $apiInstance->getCodelijstByParentId($id, $parent_id, $include_inactive);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CodelijstenApi->getCodelijstByParentId: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **parent_id** | **string**| When a codelijst contains hierarchy, you can fetch all the nodes of a certain parentId by specifying the parentId. &#39;Reizen&#39; is an example node in the codelijst &#39;your-europe&#39; that has child nodes you can fetch. | |
| **include_inactive** | **bool**| If true, the API will also return inactive nodes | [optional] |

### Return type

[**\OpenAPI\Client\Model\CodelijstJson**](../Model/CodelijstJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
