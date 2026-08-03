
# Editorial Video Content

Metadata about editorial content

*This model accepts additional fields of type Object.*

## Structure

`EditorialVideoContent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Aspect` | `Double` | Optional | - | Double getAspect() | setAspect(Double aspect) |
| `Assets` | [`EditorialVideoAssets`](../../doc/models/editorial-video-assets.md) | Optional | Asset information, including size and thumbnail URLs | EditorialVideoAssets getAssets() | setAssets(EditorialVideoAssets assets) |
| `Byline` | `String` | Optional | - | String getByline() | setByline(String byline) |
| `Caption` | `String` | Optional | - | String getCaption() | setCaption(String caption) |
| `Categories` | [`List<EditorialCategory>`](../../doc/models/editorial-category.md) | Optional | List of categories | List<EditorialCategory> getCategories() | setCategories(List<EditorialCategory> categories) |
| `DateTaken` | `LocalDate` | Optional | - | LocalDate getDateTaken() | setDateTaken(LocalDate dateTaken) |
| `Description` | `String` | Optional | - | String getDescription() | setDescription(String description) |
| `Id` | `String` | Required | - | String getId() | setId(String id) |
| `Keywords` | `List<String>` | Optional | - | List<String> getKeywords() | setKeywords(List<String> keywords) |
| `Title` | `String` | Optional | - | String getTitle() | setTitle(String title) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.EditorialVideoAssets;
import com.shutterstock.api.models.EditorialVideoContent;
import com.shutterstock.api.models.VideoPreviewUrl;
import com.shutterstock.api.models.VideoSizeDetails;
import java.io.IOException;
import java.util.Arrays;

EditorialVideoContent editorialVideoContent = new EditorialVideoContent.Builder(
    "10679854a"
)
.aspect(1D)
.assets(new EditorialVideoAssets.Builder()
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
        .build())
.byline("ViralHog/Shutterstock")
.caption("")
.categories(Arrays.asList(

    ))
.dateTaken(DateTimeHelper.fromSimpleDate("2020-11-13"))
.description("Info from Licensor: \"Peeps the Canadian Goose has been raised with our family since a gosling. Peeps has made appearances on our local news channels, TV shows, and local newspapers. He has been trained to fly next to four wheelers, jet ski's, and boats. He has brought joy to many people during the pandemic including those with cancer.\"")
.keywords(Arrays.asList(
        "2020",
        "adorable",
        "birds",
        "bizarre",
        "canadian goose",
        "cute",
        "domesticated animals",
        "entertainment",
        "feel good",
        "flew",
        "flies",
        "fly",
        "flying",
        "fun",
        "goose",
        "jet skis",
        "nature",
        "odd",
        "pets",
        "played",
        "playing",
        "plays",
        "prior lake",
        "sports",
        "strange",
        "sweet",
        "usa",
        "viralhog",
        "virals",
        "water sports",
        "weird"
    ))
.title("Peeps the Goose Has a Blast on a Jet Ski, Prior Lake, Minnesota, USA - 13 Nov 2020")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

