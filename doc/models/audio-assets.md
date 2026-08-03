
# Audio Assets

Files that are available as part of an audio asset

*This model accepts additional fields of type Object.*

## Structure

`AudioAssets`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AlbumArt` | [`AudioAssetDetails`](../../doc/models/audio-asset-details.md) | Optional | Information about a file that is part of an audio asset | AudioAssetDetails getAlbumArt() | setAlbumArt(AudioAssetDetails albumArt) |
| `CleanAudio` | [`AudioAssetDetails`](../../doc/models/audio-asset-details.md) | Optional | Information about a file that is part of an audio asset | AudioAssetDetails getCleanAudio() | setCleanAudio(AudioAssetDetails cleanAudio) |
| `OriginalAudio` | [`AudioAssetDetails`](../../doc/models/audio-asset-details.md) | Optional | Information about a file that is part of an audio asset | AudioAssetDetails getOriginalAudio() | setOriginalAudio(AudioAssetDetails originalAudio) |
| `PreviewMp3` | [`AudioAssetDetails`](../../doc/models/audio-asset-details.md) | Optional | Information about a file that is part of an audio asset | AudioAssetDetails getPreviewMp3() | setPreviewMp3(AudioAssetDetails previewMp3) |
| `PreviewOgg` | [`AudioAssetDetails`](../../doc/models/audio-asset-details.md) | Optional | Information about a file that is part of an audio asset | AudioAssetDetails getPreviewOgg() | setPreviewOgg(AudioAssetDetails previewOgg) |
| `Waveform` | [`AudioAssetDetails`](../../doc/models/audio-asset-details.md) | Optional | Information about a file that is part of an audio asset | AudioAssetDetails getWaveform() | setWaveform(AudioAssetDetails waveform) |
| `ShortsLoopsStems` | [`ShortsLoopsStems`](../../doc/models/shorts-loops-stems.md) | Optional | Links for Shorts, Loops and Stems previews | ShortsLoopsStems getShortsLoopsStems() | setShortsLoopsStems(ShortsLoopsStems shortsLoopsStems) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.AudioAssetDetails;
import com.shutterstock.api.models.AudioAssets;
import java.io.IOException;

AudioAssets audioAssets = new AudioAssets.Builder()
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
    .build();
```

