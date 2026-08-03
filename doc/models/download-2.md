
# Download 2

Information that is needed to download the image

*This model accepts additional fields of type Object.*

## Structure

`Download2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Url` | `String` | Required | URL that can be used to download the unwatermarked, licensed asset | String getUrl() | setUrl(String url) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Download2;
import java.io.IOException;

Download2 download2 = new Download2.Builder(
    "https://download.shutterstock.com/gatekeeper/[random-characters]/shutterstock_59656357.jpg"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

