
# Remove Catalog Collection Item

*This model accepts additional fields of type Object.*

## Structure

`RemoveCatalogCollectionItem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | - | String getId() | setId(String id) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.RemoveCatalogCollectionItem;
import java.io.IOException;

RemoveCatalogCollectionItem removeCatalogCollectionItem = new RemoveCatalogCollectionItem.Builder(
    "123"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

