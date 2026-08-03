
# Editorial Livefeed

Metadata about editorial livefeed

*This model accepts additional fields of type Object.*

## Structure

`EditorialLivefeed`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `CoverItem` | [`EditorialCoverItem`](../../doc/models/editorial-cover-item.md) | Optional | Cover image for editorial livefeed | EditorialCoverItem getCoverItem() | setCoverItem(EditorialCoverItem coverItem) |
| `CreatedTime` | `LocalDateTime` | Optional | When the livefeed was initially created | LocalDateTime getCreatedTime() | setCreatedTime(LocalDateTime createdTime) |
| `Id` | `String` | Required | Livefeed ID | String getId() | setId(String id) |
| `Name` | `String` | Required | Name of the livefeed | String getName() | setName(String name) |
| `TotalItemCount` | `int` | Required | Total count of items in the livefeed | int getTotalItemCount() | setTotalItemCount(int totalItemCount) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.EditorialCoverItem;
import com.shutterstock.api.models.EditorialLivefeed;
import java.io.IOException;

EditorialLivefeed editorialLivefeed = new EditorialLivefeed.Builder(
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
.build();
```

