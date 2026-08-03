
# Instrument List

List of instruments

## Structure

`InstrumentList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | `List<String>` | Required | List of instruments | List<String> getData() | setData(List<String> data) |

## Example

```java
import com.shutterstock.api.models.InstrumentList;
import java.util.Arrays;

InstrumentList instrumentList = new InstrumentList.Builder(
    Arrays.asList(
        "Orchestra",
        "Organ",
        "Oud",
        "Pads",
        "Electric Guitar"
    )
)
.build();
```

