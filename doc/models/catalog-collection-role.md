
# Catalog Collection Role

A user that has access to a catalog collection

*This model accepts additional fields of type Object.*

## Structure

`CatalogCollectionRole`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | - | String getId() | setId(String id) |
| `Type` | [`Type1`](../../doc/models/type-1.md) | Required | - | Type1 getType() | setType(Type1 type) |
| `Email` | `String` | Required | - | String getEmail() | setEmail(String email) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.CatalogCollectionRole;
import com.shutterstock.api.models.Type1;
import java.io.IOException;

CatalogCollectionRole catalogCollectionRole = new CatalogCollectionRole.Builder(
    "123",
    Type1.USER,
    "user123@org.com"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

