
# Editorial Video Assets

Asset information, including size and thumbnail URLs

*This model accepts additional fields of type Object.*

## Structure

`EditorialVideoAssets`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Original` | [`VideoSizeDetails`](../../doc/models/video-size-details.md) | Optional | Video asset information | VideoSizeDetails getOriginal() | setOriginal(VideoSizeDetails original) |
| `PreviewMp4` | [`VideoPreviewUrl`](../../doc/models/video-preview-url.md) | Optional | Video preview information | VideoPreviewUrl getPreviewMp4() | setPreviewMp4(VideoPreviewUrl previewMp4) |
| `PreviewWebm` | [`VideoPreviewUrl`](../../doc/models/video-preview-url.md) | Optional | Video preview information | VideoPreviewUrl getPreviewWebm() | setPreviewWebm(VideoPreviewUrl previewWebm) |
| `ThumbJpg` | [`VideoPreviewUrl`](../../doc/models/video-preview-url.md) | Optional | Video preview information | VideoPreviewUrl getThumbJpg() | setThumbJpg(VideoPreviewUrl thumbJpg) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.EditorialVideoAssets;
import com.shutterstock.api.models.VideoPreviewUrl;
import com.shutterstock.api.models.VideoSizeDetails;
import java.io.IOException;

EditorialVideoAssets editorialVideoAssets = new EditorialVideoAssets.Builder()
    .original(new VideoSizeDetails.Builder()
        .displayName("HD")
        .fileSize(82233387)
        .format("avc1")
        .fps(30D)
        .height(1080)
        .isLicensable(true)
        .width(1080)
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .previewMp4(new VideoPreviewUrl.Builder(
        "https://editorial-cdn.shuttercorp.net/wm-preview-mp4/10679854a/M0T7A13aNej2g82bMTI4NjY=/Shutterstock_10679854a.mp4"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .previewWebm(new VideoPreviewUrl.Builder(
        "https://editorial-cdn.shuttercorp.net/wm-preview-webm/10679854a/M4T6A63fN2j5g929MTI4NjY=/Shutterstock_10679854a.webm"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .thumbJpg(new VideoPreviewUrl.Builder(
        "https://editorial-cdn.shuttercorp.net/thumb-1/10679854a/M5TcAf30Ncjcge2eMTI4NjY=/Shutterstock_10679854a.jpg"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

