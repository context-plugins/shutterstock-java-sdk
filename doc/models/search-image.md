
# Search Image

Data required to search for an image

*This model accepts additional fields of type Object.*

## Structure

`SearchImage`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AddedDate` | `LocalDate` | Optional | Show images added on the specified date | LocalDate getAddedDate() | setAddedDate(LocalDate addedDate) |
| `AddedDateStart` | `LocalDate` | Optional | Show images added on or after the specified date | LocalDate getAddedDateStart() | setAddedDateStart(LocalDate addedDateStart) |
| `AspectRatioMin` | `Double` | Optional | Show images with the specified aspect ratio or higher, using a positive decimal of the width divided by the height, such as 1.7778 for a 16:9 image<br><br>**Constraints**: `>= 0` | Double getAspectRatioMin() | setAspectRatioMin(Double aspectRatioMin) |
| `AspectRatioMax` | `Double` | Optional | Show images with the specified aspect ratio or lower, using a positive decimal of the width divided by the height, such as 1.7778 for a 16:9 image<br><br>**Constraints**: `>= 0` | Double getAspectRatioMax() | setAspectRatioMax(Double aspectRatioMax) |
| `AspectRatio` | `Double` | Optional | Show images with the specified aspect ratio, using a positive decimal of the width divided by the height, such as 1.7778 for a 16:9 image | Double getAspectRatio() | setAspectRatio(Double aspectRatio) |
| `AddedDateEnd` | `LocalDate` | Optional | Show images added before the specified date | LocalDate getAddedDateEnd() | setAddedDateEnd(LocalDate addedDateEnd) |
| `Authentic` | `Boolean` | Optional | Show only authentic images | Boolean getAuthentic() | setAuthentic(Boolean authentic) |
| `Category` | `String` | Optional | Show images with the specified Shutterstock-defined category; specify a category name or ID | String getCategory() | setCategory(String category) |
| `Color` | `String` | Optional | Specify either a hexadecimal color in the format '4F21EA' or 'grayscale'; the API returns images that use similar colors | String getColor() | setColor(String color) |
| `Contributor` | `List<String>` | Optional | Show images with the specified contributor names or IDs, allows multiple | List<String> getContributor() | setContributor(List<String> contributor) |
| `ContributorCountry` | [`SearchImageContributorCountry`](../../doc/models/containers/search-image-contributor-country.md) | Optional | This is a container for one-of cases. | SearchImageContributorCountry getContributorCountry() | setContributorCountry(SearchImageContributorCountry contributorCountry) |
| `Fields` | `String` | Optional | Fields to display in the response; see the documentation for the fields parameter in the overview section | String getFields() | setFields(String fields) |
| `Height` | `Integer` | Optional | (Deprecated; use height_from and height_to instead) Show images with the specified height | Integer getHeight() | setHeight(Integer height) |
| `HeightFrom` | `Integer` | Optional | Show images with the specified height or larger, in pixels | Integer getHeightFrom() | setHeightFrom(Integer heightFrom) |
| `HeightTo` | `Integer` | Optional | Show images with the specified height or smaller, in pixels | Integer getHeightTo() | setHeightTo(Integer heightTo) |
| `ImageType` | [`List<ImageType>`](../../doc/models/image-type.md) | Optional | Show images of the specified type | List<ImageType> getImageType() | setImageType(List<ImageType> imageType) |
| `KeywordSafeSearch` | `Boolean` | Optional | Hide results with potentially unsafe keywords<br><br>**Default**: `true` | Boolean getKeywordSafeSearch() | setKeywordSafeSearch(Boolean keywordSafeSearch) |
| `Language` | [`Language2`](../../doc/models/language-2.md) | Optional | Set query and result language (uses Accept-Language header if not set) | Language2 getLanguage() | setLanguage(Language2 language) |
| `License` | [`List<License>`](../../doc/models/license.md) | Optional | Show only images with the specified license | List<License> getLicense() | setLicense(List<License> license) |
| `Model` | `List<String>` | Optional | Show image results with the specified model IDs | List<String> getModel() | setModel(List<String> model) |
| `Orientation` | [`Orientation`](../../doc/models/orientation.md) | Optional | Show image results with horizontal or vertical orientation | Orientation getOrientation() | setOrientation(Orientation orientation) |
| `Page` | `Integer` | Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` | Integer getPage() | setPage(Integer page) |
| `PerPage` | `Integer` | Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 0`, `<= 20` | Integer getPerPage() | setPerPage(Integer perPage) |
| `PeopleModelReleased` | `Boolean` | Optional | Show images of people with a signed model release | Boolean getPeopleModelReleased() | setPeopleModelReleased(Boolean peopleModelReleased) |
| `PeopleAge` | [`PeopleAge`](../../doc/models/people-age.md) | Optional | Show images that feature people of the specified age category | PeopleAge getPeopleAge() | setPeopleAge(PeopleAge peopleAge) |
| `PeopleEthnicity` | [`List<PeopleEthnicity>`](../../doc/models/people-ethnicity.md) | Optional | Show images with people of the specified ethnicities, or start with NOT to show images without those ethnicities | List<PeopleEthnicity> getPeopleEthnicity() | setPeopleEthnicity(List<PeopleEthnicity> peopleEthnicity) |
| `PeopleGender` | [`PeopleGender`](../../doc/models/people-gender.md) | Optional | Show images with people of the specified gender | PeopleGender getPeopleGender() | setPeopleGender(PeopleGender peopleGender) |
| `PeopleNumber` | `Integer` | Optional | Show images with the specified number of people<br><br>**Constraints**: `>= 0`, `<= 4` | Integer getPeopleNumber() | setPeopleNumber(Integer peopleNumber) |
| `Query` | `String` | Optional | One or more search terms separated by spaces; you can use NOT to filter out images that match a term | String getQuery() | setQuery(String query) |
| `Region` | [`SearchImageRegion`](../../doc/models/containers/search-image-region.md) | Optional | This is a container for any-of cases. | SearchImageRegion getRegion() | setRegion(SearchImageRegion region) |
| `Safe` | `Boolean` | Optional | Enable or disable safe search<br><br>**Default**: `true` | Boolean getSafe() | setSafe(Boolean safe) |
| `Sort` | [`Sort`](../../doc/models/sort.md) | Optional | Sort by<br><br>**Default**: `Sort.POPULAR` | Sort getSort() | setSort(Sort sort) |
| `SpellcheckQuery` | `Boolean` | Optional | Spellcheck the search query and return results on suggested spellings<br><br>**Default**: `true` | Boolean getSpellcheckQuery() | setSpellcheckQuery(Boolean spellcheckQuery) |
| `View` | [`View`](../../doc/models/view.md) | Optional | Amount of detail to render in the response<br><br>**Default**: `View.MINIMAL` | View getView() | setView(View view) |
| `Width` | `Integer` | Optional | (Deprecated; use width_from and width_to instead) Show images with the specified width | Integer getWidth() | setWidth(Integer width) |
| `WidthFrom` | `Integer` | Optional | Show images with the specified width or larger, in pixels | Integer getWidthFrom() | setWidthFrom(Integer widthFrom) |
| `WidthTo` | `Integer` | Optional | Show images with the specified width or smaller, in pixels | Integer getWidthTo() | setWidthTo(Integer widthTo) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.License;
import com.shutterstock.api.models.SearchImage;
import com.shutterstock.api.models.Sort;
import java.io.IOException;
import java.util.Arrays;

SearchImage searchImage = new SearchImage.Builder()
    .addedDate(DateTimeHelper.fromSimpleDate("2016-03-13"))
    .addedDateStart(DateTimeHelper.fromSimpleDate("2016-03-13"))
    .aspectRatioMin(67.22D)
    .aspectRatioMax(185.46D)
    .aspectRatio(80.36D)
    .license(Arrays.asList(
        License.EDITORIAL
    ))
    .query("cat")
    .sort(Sort.POPULAR)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

