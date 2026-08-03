
# Video Data List

List of videos

*This model accepts additional fields of type Object.*

## Structure

`VideoDataList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<Video>`](../../doc/models/video.md) | Optional | Videos | List<Video> getData() | setData(List<Video> data) |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | Error list; appears only if there was an error | List<Error> getErrors() | setErrors(List<Error> errors) |
| `Message` | `String` | Optional | Server-generated message, if any | String getMessage() | setMessage(String message) |
| `Page` | `Integer` | Optional | Current page that is returned | Integer getPage() | setPage(Integer page) |
| `PerPage` | `Integer` | Optional | Number of results per page | Integer getPerPage() | setPerPage(Integer perPage) |
| `TotalCount` | `Integer` | Optional | Total count of all results across all pages | Integer getTotalCount() | setTotalCount(Integer totalCount) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Category;
import com.shutterstock.api.models.Contributor;
import com.shutterstock.api.models.Error;
import com.shutterstock.api.models.Model;
import com.shutterstock.api.models.Url;
import com.shutterstock.api.models.Urls;
import com.shutterstock.api.models.Video;
import com.shutterstock.api.models.VideoAssets;
import com.shutterstock.api.models.VideoDataList;
import com.shutterstock.api.models.VideoSizeDetails;
import java.io.IOException;
import java.util.Arrays;

VideoDataList videoDataList = new VideoDataList.Builder()
    .data(Arrays.asList(
        new Video.Builder(
            new Contributor.Builder(
                "4411978"
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
            "1033184651",
            "video"
        )
        .addedDate(DateTimeHelper.fromSimpleDate("2019-07-13"))
        .affiliateUrl("affiliate_url6")
        .aspect(1.778D)
        .aspectRatio("16:9")
        .assets(new VideoAssets.Builder()
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
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
        .categories(Arrays.asList(
                new Category.Builder()
                    .id("12")
                    .name("Nature")
                    .build(),
                new Category.Builder()
                    .id("13")
                    .name("People")
                    .build()
            ))
        .description("Camera follows hipster millennial young woman in orange jacket running up on top of mountain summit at sunset, jumps on top of rocks, raises arms into air, happy and drunk on life, youth and happiness")
        .duration(14.081D)
        .hasModelRelease(true)
        .hasPropertyRelease(false)
        .isAdult(false)
        .isEditorial(false)
        .keywords(Arrays.asList(
                "active",
                "activity",
                "adventure",
                "arms",
                "backpacker",
                "carefree",
                "celebrating",
                "cliff",
                "climate",
                "cloud",
                "discovery",
                "escape",
                "explore",
                "extreme",
                "free",
                "freedom",
                "girl",
                "happy",
                "high",
                "hiker",
                "hiking",
                "hill",
                "independent",
                "inspiration",
                "landscape",
                "leisure",
                "lifestyle",
                "mountain",
                "mountains",
                "nature",
                "outdoor",
                "peak",
                "person",
                "rock",
                "scenic",
                "sky",
                "sport",
                "success",
                "summer",
                "summit",
                "sun",
                "sunset",
                "top",
                "tourism",
                "travel",
                "trekking",
                "vacation",
                "view",
                "winning",
                "woman"
            ))
        .models(Arrays.asList(
                new Model.Builder(
                    "33233810"
                )
                .build(),
                new Model.Builder(
                    "25487168"
                )
                .build()
            ))
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ))
    .errors(Arrays.asList(
        new Error.Builder(
            "message0"
        )
        .code("code8")
        .data("data0")
        .items(Arrays.asList(
                ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}")
            ))
        .path("path4")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ))
    .message("message4")
    .page(1)
    .perPage(5)
    .totalCount(25)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

