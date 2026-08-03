
# Mood List

List of audio moods

## Structure

`MoodList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | `List<String>` | Required | List of audio moods | List<String> getData() | setData(List<String> data) |

## Example

```java
import com.shutterstock.api.models.MoodList;
import java.util.Arrays;

MoodList moodList = new MoodList.Builder(
    Arrays.asList(
        "Action / Sports",
        "Adventure / Discovery",
        "Aerobics / Workout",
        "Aggressive"
    )
)
.build();
```

