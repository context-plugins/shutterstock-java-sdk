
# Roles

*This model accepts additional fields of type Object.*

## Structure

`Roles`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Owners` | [`List<CatalogCollectionRole>`](../../doc/models/catalog-collection-role.md) | Optional | - | List<CatalogCollectionRole> getOwners() | setOwners(List<CatalogCollectionRole> owners) |
| `Editors` | [`List<CatalogCollectionRole>`](../../doc/models/catalog-collection-role.md) | Optional | - | List<CatalogCollectionRole> getEditors() | setEditors(List<CatalogCollectionRole> editors) |
| `Viewers` | [`List<CatalogCollectionRole>`](../../doc/models/catalog-collection-role.md) | Optional | - | List<CatalogCollectionRole> getViewers() | setViewers(List<CatalogCollectionRole> viewers) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.CatalogCollectionRole;
import com.shutterstock.api.models.Roles;
import com.shutterstock.api.models.Type1;
import java.io.IOException;
import java.util.Arrays;

Roles roles = new Roles.Builder()
    .owners(Arrays.asList(
        new CatalogCollectionRole.Builder(
            "id4",
            Type1.USER,
            "email2"
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build(),
        new CatalogCollectionRole.Builder(
            "id4",
            Type1.USER,
            "email2"
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build(),
        new CatalogCollectionRole.Builder(
            "id4",
            Type1.USER,
            "email2"
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ))
    .editors(Arrays.asList(
        new CatalogCollectionRole.Builder(
            "id4",
            Type1.USER,
            "email2"
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ))
    .viewers(Arrays.asList(
        new CatalogCollectionRole.Builder(
            "id8",
            Type1.USER,
            "email8"
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

