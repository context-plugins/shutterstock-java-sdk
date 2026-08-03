
# Remove Catalog Collection Items

*This model accepts additional fields of type Object.*

## Structure

`RemoveCatalogCollectionItems`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Items` | [`List<RemoveCatalogCollectionItem>`](../../doc/models/remove-catalog-collection-item.md) | Required | **Constraints**: *Minimum Items*: `1`, *Maximum Items*: `50` | List<RemoveCatalogCollectionItem> getItems() | setItems(List<RemoveCatalogCollectionItem> items) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.RemoveCatalogCollectionItem;
import com.shutterstock.api.models.RemoveCatalogCollectionItems;
import java.io.IOException;
import java.util.Arrays;

RemoveCatalogCollectionItems removeCatalogCollectionItems = new RemoveCatalogCollectionItems.Builder(
    Arrays.asList(
        new RemoveCatalogCollectionItem.Builder(
            "123"
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

