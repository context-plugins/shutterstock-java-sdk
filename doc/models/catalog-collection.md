
# Catalog Collection

Catalog collection

*This model accepts additional fields of type Object.*

## Structure

`CatalogCollection`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | - | String getId() | setId(String id) |
| `Name` | `String` | Required | - | String getName() | setName(String name) |
| `CoverAsset` | [`CatalogCollectionItem`](../../doc/models/catalog-collection-item.md) | Optional | Metadata about an item that is part of a collection | CatalogCollectionItem getCoverAsset() | setCoverAsset(CatalogCollectionItem coverAsset) |
| `TotalItemCount` | `double` | Required | - | double getTotalItemCount() | setTotalItemCount(double totalItemCount) |
| `CreatedTime` | `LocalDateTime` | Required | - | LocalDateTime getCreatedTime() | setCreatedTime(LocalDateTime createdTime) |
| `UpdatedTime` | `LocalDateTime` | Required | - | LocalDateTime getUpdatedTime() | setUpdatedTime(LocalDateTime updatedTime) |
| `Visibility` | [`Visibility`](../../doc/models/visibility.md) | Required | - | Visibility getVisibility() | setVisibility(Visibility visibility) |
| `RoleAssignments` | [`CatalogCollectionRoleAssignments`](../../doc/models/catalog-collection-role-assignments.md) | Required | List of role assignments for a catalog collection | CatalogCollectionRoleAssignments getRoleAssignments() | setRoleAssignments(CatalogCollectionRoleAssignments roleAssignments) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Asset;
import com.shutterstock.api.models.CatalogCollection;
import com.shutterstock.api.models.CatalogCollectionItem;
import com.shutterstock.api.models.CatalogCollectionRole;
import com.shutterstock.api.models.CatalogCollectionRoleAssignments;
import com.shutterstock.api.models.Roles;
import com.shutterstock.api.models.Type;
import com.shutterstock.api.models.Type1;
import com.shutterstock.api.models.Visibility;
import java.io.IOException;
import java.util.Arrays;

CatalogCollection catalogCollection = new CatalogCollection.Builder(
    "126351028",
    "My collection",
    2D,
    DateTimeHelper.fromRfc8601DateTime("2021-05-20T16:15:22-04:00"),
    DateTimeHelper.fromRfc8601DateTime("2021-06-10T13:26:09-04:00"),
    Visibility.ENUM_PUBLIC,
    new CatalogCollectionRoleAssignments.Builder(
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
    .build()
)
.coverAsset(new CatalogCollectionItem.Builder(
        "123",
        new Asset.Builder(
            Type.IMAGE
        )
        .id("1690105108")
        .name("Young couple playing tennis at the court")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build(),
        DateTimeHelper.fromRfc8601DateTime("2021-06-10T13:26:09-04:00")
    )
    .collectionIds(Arrays.asList(
            "collection_ids5",
            "collection_ids6"
        ))
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

