
# Audio Asset Details

Information about a file that is part of an audio asset

*This model accepts additional fields of type Object.*

## Structure

`AudioAssetDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `FileSize` | `Integer` | Optional | File size of the track | Integer getFileSize() | setFileSize(Integer fileSize) |
| `Url` | `String` | Optional | URL the track is available at | String getUrl() | setUrl(String url) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.AudioAssetDetails;
import java.io.IOException;

AudioAssetDetails audioAssetDetails = new AudioAssetDetails.Builder()
    .fileSize(4453197)
    .url("https://ak.picdn.net/shutterstock/audio/442583/preview/preview.mp3")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

