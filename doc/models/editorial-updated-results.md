
# Editorial Updated Results

Editorial updated results

*This model accepts additional fields of type Object.*

## Structure

`EditorialUpdatedResults`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<EditorialUpdatedContent>`](../../doc/models/editorial-updated-content.md) | Required | Editorial updated items | List<EditorialUpdatedContent> getData() | setData(List<EditorialUpdatedContent> data) |
| `Message` | `String` | Optional | Optional error message | String getMessage() | setMessage(String message) |
| `Next` | `String` | Optional | Cursor value that represents the next page of results | String getNext() | setNext(String next) |
| `PerPage` | `Integer` | Optional | Number of results per page | Integer getPerPage() | setPerPage(Integer perPage) |
| `Prev` | `String` | Optional | Cursor value that represents the previous page of results | String getPrev() | setPrev(String prev) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.CommercialStatus;
import com.shutterstock.api.models.EditorialAssets;
import com.shutterstock.api.models.EditorialUpdatedContent;
import com.shutterstock.api.models.EditorialUpdatedResults;
import com.shutterstock.api.models.ImageSizeDetails;
import com.shutterstock.api.models.Rights;
import com.shutterstock.api.models.Thumbnail;
import java.io.IOException;
import java.util.Arrays;

EditorialUpdatedResults editorialUpdatedResults = new EditorialUpdatedResults.Builder(
    Arrays.asList(
        new EditorialUpdatedContent.Builder(
            "9804979n"
        )
        .commercialStatus(new CommercialStatus.Builder()
                .status("available")
                .reason("reason6")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
        .aspect(1.481D)
        .assets(new EditorialAssets.Builder()
                .original(new ImageSizeDetails.Builder()
                    .displayName("Original")
                    .dpi(44)
                    .fileSize(36)
                    .format("format6")
                    .height(3263)
                    .isLicensable(true)
                    .width(4831)
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
                .thumb170(new Thumbnail.Builder(
                    115,
                    "https://editorial01.shutterstock.com/thumb/9804979n/c4377a53/Shutterstock_9804979n.jpg",
                    170
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
                .thumb220(new Thumbnail.Builder(
                    149,
                    "https://editorial01.shutterstock.com/thumb-220/9804979n/c57a68c7/Shutterstock_9804979n.jpg",
                    220
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
                .watermark450(new Thumbnail.Builder(
                    304,
                    "https://editorial01.shutterstock.com/wm-preview-450/9804979n/37d19dce/Shutterstock_9804979n.jpg",
                    450
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
                .watermark1500(new Thumbnail.Builder(
                    1500,
                    "https://editorial01.shutterstock.com/wm-preview-1500/9933285a/ab82fea4/Shutterstock_9933285a.jpg",
                    1040
                )
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
                .smallJpg(new ImageSizeDetails.Builder()
                    .displayName("Small")
                    .height(337)
                    .isLicensable(true)
                    .width(500)
                    .build())
                .mediumJpg(new ImageSizeDetails.Builder()
                    .displayName("Med")
                    .height(675)
                    .isLicensable(true)
                    .width(1000)
                    .build())
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
        .byline("ALEX HOFFORD/EPA-EFE/Shutterstock")
        .caption("")
        .categories(Arrays.asList(

            ))
        .dateTaken(DateTimeHelper.fromSimpleDate("2018-08-24"))
        .description("Members of the TyLoo e-Sports team from China prepare to face off against the Kinguin e-Sports team from Poland at the ICBC (Asia) e-Sports and Music Festival Hong Kong 2018, Hong Kong, China, 24 August 2018. The festival runs from 24 to 26 August with professional gamers from around the world competing in international e-sports tournaments.")
        .keywords(Arrays.asList(

            ))
        .title("Hong Kong kicks off international e-Sports competition, China - 24 Aug 2018")
        .updatedTime(DateTimeHelper.fromRfc8601DateTime("2019-07-15T20:04:44-04:00"))
        .rights(new Rights.Builder()
                .countries("CAN,+DEU,+GBR,+USA,-*")
                .build())
        .updates(Arrays.asList(
                "addition"
            ))
        .supplierCode("EPA")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.message("message8")
.next("eyJ2IjoxLCJzIjoxfQ==")
.perPage(1)
.prev("")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

