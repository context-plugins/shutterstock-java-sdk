
# Collection Item Data List

List of items in a collection

*This model accepts additional fields of type Object.*

## Structure

`CollectionItemDataList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<CollectionItem>`](../../doc/models/collection-item.md) | Optional | Assets in the collection | List<CollectionItem> getData() | setData(List<CollectionItem> data) |
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
import com.shutterstock.api.models.CollectionItem;
import com.shutterstock.api.models.CollectionItemDataList;
import com.shutterstock.api.models.Error;
import java.io.IOException;
import java.util.Arrays;

CollectionItemDataList collectionItemDataList = new CollectionItemDataList.Builder()
    .data(Arrays.asList(
        new CollectionItem.Builder(
            "1690105108"
        )
        .addedTime(DateTimeHelper.fromRfc8601DateTime("2021-07-08T12:33:37.000Z"))
        .mediaType("image")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build(),
        new CollectionItem.Builder(
            "1468703072"
        )
        .addedTime(DateTimeHelper.fromRfc8601DateTime("2021-07-08T12:31:43.000Z"))
        .mediaType("image")
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
    .message("message0")
    .page(1)
    .perPage(2)
    .totalCount(82)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

