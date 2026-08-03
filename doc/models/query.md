
# Query

Query as included in the request

*This model accepts additional fields of type Object.*

## Structure

`Query`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `int` | Required | Integer ID that was passed in the request | int getId() | setId(int id) |
| `Tag` | `List<String>` | Optional | List of tags that were passed in the request | List<String> getTag() | setTag(List<String> tag) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Query;
import java.io.IOException;
import java.util.Arrays;

Query query = new Query.Builder(
    123456
)
.tag(Arrays.asList(
        "string"
    ))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

