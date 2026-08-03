
# License Image Request

Image license request data

*This model accepts additional fields of type Object.*

## Structure

`LicenseImageRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Images` | [`List<LicenseImageRequestImages>`](../../doc/models/containers/license-image-request-images.md) | Required | This is List of a container for any-of cases.<br><br>**Constraints**: *Maximum Items*: `50` | List<LicenseImageRequestImages> getImages() | setImages(List<LicenseImageRequestImages> images) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Format7;
import com.shutterstock.api.models.LicenseImage;
import com.shutterstock.api.models.LicenseImageRequest;
import com.shutterstock.api.models.Size4;
import com.shutterstock.api.models.containers.LicenseImageRequestImages;
import java.io.IOException;
import java.util.Arrays;

LicenseImageRequest licenseImageRequest = new LicenseImageRequest.Builder(
    Arrays.asList(
        LicenseImageRequestImages.fromLicenseImage(
            new LicenseImage.Builder(
                "123456789"
            )
            .authCookie(null)
            .editorialAcknowledgement(true)
            .format(Format7.JPG)
            .metadata(ApiHelper.deserialize("{\"customer_id\":\"12345\",\"geo_location\":\"US\",\"number_viewed\":\"15\",\"search_term\":\"dog\"}"))
            .price(12.34D)
            .showModal(true)
            .size(Size4.SMALL)
            .subscriptionId("s12345678")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        )
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

