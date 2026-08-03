
# Search Entities Request

Search entity request data

*This model accepts additional fields of type Object.*

## Structure

`SearchEntitiesRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Text` | `String` | Required | Plain text to extract keywords from<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `100000` | String getText() | setText(String text) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.SearchEntitiesRequest;
import java.io.IOException;

SearchEntitiesRequest searchEntitiesRequest = new SearchEntitiesRequest.Builder(
    "Planting flowers is a great way to make springtime more beautiful."
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

