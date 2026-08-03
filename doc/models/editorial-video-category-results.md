
# Editorial Video Category Results

List of editorial video categories

*This model accepts additional fields of type Object.*

## Structure

`EditorialVideoCategoryResults`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<EditorialCategory>`](../../doc/models/editorial-category.md) | Optional | - | List<EditorialCategory> getData() | setData(List<EditorialCategory> data) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.EditorialCategory;
import com.shutterstock.api.models.EditorialVideoCategoryResults;
import java.io.IOException;
import java.util.Arrays;

EditorialVideoCategoryResults editorialVideoCategoryResults = new EditorialVideoCategoryResults.Builder()
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
            .build(),
        new EditorialCategory.Builder()
            .name("Film Stills")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    ))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

