
# Genre List

List of audio genres

## Structure

`GenreList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | `List<String>` | Required | List of genres | List<String> getData() | setData(List<String> data) |

## Example

```java
import com.shutterstock.api.models.GenreList;
import java.util.Arrays;

GenreList genreList = new GenreList.Builder(
    Arrays.asList(
        "Rock",
        "Pop > Singer-Songwriter",
        "Pop > Synth Pop",
        "Production / Film Scores"
    )
)
.build();
```

