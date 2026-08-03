
# Price 1

Wholesale price information; only for rev-share partners

*This model accepts additional fields of type Object.*

## Structure

`Price1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `LocalAmount` | `Double` | Optional | Floating-point amount of the calculated rev-share price in the currency local_currency | Double getLocalAmount() | setLocalAmount(Double localAmount) |
| `LocalCurrency` | `String` | Optional | Currency of the rev-share price that was calculated | String getLocalCurrency() | setLocalCurrency(String localCurrency) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Price1;
import java.io.IOException;

Price1 price1 = new Price1.Builder()
    .localAmount(12.34D)
    .localCurrency("EUR")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

