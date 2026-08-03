
# Test Echo

Text to echo in the response

*This model accepts additional fields of type Object.*

## Structure

`TestEcho`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Text` | `String` | Optional | - | String getText() | setText(String text) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.TestEcho;
import java.io.IOException;

TestEcho testEcho = new TestEcho.Builder()
    .text("Test string")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

