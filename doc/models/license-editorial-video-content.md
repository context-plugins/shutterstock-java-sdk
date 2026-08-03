
# License Editorial Video Content

Individual editorial video content to license

*This model accepts additional fields of type Object.*

## Structure

`LicenseEditorialVideoContent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `EditorialId` | `String` | Required | Editorial ID | String getEditorialId() | setEditorialId(String editorialId) |
| `License` | [`License3`](../../doc/models/license-3.md) | Required | License agreement to use for licensing | License3 getLicense() | setLicense(License3 license) |
| `Metadata` | `Object` | Optional | Additional information for license requests for enterprise accounts and API subscriptions, 4 fields maximum; which fields are required is set by the account holder | Object getMetadata() | setMetadata(Object metadata) |
| `Size` | [`Size2`](../../doc/models/size-2.md) | Optional | Asset size to download<br><br>**Default**: `Size2.ORIGINAL` | Size2 getSize() | setSize(Size2 size) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.License3;
import com.shutterstock.api.models.LicenseEditorialVideoContent;
import com.shutterstock.api.models.Size2;
import java.io.IOException;

LicenseEditorialVideoContent licenseEditorialVideoContent = new LicenseEditorialVideoContent.Builder(
    "10679854a",
    License3.PREMIER_EDITORIAL_VIDEO_DIGITAL_ONLY
)
.metadata(ApiHelper.deserialize("{\"purchase_order\":\"12345\"}"))
.size(Size2.ORIGINAL)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

