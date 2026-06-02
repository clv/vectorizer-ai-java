# AccountApi

All URIs are relative to *https://api.vectorizer.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getAccountStatus**](AccountApi.md#getAccountStatus) | **GET** /account | Get account status |
| [**getAccountStatusWithHttpInfo**](AccountApi.md#getAccountStatusWithHttpInfo) | **GET** /account | Get account status |



## getAccountStatus

> AccountStatusResponse getAccountStatus()

Get account status

Fetch the subscription state and remaining API credits for the authenticated account.

### Example

```java
// Import classes:
import ai.vectorizer.invoker.ApiClient;
import ai.vectorizer.invoker.ApiException;
import ai.vectorizer.invoker.Configuration;
import ai.vectorizer.invoker.auth.*;
import ai.vectorizer.invoker.models.*;
import ai.vectorizer.api.AccountApi;
import ai.vectorizer.api.AccountApi.*;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.vectorizer.ai/api/v1");
        
        // Configure HTTP basic authorization: basicAuth
        HttpBasicAuth basicAuth = (HttpBasicAuth) defaultClient.getAuthentication("basicAuth");
        basicAuth.setUsername("YOUR USERNAME");
        basicAuth.setPassword("YOUR PASSWORD");

        AccountApi apiInstance = new AccountApi(defaultClient);
        try {
            AccountStatusResponse result = apiInstance.getAccountStatus();
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling AccountApi#getAccountStatus");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AccountStatusResponse**](AccountStatusResponse.md)


### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Account status for the authenticated API credentials. |  -  |
| **400** | Invalid request parameters, image input, URL fetch, or Image Token. |  -  |
| **401** | Missing or invalid API credentials. |  * WWW-Authenticate - HTTP Basic authentication challenge returned with 401 responses. <br>  |
| **402** | The account does not have an API subscription, is past due, or is out of credits. |  -  |
| **413** | The uploaded image, fetched image, or requested PNG output is too large. |  -  |
| **429** | Rate limit exceeded. Back off before retrying. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |
| **500** | Unexpected internal error. |  -  |
| **503** | Temporary overload or internal processing timeout. Retry later. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |

## getAccountStatusWithHttpInfo

> ApiResponse<AccountStatusResponse> getAccountStatus getAccountStatusWithHttpInfo()

Get account status

Fetch the subscription state and remaining API credits for the authenticated account.

### Example

```java
// Import classes:
import ai.vectorizer.invoker.ApiClient;
import ai.vectorizer.invoker.ApiException;
import ai.vectorizer.invoker.ApiResponse;
import ai.vectorizer.invoker.Configuration;
import ai.vectorizer.invoker.auth.*;
import ai.vectorizer.invoker.models.*;
import ai.vectorizer.api.AccountApi;
import ai.vectorizer.api.AccountApi.*;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.vectorizer.ai/api/v1");
        
        // Configure HTTP basic authorization: basicAuth
        HttpBasicAuth basicAuth = (HttpBasicAuth) defaultClient.getAuthentication("basicAuth");
        basicAuth.setUsername("YOUR USERNAME");
        basicAuth.setPassword("YOUR PASSWORD");

        AccountApi apiInstance = new AccountApi(defaultClient);
        try {
            ApiResponse<AccountStatusResponse> response = apiInstance.getAccountStatusWithHttpInfo();
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling AccountApi#getAccountStatus");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

ApiResponse<[**AccountStatusResponse**](AccountStatusResponse.md)>


### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Account status for the authenticated API credentials. |  -  |
| **400** | Invalid request parameters, image input, URL fetch, or Image Token. |  -  |
| **401** | Missing or invalid API credentials. |  * WWW-Authenticate - HTTP Basic authentication challenge returned with 401 responses. <br>  |
| **402** | The account does not have an API subscription, is past due, or is out of credits. |  -  |
| **413** | The uploaded image, fetched image, or requested PNG output is too large. |  -  |
| **429** | Rate limit exceeded. Back off before retrying. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |
| **500** | Unexpected internal error. |  -  |
| **503** | Temporary overload or internal processing timeout. Retry later. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |

