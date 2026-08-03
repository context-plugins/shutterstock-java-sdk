
# License Editorial Content Result

The response to a licensing request for editorial content

*This model accepts additional fields of type Object.*

## Structure

`LicenseEditorialContentResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AllotmentCharge` | `Integer` | Optional | For pre-paid plans, how many credits were used for the item license | Integer getAllotmentCharge() | setAllotmentCharge(Integer allotmentCharge) |
| `Download` | [`Download2`](../../doc/models/download-2.md) | Optional | Information that is needed to download the image | Download2 getDownload() | setDownload(Download2 download) |
| `EditorialId` | `String` | Required | Editorial ID | String getEditorialId() | setEditorialId(String editorialId) |
| `Error` | `String` | Optional | - | String getError() | setError(String error) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Download2;
import com.shutterstock.api.models.LicenseEditorialContentResult;
import java.io.IOException;

LicenseEditorialContentResult licenseEditorialContentResult = new LicenseEditorialContentResult.Builder(
    "69656358"
)
.allotmentCharge(1)
.download(new Download2.Builder(
        "https://s3-eu-west-1.amazonaws.com/api-downloads.rexfeatures.com/[random-characters].jpg?Expires=1524717323"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.error("error0")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

