# Users

```java
UsersApi usersApi = client.getUsersApi();
```

## Class Name

`UsersApi`

## Methods

* [Get User](../../doc/controllers/users.md#get-user)
* [Get Access Token](../../doc/controllers/users.md#get-access-token)
* [Get User Subscription List](../../doc/controllers/users.md#get-user-subscription-list)


# Get User

```java
CompletableFuture<ApiResponse<UserDetails>> getUserAsync()
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Requires scope

### customer_accessCode

`user.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UserDetails`](../../doc/models/user-details.md).

## Example Usage

```java
usersApi.getUserAsync().thenAccept(result -> {
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
  "id": "101782699",
  "username": "jdoe",
  "full_name": "John Doe",
  "first_name": "John",
  "last_name": "Doe",
  "language": "es",
  "contributor_id": "212"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Get Access Token

```java
CompletableFuture<ApiResponse<AccessTokenDetails>> getAccessTokenAsync()
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AccessTokenDetails`](../../doc/models/access-token-details.md).

## Example Usage

```java
usersApi.getAccessTokenAsync().thenAccept(result -> {
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
  "client_id": "c456b-26230-fa8ed-d19ab-05ce2-bf0aa",
  "customer_id": "123456789",
  "realm": "customer",
  "user_id": "123456789",
  "username": "jdoe",
  "expires_in": 3600,
  "scopes": [
    "collections.edit",
    "collections.view",
    "licenses.create",
    "licenses.view",
    "purchases.view",
    "user.view"
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Get User Subscription List

```java
CompletableFuture<ApiResponse<SubscriptionDataList>> getUserSubscriptionListAsync()
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Requires scope

### customer_accessCode

`purchases.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`SubscriptionDataList`](../../doc/models/subscription-data-list.md).

## Example Usage

```java
usersApi.getUserSubscriptionListAsync().thenAccept(result -> {
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
  "data": [
    {
      "allotment": {
        "downloads_left": 5,
        "downloads_limit": 10,
        "end_time": "2020-05-29T12:10:22-05:00",
        "start_time": "2020-05-29T12:10:22-05:00"
      },
      "description": "Annual Subscription",
      "expiration_time": "2020-05-29T12:10:22-05:00",
      "formats": [
        {
          "media_type": "image",
          "description": "Small",
          "format": "jpg",
          "min_resolution": 500,
          "size": "small"
        },
        {
          "media_type": "image",
          "description": "Med",
          "format": "jpg",
          "min_resolution": 1000,
          "size": "medium"
        },
        {
          "media_type": "image",
          "description": "Vector",
          "format": "eps",
          "size": "vector"
        }
      ],
      "id": "s8906043",
      "license": "standard",
      "asset_type": "images",
      "metadata": {}
    }
  ],
  "page": 1,
  "per_page": 5,
  "total_count": 123455
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |

