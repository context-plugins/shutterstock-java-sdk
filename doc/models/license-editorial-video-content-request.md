
# License Editorial Video Content Request

License editorial video content request

*This model accepts additional fields of type Object.*

## Structure

`LicenseEditorialVideoContentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Country` | [`LicenseEditorialVideoContentRequestCountry`](../../doc/models/containers/license-editorial-video-content-request-country.md) | Required | This is a container for one-of cases. | LicenseEditorialVideoContentRequestCountry getCountry() | setCountry(LicenseEditorialVideoContentRequestCountry country) |
| `Editorial` | [`List<LicenseEditorialVideoContent>`](../../doc/models/license-editorial-video-content.md) | Required | Editorial content to license | List<LicenseEditorialVideoContent> getEditorial() | setEditorial(List<LicenseEditorialVideoContent> editorial) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Country;
import com.shutterstock.api.models.License3;
import com.shutterstock.api.models.LicenseEditorialVideoContent;
import com.shutterstock.api.models.LicenseEditorialVideoContentRequest;
import com.shutterstock.api.models.Size2;
import com.shutterstock.api.models.containers.LicenseEditorialVideoContentRequestCountry;
import java.io.IOException;
import java.util.Arrays;

LicenseEditorialVideoContentRequest licenseEditorialVideoContentRequest = new LicenseEditorialVideoContentRequest.Builder(
    LicenseEditorialVideoContentRequestCountry.fromCountry(
        Country.USA
    ),
    Arrays.asList(
        new LicenseEditorialVideoContent.Builder(
            "10679854a",
            License3.PREMIER_EDITORIAL_VIDEO_DIGITAL_ONLY
        )
        .metadata(ApiHelper.deserialize("{\"purchase_order\":\"12345\"}"))
        .size(Size2.ORIGINAL)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

