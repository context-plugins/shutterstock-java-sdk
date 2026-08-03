
# License Video

Data required to license a video

*This model accepts additional fields of type Object.*

## Structure

`LicenseVideo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AuthCookie` | [`Cookie`](../../doc/models/cookie.md) | Optional | Cookie object | Cookie getAuthCookie() | setAuthCookie(Cookie authCookie) |
| `EditorialAcknowledgement` | `Boolean` | Optional | Whether or not this item is editorial content | Boolean getEditorialAcknowledgement() | setEditorialAcknowledgement(Boolean editorialAcknowledgement) |
| `Metadata` | `Object` | Optional | Additional information for license requests for enterprise accounts and API subscriptions, 4 fields maximum; which fields are required is set by the account holder | Object getMetadata() | setMetadata(Object metadata) |
| `Price` | `Double` | Optional | Retail price amount as a floating-point number in the transaction currency, such as 12.34; only for rev-share partners | Double getPrice() | setPrice(Double price) |
| `SearchId` | `String` | Optional | ID of the search that led to this licensing event | String getSearchId() | setSearchId(String searchId) |
| `ShowModal` | `Boolean` | Optional | (Deprecated) | Boolean getShowModal() | setShowModal(Boolean showModal) |
| `Size` | [`Size8`](../../doc/models/size-8.md) | Optional | Size of the video being licensed | Size8 getSize() | setSize(Size8 size) |
| `SubscriptionId` | `String` | Optional | ID of the subscription used for this license | String getSubscriptionId() | setSubscriptionId(String subscriptionId) |
| `VideoId` | `String` | Required | ID of the video being licensed | String getVideoId() | setVideoId(String videoId) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.LicenseVideo;
import com.shutterstock.api.models.Size8;
import java.io.IOException;

LicenseVideo licenseVideo = new LicenseVideo.Builder(
    "2140697"
)
.authCookie(null)
.editorialAcknowledgement(false)
.metadata(ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.price(205.28D)
.searchId("search_id2")
.size(Size8.HD)
.subscriptionId("s12345678")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

