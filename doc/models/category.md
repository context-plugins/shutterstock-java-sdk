
# Category

Category information

*This model accepts additional fields of type Object.*

## Structure

`Category`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Optional | Category ID | String getId() | setId(String id) |
| `Name` | `String` | Optional | Category name | String getName() | setName(String name) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Category;
import java.io.IOException;

Category category = new Category.Builder()
    .id("1")
    .name("Animals/Wildlife")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

