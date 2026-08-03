
# M Collection

Metadata about a collection of assets

*This model accepts additional fields of type Object.*

## Structure

`MCollection`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `CoverItem` | [`CollectionItem`](../../doc/models/collection-item.md) | Optional | Metadata about an item that is part of a collection | CollectionItem getCoverItem() | setCoverItem(CollectionItem coverItem) |
| `CreatedTime` | `LocalDateTime` | Optional | When the collection was created | LocalDateTime getCreatedTime() | setCreatedTime(LocalDateTime createdTime) |
| `Id` | `String` | Required | The collection ID | String getId() | setId(String id) |
| `ItemsUpdatedTime` | `LocalDateTime` | Optional | The last time this collection's items were updated | LocalDateTime getItemsUpdatedTime() | setItemsUpdatedTime(LocalDateTime itemsUpdatedTime) |
| `Name` | `String` | Required | The name of the collection | String getName() | setName(String name) |
| `ShareCode` | `String` | Optional | A code that can be used to share the collection (optional) | String getShareCode() | setShareCode(String shareCode) |
| `ShareUrl` | `String` | Optional | The browser URL that can be used to share the collection (optional) | String getShareUrl() | setShareUrl(String shareUrl) |
| `TotalItemCount` | `int` | Required | The number of items in the collection | int getTotalItemCount() | setTotalItemCount(int totalItemCount) |
| `UpdatedTime` | `LocalDateTime` | Optional | The last time the collection was update (other than changes to the items in it) | LocalDateTime getUpdatedTime() | setUpdatedTime(LocalDateTime updatedTime) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.CollectionItem;
import com.shutterstock.api.models.MCollection;
import java.io.IOException;

MCollection collection = new MCollection.Builder(
    "293542904",
    "My collection",
    85
)
.coverItem(new CollectionItem.Builder(
        "297886754"
    )
    .addedTime(DateTimeHelper.fromRfc8601DateTime("2016-03-13T12:52:32.123Z"))
    .mediaType("media_type6")
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build())
.createdTime(DateTimeHelper.fromRfc8601DateTime("2016-03-13T12:52:32.123Z"))
.itemsUpdatedTime(DateTimeHelper.fromRfc8601DateTime("2021-05-20T16:15:22-04:00"))
.shareCode("share_code2")
.shareUrl("share_url0")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
.build();
```

