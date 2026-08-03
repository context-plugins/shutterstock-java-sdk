
# License Image Result

The response to a licensing request for an image

*This model accepts additional fields of type Object.*

## Structure

`LicenseImageResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AllotmentCharge` | `Integer` | Optional | Number of credits that this licensing event used | Integer getAllotmentCharge() | setAllotmentCharge(Integer allotmentCharge) |
| `Download` | [`Download2`](../../doc/models/download-2.md) | Optional | Information that is needed to download the image | Download2 getDownload() | setDownload(Download2 download) |
| `Error` | `String` | Optional | Error message, appears only if there was an error | String getError() | setError(String error) |
| `ImageId` | `String` | Required | Image ID that was licensed | String getImageId() | setImageId(String imageId) |
| `LicenseId` | `String` | Optional | ID of the license event | String getLicenseId() | setLicenseId(String licenseId) |
| `Price` | [`Price1`](../../doc/models/price-1.md) | Optional | Wholesale price information; only for rev-share partners | Price1 getPrice() | setPrice(Price1 price) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Download2;
import com.shutterstock.api.models.LicenseImageResult;
import com.shutterstock.api.models.Price1;
import java.io.IOException;

LicenseImageResult licenseImageResult = new LicenseImageResult.Builder(
    "59656357"
)
.allotmentCharge(1)
.download(new Download2.Builder(
        "https://download.shutterstock.com/gatekeeper/[random-characters]/shutterstock_59656357.jpg"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.error("error6")
.licenseId("license_id8")
.price(new Price1.Builder()
        .localAmount(12.34D)
        .localCurrency("EUR")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

