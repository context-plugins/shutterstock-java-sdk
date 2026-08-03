
# Video Size Details

Video asset information

*This model accepts additional fields of type Object.*

## Structure

`VideoSizeDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `DisplayName` | `String` | Optional | Display name of this video size | String getDisplayName() | setDisplayName(String displayName) |
| `FileSize` | `Integer` | Optional | File size (in bytes) of this video size | Integer getFileSize() | setFileSize(Integer fileSize) |
| `Format` | `String` | Optional | Format of this video size | String getFormat() | setFormat(String format) |
| `Fps` | `Double` | Optional | Frames per second of this video size | Double getFps() | setFps(Double fps) |
| `Height` | `Integer` | Optional | Height of this video size | Integer getHeight() | setHeight(Integer height) |
| `IsLicensable` | `Boolean` | Optional | Whether or not videos can be licensed in this video size | Boolean getIsLicensable() | setIsLicensable(Boolean isLicensable) |
| `Width` | `Integer` | Optional | Width of this video size | Integer getWidth() | setWidth(Integer width) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.VideoSizeDetails;
import java.io.IOException;

VideoSizeDetails videoSizeDetails = new VideoSizeDetails.Builder()
    .displayName("Original HD")
    .fileSize(110359552)
    .format("avc1")
    .fps(29.97D)
    .height(1080)
    .isLicensable(true)
    .width(1920)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

