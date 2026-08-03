
# Search Entities Response

The response to a request for keyword analysis

*This model accepts additional fields of type Object.*

## Structure

`SearchEntitiesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Keywords` | `List<String>` | Optional | The top keywords from the submitted text | List<String> getKeywords() | setKeywords(List<String> keywords) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.SearchEntitiesResponse;
import java.io.IOException;
import java.util.Arrays;

SearchEntitiesResponse searchEntitiesResponse = new SearchEntitiesResponse.Builder()
    .keywords(Arrays.asList(
        "planting",
        "flowers",
        "springtime",
        "beautiful"
    ))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

