
# Sfx Asset Details

Information about a file that is part of an sound effect asset

*This model accepts additional fields of type Object.*

## Structure

`SfxAssetDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `FileSize` | `Integer` | Optional | File size of the sound effect | Integer getFileSize() | setFileSize(Integer fileSize) |
| `Url` | `String` | Optional | URL the sound effect is available at | String getUrl() | setUrl(String url) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.SfxAssetDetails;
import java.io.IOException;

SfxAssetDetails sfxAssetDetails = new SfxAssetDetails.Builder()
    .fileSize(123)
    .url("https://cdn.shutterstock.com/shutterstock/sfx/11222/preview_ecom_ster/hand-throw-catch-cellphone.mp3")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

