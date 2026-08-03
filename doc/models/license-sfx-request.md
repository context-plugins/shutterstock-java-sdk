
# License Sfx Request

License sounds effect asset request body

*This model accepts additional fields of type Object.*

## Structure

`LicenseSfxRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `SoundEffects` | [`List<LicenseSfx>`](../../doc/models/license-sfx.md) | Required | Sound effects to license for | List<LicenseSfx> getSoundEffects() | setSoundEffects(List<LicenseSfx> soundEffects) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.AudioLayout;
import com.shutterstock.api.models.Format11;
import com.shutterstock.api.models.LicenseSfx;
import com.shutterstock.api.models.LicenseSfxRequest;
import java.io.IOException;
import java.util.Arrays;

LicenseSfxRequest licenseSfxRequest = new LicenseSfxRequest.Builder(
    Arrays.asList(
        new LicenseSfx.Builder(
            "123456789",
            "s12345678"
        )
        .audioLayout(AudioLayout.AMBISONIC)
        .format(Format11.WAV)
        .searchId("search_id6")
        .additionalProperty("metadata", ApiHelper.deserialize("{\"customer_id\":\"12345\",\"geo_location\":\"US\",\"number_viewed\":\"15\",\"search_term\":\"dog\"}"))
        .additionalProperty("show_modal", ApiHelper.deserialize("true"))
        .additionalProperty("size", ApiHelper.deserialize("\"ambisonic\""))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

