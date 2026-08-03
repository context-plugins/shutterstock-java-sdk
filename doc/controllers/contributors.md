# Contributors

```java
ContributorsApi contributorsApi = client.getContributorsApi();
```

## Class Name

`ContributorsApi`

## Methods

* [Get Contributor List](../../doc/controllers/contributors.md#get-contributor-list)
* [Get Contributor](../../doc/controllers/contributors.md#get-contributor)
* [Get Contributor Collections List](../../doc/controllers/contributors.md#get-contributor-collections-list)
* [Get Contributor Collections](../../doc/controllers/contributors.md#get-contributor-collections)
* [Get Contributor Collection Items](../../doc/controllers/contributors.md#get-contributor-collection-items)


# Get Contributor List

This endpoint lists information about one or more contributors, including contributor type, equipment they use and other attributes.

```java
CompletableFuture<ApiResponse<ContributorProfileDataList>> getContributorListAsync(
    final List<String> id)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md) **OR** [basic](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `List<String>` | Query, Required | One or more contributor IDs |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ContributorProfileDataList`](../../doc/models/contributor-profile-data-list.md).

## Example Usage

```java
List<String> id = Arrays.asList(
    "id0",
    "id1"
);

contributorsApi.getContributorListAsync(id).thenAccept(result -> {
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
  "data": [
    {
      "about": "John Doe's photographs",
      "contributor_type": [
        "photographer"
      ],
      "display_name": "John Doe",
      "equipment": [
        "Nikon",
        "Fuji"
      ],
      "id": "12345678",
      "location": "US",
      "portfolio_url": "https://www.shutterstock.com/g/jdoe",
      "social_media": {
        "facebook": "http://example.com/jdoe",
        "google_plus": "http://example.com/jdoe",
        "linkedin": "http://example.com/jdoe",
        "pinterest": "http://example.com/jdoe",
        "tumblr": "http://example.com/jdoe",
        "twitter": "http://example.com/jdoe"
      },
      "styles": [
        "landscape",
        "nature",
        "footage_travel"
      ],
      "subjects": [
        "animals",
        "landmarks",
        "nature",
        "objects",
        "recreation"
      ],
      "website": "http://example.com/profiles/jdoe"
    }
  ],
  "page": 1,
  "per_page": 5,
  "total_count": 15
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Get Contributor

This endpoint shows information about a single contributor, including contributor type, equipment they use, and other attributes.

```java
CompletableFuture<ApiResponse<ContributorProfile>> getContributorAsync(
    final String contributorId)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md) **OR** [basic](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `contributorId` | `String` | Template, Required | Contributor ID |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ContributorProfile`](../../doc/models/contributor-profile.md).

## Example Usage

```java
String contributorId = "1653538";

contributorsApi.getContributorAsync(contributorId).thenAccept(result -> {
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
  "about": "John Doe's photographs",
  "contributor_type": [
    "photographer"
  ],
  "display_name": "John Doe",
  "equipment": [
    "Nikon",
    "Fuji"
  ],
  "id": "12345678",
  "location": "US",
  "portfolio_url": "https://www.shutterstock.com/g/jdoe",
  "social_media": {
    "facebook": "http://example.com/jdoe",
    "google_plus": "http://example.com/jdoe",
    "linkedin": "http://example.com/jdoe",
    "pinterest": "http://example.com/jdoe",
    "tumblr": "http://example.com/jdoe",
    "twitter": "http://example.com/jdoe"
  },
  "styles": [
    "landscape",
    "nature",
    "footage_travel"
  ],
  "subjects": [
    "animals",
    "landmarks",
    "nature",
    "objects",
    "recreation"
  ],
  "website": "http://example.com/profiles/jdoe"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Get Contributor Collections List

This endpoint lists collections based on contributor ID.

```java
CompletableFuture<ApiResponse<CollectionDataList>> getContributorCollectionsListAsync(
    final String contributorId,
    final Sort24 sort)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md) **OR** [basic](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `contributorId` | `String` | Template, Required | Contributor ID |
| `sort` | [`Sort24`](../../doc/models/sort-24.md) | Query, Optional | Sort order |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CollectionDataList`](../../doc/models/collection-data-list.md).

## Example Usage

```java
String contributorId = "800506";

contributorsApi.getContributorCollectionsListAsync(contributorId, null).thenAccept(result -> {
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
  "data": [
    {
      "id": "293542904",
      "name": "My collection",
      "total_item_count": 85,
      "items_updated_time": "2021-05-20T16:15:22-04:00",
      "cover_item": {
        "id": "297886754"
      }
    }
  ],
  "page": 1,
  "per_page": 100,
  "total_count": 1
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 404 | Contributor not found | `ApiException` |


# Get Contributor Collections

This endpoint gets more detailed information about a contributor's collection, including its cover image, timestamps for its creation, and most recent update. To get the items in collections, use GET /v2/contributors/{contributor_id}/collections/{id}/items.

```java
CompletableFuture<ApiResponse<MCollection>> getContributorCollectionsAsync(
    final String contributorId,
    final String id)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md) **OR** [basic](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `contributorId` | `String` | Template, Required | Contributor ID |
| `id` | `String` | Template, Required | Collection ID that belongs to the contributor |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`MCollection`](../../doc/models/m-collection.md).

## Example Usage

```java
String contributorId = "800506";
String id = "1991678";

contributorsApi.getContributorCollectionsAsync(contributorId, id).thenAccept(result -> {
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
  "id": "293542904",
  "name": "My collection",
  "total_item_count": 85,
  "items_updated_time": "2021-05-20T16:15:22-04:00",
  "cover_item": {
    "id": "297886754"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 404 | Set not found | `ApiException` |


# Get Contributor Collection Items

This endpoint lists the IDs of items in a contributor's collection and the date that each was added.

```java
CompletableFuture<ApiResponse<CollectionItemDataList>> getContributorCollectionItemsAsync(
    final String contributorId,
    final String id,
    final Integer page,
    final Integer perPage,
    final Sort5 sort)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md) **OR** [basic](../../doc/auth/basic-authentication.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `contributorId` | `String` | Template, Required | Contributor ID |
| `id` | `String` | Template, Required | Collection ID that belongs to the contributor |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 50` |
| `sort` | [`Sort5`](../../doc/models/sort-5.md) | Query, Optional | Sort order |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CollectionItemDataList`](../../doc/models/collection-item-data-list.md).

## Example Usage

```java
String contributorId = "800506";
String id = "1991678";
Integer page = 1;
Integer perPage = 20;

contributorsApi.getContributorCollectionItemsAsync(contributorId, id, page, perPage, null).thenAccept(result -> {
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
  "data": [
    {
      "added_time": "2014-05-01T05:49:46-04:00",
      "id": "168592952",
      "media_type": "image"
    },
    {
      "added_time": "2014-05-01T05:49:59-04:00",
      "id": "88269310",
      "media_type": "image"
    },
    {
      "added_time": "2014-05-01T05:50:21-04:00",
      "id": "94373977",
      "media_type": "image"
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
| 404 | Set not found | `ApiException` |

