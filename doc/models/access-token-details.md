
# Access Token Details

Access token details that are currently associated with this user

*This model accepts additional fields of type Object.*

## Structure

`AccessTokenDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ClientId` | `String` | Optional | Client ID that is associated with the user | String getClientId() | setClientId(String clientId) |
| `ContributorId` | `String` | Optional | Contributor ID that is associated with the user | String getContributorId() | setContributorId(String contributorId) |
| `CustomerId` | `String` | Optional | Customer ID that is associated with the user | String getCustomerId() | setCustomerId(String customerId) |
| `ExpiresIn` | `Integer` | Optional | Number of seconds until the access token expires; no expiration if this value is null | Integer getExpiresIn() | setExpiresIn(Integer expiresIn) |
| `OrganizationId` | `String` | Optional | Organization ID that is associated with the user | String getOrganizationId() | setOrganizationId(String organizationId) |
| `Realm` | [`Realm`](../../doc/models/realm.md) | Optional | Type of access token | Realm getRealm() | setRealm(Realm realm) |
| `Scopes` | `List<String>` | Optional | Scopes that this access token provides when used as authentication | List<String> getScopes() | setScopes(List<String> scopes) |
| `UserId` | `String` | Optional | User ID that is associated with the user | String getUserId() | setUserId(String userId) |
| `Username` | `String` | Optional | User name that is associated with the user | String getUsername() | setUsername(String username) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.AccessTokenDetails;
import com.shutterstock.api.models.Realm;
import java.io.IOException;
import java.util.Arrays;

AccessTokenDetails accessTokenDetails = new AccessTokenDetails.Builder()
    .clientId("c456b-26230-fa8ed-d19ab-05ce2-bf0aa")
    .contributorId("contributor_id8")
    .customerId("123456789")
    .expiresIn(3600)
    .organizationId("organization_id2")
    .realm(Realm.CUSTOMER)
    .scopes(Arrays.asList(
        "collections.edit",
        "collections.view",
        "licenses.create",
        "licenses.view",
        "purchases.view",
        "user.view"
    ))
    .userId("123456789")
    .username("jdoe")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

