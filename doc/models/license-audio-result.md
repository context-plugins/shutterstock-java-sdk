
# License Audio Result

The response to a licensing request for an audio track

*This model accepts additional fields of type Object.*

## Structure

`LicenseAudioResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AudioId` | `String` | Required | ID of the track that was licensed | String getAudioId() | setAudioId(String audioId) |
| `AllotmentCharge` | `Double` | Optional | Number of credits that this licensing event used | Double getAllotmentCharge() | setAllotmentCharge(Double allotmentCharge) |
| `LicenseId` | `String` | Optional | ID of the license event | String getLicenseId() | setLicenseId(String licenseId) |
| `Download` | [`AudioUrl`](../../doc/models/audio-url.md) | Optional | Audio License URL object | AudioUrl getDownload() | setDownload(AudioUrl download) |
| `Error` | `String` | Optional | Error information if applicable | String getError() | setError(String error) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.AudioUrl;
import com.shutterstock.api.models.LicenseAudioResult;
import java.io.IOException;

LicenseAudioResult licenseAudioResult = new LicenseAudioResult.Builder(
    "123456789"
)
.allotmentCharge(1D)
.licenseId("abcdef123456789ghijklmn")
.download(new AudioUrl.Builder(
        "http://download2.dev.shutterstock.com/gatekeeper/abc/original.wav"
    )
    .shortsLoopsStems("shorts_loops_stems4")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.error("error4")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

