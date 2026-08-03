
# Collection Update Request

Collection update request

*This model accepts additional fields of type Object.*

## Structure

`CollectionUpdateRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Name` | `String` | Required | The new name of the collection | String getName() | setName(String name) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.CollectionUpdateRequest;
import java.io.IOException;

CollectionUpdateRequest collectionUpdateRequest = new CollectionUpdateRequest.Builder(
    "My collection with a new name"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

