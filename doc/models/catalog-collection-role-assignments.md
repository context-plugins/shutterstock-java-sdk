
# Catalog Collection Role Assignments

List of role assignments for a catalog collection

*This model accepts additional fields of type Object.*

## Structure

`CatalogCollectionRoleAssignments`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `CollectionId` | `String` | Required | - | String getCollectionId() | setCollectionId(String collectionId) |
| `Roles` | [`Roles`](../../doc/models/roles.md) | Required | - | Roles getRoles() | setRoles(Roles roles) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.CatalogCollectionRole;
import com.shutterstock.api.models.CatalogCollectionRoleAssignments;
import com.shutterstock.api.models.Roles;
import com.shutterstock.api.models.Type1;
import java.io.IOException;
import java.util.Arrays;

CatalogCollectionRoleAssignments catalogCollectionRoleAssignments = new CatalogCollectionRoleAssignments.Builder(
    "126351028",
    new Roles.Builder()
        .owners(Arrays.asList(
            new CatalogCollectionRole.Builder(
                "321",
                Type1.USER,
                "userOne@org.com"
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        ))
        .editors(Arrays.asList(
            new CatalogCollectionRole.Builder(
                "987",
                Type1.USER,
                "userTwo@org.com"
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        ))
        .viewers(Arrays.asList(

        ))
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

