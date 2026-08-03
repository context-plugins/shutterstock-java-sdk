
# Editorial Cover Item

Cover image for editorial livefeed

*This model accepts additional fields of type Object.*

## Structure

`EditorialCoverItem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Height` | `Integer` | Optional | - | Integer getHeight() | setHeight(Integer height) |
| `Id` | `String` | Required | - | String getId() | setId(String id) |
| `Url` | `String` | Required | - | String getUrl() | setUrl(String url) |
| `Width` | `Integer` | Optional | - | Integer getWidth() | setWidth(Integer width) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.EditorialCoverItem;
import java.io.IOException;

EditorialCoverItem editorialCoverItem = new EditorialCoverItem.Builder(
    "9763363q",
    "https://editorial01.shuttercorp.net/thumb/9763363q/51e28f39/Shutterstock_9763363q.jpg"
)
.height(117)
.width(170)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

