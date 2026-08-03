
# Urls

List of URLs

*This model accepts additional fields of type Object.*

## Structure

`Urls`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Urls` | `List<String>` | Required | URLs | List<String> getUrls() | setUrls(List<String> urls) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Urls;
import java.io.IOException;
import java.util.Arrays;

Urls urls = new Urls.Builder(
    Arrays.asList(
        "string"
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

