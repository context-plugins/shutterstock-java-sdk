
# Updated Media Data List

List of updated media

*This model accepts additional fields of type Object.*

## Structure

`UpdatedMediaDataList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<UpdatedMedia>`](../../doc/models/updated-media.md) | Optional | Updated media items | List<UpdatedMedia> getData() | setData(List<UpdatedMedia> data) |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | Error list; appears only if there was an error | List<Error> getErrors() | setErrors(List<Error> errors) |
| `Message` | `String` | Optional | Server-generated message, if any | String getMessage() | setMessage(String message) |
| `Page` | `Integer` | Optional | Current page that is returned | Integer getPage() | setPage(Integer page) |
| `PerPage` | `Integer` | Optional | Number of results per page | Integer getPerPage() | setPerPage(Integer perPage) |
| `TotalCount` | `Integer` | Optional | Total count of all results across all pages | Integer getTotalCount() | setTotalCount(Integer totalCount) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Error;
import com.shutterstock.api.models.UpdatedMedia;
import com.shutterstock.api.models.UpdatedMediaDataList;
import java.io.IOException;
import java.util.Arrays;

UpdatedMediaDataList updatedMediaDataList = new UpdatedMediaDataList.Builder()
    .data(Arrays.asList(
        new UpdatedMedia.Builder(
            "123456789",
            DateTimeHelper.fromRfc8601DateTime("2020-05-29T12:10:22-05:00"),
            Arrays.asList(
                "addition",
                "edit"
            )
        )
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
        .build(),
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
    .perPage(5)
    .totalCount(13)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

