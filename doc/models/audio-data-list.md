
# Audio Data List

List of tracks

*This model accepts additional fields of type Object.*

## Structure

`AudioDataList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<Audio>`](../../doc/models/audio.md) | Optional | Tracks | List<Audio> getData() | setData(List<Audio> data) |
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
import com.shutterstock.api.models.Artist;
import com.shutterstock.api.models.Audio;
import com.shutterstock.api.models.AudioAssetDetails;
import com.shutterstock.api.models.AudioAssets;
import com.shutterstock.api.models.AudioDataList;
import com.shutterstock.api.models.Contributor;
import com.shutterstock.api.models.Error;
import java.io.IOException;
import java.util.Arrays;

AudioDataList audioDataList = new AudioDataList.Builder()
    .data(Arrays.asList(
        new Audio.Builder(
            new Contributor.Builder(
                "2847971"
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
            "434750",
            "audio"
        )
        .addedDate(DateTimeHelper.fromSimpleDate("2016-04-12"))
        .affiliateUrl("affiliate_url6")
        .album(null)
        .artists(Arrays.asList(
                new Artist.Builder(
                    "Fin Productions"
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build()
            ))
        .assets(new AudioAssets.Builder()
                .albumArt(null)
                .cleanAudio(new AudioAssetDetails.Builder()
                    .fileSize(30760372)
                    .url("url4")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .originalAudio(null)
                .previewMp3(new AudioAssetDetails.Builder()
                    .fileSize(3846606)
                    .url("https://ak.picdn.net/shutterstock/audio/434750/preview/preview.mp3")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .previewOgg(new AudioAssetDetails.Builder()
                    .fileSize(4402608)
                    .url("https://ak.picdn.net/shutterstock/audio/434750/preview/preview.ogg")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .waveform(new AudioAssetDetails.Builder()
                    .fileSize(19822)
                    .url("https://ak.picdn.net/shutterstock/audio/434750/waveform/waveform.png")
                    .build())
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
        .bpm(100)
        .description("Pulsing and feel-good, featuring slick electric guitar, synthesizer, bass, electronic drum pads and drums that create a positive, celebratory mood.")
        .duration(160D)
        .genres(Arrays.asList(
                "Dance/Electronic",
                "Electro Pop",
                "Pop/Rock"
            ))
        .instruments(Arrays.asList(
                "Bass",
                "Drums",
                "Electric guitar",
                "Pads",
                "Percussion",
                "Synthesizer"
            ))
        .isAdult(false)
        .isInstrumental(true)
        .isrc("")
        .keywords(Arrays.asList(
                "breezy",
                "celebration",
                "festive",
                "good times",
                "hopeful",
                "optimistic",
                "party",
                "positive",
                "reflective"
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
        .publishedTime(DateTimeHelper.fromRfc8601DateTime("2016-04-12T17:45:29-04:00"))
        .recordingVersion("")
        .releases(Arrays.asList(

            ))
        .similarArtists(Arrays.asList(

            ))
        .title("Fresh Love")
        .updatedTime(DateTimeHelper.fromRfc8601DateTime("2016-08-18T18:03:11-04:00"))
        .vocalDescription("")
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
        .build(),
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
        .build(),
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
    .page(76)
    .perPage(244)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

