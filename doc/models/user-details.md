
# User Details

User details

*This model accepts additional fields of type Object.*

## Structure

`UserDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ContributorId` | `String` | Optional | Unique internal identifier of the user, as a contributor | String getContributorId() | setContributorId(String contributorId) |
| `CustomerId` | `String` | Optional | Unique internal identifier of the user, as a purchaser | String getCustomerId() | setCustomerId(String customerId) |
| `Email` | `String` | Optional | Email address of the user | String getEmail() | setEmail(String email) |
| `FirstName` | `String` | Optional | First name of the user | String getFirstName() | setFirstName(String firstName) |
| `FullName` | `String` | Optional | Full name including first, middle, and last name of the user | String getFullName() | setFullName(String fullName) |
| `Id` | `String` | Optional | Unique internal identifier for the user, not tied to contributor or purchasing customer | String getId() | setId(String id) |
| `IsPremier` | `Boolean` | Optional | True if the user has access to the Premier collection, false otherwise | Boolean getIsPremier() | setIsPremier(Boolean isPremier) |
| `IsPremierParent` | `Boolean` | Optional | True if the user has access to the Premier collection and also has child users | Boolean getIsPremierParent() | setIsPremierParent(Boolean isPremierParent) |
| `Language` | `String` | Optional | Main language of the user account | String getLanguage() | setLanguage(String language) |
| `LastName` | `String` | Optional | Last name of the user | String getLastName() | setLastName(String lastName) |
| `OnlyEnhancedLicense` | `Boolean` | Optional | True if the user has an enterprise license, false otherwise | Boolean getOnlyEnhancedLicense() | setOnlyEnhancedLicense(Boolean onlyEnhancedLicense) |
| `OnlySensitiveUse` | `Boolean` | Optional | True if the user has access to sensitive use only, false otherwise | Boolean getOnlySensitiveUse() | setOnlySensitiveUse(Boolean onlySensitiveUse) |
| `OrganizationId` | `String` | Optional | Unique internal identifier for the user's organization, specific to Premier users | String getOrganizationId() | setOrganizationId(String organizationId) |
| `PremierPermissions` | `List<String>` | Optional | List of permissions allowed through the Premier client | List<String> getPremierPermissions() | setPremierPermissions(List<String> premierPermissions) |
| `Username` | `String` | Optional | User name associated to the user | String getUsername() | setUsername(String username) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.UserDetails;
import java.io.IOException;

UserDetails userDetails = new UserDetails.Builder()
    .contributorId("212")
    .customerId("customer_id2")
    .email("email2")
    .firstName("John")
    .fullName("John Doe")
    .id("101782699")
    .language("es")
    .lastName("Doe")
    .username("jdoe")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

