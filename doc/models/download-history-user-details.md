
# Download History User Details

Information about a user

*This model accepts additional fields of type Object.*

## Structure

`DownloadHistoryUserDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Username` | `String` | Required | The name of the user who downloaded the item | String getUsername() | setUsername(String username) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.DownloadHistoryUserDetails;
import java.io.IOException;

DownloadHistoryUserDetails downloadHistoryUserDetails = new DownloadHistoryUserDetails.Builder(
    "jdoe"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

