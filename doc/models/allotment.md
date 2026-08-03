
# Allotment

An allotment of credits as part of a subscription

*This model accepts additional fields of type Object.*

## Structure

`Allotment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `DownloadsLeft` | `Integer` | Optional | Number of credits remaining in the subscription | Integer getDownloadsLeft() | setDownloadsLeft(Integer downloadsLeft) |
| `DownloadsLimit` | `Integer` | Optional | Total number of credits available to this subscription | Integer getDownloadsLimit() | setDownloadsLimit(Integer downloadsLimit) |
| `EndTime` | `LocalDateTime` | Optional | Date the subscription ends | LocalDateTime getEndTime() | setEndTime(LocalDateTime endTime) |
| `StartTime` | `LocalDateTime` | Optional | Date the subscription started | LocalDateTime getStartTime() | setStartTime(LocalDateTime startTime) |
| `ContentTiers` | `Object` | Optional | Downloads left and limit values for each content tier in the license | Object getContentTiers() | setContentTiers(Object contentTiers) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Allotment;
import java.io.IOException;

Allotment allotment = new Allotment.Builder()
    .downloadsLeft(5)
    .downloadsLimit(10)
    .endTime(DateTimeHelper.fromRfc8601DateTime("2020-05-29T12:10:22-05:00"))
    .startTime(DateTimeHelper.fromRfc8601DateTime("2020-05-29T12:10:22-05:00"))
    .contentTiers(ApiHelper.deserialize("{\"standard_images\":{\"downloads_left\":5,\"downloads_limit\":10},\"offset\":{\"downloads_left\":9,\"downloads_limit\":10}}"))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

