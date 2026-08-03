
# Editorial Search Results

Editorial search results

*This model accepts additional fields of type Object.*

## Structure

`EditorialSearchResults`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<EditorialContent>`](../../doc/models/editorial-content.md) | Required | Editorial items | List<EditorialContent> getData() | setData(List<EditorialContent> data) |
| `Message` | `String` | Optional | Optional error message | String getMessage() | setMessage(String message) |
| `Next` | `String` | Optional | Cursor value that represents the next page of results | String getNext() | setNext(String next) |
| `Page` | `Integer` | Optional | Current page of the response | Integer getPage() | setPage(Integer page) |
| `PerPage` | `Integer` | Optional | Number of results per page | Integer getPerPage() | setPerPage(Integer perPage) |
| `Prev` | `String` | Optional | Cursor value that represents the previous page of results | String getPrev() | setPrev(String prev) |
| `SearchId` | `String` | Optional | Unique identifier for the search request | String getSearchId() | setSearchId(String searchId) |
| `TotalCount` | `int` | Required | Total count of all results | int getTotalCount() | setTotalCount(int totalCount) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.EditorialAssets;
import com.shutterstock.api.models.EditorialCategory;
import com.shutterstock.api.models.EditorialContent;
import com.shutterstock.api.models.EditorialSearchResults;
import com.shutterstock.api.models.ImageSizeDetails;
import com.shutterstock.api.models.Thumbnail;
import java.io.IOException;
import java.util.Arrays;

EditorialSearchResults editorialSearchResults = new EditorialSearchResults.Builder(
    Arrays.asList(
        new EditorialContent.Builder(
            "10687730b"
        )
        .aspect(1.621D)
        .assets(new EditorialAssets.Builder()
                .original(new ImageSizeDetails.Builder()
                    .displayName("Original")
                    .dpi(44)
                    .fileSize(36)
                    .format("format6")
                    .height(3693)
                    .isLicensable(true)
                    .width(5985)
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .thumb170(new Thumbnail.Builder(
                    105,
                    "https://editorial01.shuttercorp.net/thumb/10687730b/272a999e/Shutterstock_10687730b.jpg",
                    170
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
                .thumb220(new Thumbnail.Builder(
                    136,
                    "https://editorial01.shuttercorp.net/thumb-220/10687730b/927a6ebe/Shutterstock_10687730b.jpg",
                    220
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
                .watermark450(new Thumbnail.Builder(
                    278,
                    "https://editorial01.shuttercorp.net/wm-preview-450/10687730b/ff2443ad/Shutterstock_10687730b.jpg",
                    450
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
                .watermark1500(new Thumbnail.Builder(
                    926,
                    "https://editorial01.shuttercorp.net/wm-preview-1500/10687730b/ee2d7ae1/Shutterstock_10687730b.jpg",
                    1500
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
                .smallJpg(new ImageSizeDetails.Builder()
                    .displayName("Small")
                    .height(309)
                    .isLicensable(true)
                    .width(500)
                    .build())
                .mediumJpg(new ImageSizeDetails.Builder()
                    .displayName("Med")
                    .height(617)
                    .isLicensable(true)
                    .width(1000)
                    .build())
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
        .byline("Jon Super/AP/Shutterstock")
        .caption("")
        .categories(Arrays.asList(
                new EditorialCategory.Builder()
                    .name("Sport")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build()
            ))
        .dateTaken(DateTimeHelper.fromSimpleDate("2021-05-11"))
        .description("Security and stewards stand outside the Old Trafford stadium in Manchester, England, ahead of the English Premier League soccer match between Manchester United and Leicester City. This is the first Manchester United home match since fans protested against American owner Joel Glazer, forcing the postponement of the team's Premier League game against Liverpool. The protests prompted Glazer to publish a letter in which he pledged to accelerate discussions with fans about supporters being able to have a greater say at the club")
        .keywords(Arrays.asList(
                "england",
                "europe",
                "leicester city fc",
                "manchester",
                "manchester united fc",
                "men's soccer",
                "men's sports",
                "premier league",
                "professional soccer",
                "soccer",
                "sports",
                "united kingdom",
                "western europe",
                "wsoc"
            ))
        .title("Soccer Premier League, Manchester, United Kingdom - 11 May 2021")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ),
    46845
)
.message("message6")
.next("eyJ2IjoyLCJzIjoxLCJwIjpbMF19")
.page(92)
.perPage(1)
.prev("")
.searchId("BaMzOAkpHIvfnuWVRFs1ag")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

