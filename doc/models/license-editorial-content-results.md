
# License Editorial Content Results

List of editorial license results

*This model accepts additional fields of type Object.*

## Structure

`LicenseEditorialContentResults`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<LicenseEditorialContentResult>`](../../doc/models/license-editorial-content-result.md) | Optional | License results | List<LicenseEditorialContentResult> getData() | setData(List<LicenseEditorialContentResult> data) |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | Error list; appears only if there was an error | List<Error> getErrors() | setErrors(List<Error> errors) |
| `Message` | `String` | Optional | Optional error message | String getMessage() | setMessage(String message) |
| `Page` | `Integer` | Optional | Current page of the response | Integer getPage() | setPage(Integer page) |
| `PerPage` | `Integer` | Optional | Number of results per page | Integer getPerPage() | setPerPage(Integer perPage) |
| `TotalCount` | `Integer` | Optional | Total count of all results | Integer getTotalCount() | setTotalCount(Integer totalCount) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Download2;
import com.shutterstock.api.models.Error;
import com.shutterstock.api.models.LicenseEditorialContentResult;
import com.shutterstock.api.models.LicenseEditorialContentResults;
import java.io.IOException;
import java.util.Arrays;

LicenseEditorialContentResults licenseEditorialContentResults = new LicenseEditorialContentResults.Builder()
    .data(Arrays.asList(
        new LicenseEditorialContentResult.Builder(
            "69656358"
        )
        .allotmentCharge(1)
        .download(new Download2.Builder(
                "https://s3-eu-west-1.amazonaws.com/api-downloads.rexfeatures.com/[random-characters].jpg?Expires=1524717323"
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build())
        .error("error4")
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
    .message("message6")
    .page(1)
    .perPage(1)
    .totalCount(12)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

