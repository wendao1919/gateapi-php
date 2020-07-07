# GateApi\DeliveryApi

All URIs are relative to *https://api.gateio.ws/api/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**cancelDeliveryOrder**](DeliveryApi.md#cancelDeliveryOrder) | **DELETE** /delivery/{settle}/orders/{order_id} | Cancel a single order
[**cancelDeliveryOrders**](DeliveryApi.md#cancelDeliveryOrders) | **DELETE** /delivery/{settle}/orders | Cancel all &#x60;open&#x60; orders matched
[**cancelPriceTriggeredDeliveryOrder**](DeliveryApi.md#cancelPriceTriggeredDeliveryOrder) | **DELETE** /delivery/{settle}/price_orders/{order_id} | Cancel a single order
[**cancelPriceTriggeredDeliveryOrderList**](DeliveryApi.md#cancelPriceTriggeredDeliveryOrderList) | **DELETE** /delivery/{settle}/price_orders | Cancel all open orders
[**createDeliveryOrder**](DeliveryApi.md#createDeliveryOrder) | **POST** /delivery/{settle}/orders | Create a futures order
[**createPriceTriggeredDeliveryOrder**](DeliveryApi.md#createPriceTriggeredDeliveryOrder) | **POST** /delivery/{settle}/price_orders | Create a price-triggered order
[**getDeliveryContract**](DeliveryApi.md#getDeliveryContract) | **GET** /delivery/{settle}/contracts/{contract} | Get a single contract
[**getDeliveryOrder**](DeliveryApi.md#getDeliveryOrder) | **GET** /delivery/{settle}/orders/{order_id} | Get a single order
[**getDeliveryPosition**](DeliveryApi.md#getDeliveryPosition) | **GET** /delivery/{settle}/positions/{contract} | Get single position
[**getMyDeliveryTrades**](DeliveryApi.md#getMyDeliveryTrades) | **GET** /delivery/{settle}/my_trades | List personal trading history
[**getPriceTriggeredDeliveryOrder**](DeliveryApi.md#getPriceTriggeredDeliveryOrder) | **GET** /delivery/{settle}/price_orders/{order_id} | Get a single order
[**listDeliveryAccountBook**](DeliveryApi.md#listDeliveryAccountBook) | **GET** /delivery/{settle}/account_book | Query account book
[**listDeliveryAccounts**](DeliveryApi.md#listDeliveryAccounts) | **GET** /delivery/{settle}/accounts | Query futures account
[**listDeliveryCandlesticks**](DeliveryApi.md#listDeliveryCandlesticks) | **GET** /delivery/{settle}/candlesticks | Get futures candlesticks
[**listDeliveryContracts**](DeliveryApi.md#listDeliveryContracts) | **GET** /delivery/{settle}/contracts | List all futures contracts
[**listDeliveryInsuranceLedger**](DeliveryApi.md#listDeliveryInsuranceLedger) | **GET** /delivery/{settle}/insurance | Futures insurance balance history
[**listDeliveryLiquidates**](DeliveryApi.md#listDeliveryLiquidates) | **GET** /delivery/{settle}/liquidates | List liquidation history
[**listDeliveryOrderBook**](DeliveryApi.md#listDeliveryOrderBook) | **GET** /delivery/{settle}/order_book | Futures order book
[**listDeliveryOrders**](DeliveryApi.md#listDeliveryOrders) | **GET** /delivery/{settle}/orders | List futures orders
[**listDeliveryPositionClose**](DeliveryApi.md#listDeliveryPositionClose) | **GET** /delivery/{settle}/position_close | List position close history
[**listDeliveryPositions**](DeliveryApi.md#listDeliveryPositions) | **GET** /delivery/{settle}/positions | List all positions of a user
[**listDeliverySettlements**](DeliveryApi.md#listDeliverySettlements) | **GET** /delivery/{settle}/settlements | List settlement history
[**listDeliveryTickers**](DeliveryApi.md#listDeliveryTickers) | **GET** /delivery/{settle}/tickers | List futures tickers
[**listDeliveryTrades**](DeliveryApi.md#listDeliveryTrades) | **GET** /delivery/{settle}/trades | Futures trading history
[**listPriceTriggeredDeliveryOrders**](DeliveryApi.md#listPriceTriggeredDeliveryOrders) | **GET** /delivery/{settle}/price_orders | List all auto orders
[**updateDeliveryPositionLeverage**](DeliveryApi.md#updateDeliveryPositionLeverage) | **POST** /delivery/{settle}/positions/{contract}/leverage | Update position leverage
[**updateDeliveryPositionMargin**](DeliveryApi.md#updateDeliveryPositionMargin) | **POST** /delivery/{settle}/positions/{contract}/margin | Update position margin
[**updateDeliveryPositionRiskLimit**](DeliveryApi.md#updateDeliveryPositionRiskLimit) | **POST** /delivery/{settle}/positions/{contract}/risk_limit | Update position risk limit


# **cancelDeliveryOrder**
> \GateApi\Model\FuturesOrder cancelDeliveryOrder($settle, $order_id)

Cancel a single order

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$order_id = '12345'; // string | ID returned on order successfully being created

try {
    $result = $apiInstance->cancelDeliveryOrder($settle, $order_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->cancelDeliveryOrder: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **order_id** | **string**| ID returned on order successfully being created |

### Return type

[**\GateApi\Model\FuturesOrder**](../Model/FuturesOrder.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **cancelDeliveryOrders**
> \GateApi\Model\FuturesOrder[] cancelDeliveryOrders($settle, $contract, $side)

Cancel all `open` orders matched

Zero-fill order cannot be retrieved 60 seconds after cancellation

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract
$side = 'ask'; // string | All bids or asks. Both included in not specified

try {
    $result = $apiInstance->cancelDeliveryOrders($settle, $contract, $side);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->cancelDeliveryOrders: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract |
 **side** | **string**| All bids or asks. Both included in not specified | [optional]

### Return type

[**\GateApi\Model\FuturesOrder[]**](../Model/FuturesOrder.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **cancelPriceTriggeredDeliveryOrder**
> \GateApi\Model\FuturesPriceTriggeredOrder cancelPriceTriggeredDeliveryOrder($settle, $order_id)

Cancel a single order

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$order_id = 'order_id_example'; // string | ID returned on order successfully being created

try {
    $result = $apiInstance->cancelPriceTriggeredDeliveryOrder($settle, $order_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->cancelPriceTriggeredDeliveryOrder: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **order_id** | **string**| ID returned on order successfully being created |

### Return type

[**\GateApi\Model\FuturesPriceTriggeredOrder**](../Model/FuturesPriceTriggeredOrder.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **cancelPriceTriggeredDeliveryOrderList**
> \GateApi\Model\FuturesPriceTriggeredOrder[] cancelPriceTriggeredDeliveryOrderList($settle, $contract)

Cancel all open orders

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USD'; // string | Futures contract

try {
    $result = $apiInstance->cancelPriceTriggeredDeliveryOrderList($settle, $contract);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->cancelPriceTriggeredDeliveryOrderList: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract |

### Return type

[**\GateApi\Model\FuturesPriceTriggeredOrder[]**](../Model/FuturesPriceTriggeredOrder.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **createDeliveryOrder**
> \GateApi\Model\FuturesOrder createDeliveryOrder($settle, $futures_order)

Create a futures order

Zero-fill order cannot be retrieved 60 seconds after cancellation

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$futures_order = new \GateApi\Model\FuturesOrder(); // \GateApi\Model\FuturesOrder | 

try {
    $result = $apiInstance->createDeliveryOrder($settle, $futures_order);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->createDeliveryOrder: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **futures_order** | [**\GateApi\Model\FuturesOrder**](../Model/FuturesOrder.md)|  |

### Return type

[**\GateApi\Model\FuturesOrder**](../Model/FuturesOrder.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **createPriceTriggeredDeliveryOrder**
> \GateApi\Model\TriggerOrderResponse createPriceTriggeredDeliveryOrder($settle, $futures_price_triggered_order)

Create a price-triggered order

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$futures_price_triggered_order = new \GateApi\Model\FuturesPriceTriggeredOrder(); // \GateApi\Model\FuturesPriceTriggeredOrder | 

try {
    $result = $apiInstance->createPriceTriggeredDeliveryOrder($settle, $futures_price_triggered_order);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->createPriceTriggeredDeliveryOrder: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **futures_price_triggered_order** | [**\GateApi\Model\FuturesPriceTriggeredOrder**](../Model/FuturesPriceTriggeredOrder.md)|  |

### Return type

[**\GateApi\Model\TriggerOrderResponse**](../Model/TriggerOrderResponse.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getDeliveryContract**
> \GateApi\Model\DeliveryContract getDeliveryContract($settle, $contract)

Get a single contract

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


$apiInstance = new GateApi\Api\DeliveryApi();
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract

try {
    $result = $apiInstance->getDeliveryContract($settle, $contract);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->getDeliveryContract: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract |

### Return type

[**\GateApi\Model\DeliveryContract**](../Model/DeliveryContract.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getDeliveryOrder**
> \GateApi\Model\FuturesOrder getDeliveryOrder($settle, $order_id)

Get a single order

Zero-fill order cannot be retrieved 60 seconds after cancellation

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$order_id = '12345'; // string | ID returned on order successfully being created

try {
    $result = $apiInstance->getDeliveryOrder($settle, $order_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->getDeliveryOrder: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **order_id** | **string**| ID returned on order successfully being created |

### Return type

[**\GateApi\Model\FuturesOrder**](../Model/FuturesOrder.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getDeliveryPosition**
> \GateApi\Model\Position getDeliveryPosition($settle, $contract)

Get single position

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract

try {
    $result = $apiInstance->getDeliveryPosition($settle, $contract);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->getDeliveryPosition: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract |

### Return type

[**\GateApi\Model\Position**](../Model/Position.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getMyDeliveryTrades**
> \GateApi\Model\MyFuturesTrade[] getMyDeliveryTrades($settle, $contract, $order, $limit, $offset, $last_id, $count_total)

List personal trading history

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract
$order = 12345; // int | Futures order ID, return related data only if specified
$limit = 100; // int | Maximum number of records returned in one list
$offset = 0; // int | List offset, starting from 0
$last_id = '12345'; // string | Specify list staring point using the `id` of last record in previous list-query results
$count_total = 0; // int | Whether to return total number matched. Default to 0(no return)

try {
    $result = $apiInstance->getMyDeliveryTrades($settle, $contract, $order, $limit, $offset, $last_id, $count_total);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->getMyDeliveryTrades: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract | [optional]
 **order** | **int**| Futures order ID, return related data only if specified | [optional]
 **limit** | **int**| Maximum number of records returned in one list | [optional] [default to 100]
 **offset** | **int**| List offset, starting from 0 | [optional] [default to 0]
 **last_id** | **string**| Specify list staring point using the &#x60;id&#x60; of last record in previous list-query results | [optional]
 **count_total** | **int**| Whether to return total number matched. Default to 0(no return) | [optional] [default to 0]

### Return type

[**\GateApi\Model\MyFuturesTrade[]**](../Model/MyFuturesTrade.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getPriceTriggeredDeliveryOrder**
> \GateApi\Model\FuturesPriceTriggeredOrder getPriceTriggeredDeliveryOrder($settle, $order_id)

Get a single order

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$order_id = 'order_id_example'; // string | ID returned on order successfully being created

try {
    $result = $apiInstance->getPriceTriggeredDeliveryOrder($settle, $order_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->getPriceTriggeredDeliveryOrder: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **order_id** | **string**| ID returned on order successfully being created |

### Return type

[**\GateApi\Model\FuturesPriceTriggeredOrder**](../Model/FuturesPriceTriggeredOrder.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listDeliveryAccountBook**
> \GateApi\Model\FuturesAccountBook[] listDeliveryAccountBook($settle, $limit, $from, $to, $type)

Query account book

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$limit = 100; // int | Maximum number of records returned in one list
$from = 1547706332; // int | Start timestamp
$to = 1547706332; // int | End timestamp
$type = 'dnw'; // string | Changing Type: - dnw: Deposit & Withdraw - pnl: Profit & Loss by reducing position - fee: Trading fee - refr: Referrer rebate - fund: Funding - point_dnw: POINT Deposit & Withdraw - point_fee: POINT Trading fee - point_refr: POINT Referrer rebate

try {
    $result = $apiInstance->listDeliveryAccountBook($settle, $limit, $from, $to, $type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->listDeliveryAccountBook: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **limit** | **int**| Maximum number of records returned in one list | [optional] [default to 100]
 **from** | **int**| Start timestamp | [optional]
 **to** | **int**| End timestamp | [optional]
 **type** | **string**| Changing Type: - dnw: Deposit &amp; Withdraw - pnl: Profit &amp; Loss by reducing position - fee: Trading fee - refr: Referrer rebate - fund: Funding - point_dnw: POINT Deposit &amp; Withdraw - point_fee: POINT Trading fee - point_refr: POINT Referrer rebate | [optional]

### Return type

[**\GateApi\Model\FuturesAccountBook[]**](../Model/FuturesAccountBook.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listDeliveryAccounts**
> \GateApi\Model\FuturesAccount listDeliveryAccounts($settle)

Query futures account

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency

try {
    $result = $apiInstance->listDeliveryAccounts($settle);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->listDeliveryAccounts: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |

### Return type

[**\GateApi\Model\FuturesAccount**](../Model/FuturesAccount.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listDeliveryCandlesticks**
> \GateApi\Model\FuturesCandlestick[] listDeliveryCandlesticks($settle, $contract, $from, $to, $limit, $interval)

Get futures candlesticks

Return specified contract candlesticks. If prefix `contract` with `mark_`, the contract's mark price candlesticks are returned; if prefix with `index_`, index price candlesticks will be returned.  Maximum of 2000 points are returned in one query. Be sure not to exceed the limit when specifying `from`, `to` and `interval`

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


$apiInstance = new GateApi\Api\DeliveryApi();
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract
$from = 1546905600; // float | Start time of candlesticks, formatted in Unix timestamp in seconds. Default to`to - 100 * interval` if not specified
$to = 1546935600; // float | End time of candlesticks, formatted in Unix timestamp in seconds. Default to current time
$limit = 100; // int | Maximum recent data points returned. `limit` is conflicted with `from` and `to`. If either `from` or `to` is specified, request will be rejected.
$interval = '5m'; // string | Interval time between data points

try {
    $result = $apiInstance->listDeliveryCandlesticks($settle, $contract, $from, $to, $limit, $interval);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->listDeliveryCandlesticks: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract |
 **from** | **float**| Start time of candlesticks, formatted in Unix timestamp in seconds. Default to&#x60;to - 100 * interval&#x60; if not specified | [optional]
 **to** | **float**| End time of candlesticks, formatted in Unix timestamp in seconds. Default to current time | [optional]
 **limit** | **int**| Maximum recent data points returned. &#x60;limit&#x60; is conflicted with &#x60;from&#x60; and &#x60;to&#x60;. If either &#x60;from&#x60; or &#x60;to&#x60; is specified, request will be rejected. | [optional] [default to 100]
 **interval** | **string**| Interval time between data points | [optional] [default to &#39;5m&#39;]

### Return type

[**\GateApi\Model\FuturesCandlestick[]**](../Model/FuturesCandlestick.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listDeliveryContracts**
> \GateApi\Model\DeliveryContract[] listDeliveryContracts($settle)

List all futures contracts

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


$apiInstance = new GateApi\Api\DeliveryApi();
$settle = 'usdt'; // string | Settle currency

try {
    $result = $apiInstance->listDeliveryContracts($settle);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->listDeliveryContracts: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |

### Return type

[**\GateApi\Model\DeliveryContract[]**](../Model/DeliveryContract.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listDeliveryInsuranceLedger**
> \GateApi\Model\InsuranceRecord[] listDeliveryInsuranceLedger($settle, $limit)

Futures insurance balance history

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


$apiInstance = new GateApi\Api\DeliveryApi();
$settle = 'usdt'; // string | Settle currency
$limit = 100; // int | Maximum number of records returned in one list

try {
    $result = $apiInstance->listDeliveryInsuranceLedger($settle, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->listDeliveryInsuranceLedger: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **limit** | **int**| Maximum number of records returned in one list | [optional] [default to 100]

### Return type

[**\GateApi\Model\InsuranceRecord[]**](../Model/InsuranceRecord.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listDeliveryLiquidates**
> \GateApi\Model\FuturesLiquidate[] listDeliveryLiquidates($settle, $contract, $limit, $at)

List liquidation history

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract
$limit = 100; // int | Maximum number of records returned in one list
$at = 0; // int | Specify a liquidation timestamp

try {
    $result = $apiInstance->listDeliveryLiquidates($settle, $contract, $limit, $at);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->listDeliveryLiquidates: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract | [optional]
 **limit** | **int**| Maximum number of records returned in one list | [optional] [default to 100]
 **at** | **int**| Specify a liquidation timestamp | [optional] [default to 0]

### Return type

[**\GateApi\Model\FuturesLiquidate[]**](../Model/FuturesLiquidate.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listDeliveryOrderBook**
> \GateApi\Model\FuturesOrderBook listDeliveryOrderBook($settle, $contract, $interval, $limit)

Futures order book

Bids will be sorted by price from high to low, while asks sorted reversely

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


$apiInstance = new GateApi\Api\DeliveryApi();
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract
$interval = '0'; // string | Order depth. 0 means no aggregation is applied. default to 0
$limit = 10; // int | Maximum number of order depth data in asks or bids

try {
    $result = $apiInstance->listDeliveryOrderBook($settle, $contract, $interval, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->listDeliveryOrderBook: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract |
 **interval** | **string**| Order depth. 0 means no aggregation is applied. default to 0 | [optional] [default to &#39;0&#39;]
 **limit** | **int**| Maximum number of order depth data in asks or bids | [optional] [default to 10]

### Return type

[**\GateApi\Model\FuturesOrderBook**](../Model/FuturesOrderBook.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listDeliveryOrders**
> \GateApi\Model\FuturesOrder[] listDeliveryOrders($settle, $status, $contract, $limit, $offset, $last_id, $count_total)

List futures orders

Zero-fill order cannot be retrieved 60 seconds after cancellation

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$status = 'open'; // string | List orders based on status
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract
$limit = 100; // int | Maximum number of records returned in one list
$offset = 0; // int | List offset, starting from 0
$last_id = '12345'; // string | Specify list staring point using the `id` of last record in previous list-query results
$count_total = 0; // int | Whether to return total number matched. Default to 0(no return)

try {
    $result = $apiInstance->listDeliveryOrders($settle, $status, $contract, $limit, $offset, $last_id, $count_total);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->listDeliveryOrders: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **status** | **string**| List orders based on status |
 **contract** | **string**| Futures contract | [optional]
 **limit** | **int**| Maximum number of records returned in one list | [optional] [default to 100]
 **offset** | **int**| List offset, starting from 0 | [optional] [default to 0]
 **last_id** | **string**| Specify list staring point using the &#x60;id&#x60; of last record in previous list-query results | [optional]
 **count_total** | **int**| Whether to return total number matched. Default to 0(no return) | [optional] [default to 0]

### Return type

[**\GateApi\Model\FuturesOrder[]**](../Model/FuturesOrder.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listDeliveryPositionClose**
> \GateApi\Model\PositionClose[] listDeliveryPositionClose($settle, $contract, $limit)

List position close history

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract
$limit = 100; // int | Maximum number of records returned in one list

try {
    $result = $apiInstance->listDeliveryPositionClose($settle, $contract, $limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->listDeliveryPositionClose: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract | [optional]
 **limit** | **int**| Maximum number of records returned in one list | [optional] [default to 100]

### Return type

[**\GateApi\Model\PositionClose[]**](../Model/PositionClose.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listDeliveryPositions**
> \GateApi\Model\Position[] listDeliveryPositions($settle)

List all positions of a user

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency

try {
    $result = $apiInstance->listDeliveryPositions($settle);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->listDeliveryPositions: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |

### Return type

[**\GateApi\Model\Position[]**](../Model/Position.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listDeliverySettlements**
> \GateApi\Model\DeliverySettlement[] listDeliverySettlements($settle, $contract, $limit, $at)

List settlement history

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract
$limit = 100; // int | Maximum number of records returned in one list
$at = 0; // int | Specify a settlement timestamp

try {
    $result = $apiInstance->listDeliverySettlements($settle, $contract, $limit, $at);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->listDeliverySettlements: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract | [optional]
 **limit** | **int**| Maximum number of records returned in one list | [optional] [default to 100]
 **at** | **int**| Specify a settlement timestamp | [optional] [default to 0]

### Return type

[**\GateApi\Model\DeliverySettlement[]**](../Model/DeliverySettlement.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listDeliveryTickers**
> \GateApi\Model\FuturesTicker[] listDeliveryTickers($settle, $contract)

List futures tickers

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


$apiInstance = new GateApi\Api\DeliveryApi();
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract

try {
    $result = $apiInstance->listDeliveryTickers($settle, $contract);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->listDeliveryTickers: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract | [optional]

### Return type

[**\GateApi\Model\FuturesTicker[]**](../Model/FuturesTicker.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listDeliveryTrades**
> \GateApi\Model\FuturesTrade[] listDeliveryTrades($settle, $contract, $limit, $last_id, $from, $to)

Futures trading history

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


$apiInstance = new GateApi\Api\DeliveryApi();
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract
$limit = 100; // int | Maximum number of records returned in one list
$last_id = '12345'; // string | Specify list staring point using the id of last record in previous list-query results  This parameter is deprecated. Use `from` and `to` instead to limit time range
$from = 1546905600; // float | Specify starting time in Unix seconds. If not specified, `to` and `limit` will be used to limit response items. If items between `from` and `to` are more than `limit`, only `limit` number will be returned.
$to = 1546935600; // float | Specify end time in Unix seconds, default to current time

try {
    $result = $apiInstance->listDeliveryTrades($settle, $contract, $limit, $last_id, $from, $to);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->listDeliveryTrades: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract |
 **limit** | **int**| Maximum number of records returned in one list | [optional] [default to 100]
 **last_id** | **string**| Specify list staring point using the id of last record in previous list-query results  This parameter is deprecated. Use &#x60;from&#x60; and &#x60;to&#x60; instead to limit time range | [optional]
 **from** | **float**| Specify starting time in Unix seconds. If not specified, &#x60;to&#x60; and &#x60;limit&#x60; will be used to limit response items. If items between &#x60;from&#x60; and &#x60;to&#x60; are more than &#x60;limit&#x60;, only &#x60;limit&#x60; number will be returned. | [optional]
 **to** | **float**| Specify end time in Unix seconds, default to current time | [optional]

### Return type

[**\GateApi\Model\FuturesTrade[]**](../Model/FuturesTrade.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listPriceTriggeredDeliveryOrders**
> \GateApi\Model\FuturesPriceTriggeredOrder[] listPriceTriggeredDeliveryOrders($settle, $status, $contract, $limit, $offset)

List all auto orders

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$status = 'status_example'; // string | List orders based on status
$contract = 'BTC_USD'; // string | Futures contract, return related data only if specified
$limit = 100; // int | Maximum number of records returned in one list
$offset = 0; // int | List offset, starting from 0

try {
    $result = $apiInstance->listPriceTriggeredDeliveryOrders($settle, $status, $contract, $limit, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->listPriceTriggeredDeliveryOrders: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **status** | **string**| List orders based on status |
 **contract** | **string**| Futures contract, return related data only if specified | [optional]
 **limit** | **int**| Maximum number of records returned in one list | [optional] [default to 100]
 **offset** | **int**| List offset, starting from 0 | [optional] [default to 0]

### Return type

[**\GateApi\Model\FuturesPriceTriggeredOrder[]**](../Model/FuturesPriceTriggeredOrder.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **updateDeliveryPositionLeverage**
> \GateApi\Model\Position updateDeliveryPositionLeverage($settle, $contract, $leverage)

Update position leverage

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract
$leverage = '10'; // string | New position leverage

try {
    $result = $apiInstance->updateDeliveryPositionLeverage($settle, $contract, $leverage);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->updateDeliveryPositionLeverage: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract |
 **leverage** | **string**| New position leverage |

### Return type

[**\GateApi\Model\Position**](../Model/Position.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **updateDeliveryPositionMargin**
> \GateApi\Model\Position updateDeliveryPositionMargin($settle, $contract, $change)

Update position margin

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract
$change = '0.01'; // string | Margin change. Use positive number to increase margin, negative number otherwise.

try {
    $result = $apiInstance->updateDeliveryPositionMargin($settle, $contract, $change);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->updateDeliveryPositionMargin: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract |
 **change** | **string**| Margin change. Use positive number to increase margin, negative number otherwise. |

### Return type

[**\GateApi\Model\Position**](../Model/Position.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **updateDeliveryPositionRiskLimit**
> \GateApi\Model\Position updateDeliveryPositionRiskLimit($settle, $contract, $risk_limit)

Update position risk limit

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$config = new GateApi\Configuration("YOUR_API_KEY", "YOUR_API_SECRET");
$apiInstance = new GateApi\Api\DeliveryApi(null, $config);
$settle = 'usdt'; // string | Settle currency
$contract = 'BTC_USDT_WEEKLY_20200703'; // string | Futures contract
$risk_limit = '10'; // string | New position risk limit

try {
    $result = $apiInstance->updateDeliveryPositionRiskLimit($settle, $contract, $risk_limit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DeliveryApi->updateDeliveryPositionRiskLimit: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **settle** | **string**| Settle currency |
 **contract** | **string**| Futures contract |
 **risk_limit** | **string**| New position risk limit |

### Return type

[**\GateApi\Model\Position**](../Model/Position.md)

### Authorization

Authentication with API key and secret is required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)
