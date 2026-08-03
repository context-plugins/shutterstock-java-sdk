
# Contributor Profile

Contributor profile data

*This model accepts additional fields of type Object.*

## Structure

`ContributorProfile`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `About` | `String` | Optional | Short description of the contributors' library | String getAbout() | setAbout(String about) |
| `ContributorType` | `List<String>` | Optional | Type of content that the contributor specializes in (photographer, illustrator, etc) | List<String> getContributorType() | setContributorType(List<String> contributorType) |
| `DisplayName` | `String` | Optional | Preferred name to be displayed for the contributor | String getDisplayName() | setDisplayName(String displayName) |
| `Equipment` | `List<String>` | Optional | List of equipment used by the contributor (Canon EOS 5D Mark II, etc) | List<String> getEquipment() | setEquipment(List<String> equipment) |
| `Id` | `String` | Required | Contributor ID | String getId() | setId(String id) |
| `Location` | `String` | Optional | Country code representing the contributor's locale | String getLocation() | setLocation(String location) |
| `PortfolioUrl` | `String` | Optional | Web URL for the contributors' profile | String getPortfolioUrl() | setPortfolioUrl(String portfolioUrl) |
| `SocialMedia` | [`ContributorProfileSocialMedia`](../../doc/models/contributor-profile-social-media.md) | Optional | Contributor profile social media links | ContributorProfileSocialMedia getSocialMedia() | setSocialMedia(ContributorProfileSocialMedia socialMedia) |
| `Styles` | `List<String>` | Optional | List of styles that the contributor specializes in (lifestyle, mixed media, etc) | List<String> getStyles() | setStyles(List<String> styles) |
| `Subjects` | `List<String>` | Optional | Generic list of subjects for contributors' work (food_and_drink, holiday, people, etc) | List<String> getSubjects() | setSubjects(List<String> subjects) |
| `Website` | `String` | Optional | Personal website for the contributor | String getWebsite() | setWebsite(String website) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.ContributorProfile;
import com.shutterstock.api.models.ContributorProfileSocialMedia;
import java.io.IOException;
import java.util.Arrays;

ContributorProfile contributorProfile = new ContributorProfile.Builder(
    "12345678"
)
.about("John Doe's photographs")
.contributorType(Arrays.asList(
        "photographer"
    ))
.displayName("John Doe")
.equipment(Arrays.asList(
        "Nikon",
        "Fuji"
    ))
.location("US")
.portfolioUrl("https://www.shutterstock.com/g/jdoe")
.socialMedia(new ContributorProfileSocialMedia.Builder()
        .facebook("http://example.com/jdoe")
        .googlePlus("http://example.com/jdoe")
        .linkedin("http://example.com/jdoe")
        .pinterest("http://example.com/jdoe")
        .tumblr("http://example.com/jdoe")
        .twitter("http://example.com/jdoe")
        .build())
.styles(Arrays.asList(
        "landscape",
        "nature",
        "footage_travel"
    ))
.subjects(Arrays.asList(
        "animals",
        "landmarks",
        "nature",
        "objects",
        "recreation"
    ))
.website("http://example.com/profiles/jdoe")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

