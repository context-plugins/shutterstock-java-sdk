
# Collection Create Request

Collection creation request

*This model accepts additional fields of type Object.*

## Structure

`CollectionCreateRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Name` | `String` | Required | The name of the collection | String getName() | setName(String name) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.CollectionCreateRequest;
import java.io.IOException;

CollectionCreateRequest collectionCreateRequest = new CollectionCreateRequest.Builder(
    "Test Collection 19cf"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

