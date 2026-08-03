
# Grant Type

Grant type: authorization_code generates user tokens, client_credentials generates short-lived client grants

## Enumeration

`GrantType`

## Fields

| Name |
|  --- |
| `AUTHORIZATION_CODE` |
| `CLIENT_CREDENTIALS` |
| `REFRESH_TOKEN` |

## Example

```java
import com.shutterstock.api.models.GrantType;

GrantType grantType = GrantType.CLIENT_CREDENTIALS;
```

