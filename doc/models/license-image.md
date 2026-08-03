
# License Image

Data required to license an image

*This model accepts additional fields of type Object.*

## Structure

`LicenseImage`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AuthCookie` | [`Cookie`](../../doc/models/cookie.md) | Optional | Cookie object | Cookie getAuthCookie() | setAuthCookie(Cookie authCookie) |
| `EditorialAcknowledgement` | `Boolean` | Optional | Set to true to acknowledge the editorial agreement | Boolean getEditorialAcknowledgement() | setEditorialAcknowledgement(Boolean editorialAcknowledgement) |
| `Format` | [`Format7`](../../doc/models/format-7.md) | Optional | (Deprecated) Image format to download<br><br>**Default**: `Format7.JPG` | Format7 getFormat() | setFormat(Format7 format) |
| `ImageId` | `String` | Required | Image ID | String getImageId() | setImageId(String imageId) |
| `Metadata` | `Object` | Optional | Additional information for license requests for enterprise accounts and API subscriptions, 4 fields maximum; which fields are required is set by the account holder | Object getMetadata() | setMetadata(Object metadata) |
| `Price` | `Double` | Optional | For revenue-sharing transactions, the final cost to the end customer as a floating-point number in the transaction currency, such as 12.34 | Double getPrice() | setPrice(Double price) |
| `SearchId` | `String` | Optional | ID of the search that led to this licensing transaction | String getSearchId() | setSearchId(String searchId) |
| `ShowModal` | `Boolean` | Optional | (Deprecated) | Boolean getShowModal() | setShowModal(Boolean showModal) |
| `Size` | [`Size4`](../../doc/models/size-4.md) | Optional | Image size to download | Size4 getSize() | setSize(Size4 size) |
| `CustomDimensions` | [`CustomSizeDimensions`](../../doc/models/custom-size-dimensions.md) | Optional | A custom height or a custom width to resize the image to, but not both (experimental) | CustomSizeDimensions getCustomDimensions() | setCustomDimensions(CustomSizeDimensions customDimensions) |
| `SubscriptionId` | `String` | Optional | ID of the subscription to use for the download. | String getSubscriptionId() | setSubscriptionId(String subscriptionId) |
| `VerificationCode` | `String` | Optional | (Deprecated) | String getVerificationCode() | setVerificationCode(String verificationCode) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Format7;
import com.shutterstock.api.models.LicenseImage;
import com.shutterstock.api.models.Size4;
import java.io.IOException;

LicenseImage licenseImage = new LicenseImage.Builder(
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
.build();
```

