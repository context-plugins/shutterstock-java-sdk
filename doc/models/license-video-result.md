
# License Video Result

The response to a licensing request for a video

*This model accepts additional fields of type Object.*

## Structure

`LicenseVideoResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AllotmentCharge` | `Integer` | Optional | Number of credits that this licensing event used | Integer getAllotmentCharge() | setAllotmentCharge(Integer allotmentCharge) |
| `Download` | [`Url`](../../doc/models/url.md) | Optional | URL object | Url getDownload() | setDownload(Url download) |
| `LicenseId` | `String` | Optional | ID of the license event | String getLicenseId() | setLicenseId(String licenseId) |
| `Error` | `String` | Optional | Potential error that occurred during licensing | String getError() | setError(String error) |
| `Price` | [`Price2`](../../doc/models/price-2.md) | Optional | Wholesale price information; only for rev-share partners only | Price2 getPrice() | setPrice(Price2 price) |
| `VideoId` | `String` | Required | ID of the video that was licensed | String getVideoId() | setVideoId(String videoId) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.LicenseVideoResult;
import com.shutterstock.api.models.Price2;
import com.shutterstock.api.models.Url;
import java.io.IOException;

LicenseVideoResult licenseVideoResult = new LicenseVideoResult.Builder(
    "123456789"
)
.allotmentCharge(1)
.download(new Url.Builder(
        "https://download.shutterstock.com/gatekeeper/[random-characters]/shutterstock_59656357.mp4"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.licenseId("license_id6")
.error("error4")
.price(new Price2.Builder()
        .localAmount(12.34D)
        .localCurrency("EUR")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

