
# Oauth Scope Customer Access Code

OAuth 2 scopes supported by the API

## Enumeration

`OauthScopeCustomerAccessCode`

## Fields

| Name | Description |
|  --- | --- |
| `LICENSES_CREATE` | Grant the ability to download and license media on behalf of the user. |
| `PURCHASES_VIEW` | Grant read-only access to a user's purchase history. |
| `LICENSES_VIEW` | Grant read-only access to a user's licenses. |
| `COLLECTIONS_EDIT` | Grant the ability to create new collections, edit a collection, and modify the contents of a collection |
| `COLLECTIONS_VIEW` | Grant read-only access to a collection and its contents. |
| `USER_VIEW` |  |

## Example

```java
import com.shutterstock.api.models.OauthScopeCustomerAccessCode;

OauthScopeCustomerAccessCode oauthScopeCustomerAccessCode = OauthScopeCustomerAccessCode.LICENSES_VIEW;
```

