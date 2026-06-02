# VectorizationApi

All URIs are relative to *https://api.vectorizer.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**postDelete**](VectorizationApi.md#postDelete) | **POST** /delete | Delete a retained image |
| [**postDeleteWithHttpInfo**](VectorizationApi.md#postDeleteWithHttpInfo) | **POST** /delete | Delete a retained image |
| [**postDownload**](VectorizationApi.md#postDownload) | **POST** /download | Download a retained result |
| [**postDownloadWithHttpInfo**](VectorizationApi.md#postDownloadWithHttpInfo) | **POST** /download | Download a retained result |
| [**postVectorize**](VectorizationApi.md#postVectorize) | **POST** /vectorize | Vectorize an image |
| [**postVectorizeWithHttpInfo**](VectorizationApi.md#postVectorizeWithHttpInfo) | **POST** /vectorize | Vectorize an image |



## postDelete

> DeleteImageResponse postDelete(postDeleteRequest)

Delete a retained image

Delete a retained image and result before its retention period expires.

### Example

```java
// Import classes:
import ai.vectorizer.invoker.ApiClient;
import ai.vectorizer.invoker.ApiException;
import ai.vectorizer.invoker.Configuration;
import ai.vectorizer.invoker.auth.*;
import ai.vectorizer.invoker.models.*;
import ai.vectorizer.api.VectorizationApi;
import ai.vectorizer.api.VectorizationApi.*;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.vectorizer.ai/api/v1");
        
        // Configure HTTP basic authorization: basicAuth
        HttpBasicAuth basicAuth = (HttpBasicAuth) defaultClient.getAuthentication("basicAuth");
        basicAuth.setUsername("YOUR USERNAME");
        basicAuth.setPassword("YOUR PASSWORD");

        VectorizationApi apiInstance = new VectorizationApi(defaultClient);
        String imageToken = "imageToken_example"; // String | Image Token to delete before its retention period expires.
        try {
            APIpostDeleteRequest request = APIpostDeleteRequest.newBuilder()
                .imageToken(imageToken)
                .build();
            DeleteImageResponse result = apiInstance.postDelete(request);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling VectorizationApi#postDelete");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters

|    Name      |    Type       | Description   |     Notes    |
|------------- | ------------- | ------------- | -------------|
| postDeleteRequest | [**APIpostDeleteRequest**](VectorizationApi.md#APIpostDeleteRequest)|-|-|

### Return type

[**DeleteImageResponse**](DeleteImageResponse.md)


### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Image Token was deleted. |  -  |
| **400** | Invalid request parameters, image input, URL fetch, or Image Token. |  -  |
| **401** | Missing or invalid API credentials. |  * WWW-Authenticate - HTTP Basic authentication challenge returned with 401 responses. <br>  |
| **402** | The account does not have an API subscription, is past due, or is out of credits. |  -  |
| **413** | The uploaded image, fetched image, or requested PNG output is too large. |  -  |
| **429** | Rate limit exceeded. Back off before retrying. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |
| **500** | Unexpected internal error. |  -  |
| **503** | Temporary overload or internal processing timeout. Retry later. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |

## postDeleteWithHttpInfo

> ApiResponse<DeleteImageResponse> postDelete postDeleteWithHttpInfo(postDeleteRequest)

Delete a retained image

Delete a retained image and result before its retention period expires.

### Example

```java
// Import classes:
import ai.vectorizer.invoker.ApiClient;
import ai.vectorizer.invoker.ApiException;
import ai.vectorizer.invoker.ApiResponse;
import ai.vectorizer.invoker.Configuration;
import ai.vectorizer.invoker.auth.*;
import ai.vectorizer.invoker.models.*;
import ai.vectorizer.api.VectorizationApi;
import ai.vectorizer.api.VectorizationApi.*;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.vectorizer.ai/api/v1");
        
        // Configure HTTP basic authorization: basicAuth
        HttpBasicAuth basicAuth = (HttpBasicAuth) defaultClient.getAuthentication("basicAuth");
        basicAuth.setUsername("YOUR USERNAME");
        basicAuth.setPassword("YOUR PASSWORD");

        VectorizationApi apiInstance = new VectorizationApi(defaultClient);
        String imageToken = "imageToken_example"; // String | Image Token to delete before its retention period expires.
        try {
            APIpostDeleteRequest request = APIpostDeleteRequest.newBuilder()
                .imageToken(imageToken)
                .build();
            ApiResponse<DeleteImageResponse> response = apiInstance.postDeleteWithHttpInfo(request);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling VectorizationApi#postDelete");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters

|    Name      |    Type       | Description   |     Notes    |
|------------- | ------------- | ------------- | -------------|
| postDeleteRequest | [**APIpostDeleteRequest**](VectorizationApi.md#APIpostDeleteRequest)|-|-|

### Return type

ApiResponse<[**DeleteImageResponse**](DeleteImageResponse.md)>


### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Image Token was deleted. |  -  |
| **400** | Invalid request parameters, image input, URL fetch, or Image Token. |  -  |
| **401** | Missing or invalid API credentials. |  * WWW-Authenticate - HTTP Basic authentication challenge returned with 401 responses. <br>  |
| **402** | The account does not have an API subscription, is past due, or is out of credits. |  -  |
| **413** | The uploaded image, fetched image, or requested PNG output is too large. |  -  |
| **429** | Rate limit exceeded. Back off before retrying. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |
| **500** | Unexpected internal error. |  -  |
| **503** | Temporary overload or internal processing timeout. Retry later. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |


<a id="APIpostDeleteRequest"></a>
## APIpostDeleteRequest
### Properties

|     Name      |    Type       | Description   |     Notes    |
| ------------- | ------------- | ------------- | -------------|
| **imageToken** | **String** | Image Token to delete before its retention period expires. | |



## postDownload

> File postDownload(postDownloadRequest)

Download a retained result

Download a production result from a retained Image Token, optionally changing output.file_format and other output options. Include receipt when downloading additional formats after upgrading a preview result.

### Example

```java
// Import classes:
import ai.vectorizer.invoker.ApiClient;
import ai.vectorizer.invoker.ApiException;
import ai.vectorizer.invoker.Configuration;
import ai.vectorizer.invoker.auth.*;
import ai.vectorizer.invoker.models.*;
import ai.vectorizer.api.VectorizationApi;
import ai.vectorizer.api.VectorizationApi.*;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.vectorizer.ai/api/v1");
        
        // Configure HTTP basic authorization: basicAuth
        HttpBasicAuth basicAuth = (HttpBasicAuth) defaultClient.getAuthentication("basicAuth");
        basicAuth.setUsername("YOUR USERNAME");
        basicAuth.setPassword("YOUR PASSWORD");

        VectorizationApi apiInstance = new VectorizationApi(defaultClient);
        String imageToken = "imageToken_example"; // String | Image Token returned from a vectorize request with policy.retention_days > 0.
        String receipt = "receipt_example"; // String | Receipt returned in the X-Receipt response header when upgrading a preview result to production. Include it when downloading additional formats from that upgraded preview.
        String outputFileFormat = "svg"; // String | Output file format to generate.
        String outputShapeStacking = "cutouts"; // String | Whether shapes are cut out of each other or stacked atop each other.
        String outputGroupBy = "none"; // String | Grouping of shapes in output.
        String outputDrawStyle = "fill_shapes"; // String | How shapes are rendered.
        Float outputStrokesStrokeWidth = 1F; // Float | Width of stroke for shape outlines (when enabled).
        Boolean outputStrokesNonScalingStroke = true; // Boolean | Use non-scaling strokes when drawing shape outlines.
        Boolean outputStrokesUseOverrideColor = false; // Boolean | Override shape color with a specific color.
        String outputStrokesOverrideColor = "#000000"; // String | Color value to override shape stroke color if enabled. Must be in '#RRGGBB' or 'rgba(r,g,b,a)' format.
        Boolean outputGapFillerEnabled = true; // Boolean | Enable filling small visual gaps caused by vector rendering artifacts.
        Boolean outputGapFillerNonScalingStroke = true; // Boolean | Use non-scaling strokes for gap filling.
        Boolean outputGapFillerClip = false; // Boolean | Clip gap filler strokes to shape bounds when stacking shapes.
        Float outputGapFillerStrokeWidth = 2F; // Float | Width of the gap filler strokes (in output units).
        Boolean outputParameterizedShapesFlatten = false; // Boolean | Whether to flatten detected circles, rectangles, and stars to curves.
        Float outputCurvesLineFitTolerance = 0.1F; // Float | Maximum allowed error when approximating curves with line segments.
        Boolean outputCurvesAllowedQuadraticBezier = true; // Boolean | Allow quadratic Bézier curves in the output.
        Boolean outputCurvesAllowedCubicBezier = true; // Boolean | Allow cubic Bézier curves in the output.
        Boolean outputCurvesAllowedCircularArc = true; // Boolean | Allow circular arcs in the output.
        Boolean outputCurvesAllowedEllipticalArc = true; // Boolean | Allow elliptical arcs in the output.
        String outputSvgVersion = "svg_1_0"; // String | SVG version to declare in the SVG output.
        Boolean outputSvgFixedSize = false; // Boolean | Whether to fix the SVG dimensions in the output file.
        Boolean outputSvgAdobeCompatibilityMode = false; // Boolean | Enable Illustrator compatibility by disabling unsupported SVG features.
        String outputPdfVersion = "PDF_1_4"; // String | PDF version to generate for PDF output.
        String outputPdfCompressionMode = "None"; // String | Compression method to apply to PDF output streams.
        String outputEpsVersion = "PS_3_0_EPSF_3_0"; // String | EPS format version for EPS output.
        String outputDxfCompatibilityLevel = "lines_only"; // String | Level of primitive support for DXF output.
        String outputBitmapAntiAliasingMode = "anti_aliased"; // String | Anti-aliasing mode for bitmap (PNG) output.
        Float outputSizeScale = 3.4F; // Float | Overall uniform scaling factor for the output image.
        Float outputSizeWidth = 3.4F; // Float | Output width, in the selected unit (see output.size.unit).
        Float outputSizeHeight = 3.4F; // Float | Output height, in the selected unit (see output.size.unit).
        String outputSizeUnit = "none"; // String | Measurement unit for output dimensions.
        String outputSizeAspectRatio = "preserve_inset"; // String | How to preserve or stretch aspect ratio.
        Float outputSizeAlignX = 0.5F; // Float | Horizontal alignment (0.0 = left, 0.5 = center, 1.0 = right) when aspect ratio is preserved.
        Float outputSizeAlignY = 0.5F; // Float | Vertical alignment (0.0 = top, 0.5 = center, 1.0 = bottom) when aspect ratio is preserved.
        Float outputSizeInputDpi = 3.4F; // Float | Override the detected DPI of the input image for size computations.
        Float outputSizeOutputDpi = 3.4F; // Float | DPI setting for the output image.
        try {
            APIpostDownloadRequest request = APIpostDownloadRequest.newBuilder()
                .imageToken(imageToken)
                .receipt(receipt)
                .outputFileFormat(outputFileFormat)
                .outputShapeStacking(outputShapeStacking)
                .outputGroupBy(outputGroupBy)
                .outputDrawStyle(outputDrawStyle)
                .outputStrokesStrokeWidth(outputStrokesStrokeWidth)
                .outputStrokesNonScalingStroke(outputStrokesNonScalingStroke)
                .outputStrokesUseOverrideColor(outputStrokesUseOverrideColor)
                .outputStrokesOverrideColor(outputStrokesOverrideColor)
                .outputGapFillerEnabled(outputGapFillerEnabled)
                .outputGapFillerNonScalingStroke(outputGapFillerNonScalingStroke)
                .outputGapFillerClip(outputGapFillerClip)
                .outputGapFillerStrokeWidth(outputGapFillerStrokeWidth)
                .outputParameterizedShapesFlatten(outputParameterizedShapesFlatten)
                .outputCurvesLineFitTolerance(outputCurvesLineFitTolerance)
                .outputCurvesAllowedQuadraticBezier(outputCurvesAllowedQuadraticBezier)
                .outputCurvesAllowedCubicBezier(outputCurvesAllowedCubicBezier)
                .outputCurvesAllowedCircularArc(outputCurvesAllowedCircularArc)
                .outputCurvesAllowedEllipticalArc(outputCurvesAllowedEllipticalArc)
                .outputSvgVersion(outputSvgVersion)
                .outputSvgFixedSize(outputSvgFixedSize)
                .outputSvgAdobeCompatibilityMode(outputSvgAdobeCompatibilityMode)
                .outputPdfVersion(outputPdfVersion)
                .outputPdfCompressionMode(outputPdfCompressionMode)
                .outputEpsVersion(outputEpsVersion)
                .outputDxfCompatibilityLevel(outputDxfCompatibilityLevel)
                .outputBitmapAntiAliasingMode(outputBitmapAntiAliasingMode)
                .outputSizeScale(outputSizeScale)
                .outputSizeWidth(outputSizeWidth)
                .outputSizeHeight(outputSizeHeight)
                .outputSizeUnit(outputSizeUnit)
                .outputSizeAspectRatio(outputSizeAspectRatio)
                .outputSizeAlignX(outputSizeAlignX)
                .outputSizeAlignY(outputSizeAlignY)
                .outputSizeInputDpi(outputSizeInputDpi)
                .outputSizeOutputDpi(outputSizeOutputDpi)
                .build();
            File result = apiInstance.postDownload(request);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling VectorizationApi#postDownload");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters

|    Name      |    Type       | Description   |     Notes    |
|------------- | ------------- | ------------- | -------------|
| postDownloadRequest | [**APIpostDownloadRequest**](VectorizationApi.md#APIpostDownloadRequest)|-|-|

### Return type

[**File**](File.md)


### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: image/svg+xml, application/postscript, application/pdf, application/dxf, image/png, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested output file. |  * Content-Disposition - Suggested filename for the generated result. <br>  * Content-Encoding - May be gzip for SVG, EPS, or DXF responses when the request allows gzip encoding. <br>  * X-Receipt - Returned when a preview Image Token is upgraded to a production result; use it for discounted additional format downloads. <br>  * X-Credits-Charged - Credits charged for the request. This is 0 for test requests. <br>  * X-Credits-Calculated - Returned for test requests to show the credits that would have been charged for the equivalent non-test request. <br>  |
| **400** | Invalid request parameters, image input, URL fetch, or Image Token. |  -  |
| **401** | Missing or invalid API credentials. |  * WWW-Authenticate - HTTP Basic authentication challenge returned with 401 responses. <br>  |
| **402** | The account does not have an API subscription, is past due, or is out of credits. |  -  |
| **413** | The uploaded image, fetched image, or requested PNG output is too large. |  -  |
| **429** | Rate limit exceeded. Back off before retrying. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |
| **500** | Unexpected internal error. |  -  |
| **503** | Temporary overload or internal processing timeout. Retry later. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |

## postDownloadWithHttpInfo

> ApiResponse<File> postDownload postDownloadWithHttpInfo(postDownloadRequest)

Download a retained result

Download a production result from a retained Image Token, optionally changing output.file_format and other output options. Include receipt when downloading additional formats after upgrading a preview result.

### Example

```java
// Import classes:
import ai.vectorizer.invoker.ApiClient;
import ai.vectorizer.invoker.ApiException;
import ai.vectorizer.invoker.ApiResponse;
import ai.vectorizer.invoker.Configuration;
import ai.vectorizer.invoker.auth.*;
import ai.vectorizer.invoker.models.*;
import ai.vectorizer.api.VectorizationApi;
import ai.vectorizer.api.VectorizationApi.*;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.vectorizer.ai/api/v1");
        
        // Configure HTTP basic authorization: basicAuth
        HttpBasicAuth basicAuth = (HttpBasicAuth) defaultClient.getAuthentication("basicAuth");
        basicAuth.setUsername("YOUR USERNAME");
        basicAuth.setPassword("YOUR PASSWORD");

        VectorizationApi apiInstance = new VectorizationApi(defaultClient);
        String imageToken = "imageToken_example"; // String | Image Token returned from a vectorize request with policy.retention_days > 0.
        String receipt = "receipt_example"; // String | Receipt returned in the X-Receipt response header when upgrading a preview result to production. Include it when downloading additional formats from that upgraded preview.
        String outputFileFormat = "svg"; // String | Output file format to generate.
        String outputShapeStacking = "cutouts"; // String | Whether shapes are cut out of each other or stacked atop each other.
        String outputGroupBy = "none"; // String | Grouping of shapes in output.
        String outputDrawStyle = "fill_shapes"; // String | How shapes are rendered.
        Float outputStrokesStrokeWidth = 1F; // Float | Width of stroke for shape outlines (when enabled).
        Boolean outputStrokesNonScalingStroke = true; // Boolean | Use non-scaling strokes when drawing shape outlines.
        Boolean outputStrokesUseOverrideColor = false; // Boolean | Override shape color with a specific color.
        String outputStrokesOverrideColor = "#000000"; // String | Color value to override shape stroke color if enabled. Must be in '#RRGGBB' or 'rgba(r,g,b,a)' format.
        Boolean outputGapFillerEnabled = true; // Boolean | Enable filling small visual gaps caused by vector rendering artifacts.
        Boolean outputGapFillerNonScalingStroke = true; // Boolean | Use non-scaling strokes for gap filling.
        Boolean outputGapFillerClip = false; // Boolean | Clip gap filler strokes to shape bounds when stacking shapes.
        Float outputGapFillerStrokeWidth = 2F; // Float | Width of the gap filler strokes (in output units).
        Boolean outputParameterizedShapesFlatten = false; // Boolean | Whether to flatten detected circles, rectangles, and stars to curves.
        Float outputCurvesLineFitTolerance = 0.1F; // Float | Maximum allowed error when approximating curves with line segments.
        Boolean outputCurvesAllowedQuadraticBezier = true; // Boolean | Allow quadratic Bézier curves in the output.
        Boolean outputCurvesAllowedCubicBezier = true; // Boolean | Allow cubic Bézier curves in the output.
        Boolean outputCurvesAllowedCircularArc = true; // Boolean | Allow circular arcs in the output.
        Boolean outputCurvesAllowedEllipticalArc = true; // Boolean | Allow elliptical arcs in the output.
        String outputSvgVersion = "svg_1_0"; // String | SVG version to declare in the SVG output.
        Boolean outputSvgFixedSize = false; // Boolean | Whether to fix the SVG dimensions in the output file.
        Boolean outputSvgAdobeCompatibilityMode = false; // Boolean | Enable Illustrator compatibility by disabling unsupported SVG features.
        String outputPdfVersion = "PDF_1_4"; // String | PDF version to generate for PDF output.
        String outputPdfCompressionMode = "None"; // String | Compression method to apply to PDF output streams.
        String outputEpsVersion = "PS_3_0_EPSF_3_0"; // String | EPS format version for EPS output.
        String outputDxfCompatibilityLevel = "lines_only"; // String | Level of primitive support for DXF output.
        String outputBitmapAntiAliasingMode = "anti_aliased"; // String | Anti-aliasing mode for bitmap (PNG) output.
        Float outputSizeScale = 3.4F; // Float | Overall uniform scaling factor for the output image.
        Float outputSizeWidth = 3.4F; // Float | Output width, in the selected unit (see output.size.unit).
        Float outputSizeHeight = 3.4F; // Float | Output height, in the selected unit (see output.size.unit).
        String outputSizeUnit = "none"; // String | Measurement unit for output dimensions.
        String outputSizeAspectRatio = "preserve_inset"; // String | How to preserve or stretch aspect ratio.
        Float outputSizeAlignX = 0.5F; // Float | Horizontal alignment (0.0 = left, 0.5 = center, 1.0 = right) when aspect ratio is preserved.
        Float outputSizeAlignY = 0.5F; // Float | Vertical alignment (0.0 = top, 0.5 = center, 1.0 = bottom) when aspect ratio is preserved.
        Float outputSizeInputDpi = 3.4F; // Float | Override the detected DPI of the input image for size computations.
        Float outputSizeOutputDpi = 3.4F; // Float | DPI setting for the output image.
        try {
            APIpostDownloadRequest request = APIpostDownloadRequest.newBuilder()
                .imageToken(imageToken)
                .receipt(receipt)
                .outputFileFormat(outputFileFormat)
                .outputShapeStacking(outputShapeStacking)
                .outputGroupBy(outputGroupBy)
                .outputDrawStyle(outputDrawStyle)
                .outputStrokesStrokeWidth(outputStrokesStrokeWidth)
                .outputStrokesNonScalingStroke(outputStrokesNonScalingStroke)
                .outputStrokesUseOverrideColor(outputStrokesUseOverrideColor)
                .outputStrokesOverrideColor(outputStrokesOverrideColor)
                .outputGapFillerEnabled(outputGapFillerEnabled)
                .outputGapFillerNonScalingStroke(outputGapFillerNonScalingStroke)
                .outputGapFillerClip(outputGapFillerClip)
                .outputGapFillerStrokeWidth(outputGapFillerStrokeWidth)
                .outputParameterizedShapesFlatten(outputParameterizedShapesFlatten)
                .outputCurvesLineFitTolerance(outputCurvesLineFitTolerance)
                .outputCurvesAllowedQuadraticBezier(outputCurvesAllowedQuadraticBezier)
                .outputCurvesAllowedCubicBezier(outputCurvesAllowedCubicBezier)
                .outputCurvesAllowedCircularArc(outputCurvesAllowedCircularArc)
                .outputCurvesAllowedEllipticalArc(outputCurvesAllowedEllipticalArc)
                .outputSvgVersion(outputSvgVersion)
                .outputSvgFixedSize(outputSvgFixedSize)
                .outputSvgAdobeCompatibilityMode(outputSvgAdobeCompatibilityMode)
                .outputPdfVersion(outputPdfVersion)
                .outputPdfCompressionMode(outputPdfCompressionMode)
                .outputEpsVersion(outputEpsVersion)
                .outputDxfCompatibilityLevel(outputDxfCompatibilityLevel)
                .outputBitmapAntiAliasingMode(outputBitmapAntiAliasingMode)
                .outputSizeScale(outputSizeScale)
                .outputSizeWidth(outputSizeWidth)
                .outputSizeHeight(outputSizeHeight)
                .outputSizeUnit(outputSizeUnit)
                .outputSizeAspectRatio(outputSizeAspectRatio)
                .outputSizeAlignX(outputSizeAlignX)
                .outputSizeAlignY(outputSizeAlignY)
                .outputSizeInputDpi(outputSizeInputDpi)
                .outputSizeOutputDpi(outputSizeOutputDpi)
                .build();
            ApiResponse<File> response = apiInstance.postDownloadWithHttpInfo(request);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling VectorizationApi#postDownload");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters

|    Name      |    Type       | Description   |     Notes    |
|------------- | ------------- | ------------- | -------------|
| postDownloadRequest | [**APIpostDownloadRequest**](VectorizationApi.md#APIpostDownloadRequest)|-|-|

### Return type

ApiResponse<[**File**](File.md)>


### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: image/svg+xml, application/postscript, application/pdf, application/dxf, image/png, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested output file. |  * Content-Disposition - Suggested filename for the generated result. <br>  * Content-Encoding - May be gzip for SVG, EPS, or DXF responses when the request allows gzip encoding. <br>  * X-Receipt - Returned when a preview Image Token is upgraded to a production result; use it for discounted additional format downloads. <br>  * X-Credits-Charged - Credits charged for the request. This is 0 for test requests. <br>  * X-Credits-Calculated - Returned for test requests to show the credits that would have been charged for the equivalent non-test request. <br>  |
| **400** | Invalid request parameters, image input, URL fetch, or Image Token. |  -  |
| **401** | Missing or invalid API credentials. |  * WWW-Authenticate - HTTP Basic authentication challenge returned with 401 responses. <br>  |
| **402** | The account does not have an API subscription, is past due, or is out of credits. |  -  |
| **413** | The uploaded image, fetched image, or requested PNG output is too large. |  -  |
| **429** | Rate limit exceeded. Back off before retrying. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |
| **500** | Unexpected internal error. |  -  |
| **503** | Temporary overload or internal processing timeout. Retry later. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |


<a id="APIpostDownloadRequest"></a>
## APIpostDownloadRequest
### Properties

|     Name      |    Type       | Description   |     Notes    |
| ------------- | ------------- | ------------- | -------------|
| **imageToken** | **String** | Image Token returned from a vectorize request with policy.retention_days &gt; 0. | |
| **receipt** | **String** | Receipt returned in the X-Receipt response header when upgrading a preview result to production. Include it when downloading additional formats from that upgraded preview. | [optional] |
| **outputFileFormat** | **String** | Output file format to generate. | [optional] [default to svg] [enum: svg, eps, pdf, dxf, png] |
| **outputShapeStacking** | **String** | Whether shapes are cut out of each other or stacked atop each other. | [optional] [default to cutouts] [enum: cutouts, stacked] |
| **outputGroupBy** | **String** | Grouping of shapes in output. | [optional] [default to none] [enum: none, color, parent, layer] |
| **outputDrawStyle** | **String** | How shapes are rendered. | [optional] [default to fill_shapes] [enum: fill_shapes, stroke_shapes, stroke_edges] |
| **outputStrokesStrokeWidth** | **Float** | Width of stroke for shape outlines (when enabled). | [optional] [default to 1] |
| **outputStrokesNonScalingStroke** | **Boolean** | Use non-scaling strokes when drawing shape outlines. | [optional] [default to true] |
| **outputStrokesUseOverrideColor** | **Boolean** | Override shape color with a specific color. | [optional] [default to false] |
| **outputStrokesOverrideColor** | **String** | Color value to override shape stroke color if enabled. Must be in &#39;#RRGGBB&#39; or &#39;rgba(r,g,b,a)&#39; format. | [optional] [default to #000000] |
| **outputGapFillerEnabled** | **Boolean** | Enable filling small visual gaps caused by vector rendering artifacts. | [optional] [default to true] |
| **outputGapFillerNonScalingStroke** | **Boolean** | Use non-scaling strokes for gap filling. | [optional] [default to true] |
| **outputGapFillerClip** | **Boolean** | Clip gap filler strokes to shape bounds when stacking shapes. | [optional] [default to false] |
| **outputGapFillerStrokeWidth** | **Float** | Width of the gap filler strokes (in output units). | [optional] [default to 2] |
| **outputParameterizedShapesFlatten** | **Boolean** | Whether to flatten detected circles, rectangles, and stars to curves. | [optional] [default to false] |
| **outputCurvesLineFitTolerance** | **Float** | Maximum allowed error when approximating curves with line segments. | [optional] [default to 0.1] |
| **outputCurvesAllowedQuadraticBezier** | **Boolean** | Allow quadratic Bézier curves in the output. | [optional] [default to true] |
| **outputCurvesAllowedCubicBezier** | **Boolean** | Allow cubic Bézier curves in the output. | [optional] [default to true] |
| **outputCurvesAllowedCircularArc** | **Boolean** | Allow circular arcs in the output. | [optional] [default to true] |
| **outputCurvesAllowedEllipticalArc** | **Boolean** | Allow elliptical arcs in the output. | [optional] [default to true] |
| **outputSvgVersion** | **String** | SVG version to declare in the SVG output. | [optional] [default to svg_1_1] [enum: svg_1_0, svg_1_1, svg_tiny_1_2] |
| **outputSvgFixedSize** | **Boolean** | Whether to fix the SVG dimensions in the output file. | [optional] [default to false] |
| **outputSvgAdobeCompatibilityMode** | **Boolean** | Enable Illustrator compatibility by disabling unsupported SVG features. | [optional] [default to false] |
| **outputPdfVersion** | **String** | PDF version to generate for PDF output. | [optional] [default to PDF_1_4] [enum: PDF_1_4] |
| **outputPdfCompressionMode** | **String** | Compression method to apply to PDF output streams. | [optional] [default to Deflate] [enum: None, Deflate] |
| **outputEpsVersion** | **String** | EPS format version for EPS output. | [optional] [default to PS_3_0_EPSF_3_0] [enum: PS_3_0_EPSF_3_0] |
| **outputDxfCompatibilityLevel** | **String** | Level of primitive support for DXF output. | [optional] [default to lines_and_arcs] [enum: lines_only, lines_and_arcs, lines_arcs_and_splines] |
| **outputBitmapAntiAliasingMode** | **String** | Anti-aliasing mode for bitmap (PNG) output. | [optional] [default to anti_aliased] [enum: anti_aliased, aliased] |
| **outputSizeScale** | **Float** | Overall uniform scaling factor for the output image. | [optional] |
| **outputSizeWidth** | **Float** | Output width, in the selected unit (see output.size.unit). | [optional] |
| **outputSizeHeight** | **Float** | Output height, in the selected unit (see output.size.unit). | [optional] |
| **outputSizeUnit** | **String** | Measurement unit for output dimensions. | [optional] [default to none] [enum: none, px, pt, in, cm, mm] |
| **outputSizeAspectRatio** | **String** | How to preserve or stretch aspect ratio. | [optional] [default to preserve_inset] [enum: preserve_inset, preserve_overflow, stretch] |
| **outputSizeAlignX** | **Float** | Horizontal alignment (0.0 &#x3D; left, 0.5 &#x3D; center, 1.0 &#x3D; right) when aspect ratio is preserved. | [optional] [default to 0.5] |
| **outputSizeAlignY** | **Float** | Vertical alignment (0.0 &#x3D; top, 0.5 &#x3D; center, 1.0 &#x3D; bottom) when aspect ratio is preserved. | [optional] [default to 0.5] |
| **outputSizeInputDpi** | **Float** | Override the detected DPI of the input image for size computations. | [optional] |
| **outputSizeOutputDpi** | **Float** | DPI setting for the output image. | [optional] |



## postVectorize

> File postVectorize(postVectorizeRequest)

Vectorize an image

Submit exactly one image source as multipart form data: image, image.url, image.base64, or image.token. The response body is the generated SVG, EPS, PDF, DXF, or PNG file selected by output.file_format. Clients should allow an idle timeout of at least 180 seconds.

### Example

```java
// Import classes:
import ai.vectorizer.invoker.ApiClient;
import ai.vectorizer.invoker.ApiException;
import ai.vectorizer.invoker.Configuration;
import ai.vectorizer.invoker.auth.*;
import ai.vectorizer.invoker.models.*;
import ai.vectorizer.api.VectorizationApi;
import ai.vectorizer.api.VectorizationApi.*;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.vectorizer.ai/api/v1");
        
        // Configure HTTP basic authorization: basicAuth
        HttpBasicAuth basicAuth = (HttpBasicAuth) defaultClient.getAuthentication("basicAuth");
        basicAuth.setUsername("YOUR USERNAME");
        basicAuth.setPassword("YOUR PASSWORD");

        VectorizationApi apiInstance = new VectorizationApi(defaultClient);
        File image = new File("/path/to/file"); // File | Binary file upload of the image to vectorize. Accepts .bmp, .gif, .jpeg, .png, or .tiff files.
        URI imageUrl = new URI(); // URI | URL to fetch the input image from for vectorization.
        byte[] imageBase64 = null; // byte[] | Base64-encoded string of the input image. Maximum size 1 megabyte.
        String imageToken = "imageToken_example"; // String | An Image Token returned from an earlier vectorization call with policy.retention_days > 0.
        String mode = "production"; // String | Mode of operation, useful during integration work.
        Integer inputMaxPixels = 2097252; // Integer | Maximum input image size (width × height in pixels) before resizing.
        Integer policyRetentionDays = 0; // Integer | Number of days to retain the uploaded image and its results for re-use.
        Integer processingMaxColors = 0; // Integer | Maximum number of colors allowed in the vectorization result. 0 means unlimited.
        Float processingShapesMinAreaPx = 0.125F; // Float | Minimum shape area (in pixels) to keep in the result; smaller shapes are discarded.
        String processingPalette = "processingPalette_example"; // String | Palette remapping and color control, using '[color][-> remapped][~ tolerance];' format.
        String processingColorProfileInput = "ignore"; // String | How to handle ICC profiles embedded in input images.
        String processingColorProfileOutput = "ignore"; // String | ICC profile behavior for output files: preserve, ignore.
        Boolean processingParameterizedShapesEllipseGeneralEnabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesEllipseCircleEnabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesTriangleGeneralEnabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesTriangleIsoscelesEnabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesQuadrilateralGeneralEnabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesQuadrilateralRectangleEnabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesQuadrilateralBulletEnabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesStarN3Enabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesStarN4Enabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesStarN5Enabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesStarN6Enabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        String outputFileFormat = "svg"; // String | Output file format to generate.
        String outputShapeStacking = "cutouts"; // String | Whether shapes are cut out of each other or stacked atop each other.
        String outputGroupBy = "none"; // String | Grouping of shapes in output.
        String outputDrawStyle = "fill_shapes"; // String | How shapes are rendered.
        Float outputStrokesStrokeWidth = 1F; // Float | Width of stroke for shape outlines (when enabled).
        Boolean outputStrokesNonScalingStroke = true; // Boolean | Use non-scaling strokes when drawing shape outlines.
        Boolean outputStrokesUseOverrideColor = false; // Boolean | Override shape color with a specific color.
        String outputStrokesOverrideColor = "#000000"; // String | Color value to override shape stroke color if enabled. Must be in '#RRGGBB' or 'rgba(r,g,b,a)' format.
        Boolean outputGapFillerEnabled = true; // Boolean | Enable filling small visual gaps caused by vector rendering artifacts.
        Boolean outputGapFillerNonScalingStroke = true; // Boolean | Use non-scaling strokes for gap filling.
        Boolean outputGapFillerClip = false; // Boolean | Clip gap filler strokes to shape bounds when stacking shapes.
        Float outputGapFillerStrokeWidth = 2F; // Float | Width of the gap filler strokes (in output units).
        Boolean outputParameterizedShapesFlatten = false; // Boolean | Whether to flatten detected circles, rectangles, and stars to curves.
        Float outputCurvesLineFitTolerance = 0.1F; // Float | Maximum allowed error when approximating curves with line segments.
        Boolean outputCurvesAllowedQuadraticBezier = true; // Boolean | Allow quadratic Bézier curves in the output.
        Boolean outputCurvesAllowedCubicBezier = true; // Boolean | Allow cubic Bézier curves in the output.
        Boolean outputCurvesAllowedCircularArc = true; // Boolean | Allow circular arcs in the output.
        Boolean outputCurvesAllowedEllipticalArc = true; // Boolean | Allow elliptical arcs in the output.
        String outputSvgVersion = "svg_1_0"; // String | SVG version to declare in the SVG output.
        Boolean outputSvgFixedSize = false; // Boolean | Whether to fix the SVG dimensions in the output file.
        Boolean outputSvgAdobeCompatibilityMode = false; // Boolean | Enable Illustrator compatibility by disabling unsupported SVG features.
        String outputPdfVersion = "PDF_1_4"; // String | PDF version to generate for PDF output.
        String outputPdfCompressionMode = "None"; // String | Compression method to apply to PDF output streams.
        String outputEpsVersion = "PS_3_0_EPSF_3_0"; // String | EPS format version for EPS output.
        String outputDxfCompatibilityLevel = "lines_only"; // String | Level of primitive support for DXF output.
        String outputBitmapAntiAliasingMode = "anti_aliased"; // String | Anti-aliasing mode for bitmap (PNG) output.
        Float outputSizeScale = 3.4F; // Float | Overall uniform scaling factor for the output image.
        Float outputSizeWidth = 3.4F; // Float | Output width, in the selected unit (see output.size.unit).
        Float outputSizeHeight = 3.4F; // Float | Output height, in the selected unit (see output.size.unit).
        String outputSizeUnit = "none"; // String | Measurement unit for output dimensions.
        String outputSizeAspectRatio = "preserve_inset"; // String | How to preserve or stretch aspect ratio.
        Float outputSizeAlignX = 0.5F; // Float | Horizontal alignment (0.0 = left, 0.5 = center, 1.0 = right) when aspect ratio is preserved.
        Float outputSizeAlignY = 0.5F; // Float | Vertical alignment (0.0 = top, 0.5 = center, 1.0 = bottom) when aspect ratio is preserved.
        Float outputSizeInputDpi = 3.4F; // Float | Override the detected DPI of the input image for size computations.
        Float outputSizeOutputDpi = 3.4F; // Float | DPI setting for the output image.
        try {
            APIpostVectorizeRequest request = APIpostVectorizeRequest.newBuilder()
                .image(image)
                .imageUrl(imageUrl)
                .imageBase64(imageBase64)
                .imageToken(imageToken)
                .mode(mode)
                .inputMaxPixels(inputMaxPixels)
                .policyRetentionDays(policyRetentionDays)
                .processingMaxColors(processingMaxColors)
                .processingShapesMinAreaPx(processingShapesMinAreaPx)
                .processingPalette(processingPalette)
                .processingColorProfileInput(processingColorProfileInput)
                .processingColorProfileOutput(processingColorProfileOutput)
                .processingParameterizedShapesEllipseGeneralEnabled(processingParameterizedShapesEllipseGeneralEnabled)
                .processingParameterizedShapesEllipseCircleEnabled(processingParameterizedShapesEllipseCircleEnabled)
                .processingParameterizedShapesTriangleGeneralEnabled(processingParameterizedShapesTriangleGeneralEnabled)
                .processingParameterizedShapesTriangleIsoscelesEnabled(processingParameterizedShapesTriangleIsoscelesEnabled)
                .processingParameterizedShapesQuadrilateralGeneralEnabled(processingParameterizedShapesQuadrilateralGeneralEnabled)
                .processingParameterizedShapesQuadrilateralRectangleEnabled(processingParameterizedShapesQuadrilateralRectangleEnabled)
                .processingParameterizedShapesQuadrilateralBulletEnabled(processingParameterizedShapesQuadrilateralBulletEnabled)
                .processingParameterizedShapesStarN3Enabled(processingParameterizedShapesStarN3Enabled)
                .processingParameterizedShapesStarN4Enabled(processingParameterizedShapesStarN4Enabled)
                .processingParameterizedShapesStarN5Enabled(processingParameterizedShapesStarN5Enabled)
                .processingParameterizedShapesStarN6Enabled(processingParameterizedShapesStarN6Enabled)
                .outputFileFormat(outputFileFormat)
                .outputShapeStacking(outputShapeStacking)
                .outputGroupBy(outputGroupBy)
                .outputDrawStyle(outputDrawStyle)
                .outputStrokesStrokeWidth(outputStrokesStrokeWidth)
                .outputStrokesNonScalingStroke(outputStrokesNonScalingStroke)
                .outputStrokesUseOverrideColor(outputStrokesUseOverrideColor)
                .outputStrokesOverrideColor(outputStrokesOverrideColor)
                .outputGapFillerEnabled(outputGapFillerEnabled)
                .outputGapFillerNonScalingStroke(outputGapFillerNonScalingStroke)
                .outputGapFillerClip(outputGapFillerClip)
                .outputGapFillerStrokeWidth(outputGapFillerStrokeWidth)
                .outputParameterizedShapesFlatten(outputParameterizedShapesFlatten)
                .outputCurvesLineFitTolerance(outputCurvesLineFitTolerance)
                .outputCurvesAllowedQuadraticBezier(outputCurvesAllowedQuadraticBezier)
                .outputCurvesAllowedCubicBezier(outputCurvesAllowedCubicBezier)
                .outputCurvesAllowedCircularArc(outputCurvesAllowedCircularArc)
                .outputCurvesAllowedEllipticalArc(outputCurvesAllowedEllipticalArc)
                .outputSvgVersion(outputSvgVersion)
                .outputSvgFixedSize(outputSvgFixedSize)
                .outputSvgAdobeCompatibilityMode(outputSvgAdobeCompatibilityMode)
                .outputPdfVersion(outputPdfVersion)
                .outputPdfCompressionMode(outputPdfCompressionMode)
                .outputEpsVersion(outputEpsVersion)
                .outputDxfCompatibilityLevel(outputDxfCompatibilityLevel)
                .outputBitmapAntiAliasingMode(outputBitmapAntiAliasingMode)
                .outputSizeScale(outputSizeScale)
                .outputSizeWidth(outputSizeWidth)
                .outputSizeHeight(outputSizeHeight)
                .outputSizeUnit(outputSizeUnit)
                .outputSizeAspectRatio(outputSizeAspectRatio)
                .outputSizeAlignX(outputSizeAlignX)
                .outputSizeAlignY(outputSizeAlignY)
                .outputSizeInputDpi(outputSizeInputDpi)
                .outputSizeOutputDpi(outputSizeOutputDpi)
                .build();
            File result = apiInstance.postVectorize(request);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling VectorizationApi#postVectorize");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters

|    Name      |    Type       | Description   |     Notes    |
|------------- | ------------- | ------------- | -------------|
| postVectorizeRequest | [**APIpostVectorizeRequest**](VectorizationApi.md#APIpostVectorizeRequest)|-|-|

### Return type

[**File**](File.md)


### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: image/svg+xml, application/postscript, application/pdf, application/dxf, image/png, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The vectorized image file. |  * Content-Disposition - Suggested filename for the generated result. <br>  * Content-Encoding - May be gzip for SVG, EPS, or DXF responses when the request allows gzip encoding. <br>  * X-Image-Token - Returned by vectorize when policy.retention_days is greater than 0. <br>  * X-Credits-Charged - Credits charged for the request. This is 0 for test requests. <br>  * X-Credits-Calculated - Returned for test requests to show the credits that would have been charged for the equivalent non-test request. <br>  |
| **400** | Invalid request parameters, image input, URL fetch, or Image Token. |  -  |
| **401** | Missing or invalid API credentials. |  * WWW-Authenticate - HTTP Basic authentication challenge returned with 401 responses. <br>  |
| **402** | The account does not have an API subscription, is past due, or is out of credits. |  -  |
| **413** | The uploaded image, fetched image, or requested PNG output is too large. |  -  |
| **429** | Rate limit exceeded. Back off before retrying. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |
| **500** | Unexpected internal error. |  -  |
| **503** | Temporary overload or internal processing timeout. Retry later. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |

## postVectorizeWithHttpInfo

> ApiResponse<File> postVectorize postVectorizeWithHttpInfo(postVectorizeRequest)

Vectorize an image

Submit exactly one image source as multipart form data: image, image.url, image.base64, or image.token. The response body is the generated SVG, EPS, PDF, DXF, or PNG file selected by output.file_format. Clients should allow an idle timeout of at least 180 seconds.

### Example

```java
// Import classes:
import ai.vectorizer.invoker.ApiClient;
import ai.vectorizer.invoker.ApiException;
import ai.vectorizer.invoker.ApiResponse;
import ai.vectorizer.invoker.Configuration;
import ai.vectorizer.invoker.auth.*;
import ai.vectorizer.invoker.models.*;
import ai.vectorizer.api.VectorizationApi;
import ai.vectorizer.api.VectorizationApi.*;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.vectorizer.ai/api/v1");
        
        // Configure HTTP basic authorization: basicAuth
        HttpBasicAuth basicAuth = (HttpBasicAuth) defaultClient.getAuthentication("basicAuth");
        basicAuth.setUsername("YOUR USERNAME");
        basicAuth.setPassword("YOUR PASSWORD");

        VectorizationApi apiInstance = new VectorizationApi(defaultClient);
        File image = new File("/path/to/file"); // File | Binary file upload of the image to vectorize. Accepts .bmp, .gif, .jpeg, .png, or .tiff files.
        URI imageUrl = new URI(); // URI | URL to fetch the input image from for vectorization.
        byte[] imageBase64 = null; // byte[] | Base64-encoded string of the input image. Maximum size 1 megabyte.
        String imageToken = "imageToken_example"; // String | An Image Token returned from an earlier vectorization call with policy.retention_days > 0.
        String mode = "production"; // String | Mode of operation, useful during integration work.
        Integer inputMaxPixels = 2097252; // Integer | Maximum input image size (width × height in pixels) before resizing.
        Integer policyRetentionDays = 0; // Integer | Number of days to retain the uploaded image and its results for re-use.
        Integer processingMaxColors = 0; // Integer | Maximum number of colors allowed in the vectorization result. 0 means unlimited.
        Float processingShapesMinAreaPx = 0.125F; // Float | Minimum shape area (in pixels) to keep in the result; smaller shapes are discarded.
        String processingPalette = "processingPalette_example"; // String | Palette remapping and color control, using '[color][-> remapped][~ tolerance];' format.
        String processingColorProfileInput = "ignore"; // String | How to handle ICC profiles embedded in input images.
        String processingColorProfileOutput = "ignore"; // String | ICC profile behavior for output files: preserve, ignore.
        Boolean processingParameterizedShapesEllipseGeneralEnabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesEllipseCircleEnabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesTriangleGeneralEnabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesTriangleIsoscelesEnabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesQuadrilateralGeneralEnabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesQuadrilateralRectangleEnabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesQuadrilateralBulletEnabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesStarN3Enabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesStarN4Enabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesStarN5Enabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        Boolean processingParameterizedShapesStarN6Enabled = true; // Boolean | Enable detection and parameterization of this parameterized shape type.
        String outputFileFormat = "svg"; // String | Output file format to generate.
        String outputShapeStacking = "cutouts"; // String | Whether shapes are cut out of each other or stacked atop each other.
        String outputGroupBy = "none"; // String | Grouping of shapes in output.
        String outputDrawStyle = "fill_shapes"; // String | How shapes are rendered.
        Float outputStrokesStrokeWidth = 1F; // Float | Width of stroke for shape outlines (when enabled).
        Boolean outputStrokesNonScalingStroke = true; // Boolean | Use non-scaling strokes when drawing shape outlines.
        Boolean outputStrokesUseOverrideColor = false; // Boolean | Override shape color with a specific color.
        String outputStrokesOverrideColor = "#000000"; // String | Color value to override shape stroke color if enabled. Must be in '#RRGGBB' or 'rgba(r,g,b,a)' format.
        Boolean outputGapFillerEnabled = true; // Boolean | Enable filling small visual gaps caused by vector rendering artifacts.
        Boolean outputGapFillerNonScalingStroke = true; // Boolean | Use non-scaling strokes for gap filling.
        Boolean outputGapFillerClip = false; // Boolean | Clip gap filler strokes to shape bounds when stacking shapes.
        Float outputGapFillerStrokeWidth = 2F; // Float | Width of the gap filler strokes (in output units).
        Boolean outputParameterizedShapesFlatten = false; // Boolean | Whether to flatten detected circles, rectangles, and stars to curves.
        Float outputCurvesLineFitTolerance = 0.1F; // Float | Maximum allowed error when approximating curves with line segments.
        Boolean outputCurvesAllowedQuadraticBezier = true; // Boolean | Allow quadratic Bézier curves in the output.
        Boolean outputCurvesAllowedCubicBezier = true; // Boolean | Allow cubic Bézier curves in the output.
        Boolean outputCurvesAllowedCircularArc = true; // Boolean | Allow circular arcs in the output.
        Boolean outputCurvesAllowedEllipticalArc = true; // Boolean | Allow elliptical arcs in the output.
        String outputSvgVersion = "svg_1_0"; // String | SVG version to declare in the SVG output.
        Boolean outputSvgFixedSize = false; // Boolean | Whether to fix the SVG dimensions in the output file.
        Boolean outputSvgAdobeCompatibilityMode = false; // Boolean | Enable Illustrator compatibility by disabling unsupported SVG features.
        String outputPdfVersion = "PDF_1_4"; // String | PDF version to generate for PDF output.
        String outputPdfCompressionMode = "None"; // String | Compression method to apply to PDF output streams.
        String outputEpsVersion = "PS_3_0_EPSF_3_0"; // String | EPS format version for EPS output.
        String outputDxfCompatibilityLevel = "lines_only"; // String | Level of primitive support for DXF output.
        String outputBitmapAntiAliasingMode = "anti_aliased"; // String | Anti-aliasing mode for bitmap (PNG) output.
        Float outputSizeScale = 3.4F; // Float | Overall uniform scaling factor for the output image.
        Float outputSizeWidth = 3.4F; // Float | Output width, in the selected unit (see output.size.unit).
        Float outputSizeHeight = 3.4F; // Float | Output height, in the selected unit (see output.size.unit).
        String outputSizeUnit = "none"; // String | Measurement unit for output dimensions.
        String outputSizeAspectRatio = "preserve_inset"; // String | How to preserve or stretch aspect ratio.
        Float outputSizeAlignX = 0.5F; // Float | Horizontal alignment (0.0 = left, 0.5 = center, 1.0 = right) when aspect ratio is preserved.
        Float outputSizeAlignY = 0.5F; // Float | Vertical alignment (0.0 = top, 0.5 = center, 1.0 = bottom) when aspect ratio is preserved.
        Float outputSizeInputDpi = 3.4F; // Float | Override the detected DPI of the input image for size computations.
        Float outputSizeOutputDpi = 3.4F; // Float | DPI setting for the output image.
        try {
            APIpostVectorizeRequest request = APIpostVectorizeRequest.newBuilder()
                .image(image)
                .imageUrl(imageUrl)
                .imageBase64(imageBase64)
                .imageToken(imageToken)
                .mode(mode)
                .inputMaxPixels(inputMaxPixels)
                .policyRetentionDays(policyRetentionDays)
                .processingMaxColors(processingMaxColors)
                .processingShapesMinAreaPx(processingShapesMinAreaPx)
                .processingPalette(processingPalette)
                .processingColorProfileInput(processingColorProfileInput)
                .processingColorProfileOutput(processingColorProfileOutput)
                .processingParameterizedShapesEllipseGeneralEnabled(processingParameterizedShapesEllipseGeneralEnabled)
                .processingParameterizedShapesEllipseCircleEnabled(processingParameterizedShapesEllipseCircleEnabled)
                .processingParameterizedShapesTriangleGeneralEnabled(processingParameterizedShapesTriangleGeneralEnabled)
                .processingParameterizedShapesTriangleIsoscelesEnabled(processingParameterizedShapesTriangleIsoscelesEnabled)
                .processingParameterizedShapesQuadrilateralGeneralEnabled(processingParameterizedShapesQuadrilateralGeneralEnabled)
                .processingParameterizedShapesQuadrilateralRectangleEnabled(processingParameterizedShapesQuadrilateralRectangleEnabled)
                .processingParameterizedShapesQuadrilateralBulletEnabled(processingParameterizedShapesQuadrilateralBulletEnabled)
                .processingParameterizedShapesStarN3Enabled(processingParameterizedShapesStarN3Enabled)
                .processingParameterizedShapesStarN4Enabled(processingParameterizedShapesStarN4Enabled)
                .processingParameterizedShapesStarN5Enabled(processingParameterizedShapesStarN5Enabled)
                .processingParameterizedShapesStarN6Enabled(processingParameterizedShapesStarN6Enabled)
                .outputFileFormat(outputFileFormat)
                .outputShapeStacking(outputShapeStacking)
                .outputGroupBy(outputGroupBy)
                .outputDrawStyle(outputDrawStyle)
                .outputStrokesStrokeWidth(outputStrokesStrokeWidth)
                .outputStrokesNonScalingStroke(outputStrokesNonScalingStroke)
                .outputStrokesUseOverrideColor(outputStrokesUseOverrideColor)
                .outputStrokesOverrideColor(outputStrokesOverrideColor)
                .outputGapFillerEnabled(outputGapFillerEnabled)
                .outputGapFillerNonScalingStroke(outputGapFillerNonScalingStroke)
                .outputGapFillerClip(outputGapFillerClip)
                .outputGapFillerStrokeWidth(outputGapFillerStrokeWidth)
                .outputParameterizedShapesFlatten(outputParameterizedShapesFlatten)
                .outputCurvesLineFitTolerance(outputCurvesLineFitTolerance)
                .outputCurvesAllowedQuadraticBezier(outputCurvesAllowedQuadraticBezier)
                .outputCurvesAllowedCubicBezier(outputCurvesAllowedCubicBezier)
                .outputCurvesAllowedCircularArc(outputCurvesAllowedCircularArc)
                .outputCurvesAllowedEllipticalArc(outputCurvesAllowedEllipticalArc)
                .outputSvgVersion(outputSvgVersion)
                .outputSvgFixedSize(outputSvgFixedSize)
                .outputSvgAdobeCompatibilityMode(outputSvgAdobeCompatibilityMode)
                .outputPdfVersion(outputPdfVersion)
                .outputPdfCompressionMode(outputPdfCompressionMode)
                .outputEpsVersion(outputEpsVersion)
                .outputDxfCompatibilityLevel(outputDxfCompatibilityLevel)
                .outputBitmapAntiAliasingMode(outputBitmapAntiAliasingMode)
                .outputSizeScale(outputSizeScale)
                .outputSizeWidth(outputSizeWidth)
                .outputSizeHeight(outputSizeHeight)
                .outputSizeUnit(outputSizeUnit)
                .outputSizeAspectRatio(outputSizeAspectRatio)
                .outputSizeAlignX(outputSizeAlignX)
                .outputSizeAlignY(outputSizeAlignY)
                .outputSizeInputDpi(outputSizeInputDpi)
                .outputSizeOutputDpi(outputSizeOutputDpi)
                .build();
            ApiResponse<File> response = apiInstance.postVectorizeWithHttpInfo(request);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling VectorizationApi#postVectorize");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters

|    Name      |    Type       | Description   |     Notes    |
|------------- | ------------- | ------------- | -------------|
| postVectorizeRequest | [**APIpostVectorizeRequest**](VectorizationApi.md#APIpostVectorizeRequest)|-|-|

### Return type

ApiResponse<[**File**](File.md)>


### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: image/svg+xml, application/postscript, application/pdf, application/dxf, image/png, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The vectorized image file. |  * Content-Disposition - Suggested filename for the generated result. <br>  * Content-Encoding - May be gzip for SVG, EPS, or DXF responses when the request allows gzip encoding. <br>  * X-Image-Token - Returned by vectorize when policy.retention_days is greater than 0. <br>  * X-Credits-Charged - Credits charged for the request. This is 0 for test requests. <br>  * X-Credits-Calculated - Returned for test requests to show the credits that would have been charged for the equivalent non-test request. <br>  |
| **400** | Invalid request parameters, image input, URL fetch, or Image Token. |  -  |
| **401** | Missing or invalid API credentials. |  * WWW-Authenticate - HTTP Basic authentication challenge returned with 401 responses. <br>  |
| **402** | The account does not have an API subscription, is past due, or is out of credits. |  -  |
| **413** | The uploaded image, fetched image, or requested PNG output is too large. |  -  |
| **429** | Rate limit exceeded. Back off before retrying. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |
| **500** | Unexpected internal error. |  -  |
| **503** | Temporary overload or internal processing timeout. Retry later. |  * Retry-After - Number of seconds to wait before retrying, when provided. <br>  |


<a id="APIpostVectorizeRequest"></a>
## APIpostVectorizeRequest
### Properties

|     Name      |    Type       | Description   |     Notes    |
| ------------- | ------------- | ------------- | -------------|
| **image** | **File** | Binary file upload of the image to vectorize. Accepts .bmp, .gif, .jpeg, .png, or .tiff files. | [optional] |
| **imageUrl** | **URI** | URL to fetch the input image from for vectorization. | [optional] |
| **imageBase64** | **byte[]** | Base64-encoded string of the input image. Maximum size 1 megabyte. | [optional] |
| **imageToken** | **String** | An Image Token returned from an earlier vectorization call with policy.retention_days &gt; 0. | [optional] |
| **mode** | **String** | Mode of operation, useful during integration work. | [optional] [default to production] [enum: production, preview, test, test_preview] |
| **inputMaxPixels** | **Integer** | Maximum input image size (width × height in pixels) before resizing. | [optional] [default to 2097252] |
| **policyRetentionDays** | **Integer** | Number of days to retain the uploaded image and its results for re-use. | [optional] [default to 0] |
| **processingMaxColors** | **Integer** | Maximum number of colors allowed in the vectorization result. 0 means unlimited. | [optional] [default to 0] |
| **processingShapesMinAreaPx** | **Float** | Minimum shape area (in pixels) to keep in the result; smaller shapes are discarded. | [optional] [default to 0.125] |
| **processingPalette** | **String** | Palette remapping and color control, using &#39;[color][-&gt; remapped][~ tolerance];&#39; format. | [optional] |
| **processingColorProfileInput** | **String** | How to handle ICC profiles embedded in input images. | [optional] [default to ignore] [enum: ignore, preserve] |
| **processingColorProfileOutput** | **String** | ICC profile behavior for output files: preserve, ignore. | [optional] [default to ignore] |
| **processingParameterizedShapesEllipseGeneralEnabled** | **Boolean** | Enable detection and parameterization of this parameterized shape type. | [optional] [default to true] |
| **processingParameterizedShapesEllipseCircleEnabled** | **Boolean** | Enable detection and parameterization of this parameterized shape type. | [optional] [default to true] |
| **processingParameterizedShapesTriangleGeneralEnabled** | **Boolean** | Enable detection and parameterization of this parameterized shape type. | [optional] [default to true] |
| **processingParameterizedShapesTriangleIsoscelesEnabled** | **Boolean** | Enable detection and parameterization of this parameterized shape type. | [optional] [default to true] |
| **processingParameterizedShapesQuadrilateralGeneralEnabled** | **Boolean** | Enable detection and parameterization of this parameterized shape type. | [optional] [default to true] |
| **processingParameterizedShapesQuadrilateralRectangleEnabled** | **Boolean** | Enable detection and parameterization of this parameterized shape type. | [optional] [default to true] |
| **processingParameterizedShapesQuadrilateralBulletEnabled** | **Boolean** | Enable detection and parameterization of this parameterized shape type. | [optional] [default to true] |
| **processingParameterizedShapesStarN3Enabled** | **Boolean** | Enable detection and parameterization of this parameterized shape type. | [optional] [default to true] |
| **processingParameterizedShapesStarN4Enabled** | **Boolean** | Enable detection and parameterization of this parameterized shape type. | [optional] [default to true] |
| **processingParameterizedShapesStarN5Enabled** | **Boolean** | Enable detection and parameterization of this parameterized shape type. | [optional] [default to true] |
| **processingParameterizedShapesStarN6Enabled** | **Boolean** | Enable detection and parameterization of this parameterized shape type. | [optional] [default to true] |
| **outputFileFormat** | **String** | Output file format to generate. | [optional] [default to svg] [enum: svg, eps, pdf, dxf, png] |
| **outputShapeStacking** | **String** | Whether shapes are cut out of each other or stacked atop each other. | [optional] [default to cutouts] [enum: cutouts, stacked] |
| **outputGroupBy** | **String** | Grouping of shapes in output. | [optional] [default to none] [enum: none, color, parent, layer] |
| **outputDrawStyle** | **String** | How shapes are rendered. | [optional] [default to fill_shapes] [enum: fill_shapes, stroke_shapes, stroke_edges] |
| **outputStrokesStrokeWidth** | **Float** | Width of stroke for shape outlines (when enabled). | [optional] [default to 1] |
| **outputStrokesNonScalingStroke** | **Boolean** | Use non-scaling strokes when drawing shape outlines. | [optional] [default to true] |
| **outputStrokesUseOverrideColor** | **Boolean** | Override shape color with a specific color. | [optional] [default to false] |
| **outputStrokesOverrideColor** | **String** | Color value to override shape stroke color if enabled. Must be in &#39;#RRGGBB&#39; or &#39;rgba(r,g,b,a)&#39; format. | [optional] [default to #000000] |
| **outputGapFillerEnabled** | **Boolean** | Enable filling small visual gaps caused by vector rendering artifacts. | [optional] [default to true] |
| **outputGapFillerNonScalingStroke** | **Boolean** | Use non-scaling strokes for gap filling. | [optional] [default to true] |
| **outputGapFillerClip** | **Boolean** | Clip gap filler strokes to shape bounds when stacking shapes. | [optional] [default to false] |
| **outputGapFillerStrokeWidth** | **Float** | Width of the gap filler strokes (in output units). | [optional] [default to 2] |
| **outputParameterizedShapesFlatten** | **Boolean** | Whether to flatten detected circles, rectangles, and stars to curves. | [optional] [default to false] |
| **outputCurvesLineFitTolerance** | **Float** | Maximum allowed error when approximating curves with line segments. | [optional] [default to 0.1] |
| **outputCurvesAllowedQuadraticBezier** | **Boolean** | Allow quadratic Bézier curves in the output. | [optional] [default to true] |
| **outputCurvesAllowedCubicBezier** | **Boolean** | Allow cubic Bézier curves in the output. | [optional] [default to true] |
| **outputCurvesAllowedCircularArc** | **Boolean** | Allow circular arcs in the output. | [optional] [default to true] |
| **outputCurvesAllowedEllipticalArc** | **Boolean** | Allow elliptical arcs in the output. | [optional] [default to true] |
| **outputSvgVersion** | **String** | SVG version to declare in the SVG output. | [optional] [default to svg_1_1] [enum: svg_1_0, svg_1_1, svg_tiny_1_2] |
| **outputSvgFixedSize** | **Boolean** | Whether to fix the SVG dimensions in the output file. | [optional] [default to false] |
| **outputSvgAdobeCompatibilityMode** | **Boolean** | Enable Illustrator compatibility by disabling unsupported SVG features. | [optional] [default to false] |
| **outputPdfVersion** | **String** | PDF version to generate for PDF output. | [optional] [default to PDF_1_4] [enum: PDF_1_4] |
| **outputPdfCompressionMode** | **String** | Compression method to apply to PDF output streams. | [optional] [default to Deflate] [enum: None, Deflate] |
| **outputEpsVersion** | **String** | EPS format version for EPS output. | [optional] [default to PS_3_0_EPSF_3_0] [enum: PS_3_0_EPSF_3_0] |
| **outputDxfCompatibilityLevel** | **String** | Level of primitive support for DXF output. | [optional] [default to lines_and_arcs] [enum: lines_only, lines_and_arcs, lines_arcs_and_splines] |
| **outputBitmapAntiAliasingMode** | **String** | Anti-aliasing mode for bitmap (PNG) output. | [optional] [default to anti_aliased] [enum: anti_aliased, aliased] |
| **outputSizeScale** | **Float** | Overall uniform scaling factor for the output image. | [optional] |
| **outputSizeWidth** | **Float** | Output width, in the selected unit (see output.size.unit). | [optional] |
| **outputSizeHeight** | **Float** | Output height, in the selected unit (see output.size.unit). | [optional] |
| **outputSizeUnit** | **String** | Measurement unit for output dimensions. | [optional] [default to none] [enum: none, px, pt, in, cm, mm] |
| **outputSizeAspectRatio** | **String** | How to preserve or stretch aspect ratio. | [optional] [default to preserve_inset] [enum: preserve_inset, preserve_overflow, stretch] |
| **outputSizeAlignX** | **Float** | Horizontal alignment (0.0 &#x3D; left, 0.5 &#x3D; center, 1.0 &#x3D; right) when aspect ratio is preserved. | [optional] [default to 0.5] |
| **outputSizeAlignY** | **Float** | Vertical alignment (0.0 &#x3D; top, 0.5 &#x3D; center, 1.0 &#x3D; bottom) when aspect ratio is preserved. | [optional] [default to 0.5] |
| **outputSizeInputDpi** | **Float** | Override the detected DPI of the input image for size computations. | [optional] |
| **outputSizeOutputDpi** | **Float** | DPI setting for the output image. | [optional] |


