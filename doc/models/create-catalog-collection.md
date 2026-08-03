
# Create Catalog Collection

*This model accepts additional fields of type Object.*

## Structure

`CreateCatalogCollection`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Name` | `String` | Required | **Constraints**: *Minimum Length*: `1`, *Maximum Length*: `100000` | String getName() | setName(String name) |
| `Visibility` | [`Visibility`](../../doc/models/visibility.md) | Optional | **Default**: `Visibility.ENUM_PRIVATE` | Visibility getVisibility() | setVisibility(Visibility visibility) |
| `Items` | [`List<CreateCatalogCollectionItem>`](../../doc/models/create-catalog-collection-item.md) | Optional | **Constraints**: *Maximum Items*: `50` | List<CreateCatalogCollectionItem> getItems() | setItems(List<CreateCatalogCollectionItem> items) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Asset4;
import com.shutterstock.api.models.CreateCatalogCollection;
import com.shutterstock.api.models.CreateCatalogCollectionItem;
import com.shutterstock.api.models.Visibility;
import java.io.IOException;
import java.util.Arrays;

CreateCatalogCollection createCatalogCollection = new CreateCatalogCollection.Builder(
    "New Collection"
)
.visibility(Visibility.ENUM_PUBLIC)
.items(Arrays.asList(
        new CreateCatalogCollectionItem.Builder(
            new Asset4.Builder(
                "image"
            )
            .id("1690105108")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

