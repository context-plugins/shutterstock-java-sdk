
# Image Search Results

Image search results

*This model accepts additional fields of type Object.*

## Structure

`ImageSearchResults`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<Image>`](../../doc/models/image.md) | Required | List of images | List<Image> getData() | setData(List<Image> data) |
| `Message` | `String` | Optional | Server-generated message, if any | String getMessage() | setMessage(String message) |
| `Page` | `Integer` | Optional | Current page that is returned | Integer getPage() | setPage(Integer page) |
| `PerPage` | `Integer` | Optional | Number of results per page | Integer getPerPage() | setPerPage(Integer perPage) |
| `SearchId` | `String` | Required | Unique identifier for the search request | String getSearchId() | setSearchId(String searchId) |
| `SpellcheckInfo` | `Object` | Optional | Returns information if search phrase has potentially been mistyped or another query would lead to better search results | Object getSpellcheckInfo() | setSpellcheckInfo(Object spellcheckInfo) |
| `TotalCount` | `int` | Required | Total count of all results across all pages | int getTotalCount() | setTotalCount(int totalCount) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Assets3;
import com.shutterstock.api.models.Category;
import com.shutterstock.api.models.Contributor;
import com.shutterstock.api.models.Image;
import com.shutterstock.api.models.ImageSearchResults;
import com.shutterstock.api.models.Thumbnail;
import java.io.IOException;
import java.util.Arrays;

ImageSearchResults imageSearchResults = new ImageSearchResults.Builder(
    Arrays.asList(
        new Image.Builder(
            new Contributor.Builder(
                "250738318"
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
            "1572478477",
            "image"
        )
        .addedDate(DateTimeHelper.fromSimpleDate("2016-03-13"))
        .affiliateUrl("affiliate_url6")
        .aspect(1.5D)
        .assets(new Assets3.Builder()
                .hugeJpg(null)
                .hugeThumb(new Thumbnail.Builder(
                    260,
                    "https://image.shutterstock.com/image-photo/cropped-image-woman-gardening-260nw-1572478477.jpg",
                    390
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
                .largeThumb(new Thumbnail.Builder(
                    100,
                    "https://thumb7.shutterstock.com/thumb_large/250738318/1572478477/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
                    150
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
                .mediumJpg(null)
                .preview(new Thumbnail.Builder(
                    300,
                    "https://image.shutterstock.com/display_pic_with_logo/250738318/1572478477/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
                    450
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
                .preview1000(new Thumbnail.Builder(
                    667,
                    "https://ak.picdn.net/shutterstock/photos/1572478477/watermark_1000/1706028c641ea2f443057287c67d9b91/preview_1000-1572478477.jpg",
                    1000
                )
                .build())
                .preview1500(new Thumbnail.Builder(
                    1000,
                    "https://image.shutterstock.com/z/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
                    1500
                )
                .build())
                .smallThumb(new Thumbnail.Builder(
                    67,
                    "https://thumb7.shutterstock.com/thumb_small/250738318/1572478477/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
                    100
                )
                .build())
                .mosaic(new Thumbnail.Builder(
                    167,
                    "https://image.shutterstock.com/image-photo/stock-photo-cropped-image-of-woman-gardening-250nw-1572478477.jpg",
                    250
                )
                .build())
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
        .categories(Arrays.asList(
                new Category.Builder()
                    .id("id8")
                    .name("name8")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build(),
                new Category.Builder()
                    .id("id8")
                    .name("name8")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build(),
                new Category.Builder()
                    .id("id8")
                    .name("name8")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build()
            ))
        .description("cropped image of woman gardening")
        .hasModelRelease(true)
        .imageType("photo")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ),
    "749090bb-2967-4a20-b22e-c800dc845e10",
    45
)
.message("message8")
.page(1)
.perPage(5)
.spellcheckInfo(ApiHelper.deserialize("{}"))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

