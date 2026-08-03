
# License Video Request

List of videos to license

*This model accepts additional fields of type Object.*

## Structure

`LicenseVideoRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Videos` | [`List<LicenseVideo>`](../../doc/models/license-video.md) | Required | Videos to license<br><br>**Constraints**: *Maximum Items*: `50` | List<LicenseVideo> getVideos() | setVideos(List<LicenseVideo> videos) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.LicenseVideo;
import com.shutterstock.api.models.LicenseVideoRequest;
import com.shutterstock.api.models.Size8;
import java.io.IOException;
import java.util.Arrays;

LicenseVideoRequest licenseVideoRequest = new LicenseVideoRequest.Builder(
    Arrays.asList(
        new LicenseVideo.Builder(
            "2140697"
        )
        .authCookie(null)
        .editorialAcknowledgement(false)
        .metadata(ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .price(63.12D)
        .searchId("search_id6")
        .size(Size8.HD)
        .subscriptionId("s12345678")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

