
# Oauth Access Token Response

Access token response to client apps

*This model accepts additional fields of type Object.*

## Structure

`OauthAccessTokenResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AccessToken` | `String` | Required | Access token that can be used for future requests | String getAccessToken() | setAccessToken(String accessToken) |
| `ExpiresIn` | `Integer` | Optional | Number of seconds before token expires, only present for expiring tokens | Integer getExpiresIn() | setExpiresIn(Integer expiresIn) |
| `TokenType` | `String` | Required | Type of token<br><br>**Default**: `"Bearer"` | String getTokenType() | setTokenType(String tokenType) |
| `RefreshToken` | `String` | Optional | A refresh token that can be used to renew the access_token when it expires, only present for expiring tokens | String getRefreshToken() | setRefreshToken(String refreshToken) |
| `UserToken` | `String` | Optional | Metadata about the access_token, only present for expiring tokens | String getUserToken() | setUserToken(String userToken) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.OauthAccessTokenResponse;
import java.io.IOException;

OauthAccessTokenResponse oauthAccessTokenResponse = new OauthAccessTokenResponse.Builder(
    "v2/NmQwOTc0NTBiMjA5YzZkY2Q4NTkvMTA4OTg1MDk5L2N1c3RvbWVyLzIvZjB2a0RseGo4Rkt6ZjRmVWJNMm10V2VzcHh1NTBlZWJ6andUQU1NeTVYYnNFTDVWOFRJakItS2RnZTlmbEY1Y3haNWdXLUtYc2JhaXo5djk0V0p2QzZUUWZ4c2FNWm41NkdLYUgyVWlCaVUtQTNVMV9YQWpzd3lpblI3SlZEem8wSG1qQ2NzSkJlX3VQTnNXenBIdkd4SXViVi1rRGJTVENCV0g1U3U0RXRJSV9rSm5lQkl5QXlvbm5JN241UUhv",
    "Bearer"
)
.expiresIn(182)
.refreshToken("refresh_token6")
.userToken("user_token8")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

