
# Thumbnail

Image thumbnail information

*This model accepts additional fields of type Object.*

## Structure

`Thumbnail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Height` | `int` | Required | Height in pixels of the image thumbnail | int getHeight() | setHeight(int height) |
| `Url` | `String` | Required | Direct URL to the image | String getUrl() | setUrl(String url) |
| `Width` | `int` | Required | Width in pixels of the image thumbnail | int getWidth() | setWidth(int width) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Thumbnail;
import java.io.IOException;

Thumbnail thumbnail = new Thumbnail.Builder(
    100,
    "https://thumb7.shutterstock.com/thumb_large/250738318/1572478477/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
    150
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

