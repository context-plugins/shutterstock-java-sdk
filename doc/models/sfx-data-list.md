
# Sfx Data List

List of sound effects

*This model accepts additional fields of type Object.*

## Structure

`SfxDataList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<Sfx>`](../../doc/models/sfx.md) | Optional | Sound Effects | List<Sfx> getData() | setData(List<Sfx> data) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Contributor;
import com.shutterstock.api.models.Sfx;
import com.shutterstock.api.models.SfxDataList;
import java.io.IOException;
import java.util.Arrays;

SfxDataList sfxDataList = new SfxDataList.Builder()
    .data(Arrays.asList(
        new Sfx.Builder(
            new Contributor.Builder(
                "1234"
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
            "123",
            "sfx"
        )
        .addedDate(DateTimeHelper.fromSimpleDate("2016-03-13"))
        .affiliateUrl("affiliate_url6")
        .artist("artist8")
        .assets(null)
        .description("description0")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

