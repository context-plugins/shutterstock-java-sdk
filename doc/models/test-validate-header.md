
# Test Validate Header

Validation results

*This model accepts additional fields of type Object.*

## Structure

`TestValidateHeader`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `UserAgent` | `String` | Optional | User agent to expect in the response | String getUserAgent() | setUserAgent(String userAgent) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.TestValidateHeader;
import java.io.IOException;

TestValidateHeader testValidateHeader = new TestValidateHeader.Builder()
    .userAgent("Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/51.0.2704.103 Safari/537.36")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

