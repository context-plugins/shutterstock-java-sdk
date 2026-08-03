
# Collection Data List

List of collections

*This model accepts additional fields of type Object.*

## Structure

`CollectionDataList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<MCollection>`](../../doc/models/m-collection.md) | Optional | Collections | List<MCollection> getData() | setData(List<MCollection> data) |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | Error list; appears only if there was an error | List<Error> getErrors() | setErrors(List<Error> errors) |
| `Message` | `String` | Optional | Server-generated message, if any | String getMessage() | setMessage(String message) |
| `Page` | `Integer` | Optional | The current page of results | Integer getPage() | setPage(Integer page) |
| `PerPage` | `Integer` | Optional | The number of results per page | Integer getPerPage() | setPerPage(Integer perPage) |
| `TotalCount` | `Integer` | Optional | The total number of results across all pages | Integer getTotalCount() | setTotalCount(Integer totalCount) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.CollectionDataList;
import com.shutterstock.api.models.CollectionItem;
import com.shutterstock.api.models.Error;
import com.shutterstock.api.models.MCollection;
import java.io.IOException;
import java.util.Arrays;

CollectionDataList collectionDataList = new CollectionDataList.Builder()
    .data(Arrays.asList(
        new MCollection.Builder(
            "293542904",
            "My collection",
            85
        )
        .coverItem(new CollectionItem.Builder(
                "297886754"
            )
            .addedTime(DateTimeHelper.fromRfc8601DateTime("2016-03-13T12:52:32.123Z"))
            .mediaType("media_type6")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build())
        .createdTime(DateTimeHelper.fromRfc8601DateTime("2016-03-13T12:52:32.123Z"))
        .itemsUpdatedTime(DateTimeHelper.fromRfc8601DateTime("2021-05-20T16:15:22-04:00"))
        .shareCode("share_code6")
        .shareUrl("share_url4")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ))
    .errors(Arrays.asList(
        new Error.Builder(
            "message0"
        )
        .code("code8")
        .data("data0")
        .items(Arrays.asList(
                ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}")
            ))
        .path("path4")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ))
    .message("message4")
    .page(1)
    .perPage(100)
    .totalCount(1)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

