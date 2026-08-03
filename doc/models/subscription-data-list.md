
# Subscription Data List

List of subscriptions

*This model accepts additional fields of type Object.*

## Structure

`SubscriptionDataList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<Subscription>`](../../doc/models/subscription.md) | Optional | Subscriptions retrieved from this user | List<Subscription> getData() | setData(List<Subscription> data) |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | Error list; appears only if there was an error | List<Error> getErrors() | setErrors(List<Error> errors) |
| `Message` | `String` | Optional | Optional error message | String getMessage() | setMessage(String message) |
| `Page` | `Integer` | Optional | Current page that is being queried | Integer getPage() | setPage(Integer page) |
| `PerPage` | `Integer` | Optional | Amount of subscriptions to show per page | Integer getPerPage() | setPerPage(Integer perPage) |
| `TotalCount` | `Integer` | Optional | Total number of subscriptions for this user | Integer getTotalCount() | setTotalCount(Integer totalCount) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Allotment;
import com.shutterstock.api.models.Error;
import com.shutterstock.api.models.LicenseFormat;
import com.shutterstock.api.models.MediaType;
import com.shutterstock.api.models.Subscription;
import com.shutterstock.api.models.SubscriptionDataList;
import java.io.IOException;
import java.util.Arrays;

SubscriptionDataList subscriptionDataList = new SubscriptionDataList.Builder()
    .data(Arrays.asList(
        new Subscription.Builder(
            "s8906043"
        )
        .allotment(new Allotment.Builder()
                .downloadsLeft(5)
                .downloadsLimit(10)
                .endTime(DateTimeHelper.fromRfc8601DateTime("2020-05-29T12:10:22-05:00"))
                .startTime(DateTimeHelper.fromRfc8601DateTime("2020-05-29T12:10:22-05:00"))
                .contentTiers(ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                .build())
        .description("Annual Subscription")
        .expirationTime(DateTimeHelper.fromRfc8601DateTime("2020-05-29T12:10:22-05:00"))
        .formats(Arrays.asList(
                new LicenseFormat.Builder()
                    .description("Small")
                    .format("jpg")
                    .mediaType(MediaType.IMAGE)
                    .minResolution(500)
                    .size("small")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build(),
                new LicenseFormat.Builder()
                    .description("Med")
                    .format("jpg")
                    .mediaType(MediaType.IMAGE)
                    .minResolution(1000)
                    .size("medium")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build(),
                new LicenseFormat.Builder()
                    .description("Vector")
                    .format("eps")
                    .mediaType(MediaType.IMAGE)
                    .minResolution(8)
                    .size("vector")
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build()
            ))
        .license("standard")
        .assetType("images")
        .metadata(ApiHelper.deserialize("{}"))
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
    .perPage(5)
    .totalCount(123455)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

