
# Video Search Results

Video search results

*This model accepts additional fields of type Object.*

## Structure

`VideoSearchResults`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<Video>`](../../doc/models/video.md) | Required | List of videos | List<Video> getData() | setData(List<Video> data) |
| `Message` | `String` | Optional | Server-generated message, if any | String getMessage() | setMessage(String message) |
| `Page` | `Integer` | Optional | Current page that is returned | Integer getPage() | setPage(Integer page) |
| `PerPage` | `Integer` | Optional | Number of results per page | Integer getPerPage() | setPerPage(Integer perPage) |
| `TotalCount` | `int` | Required | Total count of all results across all pages | int getTotalCount() | setTotalCount(int totalCount) |
| `SearchId` | `String` | Required | Unique identifier for the search request | String getSearchId() | setSearchId(String searchId) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Contributor;
import com.shutterstock.api.models.Url;
import com.shutterstock.api.models.Video;
import com.shutterstock.api.models.VideoAssets;
import com.shutterstock.api.models.VideoSearchResults;
import java.io.IOException;
import java.util.Arrays;

VideoSearchResults videoSearchResults = new VideoSearchResults.Builder(
    Arrays.asList(
        new Video.Builder(
            new Contributor.Builder(
                "4411978"
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
            "1033184651",
            "video"
        )
        .addedDate(DateTimeHelper.fromSimpleDate("2016-03-13"))
        .affiliateUrl("affiliate_url6")
        .aspect(1.778D)
        .aspectRatio("16:9")
        .assets(new VideoAssets.Builder()
                .m4K(null)
                .hd(null)
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
                .thumbJpg(new Url.Builder(
                    "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/12.jpg"
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
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
        .description("Camera follows hipster millennial young woman in orange jacket running up on top of mountain summit at sunset, jumps on top of rocks, raises arms into air, happy and drunk on life, youth and happiness")
        .duration(14.081D)
        .hasModelRelease(true)
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ),
    123,
    "749090bb-2967-4a20-b22e-c800dc845e10"
)
.message("message0")
.page(1)
.perPage(5)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

