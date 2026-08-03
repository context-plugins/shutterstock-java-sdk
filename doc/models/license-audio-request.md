
# License Audio Request

Audio license request data

*This model accepts additional fields of type Object.*

## Structure

`LicenseAudioRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Audio` | [`List<LicenseAudio>`](../../doc/models/license-audio.md) | Required | List of audio tracks to license<br><br>**Constraints**: *Maximum Items*: `50` | List<LicenseAudio> getAudio() | setAudio(List<LicenseAudio> audio) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.License1;
import com.shutterstock.api.models.LicenseAudio;
import com.shutterstock.api.models.LicenseAudioRequest;
import java.io.IOException;
import java.util.Arrays;

LicenseAudioRequest licenseAudioRequest = new LicenseAudioRequest.Builder(
    Arrays.asList(
        new LicenseAudio.Builder(
            "591623"
        )
        .license(License1.AUDIO_PLATFORM)
        .searchId("search_id8")
        .additionalProperty("metadata", ApiHelper.deserialize("{\"customer_id\":\"12345\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

