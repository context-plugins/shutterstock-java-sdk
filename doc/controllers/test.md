# Test

```java
TestApi testApi = client.getTestApi();
```

## Class Name

`TestApi`

## Methods

* [Echo](../../doc/controllers/test.md#echo)
* [Validate](../../doc/controllers/test.md#validate)


# Echo

:information_source: **Note** This endpoint does not require authentication.

```java
CompletableFuture<ApiResponse<TestEcho>> echoAsync(
    final String text)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `text` | `String` | Query, Optional | Text to echo<br><br>**Default**: `"ok"` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`TestEcho`](../../doc/models/test-echo.md).

## Example Usage

```java
String text = "ok";

testApi.echoAsync(text).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response *(as JSON)*

```json
{
  "text": "Test string"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Validate

:information_source: **Note** This endpoint does not require authentication.

```java
CompletableFuture<ApiResponse<TestValidate>> validateAsync(
    final int id,
    final List<String> tag,
    final String userAgent)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `int` | Query, Required | Integer ID |
| `tag` | `List<String>` | Query, Optional | List of tags |
| `userAgent` | `String` | Header, Optional | User agent |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`TestValidate`](../../doc/models/test-validate.md).

## Example Usage

```java
int id = 123;

testApi.validateAsync(id, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response *(as JSON)*

```json
{
  "header": {
    "user-agent": "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/51.0.2704.103 Safari/537.36"
  },
  "query": {
    "id": 123456,
    "tag": [
      "Test string"
    ]
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |

