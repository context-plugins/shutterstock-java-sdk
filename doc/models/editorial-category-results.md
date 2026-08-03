
# Editorial Category Results

List of editorial categories

*This model accepts additional fields of type Object.*

## Structure

`EditorialCategoryResults`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<EditorialCategory>`](../../doc/models/editorial-category.md) | Optional | List of editorial categories | List<EditorialCategory> getData() | setData(List<EditorialCategory> data) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.EditorialCategory;
import com.shutterstock.api.models.EditorialCategoryResults;
import java.io.IOException;
import java.util.Arrays;

EditorialCategoryResults editorialCategoryResults = new EditorialCategoryResults.Builder()
    .data(Arrays.asList(
        new EditorialCategory.Builder()
            .name("Animal")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
        new EditorialCategory.Builder()
            .name("Awards")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
        new EditorialCategory.Builder()
            .name("Art")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    ))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

