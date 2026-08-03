
# Error

Error object

*This model accepts additional fields of type Object.*

## Structure

`Error`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Code` | `String` | Optional | The error code of this error | String getCode() | setCode(String code) |
| `Data` | `String` | Optional | Debugging information about the error | String getData() | setData(String data) |
| `Items` | `List<Object>` | Optional | A list of items that produced the error | List<Object> getItems() | setItems(List<Object> items) |
| `Message` | `String` | Required | Specific details about this error | String getMessage() | setMessage(String message) |
| `Path` | `String` | Optional | Internal code reference to the source of the error | String getPath() | setPath(String path) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Error;
import java.io.IOException;
import java.util.Arrays;

Error error = new Error.Builder(
    "Invalid type: string should be integer"
)
.code("VALIDATION_INVALID_TYPE")
.data("'10'")
.items(Arrays.asList(
        ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
        ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}")
    ))
.path("$.query.page")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

