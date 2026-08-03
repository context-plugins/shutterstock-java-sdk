
# Audio Url

Audio License URL object

*This model accepts additional fields of type Object.*

## Structure

`AudioUrl`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Url` | `String` | Required | URL that can be used to download the unwatermarked, licensed asset | String getUrl() | setUrl(String url) |
| `ShortsLoopsStems` | `String` | Optional | URL that can be used to download the .zip file containing shorts, loops, and stems | String getShortsLoopsStems() | setShortsLoopsStems(String shortsLoopsStems) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.AudioUrl;
import java.io.IOException;

AudioUrl audioUrl = new AudioUrl.Builder(
    "https://download.shutterstock.com/gatekeeper/[random-characters]/shutterstock_59656357.jpg"
)
.shortsLoopsStems("shorts_loops_stems2")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

