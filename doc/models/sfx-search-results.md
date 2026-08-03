
# Sfx Search Results

Sound effects search results

*This model accepts additional fields of type Object.*

## Structure

`SfxSearchResults`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<Sfx>`](../../doc/models/sfx.md) | Required | List of tracks | List<Sfx> getData() | setData(List<Sfx> data) |
| `Message` | `String` | Optional | Server-generated message, if any | String getMessage() | setMessage(String message) |
| `Page` | `Integer` | Optional | Current page that is returned | Integer getPage() | setPage(Integer page) |
| `PerPage` | `Integer` | Optional | Number of results per page | Integer getPerPage() | setPerPage(Integer perPage) |
| `TotalCount` | `int` | Required | Total count of all results across all pages | int getTotalCount() | setTotalCount(int totalCount) |
| `SearchId` | `String` | Required | ID of the search | String getSearchId() | setSearchId(String searchId) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Contributor;
import com.shutterstock.api.models.Sfx;
import com.shutterstock.api.models.SfxAssetDetails;
import com.shutterstock.api.models.SfxAssets;
import com.shutterstock.api.models.SfxSearchResults;
import java.io.IOException;
import java.util.Arrays;

SfxSearchResults sfxSearchResults = new SfxSearchResults.Builder(
    Arrays.asList(
        new Sfx.Builder(
            new Contributor.Builder(
                "321402911"
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
            "123",
            "sfx"
        )
        .addedDate(DateTimeHelper.fromSimpleDate("2022-07-29"))
        .affiliateUrl("affiliate_url6")
        .artist("artist8")
        .assets(new SfxAssets.Builder()
                .previewMp3(new SfxAssetDetails.Builder()
                    .fileSize(54)
                    .url("https://cdn.shutterstock.com/shutterstock/sfx/21230/preview_ecom_ster/heavy-duty-interface-feedback.mp3")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .waveform(new SfxAssetDetails.Builder()
                    .fileSize(74)
                    .url("https://cdn.shutterstock.com/shutterstock/sfx/21230/wvfm_img/heavy-duty-interface-feedback.png")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
        .description("User interface calculations, scanning, thinking, text displayed on screen. Screen gak or garble.")
        .title("Heavy Duty Interface Feedback")
        .updatedTime(DateTimeHelper.fromRfc8601DateTime("2022-08-04T15:11:15.711Z"))
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ),
    14881,
    "e6f84c4c-ffdd-499b-ad89-72c65a896ead"
)
.message("message2")
.page(196)
.perPage(108)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

