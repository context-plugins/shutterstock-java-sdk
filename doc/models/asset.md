
# Asset

*This model accepts additional fields of type Object.*

## Structure

`Asset`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Optional | - | String getId() | setId(String id) |
| `Type` | [`Type`](../../doc/models/type.md) | Required | - | Type getType() | setType(Type type) |
| `Name` | `String` | Optional | - | String getName() | setName(String name) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Asset;
import com.shutterstock.api.models.Type;
import java.io.IOException;

Asset asset = new Asset.Builder(
    Type.IMAGE
)
.id("id0")
.name("name0")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

