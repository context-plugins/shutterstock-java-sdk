
# Cookie

Cookie object

*This model accepts additional fields of type Object.*

## Structure

`Cookie`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Name` | `String` | Required | The name of the cookie | String getName() | setName(String name) |
| `Value` | `String` | Required | The value of the cookie | String getValue() | setValue(String value) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Cookie;
import java.io.IOException;

Cookie cookie = new Cookie.Builder(
    "The name of the cookie",
    "The value of the cookie"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

