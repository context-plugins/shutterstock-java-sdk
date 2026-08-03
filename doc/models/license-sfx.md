
# License Sfx

*This model accepts additional fields of type Object.*

## Structure

`LicenseSfx`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `SfxId` | `String` | Required | ID of the sounds effect being licensed | String getSfxId() | setSfxId(String sfxId) |
| `AudioLayout` | [`AudioLayout`](../../doc/models/audio-layout.md) | Optional | - | AudioLayout getAudioLayout() | setAudioLayout(AudioLayout audioLayout) |
| `Format` | [`Format11`](../../doc/models/format-11.md) | Optional | - | Format11 getFormat() | setFormat(Format11 format) |
| `SearchId` | `String` | Optional | ID of the search that led to this licensing event | String getSearchId() | setSearchId(String searchId) |
| `SubscriptionId` | `String` | Required | ID of the subscription to use for the download. | String getSubscriptionId() | setSubscriptionId(String subscriptionId) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.AudioLayout;
import com.shutterstock.api.models.Format11;
import com.shutterstock.api.models.LicenseSfx;
import java.io.IOException;

LicenseSfx licenseSfx = new LicenseSfx.Builder(
    "123456789",
    "s12345678"
)
.audioLayout(AudioLayout.AMBISONIC)
.format(Format11.WAV)
.searchId("search_id6")
.additionalProperty("metadata", ApiHelper.deserialize("{\"customer_id\":\"12345\",\"geo_location\":\"US\",\"number_viewed\":\"15\",\"search_term\":\"dog\"}"))
.additionalProperty("show_modal", ApiHelper.deserialize("true"))
.additionalProperty("size", ApiHelper.deserialize("\"ambisonic\""))
.build();
```

