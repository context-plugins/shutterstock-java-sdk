
# License Audio

An audio track in a licensing request

*This model accepts additional fields of type Object.*

## Structure

`LicenseAudio`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AudioId` | `String` | Required | ID of the track being licensed | String getAudioId() | setAudioId(String audioId) |
| `License` | [`License1`](../../doc/models/license-1.md) | Optional | Type of license | License1 getLicense() | setLicense(License1 license) |
| `SearchId` | `String` | Optional | ID of the search that led to this licensing event | String getSearchId() | setSearchId(String searchId) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.License1;
import com.shutterstock.api.models.LicenseAudio;
import java.io.IOException;

LicenseAudio licenseAudio = new LicenseAudio.Builder(
    "123456789"
)
.license(License1.AUDIO_PLATFORM)
.searchId("987654321")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

