
# Download History Media Details

Information about the downloaded media

*This model accepts additional fields of type Object.*

## Structure

`DownloadHistoryMediaDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Format` | [`DownloadHistoryFormatDetails`](../../doc/models/download-history-format-details.md) | Optional | Information about the format of a download | DownloadHistoryFormatDetails getFormat() | setFormat(DownloadHistoryFormatDetails format) |
| `Id` | `String` | Required | ID of the download history media details | String getId() | setId(String id) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.DownloadHistoryFormatDetails;
import com.shutterstock.api.models.DownloadHistoryMediaDetails;
import java.io.IOException;

DownloadHistoryMediaDetails downloadHistoryMediaDetails = new DownloadHistoryMediaDetails.Builder(
    "1234567"
)
.format(new DownloadHistoryFormatDetails.Builder()
        .format("jpg")
        .size("medium")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

