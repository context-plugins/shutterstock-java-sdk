
# Editorial Assets

Asset information, including size and thumbnail URLs

*This model accepts additional fields of type Object.*

## Structure

`EditorialAssets`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Original` | [`ImageSizeDetails`](../../doc/models/image-size-details.md) | Optional | Image size information | ImageSizeDetails getOriginal() | setOriginal(ImageSizeDetails original) |
| `Thumb170` | [`Thumbnail`](../../doc/models/thumbnail.md) | Optional | Image thumbnail information | Thumbnail getThumb170() | setThumb170(Thumbnail thumb170) |
| `Thumb220` | [`Thumbnail`](../../doc/models/thumbnail.md) | Optional | Image thumbnail information | Thumbnail getThumb220() | setThumb220(Thumbnail thumb220) |
| `Watermark450` | [`Thumbnail`](../../doc/models/thumbnail.md) | Optional | Image thumbnail information | Thumbnail getWatermark450() | setWatermark450(Thumbnail watermark450) |
| `Watermark1500` | [`Thumbnail`](../../doc/models/thumbnail.md) | Optional | Image thumbnail information | Thumbnail getWatermark1500() | setWatermark1500(Thumbnail watermark1500) |
| `SmallJpg` | [`ImageSizeDetails`](../../doc/models/image-size-details.md) | Optional | Image size information | ImageSizeDetails getSmallJpg() | setSmallJpg(ImageSizeDetails smallJpg) |
| `MediumJpg` | [`ImageSizeDetails`](../../doc/models/image-size-details.md) | Optional | Image size information | ImageSizeDetails getMediumJpg() | setMediumJpg(ImageSizeDetails mediumJpg) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.EditorialAssets;
import com.shutterstock.api.models.ImageSizeDetails;
import com.shutterstock.api.models.Thumbnail;
import java.io.IOException;

EditorialAssets editorialAssets = new EditorialAssets.Builder()
    .original(new ImageSizeDetails.Builder()
        .displayName("Original")
        .dpi(44)
        .fileSize(36)
        .format("format6")
        .height(3693)
        .isLicensable(true)
        .width(5985)
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .thumb170(new Thumbnail.Builder(
        105,
        "https://editorial01.shuttercorp.net/thumb/10687730b/272a999e/Shutterstock_10687730b.jpg",
        170
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .thumb220(new Thumbnail.Builder(
        136,
        "https://editorial01.shuttercorp.net/thumb-220/10687730b/927a6ebe/Shutterstock_10687730b.jpg",
        220
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .watermark450(new Thumbnail.Builder(
        278,
        "https://editorial01.shuttercorp.net/wm-preview-450/10687730b/ff2443ad/Shutterstock_10687730b.jpg",
        450
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .watermark1500(new Thumbnail.Builder(
        926,
        "https://editorial01.shuttercorp.net/wm-preview-1500/10687730b/ee2d7ae1/Shutterstock_10687730b.jpg",
        1500
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .smallJpg(new ImageSizeDetails.Builder()
        .displayName("Small")
        .height(309)
        .isLicensable(true)
        .width(500)
        .build())
    .mediumJpg(new ImageSizeDetails.Builder()
        .displayName("Med")
        .height(617)
        .isLicensable(true)
        .width(1000)
        .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

