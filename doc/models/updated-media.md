
# Updated Media

Information about a piece of updated media

*This model accepts additional fields of type Object.*

## Structure

`UpdatedMedia`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | ID of the media | String getId() | setId(String id) |
| `UpdatedTime` | `LocalDateTime` | Required | Date that the media was updated | LocalDateTime getUpdatedTime() | setUpdatedTime(LocalDateTime updatedTime) |
| `Updates` | `List<String>` | Required | Types of updates that were made to the piece of media | List<String> getUpdates() | setUpdates(List<String> updates) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.UpdatedMedia;
import java.io.IOException;
import java.util.Arrays;

UpdatedMedia updatedMedia = new UpdatedMedia.Builder(
    "123456789",
    DateTimeHelper.fromRfc8601DateTime("2020-05-29T12:10:22-05:00"),
    Arrays.asList(
        "addition",
        "edit"
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

