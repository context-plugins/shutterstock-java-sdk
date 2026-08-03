
# Test Validate

Validation results

*This model accepts additional fields of type Object.*

## Structure

`TestValidate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Header` | [`Header`](../../doc/models/header.md) | Optional | Headers as included in the request | Header getHeader() | setHeader(Header header) |
| `Query` | [`Query`](../../doc/models/query.md) | Optional | Query as included in the request | Query getQuery() | setQuery(Query query) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.Header;
import com.shutterstock.api.models.Query;
import com.shutterstock.api.models.TestValidate;
import java.io.IOException;
import java.util.Arrays;

TestValidate testValidate = new TestValidate.Builder()
    .header(new Header.Builder()
        .userAgent("Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/51.0.2704.103 Safari/537.36")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
    .query(new Query.Builder(
        123456
    )
    .tag(Arrays.asList(
            "Test string"
        ))
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

