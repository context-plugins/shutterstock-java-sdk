
# Audio

Audio metadata

*This model accepts additional fields of type Object.*

## Structure

`Audio`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AddedDate` | `LocalDate` | Optional | Date this track was added to the Shutterstock library | LocalDate getAddedDate() | setAddedDate(LocalDate addedDate) |
| `AffiliateUrl` | `String` | Optional | Affiliate referral link; appears only for registered affiliate partners | String getAffiliateUrl() | setAffiliateUrl(String affiliateUrl) |
| `Album` | [`Album`](../../doc/models/album.md) | Optional | Album metadata | Album getAlbum() | setAlbum(Album album) |
| `Artists` | [`List<Artist>`](../../doc/models/artist.md) | Optional | List of artists | List<Artist> getArtists() | setArtists(List<Artist> artists) |
| `Assets` | [`AudioAssets`](../../doc/models/audio-assets.md) | Optional | Files that are available as part of an audio asset | AudioAssets getAssets() | setAssets(AudioAssets assets) |
| `Bpm` | `Integer` | Optional | BPM (beats per minute) of this track | Integer getBpm() | setBpm(Integer bpm) |
| `Contributor` | [`Contributor`](../../doc/models/contributor.md) | Required | Information about a contributor | Contributor getContributor() | setContributor(Contributor contributor) |
| `DeletedTime` | `LocalDateTime` | Optional | - | LocalDateTime getDeletedTime() | setDeletedTime(LocalDateTime deletedTime) |
| `Description` | `String` | Optional | Description of this track | String getDescription() | setDescription(String description) |
| `Duration` | `Double` | Optional | Duration of this track in seconds | Double getDuration() | setDuration(Double duration) |
| `Genres` | `List<String>` | Optional | List of all genres for this track | List<String> getGenres() | setGenres(List<String> genres) |
| `Id` | `String` | Required | Shutterstock ID of this track | String getId() | setId(String id) |
| `Instruments` | `List<String>` | Optional | List of all instruments that appear in this track | List<String> getInstruments() | setInstruments(List<String> instruments) |
| `IsAdult` | `Boolean` | Optional | Whether or not this track contains adult content | Boolean getIsAdult() | setIsAdult(Boolean isAdult) |
| `IsInstrumental` | `Boolean` | Optional | Whether or not this track is purely instrumental (lacking lyrics) | Boolean getIsInstrumental() | setIsInstrumental(Boolean isInstrumental) |
| `Isrc` | `String` | Optional | - | String getIsrc() | setIsrc(String isrc) |
| `Keywords` | `List<String>` | Optional | List of all keywords for this track | List<String> getKeywords() | setKeywords(List<String> keywords) |
| `Language` | `String` | Optional | Language of this track's lyrics | String getLanguage() | setLanguage(String language) |
| `Lyrics` | `String` | Optional | Lyrics of this track | String getLyrics() | setLyrics(String lyrics) |
| `MediaType` | `String` | Required | Media type of this track; should always be "audio" | String getMediaType() | setMediaType(String mediaType) |
| `ModelReleases` | [`List<ModelRelease>`](../../doc/models/model-release.md) | Optional | List of all model releases for this track | List<ModelRelease> getModelReleases() | setModelReleases(List<ModelRelease> modelReleases) |
| `Moods` | `List<String>` | Optional | List of all moods of this track | List<String> getMoods() | setMoods(List<String> moods) |
| `PublishedTime` | `LocalDateTime` | Optional | Time this track was published | LocalDateTime getPublishedTime() | setPublishedTime(LocalDateTime publishedTime) |
| `RecordingVersion` | `String` | Optional | Recording version of this track | String getRecordingVersion() | setRecordingVersion(String recordingVersion) |
| `Releases` | `List<String>` | Optional | List of all releases of this track | List<String> getReleases() | setReleases(List<String> releases) |
| `SimilarArtists` | [`List<Artist>`](../../doc/models/artist.md) | Optional | List of all similar artists of this track | List<Artist> getSimilarArtists() | setSimilarArtists(List<Artist> similarArtists) |
| `SubmittedTime` | `LocalDateTime` | Optional | Time this track was submitted | LocalDateTime getSubmittedTime() | setSubmittedTime(LocalDateTime submittedTime) |
| `Title` | `String` | Optional | Title of this track | String getTitle() | setTitle(String title) |
| `UpdatedTime` | `LocalDateTime` | Optional | Time this track was last updated | LocalDateTime getUpdatedTime() | setUpdatedTime(LocalDateTime updatedTime) |
| `VocalDescription` | `String` | Optional | Vocal description of this track | String getVocalDescription() | setVocalDescription(String vocalDescription) |
| `Url` | `String` | Optional | - | String getUrl() | setUrl(String url) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Artist;
import com.shutterstock.api.models.Audio;
import com.shutterstock.api.models.AudioAssetDetails;
import com.shutterstock.api.models.AudioAssets;
import com.shutterstock.api.models.Contributor;
import java.io.IOException;
import java.util.Arrays;

Audio audio = new Audio.Builder(
    new Contributor.Builder(
        "2847971"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build(),
    "442583",
    "audio"
)
.addedDate(DateTimeHelper.fromSimpleDate("2016-08-16"))
.affiliateUrl("affiliate_url4")
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
.build();
```

