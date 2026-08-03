
# Download History Revshare Details

Pricing information for revenue-sharing transactions

*This model accepts additional fields of type Object.*

## Structure

`DownloadHistoryRevshareDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `PurchaseAmount` | `String` | Required | The amount charged for the license | String getPurchaseAmount() | setPurchaseAmount(String purchaseAmount) |
| `PurchaseCurrency` | `String` | Required | The currency the amount was charged in | String getPurchaseCurrency() | setPurchaseCurrency(String purchaseCurrency) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.DownloadHistoryRevshareDetails;
import java.io.IOException;

DownloadHistoryRevshareDetails downloadHistoryRevshareDetails = new DownloadHistoryRevshareDetails.Builder(
    "8.65",
    "USD"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

