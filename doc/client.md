
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](../README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| httpClientConfig | [`Consumer<HttpClientConfiguration.Builder>`](../doc/http-client-configuration-builder.md) | Set up Http Client Configuration instance. |
| loggingConfig | [`Consumer<ApiLoggingConfiguration.Builder>`](../doc/api-logging-configuration-builder.md) | Set up Logging Configuration instance. |
| basicCredentials | [`BasicCredentials`](auth/basic-authentication.md) | The Credentials Setter for Basic Authentication |
| customerAccessCodeCredentials | [`CustomerAccessCodeCredentials`](auth/oauth-2-authorization-code-grant.md) | The Credentials Setter for OAuth 2 Authorization Code Grant |

The API client can be initialized as follows:

```java
import com.shutterstock.api.Environment;
import com.shutterstock.api.ShutterstockApiExplorerClient;
import com.shutterstock.api.authentication.BasicModel;
import com.shutterstock.api.authentication.CustomerAccessCodeModel;
import com.shutterstock.api.exceptions.ApiException;
import com.shutterstock.api.http.response.ApiResponse;
import com.shutterstock.api.models.OauthScopeCustomerAccessCode;
import com.shutterstock.api.models.OauthToken;
import java.io.IOException;
import java.util.Arrays;
import org.slf4j.event.Level;

public class Program {
    public static void main(String[] args) {
        ShutterstockApiExplorerClient client = new ShutterstockApiExplorerClient.Builder()
            .loggingConfig(builder -> builder
                    .level(Level.DEBUG)
                    .requestConfig(logConfigBuilder -> logConfigBuilder.body(true))
                    .responseConfig(logConfigBuilder -> logConfigBuilder.headers(true)))
            .httpClientConfig(configBuilder -> configBuilder
                    .timeout(0))
            .basicCredentials(new BasicModel.Builder(
                    "Username",
                    "Password"
                )
                .build())
            .customerAccessCodeCredentials(new CustomerAccessCodeModel.Builder(
                    "OAuthClientId",
                    "OAuthClientSecret",
                    "OAuthRedirectUri"
                )
                .oauthScopes(Arrays.asList(
                        OauthScopeCustomerAccessCode.LICENSES_CREATE,
                        OauthScopeCustomerAccessCode.PURCHASES_VIEW
                    ))
                .build())
            .environment(Environment.PRODUCTION)
            .build();

    }
}
```

## Shutterstock API ExplorerClient Class

The gateway for the SDK. This class acts as a factory for the Apis and also holds the configuration of the SDK.

### Apis

| Name | Description | Return Type |
|  --- | --- | --- |
| `getImagesApi()` | Provides access to Images controller. | `ImagesApi` |
| `getVideosApi()` | Provides access to Videos controller. | `VideosApi` |
| `getAudioApi()` | Provides access to Audio controller. | `AudioApi` |
| `getSoundEffectsApi()` | Provides access to SoundEffects controller. | `SoundEffectsApi` |
| `getEditorialImagesApi()` | Provides access to EditorialImages controller. | `EditorialImagesApi` |
| `getEditorialVideoApi()` | Provides access to EditorialVideo controller. | `EditorialVideoApi` |
| `getComputerVisionApi()` | Provides access to ComputerVision controller. | `ComputerVisionApi` |
| `getCatalogApi()` | Provides access to Catalog controller. | `CatalogApi` |
| `getContributorsApi()` | Provides access to Contributors controller. | `ContributorsApi` |
| `getUsersApi()` | Provides access to Users controller. | `UsersApi` |
| `getTestApi()` | Provides access to Test controller. | `TestApi` |
| `getOauthApi()` | Provides access to Oauth controller. | `OauthApi` |
| `getOauthAuthorizationApi()` | Provides access to OauthAuthorization controller. | `OauthAuthorizationApi` |

### Methods

| Name | Description | Return Type |
|  --- | --- | --- |
| `shutdown()` | Shutdown the underlying HttpClient instance. | `void` |
| `getEnvironment()` | Current API environment. | `Environment` |
| `getHttpClient()` | The HTTP Client instance to use for making HTTP requests. | `HttpClient` |
| `getHttpClientConfig()` | Http Client Configuration instance. | [`ReadonlyHttpClientConfiguration`](../doc/http-client-configuration.md) |
| `getLoggingConfig()` | Logging Configuration instance. | [`ReadonlyLoggingConfiguration`](../doc/api-logging-configuration.md) |
| `getBasicCredentials()` | The credentials to use with Basic. | [`BasicCredentials`](auth/basic-authentication.md) |
| `getCustomerAccessCodeCredentials()` | The credentials to use with CustomerAccessCode. | [`CustomerAccessCodeCredentials`](auth/oauth-2-authorization-code-grant.md) |
| `getBaseUri(Server server)` | Get base URI by current environment | `String` |
| `getBaseUri()` | Get base URI by current environment | `String` |

