
# License Sfx Result Data List

List of information about licensed sound effects

*This model accepts additional fields of type Object.*

## Structure

`LicenseSfxResultDataList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<LicenseSfxResult>`](../../doc/models/license-sfx-result.md) | Optional | Sound effects license results | List<LicenseSfxResult> getData() | setData(List<LicenseSfxResult> data) |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | Error list; appears only if there was an error | List<Error> getErrors() | setErrors(List<Error> errors) |
| `Message` | `String` | Optional | Server-generated message, if any | String getMessage() | setMessage(String message) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Download6;
import com.shutterstock.api.models.Error;
import com.shutterstock.api.models.LicenseSfxResult;
import com.shutterstock.api.models.LicenseSfxResultDataList;
import java.io.IOException;
import java.util.Arrays;

LicenseSfxResultDataList licenseSfxResultDataList = new LicenseSfxResultDataList.Builder()
    .data(Arrays.asList(
        new LicenseSfxResult.Builder(
            "123456789"
        )
        .allotmentCharge(1)
        .download(new Download6.Builder(
                "https://download.shutterstock.com/gatekeeper/[random-characters]/shutterstock_59656357.mp3"
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build())
        .error("error4")
        .licenseId("license_id6")
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
.additionalProperty("page", ApiHelper.deserialize("1"))
.additionalProperty("per_page", ApiHelper.deserialize("5"))
.additionalProperty("total_count", ApiHelper.deserialize("123455"))
    .build();
```

