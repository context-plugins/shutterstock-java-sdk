
# Audio Search Results

Audio search results

*This model accepts additional fields of type Object.*

## Structure

`AudioSearchResults`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<Audio>`](../../doc/models/audio.md) | Required | List of tracks | List<Audio> getData() | setData(List<Audio> data) |
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
import com.shutterstock.api.models.Artist;
import com.shutterstock.api.models.Audio;
import com.shutterstock.api.models.AudioAssetDetails;
import com.shutterstock.api.models.AudioAssets;
import com.shutterstock.api.models.AudioSearchResults;
import com.shutterstock.api.models.Contributor;
import java.io.IOException;
import java.util.Arrays;

AudioSearchResults audioSearchResults = new AudioSearchResults.Builder(
    Arrays.asList(
        new Audio.Builder(
            new Contributor.Builder(
                "2847971"
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
            "442583",
            "audio"
        )
        .addedDate(DateTimeHelper.fromSimpleDate("2016-08-16"))
        .affiliateUrl("affiliate_url6")
        .album(null)
        .artists(Arrays.asList(
                new Artist.Builder(
                    "Klimenko Music"
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build()
            ))
        .assets(new AudioAssets.Builder()
                .albumArt(null)
                .cleanAudio(new AudioAssetDetails.Builder()
                    .fileSize(35188408)
                    .url("url4")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .originalAudio(null)
                .previewMp3(new AudioAssetDetails.Builder()
                    .fileSize(4400203)
                    .url("https://ak.picdn.net/shutterstock/audio/442583/preview/preview.mp3")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .previewOgg(new AudioAssetDetails.Builder()
                    .fileSize(4453197)
                    .url("https://ak.picdn.net/shutterstock/audio/442583/preview/preview.ogg")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .waveform(new AudioAssetDetails.Builder()
                    .fileSize(18778)
                    .url("https://ak.picdn.net/shutterstock/audio/442583/waveform/waveform.png")
                    .build())
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
        .bpm(110)
        .description("Pulsing and feel-good, featuring soaring synthesizer, groovy synth bass drums and synth drums that create a euphoric, upbeat mood.")
        .duration(183D)
        .genres(Arrays.asList(
                "Dance/Electronic",
                "Electro Pop",
                "Pop/Rock"
            ))
        .instruments(Arrays.asList(
                "Piano",
                "Synth bass",
                "Synth drums",
                "Synthesizer"
            ))
        .isAdult(false)
        .isInstrumental(true)
        .isrc("")
        .keywords(Arrays.asList(
                "celebratory",
                "chic",
                "euphoric",
                "good times",
                "hip",
                "optimistic",
                "party",
                "soaring",
                "upbeat"
            ))
        .language("en")
        .lyrics("")
        .moods(Arrays.asList(
                "Bright",
                "Confident",
                "Fun",
                "Happy",
                "Inspiring",
                "Optimistic",
                "Playful",
                "Sophisticated",
                "Stylish",
                "Uplifting"
            ))
        .publishedTime(DateTimeHelper.fromRfc8601DateTime("2016-08-16T14:30:03-04:00"))
        .recordingVersion("")
        .releases(Arrays.asList(

            ))
        .similarArtists(Arrays.asList(

            ))
        .title("Another Tomorrow")
        .updatedTime(DateTimeHelper.fromRfc8601DateTime("2016-08-18T17:59:33-04:00"))
        .vocalDescription("")
        .url("")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ),
    123455,
    "749090bb-2967-4a20-b22e-c800dc845e10"
)
.message("message2")
.page(1)
.perPage(5)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

