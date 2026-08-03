
# Download History Format Details

Information about the format of a download

*This model accepts additional fields of type Object.*

## Structure

`DownloadHistoryFormatDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Format` | `String` | Optional | The format of the downloaded media | String getFormat() | setFormat(String format) |
| `Size` | `String` | Optional | The size of the downloaded media | String getSize() | setSize(String size) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.DownloadHistoryFormatDetails;
import java.io.IOException;

DownloadHistoryFormatDetails downloadHistoryFormatDetails = new DownloadHistoryFormatDetails.Builder()
    .format("jpg")
    .size("medium")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

