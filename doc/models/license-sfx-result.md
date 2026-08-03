
# License Sfx Result

The response to a licensing request for an sound effects

*This model accepts additional fields of type Object.*

## Structure

`LicenseSfxResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AllotmentCharge` | `Integer` | Optional | Number of credits that this licensing event used | Integer getAllotmentCharge() | setAllotmentCharge(Integer allotmentCharge) |
| `Download` | [`Download6`](../../doc/models/download-6.md) | Optional | Information that is needed to download the sound effects | Download6 getDownload() | setDownload(Download6 download) |
| `Error` | `String` | Optional | Error message, appears only if there was an error | String getError() | setError(String error) |
| `SfxId` | `String` | Required | Sound effects ID that was licensed | String getSfxId() | setSfxId(String sfxId) |
| `LicenseId` | `String` | Optional | ID of the license event | String getLicenseId() | setLicenseId(String licenseId) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Download6;
import com.shutterstock.api.models.LicenseSfxResult;
import java.io.IOException;

LicenseSfxResult licenseSfxResult = new LicenseSfxResult.Builder(
    "59656357"
)
.allotmentCharge(1)
.download(new Download6.Builder(
        "https://download.shutterstock.com/gatekeeper/[random-characters]/shutterstock_59656357.wav"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.error("error0")
.licenseId("license_id2")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

