
# Catalog Collection Item

Metadata about an item that is part of a collection

*This model accepts additional fields of type Object.*

## Structure

`CatalogCollectionItem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | - | String getId() | setId(String id) |
| `Asset` | [`Asset`](../../doc/models/asset.md) | Required | - | Asset getAsset() | setAsset(Asset asset) |
| `CreatedTime` | `LocalDateTime` | Required | - | LocalDateTime getCreatedTime() | setCreatedTime(LocalDateTime createdTime) |
| `CollectionIds` | `List<String>` | Optional | The collection IDs that this asset belongs to | List<String> getCollectionIds() | setCollectionIds(List<String> collectionIds) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Asset;
import com.shutterstock.api.models.CatalogCollectionItem;
import com.shutterstock.api.models.Type;
import java.io.IOException;
import java.util.Arrays;

CatalogCollectionItem catalogCollectionItem = new CatalogCollectionItem.Builder(
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
        "126351028"
    ))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

