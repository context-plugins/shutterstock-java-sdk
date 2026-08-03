
# Image Size Details

Image size information

*This model accepts additional fields of type Object.*

## Structure

`ImageSizeDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `DisplayName` | `String` | Optional | Display name of this image size | String getDisplayName() | setDisplayName(String displayName) |
| `Dpi` | `Integer` | Optional | - | Integer getDpi() | setDpi(Integer dpi) |
| `FileSize` | `Integer` | Optional | File size (in bytes) of this image size | Integer getFileSize() | setFileSize(Integer fileSize) |
| `Format` | `String` | Optional | Format of this image size | String getFormat() | setFormat(String format) |
| `Height` | `Integer` | Optional | Height of this image size | Integer getHeight() | setHeight(Integer height) |
| `IsLicensable` | `Boolean` | Optional | Whether or not this image can be licensed in this image size | Boolean getIsLicensable() | setIsLicensable(Boolean isLicensable) |
| `Width` | `Integer` | Optional | Width of this image size | Integer getWidth() | setWidth(Integer width) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.ImageSizeDetails;
import java.io.IOException;

ImageSizeDetails imageSizeDetails = new ImageSizeDetails.Builder()
    .displayName("Med")
    .dpi(300)
    .fileSize(860200)
    .format("jpg")
    .height(667)
    .isLicensable(true)
    .width(1000)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

