
# Collection Item

Metadata about an item that is part of a collection

*This model accepts additional fields of type Object.*

## Structure

`CollectionItem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AddedTime` | `LocalDateTime` | Optional | The date the item was added to the collection | LocalDateTime getAddedTime() | setAddedTime(LocalDateTime addedTime) |
| `Id` | `String` | Required | ID of the item | String getId() | setId(String id) |
| `MediaType` | `String` | Optional | The media type of the item, such as image, video, or audio | String getMediaType() | setMediaType(String mediaType) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.CollectionItem;
import java.io.IOException;

CollectionItem collectionItem = new CollectionItem.Builder(
    "1690105108"
)
.addedTime(DateTimeHelper.fromRfc8601DateTime("2020-05-29T12:10:22-05:00"))
.mediaType("image")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

