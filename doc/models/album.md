
# Album

Album metadata

## Structure

`Album`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | The album ID | String getId() | setId(String id) |
| `Title` | `String` | Required | The album title | String getTitle() | setTitle(String title) |

## Example

```java
import com.shutterstock.api.models.Album;

Album album = new Album.Builder(
    "1234567",
    "Happy Music"
)
.build();
```

