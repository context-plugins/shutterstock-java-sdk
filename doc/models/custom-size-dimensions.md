
# Custom Size Dimensions

A custom height or a custom width to resize the image to, but not both (experimental)

*This model accepts additional fields of type Object.*

## Structure

`CustomSizeDimensions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Height` | `Integer` | Optional | Custom height to resize the image to<br><br>**Constraints**: `>= 100` | Integer getHeight() | setHeight(Integer height) |
| `Width` | `Integer` | Optional | Custom width to resize the image to<br><br>**Constraints**: `>= 100` | Integer getWidth() | setWidth(Integer width) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.CustomSizeDimensions;
import java.io.IOException;

CustomSizeDimensions customSizeDimensions = new CustomSizeDimensions.Builder()
    .height(600)
    .width(800)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

