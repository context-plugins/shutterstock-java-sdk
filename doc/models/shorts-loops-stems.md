
# Shorts Loops Stems

Links for Shorts, Loops and Stems previews

*This model accepts additional fields of type Object.*

## Structure

`ShortsLoopsStems`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Shorts` | [`Map<String, Shorts>`](../../doc/models/shorts.md) | Optional | - | Map<String, Shorts> getShorts() | setShorts(Map<String, Shorts> shorts) |
| `Loops` | [`Map<String, Loops>`](../../doc/models/loops.md) | Optional | - | Map<String, Loops> getLoops() | setLoops(Map<String, Loops> loops) |
| `Stems` | [`Map<String, Stems>`](../../doc/models/stems.md) | Optional | - | Map<String, Stems> getStems() | setStems(Map<String, Stems> stems) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Loops;
import com.shutterstock.api.models.Shorts;
import com.shutterstock.api.models.ShortsLoopsStems;
import com.shutterstock.api.models.Stems;
import java.io.IOException;
import java.util.LinkedHashMap;

ShortsLoopsStems shortsLoopsStems = new ShortsLoopsStems.Builder()
    .shorts(new LinkedHashMap<String, Shorts>() {{
        put("short_preview_1", new Shorts.Builder()
            .url("http://picdn.shuttercorp.net/shutterstock/audio/464947/short_preview_1/short_preview_1.mp3")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build());
        put("short_preview_2", new Shorts.Builder()
            .url("http://picdn.shuttercorp.net/shutterstock/audio/464947/short_preview_2/short_preview_2.mp3")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build());
    }})
    .loops(new LinkedHashMap<String, Loops>() {{
        put("loop_preview_1", new Loops.Builder()
            .url("http://picdn.shuttercorp.net/shutterstock/audio/464947/loop_preview_1/loop_preview_1.mp3")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build());
        put("loop_preview_2", new Loops.Builder()
            .url("http://picdn.shuttercorp.net/shutterstock/audio/464947/loop_preview_2/loop_preview_2.mp3")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build());
    }})
    .stems(new LinkedHashMap<String, Stems>() {{
        put("stem_preview_1", new Stems.Builder()
            .url("http://picdn.shuttercorp.net/shutterstock/audio/464947/stem_preview_1/stem_preview_1.mp3")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build());
        put("stem_preview_2", new Stems.Builder()
            .url("http://picdn.shuttercorp.net/shutterstock/audio/464947/stem_preview_1/stem_preview_1.mp3")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build());
    }})
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

