
# Video

Information about a video

*This model accepts additional fields of type Object.*

## Structure

`Video`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AddedDate` | `LocalDate` | Optional | Date this video was added to the Shutterstock library | LocalDate getAddedDate() | setAddedDate(LocalDate addedDate) |
| `AffiliateUrl` | `String` | Optional | Affiliate referral link; appears only for registered affiliate partners | String getAffiliateUrl() | setAffiliateUrl(String affiliateUrl) |
| `Aspect` | `Double` | Optional | Aspect ratio of this video in decimal format, such as 0.6667 | Double getAspect() | setAspect(Double aspect) |
| `AspectRatio` | `String` | Optional | Aspect ratio of the video as a ratio, such as 16:9 | String getAspectRatio() | setAspectRatio(String aspectRatio) |
| `Assets` | [`VideoAssets`](../../doc/models/video-assets.md) | Optional | Video asset information | VideoAssets getAssets() | setAssets(VideoAssets assets) |
| `Categories` | [`List<Category>`](../../doc/models/category.md) | Optional | List of categories | List<Category> getCategories() | setCategories(List<Category> categories) |
| `Contributor` | [`Contributor`](../../doc/models/contributor.md) | Required | Information about a contributor | Contributor getContributor() | setContributor(Contributor contributor) |
| `Description` | `String` | Optional | Description of this video | String getDescription() | setDescription(String description) |
| `Duration` | `Double` | Optional | Duration of this video, in seconds | Double getDuration() | setDuration(Double duration) |
| `HasModelRelease` | `Boolean` | Optional | Whether or not this video has been released for use by the model appearing in it | Boolean getHasModelRelease() | setHasModelRelease(Boolean hasModelRelease) |
| `HasPropertyRelease` | `Boolean` | Optional | Whether or not this video has received a release to show the landmark or property appearing in it | Boolean getHasPropertyRelease() | setHasPropertyRelease(Boolean hasPropertyRelease) |
| `Id` | `String` | Required | ID of the video | String getId() | setId(String id) |
| `IsAdult` | `Boolean` | Optional | Whether or not this video contains adult content | Boolean getIsAdult() | setIsAdult(Boolean isAdult) |
| `IsEditorial` | `Boolean` | Optional | Whether or not this video is editorial content | Boolean getIsEditorial() | setIsEditorial(Boolean isEditorial) |
| `IsSelect` | `Boolean` | Optional | Whether or not this video is part of the select collection | Boolean getIsSelect() | setIsSelect(Boolean isSelect) |
| `Keywords` | `List<String>` | Optional | Keywords associated with the content of this video | List<String> getKeywords() | setKeywords(List<String> keywords) |
| `MediaType` | `String` | Required | Media type of this video, should always be "video" | String getMediaType() | setMediaType(String mediaType) |
| `Models` | [`List<Model>`](../../doc/models/model.md) | Optional | List of models in this video | List<Model> getModels() | setModels(List<Model> models) |
| `Releases` | [`List<ModelRelease>`](../../doc/models/model-release.md) | Optional | List of all releases of this video | List<ModelRelease> getReleases() | setReleases(List<ModelRelease> releases) |
| `Url` | `String` | Optional | Link to video information page; included only for certain accounts | String getUrl() | setUrl(String url) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Category;
import com.shutterstock.api.models.Contributor;
import com.shutterstock.api.models.Model;
import com.shutterstock.api.models.Url;
import com.shutterstock.api.models.Urls;
import com.shutterstock.api.models.Video;
import com.shutterstock.api.models.VideoAssets;
import com.shutterstock.api.models.VideoSizeDetails;
import java.io.IOException;
import java.util.Arrays;

Video video = new Video.Builder(
    new Contributor.Builder(
        "4411978"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build(),
    "1033184651",
    "video"
)
.addedDate(DateTimeHelper.fromSimpleDate("2019-07-13"))
.affiliateUrl("affiliate_url2")
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
.build();
```

