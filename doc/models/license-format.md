
# License Format

Description of a license

*This model accepts additional fields of type Object.*

## Structure

`LicenseFormat`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Description` | `String` | Optional | Description of the license | String getDescription() | setDescription(String description) |
| `Format` | `String` | Optional | Format or extension of the media, such as mpeg for videos or jpeg for images | String getFormat() | setFormat(String format) |
| `MediaType` | [`MediaType`](../../doc/models/media-type.md) | Optional | Media type of the license | MediaType getMediaType() | setMediaType(MediaType mediaType) |
| `MinResolution` | `Integer` | Optional | Width of the media, in pixels, allowed by this license | Integer getMinResolution() | setMinResolution(Integer minResolution) |
| `Size` | `String` | Optional | Keyword that details the size of the media, such as hd or sd for video, huge or vector for images | String getSize() | setSize(String size) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.LicenseFormat;
import com.shutterstock.api.models.MediaType;
import java.io.IOException;

LicenseFormat licenseFormat = new LicenseFormat.Builder()
    .description("Med")
    .format("jpg")
    .mediaType(MediaType.IMAGE)
    .minResolution(1000)
    .size("medium")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

