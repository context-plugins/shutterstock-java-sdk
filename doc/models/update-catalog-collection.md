
# Update Catalog Collection

*This model accepts additional fields of type Object.*

## Structure

`UpdateCatalogCollection`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Name` | `String` | Optional | **Constraints**: *Minimum Length*: `1`, *Maximum Length*: `100000` | String getName() | setName(String name) |
| `Visibility` | [`Visibility`](../../doc/models/visibility.md) | Optional | - | Visibility getVisibility() | setVisibility(Visibility visibility) |
| `CoverAsset` | [`RemoveCatalogCollectionItem`](../../doc/models/remove-catalog-collection-item.md) | Optional | - | RemoveCatalogCollectionItem getCoverAsset() | setCoverAsset(RemoveCatalogCollectionItem coverAsset) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.RemoveCatalogCollectionItem;
import com.shutterstock.api.models.UpdateCatalogCollection;
import com.shutterstock.api.models.Visibility;
import java.io.IOException;

UpdateCatalogCollection updateCatalogCollection = new UpdateCatalogCollection.Builder()
    .name("My Collection")
    .visibility(Visibility.ENUM_PUBLIC)
    .coverAsset(new RemoveCatalogCollectionItem.Builder(
        "123"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

