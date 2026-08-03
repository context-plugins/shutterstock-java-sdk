
# Suggestions

List of search suggestions

*This model accepts additional fields of type Object.*

## Structure

`Suggestions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | `List<String>` | Optional | Search suggestions | List<String> getData() | setData(List<String> data) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Suggestions;
import java.io.IOException;
import java.util.Arrays;

Suggestions suggestions = new Suggestions.Builder()
    .data(Arrays.asList(
        "cat scan",
        "cats and dogs",
        "cats playing",
        "catsuit",
        "cat silhouette",
        "catskills",
        "cats eyes",
        "cat sitting",
        "cat sleeping",
        "cats eye"
    ))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

