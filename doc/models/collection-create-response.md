
# Collection Create Response

Collection creation response

*This model accepts additional fields of type Object.*

## Structure

`CollectionCreateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | ID of the new collection | String getId() | setId(String id) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.CollectionCreateResponse;
import java.io.IOException;

CollectionCreateResponse collectionCreateResponse = new CollectionCreateResponse.Builder(
    "48433105"
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

