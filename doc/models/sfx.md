
# Sfx

SFX metadata

*This model accepts additional fields of type Object.*

## Structure

`Sfx`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AddedDate` | `LocalDate` | Optional | Date this sound effect was added to the Shutterstock library | LocalDate getAddedDate() | setAddedDate(LocalDate addedDate) |
| `AffiliateUrl` | `String` | Optional | Affiliate referral link; appears only for registered affiliate partners | String getAffiliateUrl() | setAffiliateUrl(String affiliateUrl) |
| `Artist` | `String` | Optional | Artist of the sound effect | String getArtist() | setArtist(String artist) |
| `Assets` | [`SfxAssets`](../../doc/models/sfx-assets.md) | Optional | Files that are available as part of an sound effect asset | SfxAssets getAssets() | setAssets(SfxAssets assets) |
| `Contributor` | [`Contributor`](../../doc/models/contributor.md) | Required | Information about a contributor | Contributor getContributor() | setContributor(Contributor contributor) |
| `Description` | `String` | Optional | Description of this sound effect | String getDescription() | setDescription(String description) |
| `Duration` | `Double` | Optional | Duration of this sound effect in seconds | Double getDuration() | setDuration(Double duration) |
| `Id` | `String` | Required | Shutterstock ID of this sound effect | String getId() | setId(String id) |
| `Keywords` | `List<String>` | Optional | List of all keywords for this sound effect | List<String> getKeywords() | setKeywords(List<String> keywords) |
| `MediaType` | `String` | Required | Media type of this track; should always be "sfx" | String getMediaType() | setMediaType(String mediaType) |
| `Releases` | `List<String>` | Optional | List of all releases of this sound effect | List<String> getReleases() | setReleases(List<String> releases) |
| `Title` | `String` | Optional | Title of this sound effect | String getTitle() | setTitle(String title) |
| `UpdatedTime` | `LocalDateTime` | Optional | Time this sound effect was last updated | LocalDateTime getUpdatedTime() | setUpdatedTime(LocalDateTime updatedTime) |
| `Url` | `String` | Optional | - | String getUrl() | setUrl(String url) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Contributor;
import com.shutterstock.api.models.Sfx;
import java.io.IOException;

Sfx sfx = new Sfx.Builder(
    new Contributor.Builder(
        "1234"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build(),
    "123",
    "sfx"
)
.addedDate(DateTimeHelper.fromSimpleDate("2016-03-13"))
.affiliateUrl("affiliate_url8")
.artist("artist0")
.assets(null)
.description("description8")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

