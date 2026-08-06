
# HttpProxyConfiguration.Builder

Class to build instances of [HttpProxyConfiguration](../doc/http-proxy-configuration.md).

## Constructors

| Name | Description |
|  --- | --- |
| `Builder()` | Default Constructor to initiate builder with default properties. |

## Methods

| Name | Description | Return Type |
|  --- | --- | --- |
| `Builder(String address, int port)` | Constructs HttpProxyConfiguration.Builder with proxy address and port. | `HttpProxyConfiguration.Builder` |
| `auth(String username, String password)` | Sets the username and password for proxy auth. | `HttpProxyConfiguration.Builder` |
| `build()` | Builds a new HttpProxyConfiguration object using the set fields. | [`HttpProxyConfiguration`](../doc/http-proxy-configuration.md) |

### Client Initialization with Proxy Configuration

To configure the SDK to use a proxy server, initialize the proxy configuration during client setup as shown in the Usage Example.

## Usage Example

```java
import com.shutterstock.api.ShutterstockClient;
import com.shutterstock.api.http.client.HttpProxyConfiguration;

ShutterstockClient client = new ShutterstockClient.Builder()
  .httpClientConfig(configBuilder -> configBuilder
      .proxyConfig(new HttpProxyConfiguration.Builder("http://localhost",
          8080).auth("username", "password")))
  .build();
```

