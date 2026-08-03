
# Subscription

Subscription information

*This model accepts additional fields of type Object.*

## Structure

`Subscription`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Allotment` | [`Allotment`](../../doc/models/allotment.md) | Optional | An allotment of credits as part of a subscription | Allotment getAllotment() | setAllotment(Allotment allotment) |
| `Description` | `String` | Optional | Description of the subscription | String getDescription() | setDescription(String description) |
| `ExpirationTime` | `LocalDateTime` | Optional | Date the subscription ends | LocalDateTime getExpirationTime() | setExpirationTime(LocalDateTime expirationTime) |
| `Formats` | [`List<LicenseFormat>`](../../doc/models/license-format.md) | Optional | List of formats that are licensable for the subscription | List<LicenseFormat> getFormats() | setFormats(List<LicenseFormat> formats) |
| `Id` | `String` | Required | Unique internal identifier for the subscription | String getId() | setId(String id) |
| `License` | `String` | Optional | Internal identifier for the type of subscription | String getLicense() | setLicense(String license) |
| `AssetType` | `String` | Optional | Identifier for the type of assets associated with this subscription (images, videos, audio, editorial) | String getAssetType() | setAssetType(String assetType) |
| `Metadata` | `Object` | Optional | Subscription metadata; different for each customer | Object getMetadata() | setMetadata(Object metadata) |
| `PricePerDownload` | [`Price`](../../doc/models/price.md) | Optional | Price | Price getPricePerDownload() | setPricePerDownload(Price pricePerDownload) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Allotment;
import com.shutterstock.api.models.LicenseFormat;
import com.shutterstock.api.models.MediaType;
import com.shutterstock.api.models.Subscription;
import java.io.IOException;
import java.util.Arrays;

Subscription subscription = new Subscription.Builder(
    "s8906043"
)
.allotment(new Allotment.Builder()
        .downloadsLeft(5)
        .downloadsLimit(10)
        .endTime(DateTimeHelper.fromRfc8601DateTime("2020-05-29T12:10:22-05:00"))
        .startTime(DateTimeHelper.fromRfc8601DateTime("2020-05-29T12:10:22-05:00"))
        .contentTiers(ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
.description("Annual Subscription")
.expirationTime(DateTimeHelper.fromRfc8601DateTime("2020-05-29T12:10:22-05:00"))
.formats(Arrays.asList(
        new LicenseFormat.Builder()
            .description("Small")
            .format("jpg")
            .mediaType(MediaType.IMAGE)
            .minResolution(500)
            .size("small")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
        new LicenseFormat.Builder()
            .description("Med")
            .format("jpg")
            .mediaType(MediaType.IMAGE)
            .minResolution(1000)
            .size("medium")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
        new LicenseFormat.Builder()
            .description("Vector")
            .format("eps")
            .mediaType(MediaType.IMAGE)
            .minResolution(8)
            .size("vector")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    ))
.license("standard")
.assetType("images")
.metadata(ApiHelper.deserialize("{}"))
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

