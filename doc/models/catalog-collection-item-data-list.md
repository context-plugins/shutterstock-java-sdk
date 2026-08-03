
# Catalog Collection Item Data List

List of catalog collection items

*This model accepts additional fields of type Object.*

## Structure

`CatalogCollectionItemDataList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Page` | `double` | Required | - | double getPage() | setPage(double page) |
| `PerPage` | `double` | Required | - | double getPerPage() | setPerPage(double perPage) |
| `TotalCount` | `double` | Required | - | double getTotalCount() | setTotalCount(double totalCount) |
| `Data` | [`List<CatalogCollectionItem>`](../../doc/models/catalog-collection-item.md) | Required | List of catalog collection items | List<CatalogCollectionItem> getData() | setData(List<CatalogCollectionItem> data) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Asset;
import com.shutterstock.api.models.CatalogCollectionItem;
import com.shutterstock.api.models.CatalogCollectionItemDataList;
import com.shutterstock.api.models.Type;
import java.io.IOException;
import java.util.Arrays;

CatalogCollectionItemDataList catalogCollectionItemDataList = new CatalogCollectionItemDataList.Builder(
    1D,
    1D,
    82D,
    Arrays.asList(
        new CatalogCollectionItem.Builder(
            "123",
            new Asset.Builder(
                Type.IMAGE
            )
            .id("1690105108")
            .name("Young couple playing tennis at the court")
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
            DateTimeHelper.fromRfc8601DateTime("2021-06-10T13:26:09-04:00")
        )
        .collectionIds(Arrays.asList(
                "126351028"
            ))
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

