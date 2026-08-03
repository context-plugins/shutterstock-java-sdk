
# Image Assets

Information about the assets that are part of an image

*This model accepts additional fields of type Object.*

## Structure

`ImageAssets`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `HugeJpg` | [`ImageSizeDetails`](../../doc/models/image-size-details.md) | Optional | Image size information | ImageSizeDetails getHugeJpg() | setHugeJpg(ImageSizeDetails hugeJpg) |
| `HugeThumb` | [`Thumbnail`](../../doc/models/thumbnail.md) | Optional | Image thumbnail information | Thumbnail getHugeThumb() | setHugeThumb(Thumbnail hugeThumb) |
| `LargeThumb` | [`Thumbnail`](../../doc/models/thumbnail.md) | Optional | Image thumbnail information | Thumbnail getLargeThumb() | setLargeThumb(Thumbnail largeThumb) |
| `MediumJpg` | [`ImageSizeDetails`](../../doc/models/image-size-details.md) | Optional | Image size information | ImageSizeDetails getMediumJpg() | setMediumJpg(ImageSizeDetails mediumJpg) |
| `Preview` | [`Thumbnail`](../../doc/models/thumbnail.md) | Optional | Image thumbnail information | Thumbnail getPreview() | setPreview(Thumbnail preview) |
| `Preview1000` | [`Thumbnail`](../../doc/models/thumbnail.md) | Optional | Image thumbnail information | Thumbnail getPreview1000() | setPreview1000(Thumbnail preview1000) |
| `Preview1500` | [`Thumbnail`](../../doc/models/thumbnail.md) | Optional | Image thumbnail information | Thumbnail getPreview1500() | setPreview1500(Thumbnail preview1500) |
| `SmallJpg` | [`ImageSizeDetails`](../../doc/models/image-size-details.md) | Optional | Image size information | ImageSizeDetails getSmallJpg() | setSmallJpg(ImageSizeDetails smallJpg) |
| `SmallThumb` | [`Thumbnail`](../../doc/models/thumbnail.md) | Optional | Image thumbnail information | Thumbnail getSmallThumb() | setSmallThumb(Thumbnail smallThumb) |
| `SupersizeJpg` | [`ImageSizeDetails`](../../doc/models/image-size-details.md) | Optional | Image size information | ImageSizeDetails getSupersizeJpg() | setSupersizeJpg(ImageSizeDetails supersizeJpg) |
| `VectorEps` | [`ImageSizeDetails`](../../doc/models/image-size-details.md) | Optional | Image size information | ImageSizeDetails getVectorEps() | setVectorEps(ImageSizeDetails vectorEps) |
| `Mosaic` | [`Thumbnail`](../../doc/models/thumbnail.md) | Optional | Image thumbnail information | Thumbnail getMosaic() | setMosaic(Thumbnail mosaic) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.ImageAssets;
import com.shutterstock.api.models.Thumbnail;
import java.io.IOException;

ImageAssets imageAssets = new ImageAssets.Builder()
    .hugeJpg(null)
    .hugeThumb(new Thumbnail.Builder(
        260,
        "https://image.shutterstock.com/image-photo/cropped-image-woman-gardening-260nw-1572478477.jpg",
        390
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .largeThumb(new Thumbnail.Builder(
        100,
        "https://thumb7.shutterstock.com/thumb_large/250738318/1572478477/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
        150
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .mediumJpg(null)
    .preview(new Thumbnail.Builder(
        300,
        "https://image.shutterstock.com/display_pic_with_logo/250738318/1572478477/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
        450
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .preview1000(new Thumbnail.Builder(
        667,
        "https://ak.picdn.net/shutterstock/photos/1572478477/watermark_1000/1706028c641ea2f443057287c67d9b91/preview_1000-1572478477.jpg",
        1000
    )
    .build())
    .preview1500(new Thumbnail.Builder(
        1000,
        "https://image.shutterstock.com/z/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
        1500
    )
    .build())
    .smallThumb(new Thumbnail.Builder(
        67,
        "https://thumb7.shutterstock.com/thumb_small/250738318/1572478477/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
        100
    )
    .build())
    .mosaic(new Thumbnail.Builder(
        167,
        "https://image.shutterstock.com/image-photo/cropped-image-woman-gardening-250nw-1572478477.jpg",
        250
    )
    .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

