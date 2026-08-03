
# Download History

Information about a downloaded media item. Applicable for all media types, only one of 'audio', 'image' or 'video' will be in a single DownloadHistory object

*This model accepts additional fields of type Object.*

## Structure

`DownloadHistory`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Audio` | [`DownloadHistoryMediaDetails`](../../doc/models/download-history-media-details.md) | Optional | Information about the downloaded media | DownloadHistoryMediaDetails getAudio() | setAudio(DownloadHistoryMediaDetails audio) |
| `DownloadTime` | `LocalDateTime` | Required | Date the media was downloaded the first time | LocalDateTime getDownloadTime() | setDownloadTime(LocalDateTime downloadTime) |
| `Id` | `String` | Required | ID of the download | String getId() | setId(String id) |
| `Image` | [`DownloadHistoryMediaDetails`](../../doc/models/download-history-media-details.md) | Optional | Information about the downloaded media | DownloadHistoryMediaDetails getImage() | setImage(DownloadHistoryMediaDetails image) |
| `IsDownloadable` | `Boolean` | Optional | Specifies if the media is downloadable via its respective downloads endpoint | Boolean getIsDownloadable() | setIsDownloadable(Boolean isDownloadable) |
| `License` | `String` | Required | The name of the license of this download | String getLicense() | setLicense(String license) |
| `Metadata` | `Object` | Optional | The metadata that was passed in the original licensing request | Object getMetadata() | setMetadata(Object metadata) |
| `SubscriptionId` | `String` | Optional | ID of the subscription used to perform this download | String getSubscriptionId() | setSubscriptionId(String subscriptionId) |
| `User` | [`DownloadHistoryUserDetails`](../../doc/models/download-history-user-details.md) | Optional | Information about a user | DownloadHistoryUserDetails getUser() | setUser(DownloadHistoryUserDetails user) |
| `Video` | [`DownloadHistoryMediaDetails`](../../doc/models/download-history-media-details.md) | Optional | Information about the downloaded media | DownloadHistoryMediaDetails getVideo() | setVideo(DownloadHistoryMediaDetails video) |
| `Revshare` | [`DownloadHistoryRevshareDetails`](../../doc/models/download-history-revshare-details.md) | Optional | Pricing information for revenue-sharing transactions | DownloadHistoryRevshareDetails getRevshare() | setRevshare(DownloadHistoryRevshareDetails revshare) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.DownloadHistory;
import com.shutterstock.api.models.DownloadHistoryFormatDetails;
import com.shutterstock.api.models.DownloadHistoryMediaDetails;
import com.shutterstock.api.models.DownloadHistoryUserDetails;
import java.io.IOException;

DownloadHistory downloadHistory = new DownloadHistory.Builder(
    DateTimeHelper.fromRfc8601DateTime("2021-05-20T20:31:46.000Z"),
    "a24499ca3ccd912a6d8316d45f953ef092",
    "standard"
)
.audio(null)
.image(new DownloadHistoryMediaDetails.Builder(
        "1234567"
    )
    .format(new DownloadHistoryFormatDetails.Builder()
            .format("format0")
            .size("medium")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build())
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.isDownloadable(true)
.metadata(ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.subscriptionId("s12345678")
.user(new DownloadHistoryUserDetails.Builder(
        "jdoe"
    )
    .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

