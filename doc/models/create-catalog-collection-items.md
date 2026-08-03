
# Create Catalog Collection Items

*This model accepts additional fields of type Object.*

## Structure

`CreateCatalogCollectionItems`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Items` | [`List<CreateCatalogCollectionItem>`](../../doc/models/create-catalog-collection-item.md) | Required | **Constraints**: *Minimum Items*: `1`, *Maximum Items*: `50` | List<CreateCatalogCollectionItem> getItems() | setItems(List<CreateCatalogCollectionItem> items) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Asset4;
import com.shutterstock.api.models.CreateCatalogCollectionItem;
import com.shutterstock.api.models.CreateCatalogCollectionItems;
import java.io.IOException;
import java.util.Arrays;

CreateCatalogCollectionItems createCatalogCollectionItems = new CreateCatalogCollectionItems.Builder(
    Arrays.asList(
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
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

