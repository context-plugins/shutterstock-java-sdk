
# License Image Vector

Data required to license an image

*This model accepts additional fields of type Object.*

## Structure

`LicenseImageVector`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AuthCookie` | [`Cookie`](../../doc/models/cookie.md) | Optional | Cookie object | Cookie getAuthCookie() | setAuthCookie(Cookie authCookie) |
| `EditorialAcknowledgement` | `Boolean` | Optional | Set to true to acknowledge the editorial agreement | Boolean getEditorialAcknowledgement() | setEditorialAcknowledgement(Boolean editorialAcknowledgement) |
| `Format` | [`Format9`](../../doc/models/format-9.md) | Optional | (Deprecated) Image format to download<br><br>**Default**: `Format9.EPS` | Format9 getFormat() | setFormat(Format9 format) |
| `ImageId` | `String` | Required | Image ID | String getImageId() | setImageId(String imageId) |
| `Metadata` | `Object` | Optional | Additional information for license requests for enterprise accounts and API subscriptions, 4 fields maximum; which fields are required is set by the account holder | Object getMetadata() | setMetadata(Object metadata) |
| `Price` | `Double` | Optional | For revenue-sharing transactions, the final cost to the end customer as a floating-point number in the transaction currency, such as 12.34 | Double getPrice() | setPrice(Double price) |
| `SearchId` | `String` | Optional | ID of the search that led to this licensing transaction | String getSearchId() | setSearchId(String searchId) |
| `ShowModal` | `Boolean` | Optional | (Deprecated) | Boolean getShowModal() | setShowModal(Boolean showModal) |
| `Size` | [`Size6`](../../doc/models/size-6.md) | Optional | Image size to download | Size6 getSize() | setSize(Size6 size) |
| `SubscriptionId` | `String` | Optional | ID of the subscription to use for the download. | String getSubscriptionId() | setSubscriptionId(String subscriptionId) |
| `VerificationCode` | `String` | Optional | (Deprecated) | String getVerificationCode() | setVerificationCode(String verificationCode) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Format9;
import com.shutterstock.api.models.LicenseImageVector;
import com.shutterstock.api.models.Size6;
import java.io.IOException;

LicenseImageVector licenseImageVector = new LicenseImageVector.Builder(
    "123456789"
)
.authCookie(null)
.editorialAcknowledgement(true)
.format(Format9.EPS)
.metadata(ApiHelper.deserialize("{\"customer_id\":\"12345\",\"geo_location\":\"US\",\"number_viewed\":\"15\",\"search_term\":\"dog\"}"))
.price(12.34D)
.showModal(true)
.size(Size6.VECTOR)
.subscriptionId("s12345678")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

