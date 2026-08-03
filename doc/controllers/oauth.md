# oauth

```java
OauthApi oauthApi = client.getOauthApi();
```

## Class Name

`OauthApi`

## Methods

* [Authorize](../../doc/controllers/oauth.md#authorize)
* [Create Access Token](../../doc/controllers/oauth.md#create-access-token)


# Authorize

This endpoint returns a redirect URI (in the 'Location' header) that the customer uses to authorize your application and, together with POST /v2/oauth/access_token, generate an access token that represents that authorization.

:information_source: **Note** This endpoint does not require authentication.

```java
CompletableFuture<ApiResponse<Void>> authorizeAsync(
    final String clientId,
    final String redirectUri,
    final ResponseType responseType,
    final String state,
    final Realm2 realm,
    final String scope)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clientId` | `String` | Query, Required | Client ID (Consumer Key) of your application |
| `redirectUri` | `String` | Query, Required | The callback URI to send the request to after authorization; must use a host name that is registered with your application |
| `responseType` | [`ResponseType`](../../doc/models/response-type.md) | Query, Required | Type of temporary authorization code that will be used to generate an access code; the only valid value is 'code' |
| `state` | `String` | Query, Required | Unique value used by the calling app to verify the request |
| `realm` | [`Realm2`](../../doc/models/realm-2.md) | Query, Optional | User type to be authorized (usually 'customer')<br><br>**Default**: `Realm2.CUSTOMER` |
| `scope` | `String` | Query, Optional | Space-separated list of scopes to be authorized<br><br>**Default**: `"user.view"` |

## Response Type

**200**

`void`

## Example Usage

```java
String clientId = "6d097450b209c6dcd859";
String redirectUri = "localhost";
ResponseType responseType = ResponseType.CODE;
String state = "1540290465000";
Realm2 realm = Realm2.CUSTOMER;
String scope = "user.view";

oauthApi.authorizeAsync(clientId, redirectUri, responseType, state, realm, scope).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Create Access Token

This endpoint returns an access token for the specified user and with the specified scopes. The token does not expire until the user changes their password. The body parameters must be encoded as form data.

:information_source: **Note** This endpoint does not require authentication.

```java
CompletableFuture<ApiResponse<OauthAccessTokenResponse>> createAccessTokenAsync(
    final String clientId,
    final GrantType grantType,
    final String clientSecret,
    final String code,
    final Realm3 realm,
    final Expires expires,
    final String refreshToken)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clientId` | `String` | Form, Required | Client ID (Consumer Key) of your application |
| `grantType` | [`GrantType`](../../doc/models/grant-type.md) | Form, Required | Grant type: authorization_code generates user tokens, client_credentials generates short-lived client grants |
| `clientSecret` | `String` | Form, Optional | Client Secret (Consumer Secret) of your application |
| `code` | `String` | Form, Optional | Response code from the /oauth/authorize flow; required if grant_type=authorization_code |
| `realm` | [`Realm3`](../../doc/models/realm-3.md) | Form, Optional | User type to be authorized (usually 'customer')<br><br>**Default**: `Realm3.CUSTOMER` |
| `expires` | [`Expires`](../../doc/models/expires.md) | Form, Optional | Whether or not the token expires, expiring tokens come with a refresh_token to renew the access_token<br><br>**Default**: `Expires.ENUM_FALSE` |
| `refreshToken` | `String` | Form, Optional | Pass this along with grant_type=refresh_token to get a fresh access token |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`OauthAccessTokenResponse`](../../doc/models/oauth-access-token-response.md).

## Example Usage

```java
String clientId = "141024g14g28104gff1h";
GrantType grantType = GrantType.CLIENT_CREDENTIALS;
Realm3 realm = Realm3.CUSTOMER;
Expires expires = Expires.ENUM_FALSE;

oauthApi.createAccessTokenAsync(clientId, grantType, null, null, realm, expires, null).thenAccept(result -> {
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
  "access_token": "v2/NmQwOTc0NTBiMjA5YzZkY2Q4NTkvMTA4OTg1MDk5L2N1c3RvbWVyLzIvZjB2a0RseGo4Rkt6ZjRmVWJNMm10V2VzcHh1NTBlZWJ6andUQU1NeTVYYnNFTDVWOFRJakItS2RnZTlmbEY1Y3haNWdXLUtYc2JhaXo5djk0V0p2QzZUUWZ4c2FNWm41NkdLYUgyVWlCaVUtQTNVMV9YQWpzd3lpblI3SlZEem8wSG1qQ2NzSkJlX3VQTnNXenBIdkd4SXViVi1rRGJTVENCV0g1U3U0RXRJSV9rSm5lQkl5QXlvbm5JN241UUhv",
  "token_type": "Bearer"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |

