
# License Editorial Content Request

License editorial content request

*This model accepts additional fields of type Object.*

## Structure

`LicenseEditorialContentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Country` | [`LicenseEditorialContentRequestCountry`](../../doc/models/containers/license-editorial-content-request-country.md) | Required | This is a container for one-of cases. | LicenseEditorialContentRequestCountry getCountry() | setCountry(LicenseEditorialContentRequestCountry country) |
| `Editorial` | [`List<LicenseEditorialContent>`](../../doc/models/license-editorial-content.md) | Required | Editorial content to license | List<LicenseEditorialContent> getEditorial() | setEditorial(List<LicenseEditorialContent> editorial) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Country;
import com.shutterstock.api.models.LicenseEditorialContent;
import com.shutterstock.api.models.LicenseEditorialContentRequest;
import com.shutterstock.api.models.Size;
import com.shutterstock.api.models.containers.LicenseEditorialContentRequestCountry;
import java.io.IOException;
import java.util.Arrays;

LicenseEditorialContentRequest licenseEditorialContentRequest = new LicenseEditorialContentRequest.Builder(
    LicenseEditorialContentRequestCountry.fromCountry(
        Country.USA
    ),
    Arrays.asList(
        new LicenseEditorialContent.Builder(
            "10687730b",
            "premier_editorial_comp"
        )
        .metadata(ApiHelper.deserialize("{\"customer_id\":\"12345\",\"geo_location\":\"US\",\"number_viewed\":\"15\",\"search_term\":\"dog\"}"))
        .size(Size.ORIGINAL)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

