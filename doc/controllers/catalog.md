# Catalog

```java
CatalogApi catalogApi = client.getCatalogApi();
```

## Class Name

`CatalogApi`

## Methods

* [Search Catalog](../../doc/controllers/catalog.md#search-catalog)
* [Get Collections](../../doc/controllers/catalog.md#get-collections)
* [Create Collection](../../doc/controllers/catalog.md#create-collection)
* [Update Collection](../../doc/controllers/catalog.md#update-collection)
* [Delete Collection](../../doc/controllers/catalog.md#delete-collection)
* [Add to Collection](../../doc/controllers/catalog.md#add-to-collection)
* [Delete from Collection](../../doc/controllers/catalog.md#delete-from-collection)


# Search Catalog

This endpoint searches for assets in the account's catalog. If you specify more than one search parameter, the API uses an AND condition. Array parameters can be specified multiple times; in this case, the API uses an AND or an OR condition with those values, depending on the parameter. You can also filter search terms out in the `query` parameter by prefixing the term with NOT.

```java
CompletableFuture<ApiResponse<CatalogCollectionItemDataList>> searchCatalogAsync(
    final Sort5 sort,
    final Integer page,
    final Integer perPage,
    final String query,
    final List<String> collectionId,
    final List<AssetType> assetType)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sort` | [`Sort5`](../../doc/models/sort-5.md) | Query, Optional | Sort by<br><br>**Default**: `Sort5.NEWEST` |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 0`, `<= 500` |
| `query` | `String` | Query, Optional | One or more search terms separated by spaces |
| `collectionId` | `List<String>` | Query, Optional | Filter by collection id<br><br>**Constraints**: *Maximum Items*: `50` |
| `assetType` | [`List<AssetType>`](../../doc/models/asset-type.md) | Query, Optional | Filter by asset type |

## Requires scope

### customer_accessCode

`collections.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CatalogCollectionItemDataList`](../../doc/models/catalog-collection-item-data-list.md).

## Example Usage

```java
Sort5 sort = Sort5.NEWEST;
Integer page = 1;
Integer perPage = 50;
String query = "dogs on the beach";
List<String> collectionId = Arrays.asList(
    "123456",
    "456789",
    "13579"
);

List<AssetType> assetType = Arrays.asList(
    AssetType.IMAGE,
    AssetType.EDITORIALIMAGE
);

catalogApi.searchCatalogAsync(sort, page, perPage, query, collectionId, assetType).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response *(as JSON)*

```json
{
  "page": 1,
  "per_page": 1,
  "total_count": 82,
  "data": [
    {
      "id": "123",
      "asset": {
        "id": "1690105108",
        "type": "image",
        "name": "Young couple playing tennis at the court"
      },
      "created_time": "2021-06-10T13:26:09-04:00",
      "collection_ids": [
        "126351028"
      ]
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Get Collections

This endpoint returns a list of catalog collections.

```java
CompletableFuture<ApiResponse<CatalogCollectionDataList>> getCollectionsAsync(
    final Integer page,
    final Integer perPage,
    final Sort5 sort,
    final Boolean shared)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 2`, `<= 50` |
| `sort` | [`Sort5`](../../doc/models/sort-5.md) | Query, Optional | Sort by<br><br>**Default**: `Sort5.NEWEST` |
| `shared` | `Boolean` | Query, Optional | Set to true to omit collections that you own and return only collections  that are shared with you<br><br>**Default**: `false` |

## Requires scope

### customer_accessCode

`collections.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CatalogCollectionDataList`](../../doc/models/catalog-collection-data-list.md).

## Example Usage

```java
Integer page = 1;
Integer perPage = 20;
Sort5 sort = Sort5.NEWEST;
Boolean shared = false;

catalogApi.getCollectionsAsync(page, perPage, sort, shared).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response *(as JSON)*

```json
{
  "page": 1,
  "per_page": 20,
  "total_count": 1,
  "data": [
    {
      "id": "126351028",
      "name": "My collection",
      "cover_asset": {
        "id": "123",
        "asset": {
          "id": "1690105108",
          "type": "image",
          "name": "Young couple playing tennis at the court"
        },
        "created_time": "2021-06-10T13:26:09-04:00"
      },
      "total_item_count": 2,
      "created_time": "2021-05-20T16:15:22-04:00",
      "updated_time": "2021-06-10T13:26:09-04:00",
      "visibility": "public",
      "role_assignments": {
        "collection_id": "126351028",
        "roles": {
          "owners": [
            {
              "id": "321",
              "type": "USER",
              "email": "userOne@org.com"
            }
          ],
          "editors": [
            {
              "id": "987",
              "type": "USER",
              "email": "userTwo@org.com"
            }
          ],
          "viewers": []
        }
      }
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid status value | `ApiException` |


# Create Collection

This endpoint creates a catalog collection and optionally adds assets. To add assets to the collection later, use `PATCH /v2/catalog/collections/{collection_id}/items`.

```java
CompletableFuture<ApiResponse<CatalogCollection>> createCollectionAsync(
    final CreateCatalogCollection body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateCatalogCollection`](../../doc/models/create-catalog-collection.md) | Body, Required | Create a catalog collection and, optionally, add items. |

## Requires scope

### customer_accessCode

`collections.edit`, `collections.view`

## Response Type

**201**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CatalogCollection`](../../doc/models/catalog-collection.md).

## Example Usage

```java
CreateCatalogCollection body = new CreateCatalogCollection.Builder(
    "New Collection"
)
.visibility(Visibility.ENUM_PUBLIC)
.items(Arrays.asList(
        new CreateCatalogCollectionItem.Builder(
            new Asset4.Builder(
                "image"
            )
            .id("1690105108")
            .build()
        )
        .build()
    ))
.build();

catalogApi.createCollectionAsync(body).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response *(as JSON)*

```json
{
  "id": "126351028",
  "name": "My collection",
  "cover_asset": {
    "id": "123",
    "asset": {
      "id": "1690105108",
      "type": "image",
      "name": "Young couple playing tennis at the court"
    },
    "created_time": "2021-06-10T13:26:09-04:00"
  },
  "total_item_count": 2,
  "created_time": "2021-05-20T16:15:22-04:00",
  "updated_time": "2021-06-10T13:26:09-04:00",
  "visibility": "public",
  "role_assignments": {
    "collection_id": "126351028",
    "roles": {
      "owners": [
        {
          "id": "321",
          "type": "USER",
          "email": "userOne@org.com"
        }
      ],
      "editors": [
        {
          "id": "987",
          "type": "USER",
          "email": "userTwo@org.com"
        }
      ],
      "viewers": []
    }
  }
}
```


# Update Collection

This endpoint updates the metadata of a catalog collection.

```java
CompletableFuture<ApiResponse<CatalogCollection>> updateCollectionAsync(
    final String collectionId,
    final UpdateCatalogCollection body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `collectionId` | `String` | Template, Required | ID of collection that needs to be modified |
| `body` | [`UpdateCatalogCollection`](../../doc/models/update-catalog-collection.md) | Body, Required | Collections Metadata to update |

## Requires scope

### customer_accessCode

`collections.edit`, `collections.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CatalogCollection`](../../doc/models/catalog-collection.md).

## Example Usage

```java
String collectionId = "126351028";
UpdateCatalogCollection body = new UpdateCatalogCollection.Builder()
    .name("My Collection")
    .visibility(Visibility.ENUM_PUBLIC)
    .coverAsset(new RemoveCatalogCollectionItem.Builder(
        "123"
    )
    .build())
    .build();

catalogApi.updateCollectionAsync(collectionId, body).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response *(as JSON)*

```json
{
  "id": "126351028",
  "name": "My collection",
  "cover_asset": {
    "id": "123",
    "asset": {
      "id": "1690105108",
      "type": "image",
      "name": "Young couple playing tennis at the court"
    },
    "created_time": "2021-06-10T13:26:09-04:00"
  },
  "total_item_count": 2,
  "created_time": "2021-05-20T16:15:22-04:00",
  "updated_time": "2021-06-10T13:26:09-04:00",
  "visibility": "public",
  "role_assignments": {
    "collection_id": "126351028",
    "roles": {
      "owners": [
        {
          "id": "321",
          "type": "USER",
          "email": "userOne@org.com"
        }
      ],
      "editors": [
        {
          "id": "987",
          "type": "USER",
          "email": "userTwo@org.com"
        }
      ],
      "viewers": []
    }
  }
}
```


# Delete Collection

This endpoint deletes a catalog collection. It does not remove the assets from the user's account's catalog.

```java
CompletableFuture<ApiResponse<Void>> deleteCollectionAsync(
    final String collectionId)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `collectionId` | `String` | Template, Required | The ID of the collection to delete |

## Requires scope

### customer_accessCode

`collections.edit`

## Response Type

**204**: OK

`void`

## Example Usage

```java
String collectionId = "126351028";

catalogApi.deleteCollectionAsync(collectionId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | Collection not found | `ApiException` |


# Add to Collection

This endpoint adds assets to a catalog collection. It also automatically adds the assets to the user's account's catalog.

```java
CompletableFuture<ApiResponse<CatalogCollection>> addToCollectionAsync(
    final String collectionId,
    final CreateCatalogCollectionItems body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `collectionId` | `String` | Template, Required | The ID of the collection to add assets to |
| `body` | [`CreateCatalogCollectionItems`](../../doc/models/create-catalog-collection-items.md) | Body, Required | Collection item attributes to add to collection |

## Requires scope

### customer_accessCode

`collections.edit`, `collections.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CatalogCollection`](../../doc/models/catalog-collection.md).

## Example Usage

```java
String collectionId = "126351028";
CreateCatalogCollectionItems body = new CreateCatalogCollectionItems.Builder(
    Arrays.asList(
        new CreateCatalogCollectionItem.Builder(
            new Asset4.Builder(
                "image"
            )
            .id("1690105108")
            .build()
        )
        .build()
    )
)
.build();

catalogApi.addToCollectionAsync(collectionId, body).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response *(as JSON)*

```json
{
  "id": "126351028",
  "name": "My collection",
  "cover_asset": {
    "id": "123",
    "asset": {
      "id": "1690105108",
      "type": "image",
      "name": "Young couple playing tennis at the court"
    },
    "created_time": "2021-06-10T13:26:09-04:00"
  },
  "total_item_count": 2,
  "created_time": "2021-05-20T16:15:22-04:00",
  "updated_time": "2021-06-10T13:26:09-04:00",
  "visibility": "public",
  "role_assignments": {
    "collection_id": "126351028",
    "roles": {
      "owners": [
        {
          "id": "321",
          "type": "USER",
          "email": "userOne@org.com"
        }
      ],
      "editors": [
        {
          "id": "987",
          "type": "USER",
          "email": "userTwo@org.com"
        }
      ],
      "viewers": []
    }
  }
}
```


# Delete from Collection

This endpoint removes assets from a catalog collection. It does not remove the assets from the user's account's catalog.

```java
CompletableFuture<ApiResponse<CatalogCollection>> deleteFromCollectionAsync(
    final String collectionId,
    final RemoveCatalogCollectionItems body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `collectionId` | `String` | Template, Required | The ID of the collection to remove assets from |
| `body` | [`RemoveCatalogCollectionItems`](../../doc/models/remove-catalog-collection-items.md) | Body, Required | Items to remove from the collection |

## Requires scope

### customer_accessCode

`collections.edit`, `collections.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CatalogCollection`](../../doc/models/catalog-collection.md).

## Example Usage

```java
String collectionId = "126351028";
RemoveCatalogCollectionItems body = new RemoveCatalogCollectionItems.Builder(
    Arrays.asList(
        new RemoveCatalogCollectionItem.Builder(
            "123"
        )
        .build()
    )
)
.build();

catalogApi.deleteFromCollectionAsync(collectionId, body).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    // TODO failure callback handler
    exception.printStackTrace();
    return null;
});
```

## Example Response *(as JSON)*

```json
{
  "id": "126351028",
  "name": "My collection",
  "cover_asset": {
    "id": "123",
    "asset": {
      "id": "1690105108",
      "type": "image",
      "name": "Young couple playing tennis at the court"
    },
    "created_time": "2021-06-10T13:26:09-04:00"
  },
  "total_item_count": 2,
  "created_time": "2021-05-20T16:15:22-04:00",
  "updated_time": "2021-06-10T13:26:09-04:00",
  "visibility": "public",
  "role_assignments": {
    "collection_id": "126351028",
    "roles": {
      "owners": [
        {
          "id": "321",
          "type": "USER",
          "email": "userOne@org.com"
        }
      ],
      "editors": [
        {
          "id": "987",
          "type": "USER",
          "email": "userTwo@org.com"
        }
      ],
      "viewers": []
    }
  }
}
```

