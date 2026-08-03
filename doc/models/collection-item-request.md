
# Collection Item Request

Request to get a list of items in a collection

*This model accepts additional fields of type Object.*

## Structure

`CollectionItemRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Items` | [`List<CollectionItem>`](../../doc/models/collection-item.md) | Required | List of items | List<CollectionItem> getItems() | setItems(List<CollectionItem> items) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.CollectionItem;
import com.shutterstock.api.models.CollectionItemRequest;
import java.io.IOException;
import java.util.Arrays;

CollectionItemRequest collectionItemRequest = new CollectionItemRequest.Builder(
    Arrays.asList(
        new CollectionItem.Builder(
            "1690105108"
        )
        .addedTime(DateTimeHelper.fromRfc8601DateTime("2020-05-29T12:10:22-05:00"))
        .mediaType("image")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

