
# Rights

*This model accepts additional fields of type Object.*

## Structure

`Rights`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Countries` | `String` | Optional | - | String getCountries() | setCountries(String countries) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Rights;
import java.io.IOException;

Rights rights = new Rights.Builder()
    .countries("countries0")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

