
# Editorial Image Livefeed List

List of editorial livefeeds

*This model accepts additional fields of type Object.*

## Structure

`EditorialImageLivefeedList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<EditorialImageLivefeed>`](../../doc/models/editorial-image-livefeed.md) | Required | Editorial livefeeds | List<EditorialImageLivefeed> getData() | setData(List<EditorialImageLivefeed> data) |
| `Message` | `String` | Optional | Optional error message | String getMessage() | setMessage(String message) |
| `Page` | `Integer` | Optional | Current page of the response | Integer getPage() | setPage(Integer page) |
| `PerPage` | `Integer` | Optional | Number of results per page | Integer getPerPage() | setPerPage(Integer perPage) |
| `TotalCount` | `int` | Required | Total count of all results | int getTotalCount() | setTotalCount(int totalCount) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.EditorialCoverItem;
import com.shutterstock.api.models.EditorialImageLivefeed;
import com.shutterstock.api.models.EditorialImageLivefeedList;
import java.io.IOException;
import java.util.Arrays;

EditorialImageLivefeedList editorialImageLivefeedList = new EditorialImageLivefeedList.Builder(
    Arrays.asList(
        new EditorialImageLivefeed.Builder(
            "2018%2F07%2F17%2FPrince%20Charles%20and%20Camilla%20Duchess%20of%20Cornwall%20visit%20to%20Cornwall%2C%20Day%202",
            "Prince Charles and Camilla Duchess of Cornwall visit to Cornwall, Day 2",
            38
        )
        .coverItem(new EditorialCoverItem.Builder(
                "9763363q",
                "https://editorial01.shuttercorp.net/thumb/9763363q/51e28f39/Shutterstock_9763363q.jpg"
            )
            .height(117)
            .width(170)
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build())
        .createdTime(DateTimeHelper.fromRfc8601DateTime("2018-07-17T12:42:03+00:00"))
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ),
    5300
)
.message("message6")
.page(1)
.perPage(1)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

