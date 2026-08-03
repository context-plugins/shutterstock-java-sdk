
# Contributor Profile Social Media

Contributor profile social media links

*This model accepts additional fields of type Object.*

## Structure

`ContributorProfileSocialMedia`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Facebook` | `String` | Optional | Facebook link for contributor | String getFacebook() | setFacebook(String facebook) |
| `GooglePlus` | `String` | Optional | Google+ link for contributor | String getGooglePlus() | setGooglePlus(String googlePlus) |
| `Linkedin` | `String` | Optional | LinkedIn link for contributor | String getLinkedin() | setLinkedin(String linkedin) |
| `Pinterest` | `String` | Optional | Pinterest page for contributor | String getPinterest() | setPinterest(String pinterest) |
| `Tumblr` | `String` | Optional | Tumblr link for contributor | String getTumblr() | setTumblr(String tumblr) |
| `Twitter` | `String` | Optional | Twitter link for contributor | String getTwitter() | setTwitter(String twitter) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.ContributorProfileSocialMedia;
import java.io.IOException;

ContributorProfileSocialMedia contributorProfileSocialMedia = new ContributorProfileSocialMedia.Builder()
    .facebook("http://example.com/jdoe")
    .googlePlus("http://example.com/jdoe")
    .linkedin("http://example.com/jdoe")
    .pinterest("http://example.com/jdoe")
    .tumblr("http://example.com/jdoe")
    .twitter("http://example.com/jdoe")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

