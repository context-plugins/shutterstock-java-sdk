
# Sfx Url

Sound effect license URL object

*This model accepts additional fields of type Object.*

## Structure

`SfxUrl`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Url` | `String` | Required | URL that can be used to download the unwatermarked, licensed asset | String getUrl() | setUrl(String url) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.SfxUrl;
import java.io.IOException;

SfxUrl sfxUrl = new SfxUrl.Builder(
    "https://download.shutterstock.com/gatekeeper/[random-characters]/shutterstock_59656357.jpg"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

