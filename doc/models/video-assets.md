
# Video Assets

Video asset information

*This model accepts additional fields of type Object.*

## Structure

`VideoAssets`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `M4K` | [`VideoSizeDetails`](../../doc/models/video-size-details.md) | Optional | Video asset information | VideoSizeDetails getM4K() | setM4K(VideoSizeDetails m4K) |
| `Hd` | [`VideoSizeDetails`](../../doc/models/video-size-details.md) | Optional | Video asset information | VideoSizeDetails getHd() | setHd(VideoSizeDetails hd) |
| `PreviewJpg` | [`Url`](../../doc/models/url.md) | Optional | URL object | Url getPreviewJpg() | setPreviewJpg(Url previewJpg) |
| `PreviewMp4` | [`Url`](../../doc/models/url.md) | Optional | URL object | Url getPreviewMp4() | setPreviewMp4(Url previewMp4) |
| `PreviewWebm` | [`Url`](../../doc/models/url.md) | Optional | URL object | Url getPreviewWebm() | setPreviewWebm(Url previewWebm) |
| `Sd` | [`VideoSizeDetails`](../../doc/models/video-size-details.md) | Optional | Video asset information | VideoSizeDetails getSd() | setSd(VideoSizeDetails sd) |
| `ThumbJpg` | [`Url`](../../doc/models/url.md) | Optional | URL object | Url getThumbJpg() | setThumbJpg(Url thumbJpg) |
| `ThumbJpgs` | [`Urls`](../../doc/models/urls.md) | Optional | List of URLs | Urls getThumbJpgs() | setThumbJpgs(Urls thumbJpgs) |
| `ThumbMp4` | [`Url`](../../doc/models/url.md) | Optional | URL object | Url getThumbMp4() | setThumbMp4(Url thumbMp4) |
| `ThumbWebm` | [`Url`](../../doc/models/url.md) | Optional | URL object | Url getThumbWebm() | setThumbWebm(Url thumbWebm) |
| `Web` | [`VideoSizeDetails`](../../doc/models/video-size-details.md) | Optional | Video asset information | VideoSizeDetails getWeb() | setWeb(VideoSizeDetails web) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Url;
import com.shutterstock.api.models.Urls;
import com.shutterstock.api.models.VideoAssets;
import com.shutterstock.api.models.VideoSizeDetails;
import java.io.IOException;
import java.util.Arrays;

VideoAssets videoAssets = new VideoAssets.Builder()
    .m4K(null)
    .hd(new VideoSizeDetails.Builder()
        .displayName("Original HD")
        .fileSize(110359552)
        .format("avc1")
        .fps(29.97D)
        .height(1080)
        .isLicensable(true)
        .width(1920)
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .previewJpg(new Url.Builder(
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/12.jpg"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .previewMp4(new Url.Builder(
        "https://ak.picdn.net/shutterstock/videos/1033184651/preview/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.mp4"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .previewWebm(new Url.Builder(
        "https://ak.picdn.net/shutterstock/videos/1033184651/preview/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.webm"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
    .sd(new VideoSizeDetails.Builder()
        .displayName("Standard Definition MPEG")
        .fileSize(4577280)
        .format("mov")
        .fps(29.97D)
        .height(480)
        .isLicensable(true)
        .width(852)
        .build())
    .thumbJpg(new Url.Builder(
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/12.jpg"
    )
    .build())
    .thumbJpgs(new Urls.Builder(
        Arrays.asList(
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/1.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/2.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/3.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/4.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/5.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/6.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/7.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/8.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/9.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/10.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/11.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/12.jpg"
        )
    )
    .build())
    .thumbMp4(new Url.Builder(
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.mp4"
    )
    .build())
    .thumbWebm(new Url.Builder(
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.webm"
    )
    .build())
    .web(new VideoSizeDetails.Builder()
        .displayName("Low Resolution MPEG")
        .fileSize(1291264)
        .format("mov")
        .fps(29.97D)
        .height(240)
        .isLicensable(true)
        .width(426)
        .build())
.additionalProperty("original_filename", ApiHelper.deserialize("\"123.mp4\""))
    .build();
```

