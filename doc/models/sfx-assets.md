
# Sfx Assets

Files that are available as part of an sound effect asset

*This model accepts additional fields of type Object.*

## Structure

`SfxAssets`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `PreviewMp3` | [`SfxAssetDetails`](../../doc/models/sfx-asset-details.md) | Optional | Information about a file that is part of an sound effect asset | SfxAssetDetails getPreviewMp3() | setPreviewMp3(SfxAssetDetails previewMp3) |
| `Waveform` | [`SfxAssetDetails`](../../doc/models/sfx-asset-details.md) | Optional | Information about a file that is part of an sound effect asset | SfxAssetDetails getWaveform() | setWaveform(SfxAssetDetails waveform) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.SfxAssetDetails;
import com.shutterstock.api.models.SfxAssets;
import java.io.IOException;

SfxAssets sfxAssets = new SfxAssets.Builder()
    .previewMp3(new SfxAssetDetails.Builder()
        .fileSize(123)
        .url("https://cdn.shutterstock.com/shutterstock/sfx/11222/preview_ecom_ster/hand-throw-catch-cellphone.mp3")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .waveform(new SfxAssetDetails.Builder()
        .fileSize(123)
        .url("https://cdn.shutterstock.com/shutterstock/sfx/11222/preview_ecom_ster/hand-throw-catch-cellphone.mp3")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

