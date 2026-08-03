
# License Editorial Content

Individual editorial content to license

*This model accepts additional fields of type Object.*

## Structure

`LicenseEditorialContent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `EditorialId` | `String` | Required | Editorial ID | String getEditorialId() | setEditorialId(String editorialId) |
| `License` | `String` | Required | License agreement to use for licensing | String getLicense() | setLicense(String license) |
| `Metadata` | `Object` | Optional | Additional information for license requests for enterprise accounts and API subscriptions, 4 fields maximum; which fields are required is set by the account holder | Object getMetadata() | setMetadata(Object metadata) |
| `Size` | [`Size`](../../doc/models/size.md) | Optional | Asset size to download<br><br>**Default**: `Size.ORIGINAL` | Size getSize() | setSize(Size size) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.LicenseEditorialContent;
import com.shutterstock.api.models.Size;
import java.io.IOException;

LicenseEditorialContent licenseEditorialContent = new LicenseEditorialContent.Builder(
    "10687730b",
    "premier_editorial_comp"
)
.metadata(ApiHelper.deserialize("{\"customer_id\":\"12345\",\"geo_location\":\"US\",\"number_viewed\":\"15\",\"search_term\":\"dog\"}"))
.size(Size.ORIGINAL)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

