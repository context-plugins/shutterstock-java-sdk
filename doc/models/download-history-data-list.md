
# Download History Data List

List of download events

*This model accepts additional fields of type Object.*

## Structure

`DownloadHistoryDataList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<DownloadHistory>`](../../doc/models/download-history.md) | Optional | Download events | List<DownloadHistory> getData() | setData(List<DownloadHistory> data) |
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
import com.shutterstock.api.models.DownloadHistory;
import com.shutterstock.api.models.DownloadHistoryDataList;
import com.shutterstock.api.models.DownloadHistoryFormatDetails;
import com.shutterstock.api.models.DownloadHistoryMediaDetails;
import com.shutterstock.api.models.DownloadHistoryUserDetails;
import com.shutterstock.api.models.Error;
import java.io.IOException;
import java.util.Arrays;

DownloadHistoryDataList downloadHistoryDataList = new DownloadHistoryDataList.Builder()
    .data(Arrays.asList(
        new DownloadHistory.Builder(
            DateTimeHelper.fromRfc8601DateTime("2021-07-15T15:46:34.000Z"),
            "e1eba3833793e77188d22caae8bac9f2cd",
            "premier_editorial_all_digital"
        )
        .audio(null)
        .image(new DownloadHistoryMediaDetails.Builder(
                "9763363ao"
            )
            .format(new DownloadHistoryFormatDetails.Builder()
                    .format("format0")
                    .size("original")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build())
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build())
        .isDownloadable(false)
        .metadata(ApiHelper.deserialize("{\"purchase_order\":\"123456\",\"client\":\"Company A\",\"job\":\"Important project\",\"other\":\"Important media\"}"))
        .subscriptionId("s12345678")
        .user(new DownloadHistoryUserDetails.Builder(
                "editorial_test_account_002"
            )
            .build())
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
    .perPage(1)
    .totalCount(2890)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

