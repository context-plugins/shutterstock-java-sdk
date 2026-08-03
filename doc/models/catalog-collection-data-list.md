
# Catalog Collection Data List

List of catalog collections

*This model accepts additional fields of type Object.*

## Structure

`CatalogCollectionDataList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Page` | `double` | Required | - | double getPage() | setPage(double page) |
| `PerPage` | `double` | Required | - | double getPerPage() | setPerPage(double perPage) |
| `TotalCount` | `double` | Required | - | double getTotalCount() | setTotalCount(double totalCount) |
| `Data` | [`List<CatalogCollection>`](../../doc/models/catalog-collection.md) | Required | List of catalog collections | List<CatalogCollection> getData() | setData(List<CatalogCollection> data) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Asset;
import com.shutterstock.api.models.CatalogCollection;
import com.shutterstock.api.models.CatalogCollectionDataList;
import com.shutterstock.api.models.CatalogCollectionItem;
import com.shutterstock.api.models.CatalogCollectionRole;
import com.shutterstock.api.models.CatalogCollectionRoleAssignments;
import com.shutterstock.api.models.Roles;
import com.shutterstock.api.models.Type;
import com.shutterstock.api.models.Type1;
import com.shutterstock.api.models.Visibility;
import java.io.IOException;
import java.util.Arrays;

CatalogCollectionDataList catalogCollectionDataList = new CatalogCollectionDataList.Builder(
    1D,
    20D,
    1D,
    Arrays.asList(
        new CatalogCollection.Builder(
            "126351028",
            "My collection",
            2D,
            DateTimeHelper.fromRfc8601DateTime("2021-05-20T16:15:22-04:00"),
            DateTimeHelper.fromRfc8601DateTime("2021-06-10T13:26:09-04:00"),
            Visibility.ENUM_PUBLIC,
            new CatalogCollectionRoleAssignments.Builder(
                "126351028",
                new Roles.Builder()
                    .owners(Arrays.asList(
                        new CatalogCollectionRole.Builder(
                            "321",
                            Type1.USER,
                            "userOne@org.com"
                        )
                        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                        .build()
                    ))
                    .editors(Arrays.asList(
                        new CatalogCollectionRole.Builder(
                            "987",
                            Type1.USER,
                            "userTwo@org.com"
                        )
                        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                        .build()
                    ))
                    .viewers(Arrays.asList(

                    ))
                .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
                    .build()
            )
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
        )
        .coverAsset(new CatalogCollectionItem.Builder(
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
                    "collection_ids5",
                    "collection_ids6"
                ))
            .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build())
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    )
)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

