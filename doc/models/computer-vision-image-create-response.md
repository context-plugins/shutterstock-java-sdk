
# Computer Vision Image Create Response

Asset upload information

*This model accepts additional fields of type Object.*

## Structure

`ComputerVisionImageCreateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `UploadId` | `String` | Required | - | String getUploadId() | setUploadId(String uploadId) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.ComputerVisionImageCreateResponse;
import java.io.IOException;

ComputerVisionImageCreateResponse computerVisionImageCreateResponse = new ComputerVisionImageCreateResponse.Builder(
    "Udb14e1c3540bdbf82b4b3fe12d3a44f2"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

