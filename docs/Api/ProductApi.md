# OpenAPI\Client\ProductApi

All URIs are relative to https://api.ipdc.tni-vlaanderen.be, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**findProductByIdOrProductnummer()**](ProductApi.md#findProductByIdOrProductnummer) | **GET** /id/product/{idOrProductnummer} | Fetch the details of a instantie or concept. Redirects to /doc/product/{idOrProductnummer}. |
| [**findProductPage()**](ProductApi.md#findProductPage) | **GET** /doc/product | Fetch product page. Filter by using requestparams. |
| [**findProductenByIdsOrProductnummers()**](ProductApi.md#findProductenByIdsOrProductnummers) | **GET** /doc/product/byIdsOrProductnummers/{ids} | Fetch the details of the producten. |
| [**getProduct()**](ProductApi.md#getProduct) | **GET** /doc/product/{idOrProductnummer} | Fetch the details of a instantie or concept |


## `findProductByIdOrProductnummer()`

```php
findProductByIdOrProductnummer($id_or_productnummer)
```

Fetch the details of a instantie or concept. Redirects to /doc/product/{idOrProductnummer}.

**Permissions**: PRODUCT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ProductApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id_or_productnummer = 'id_or_productnummer_example'; // string | Pass the id or the productnummer of the product to fetch

try {
    $apiInstance->findProductByIdOrProductnummer($id_or_productnummer);
} catch (Exception $e) {
    echo 'Exception when calling ProductApi->findProductByIdOrProductnummer: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id_or_productnummer** | **string**| Pass the id or the productnummer of the product to fetch | |

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

## `findProductPage()`

```php
findProductPage($page_index, $limit, $vertaling, $zoekterm, $gearchiveerd): \OpenAPI\Client\Model\HydraCollectionProductJson
```

Fetch product page. Filter by using requestparams.

**Permissions**: PRODUCT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ProductApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$page_index = 56; // int | Specifies the page the API needs to return. Default 0 (first page)
$limit = 56; // int | Specifies the amount of instances on one page.
$vertaling = 'vertaling_example'; // string | If specified, the API will only return instances of that language
$zoekterm = 'zoekterm_example'; // string | If specified, the API will only return instances where the name and/or description and/or search terms matches the value of the zoekterm.  If the 'vertalingen' queryparam is passed, we will only look for a match in instances for the specified language.
$gearchiveerd = True; // bool | If true, the API will also return concepts that have been archived

try {
    $result = $apiInstance->findProductPage($page_index, $limit, $vertaling, $zoekterm, $gearchiveerd);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProductApi->findProductPage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page_index** | **int**| Specifies the page the API needs to return. Default 0 (first page) | [optional] |
| **limit** | **int**| Specifies the amount of instances on one page. | [optional] |
| **vertaling** | **string**| If specified, the API will only return instances of that language | [optional] |
| **zoekterm** | **string**| If specified, the API will only return instances where the name and/or description and/or search terms matches the value of the zoekterm.  If the &#39;vertalingen&#39; queryparam is passed, we will only look for a match in instances for the specified language. | [optional] |
| **gearchiveerd** | **bool**| If true, the API will also return concepts that have been archived | [optional] |

### Return type

[**\OpenAPI\Client\Model\HydraCollectionProductJson**](../Model/HydraCollectionProductJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `findProductenByIdsOrProductnummers()`

```php
findProductenByIdsOrProductnummers($ids): \OpenAPI\Client\Model\ProductJson[]
```

Fetch the details of the producten.

**Permissions**: PRODUCT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ProductApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$ids = 'ids_example'; // string | Pass the product-ids or productnummers of the products to fetch. This should be encoded as a comma-separated list.

try {
    $result = $apiInstance->findProductenByIdsOrProductnummers($ids);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProductApi->findProductenByIdsOrProductnummers: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ids** | **string**| Pass the product-ids or productnummers of the products to fetch. This should be encoded as a comma-separated list. | |

### Return type

[**\OpenAPI\Client\Model\ProductJson[]**](../Model/ProductJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getProduct()`

```php
getProduct($id_or_productnummer): \OpenAPI\Client\Model\ProductJson
```

Fetch the details of a instantie or concept

**Permissions**: PRODUCT_READ

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\ProductApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$id_or_productnummer = 'id_or_productnummer_example'; // string | Pass the id or the productnummer of the product to fetch

try {
    $result = $apiInstance->getProduct($id_or_productnummer);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProductApi->getProduct: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id_or_productnummer** | **string**| Pass the id or the productnummer of the product to fetch | |

### Return type

[**\OpenAPI\Client\Model\ProductJson**](../Model/ProductJson.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/ld+json`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
