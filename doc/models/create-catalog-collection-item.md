
# Create Catalog Collection Item

*This model accepts additional fields of type Object.*

## Structure

`CreateCatalogCollectionItem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Asset` | [`Asset4`](../../doc/models/asset-4.md) | Required | - | Asset4 getAsset() | setAsset(Asset4 asset) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Asset4;
import com.shutterstock.api.models.CreateCatalogCollectionItem;
import java.io.IOException;

CreateCatalogCollectionItem createCatalogCollectionItem = new CreateCatalogCollectionItem.Builder(
    new Asset4.Builder(
        "image"
    )
    .id("1690105108")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build()
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

