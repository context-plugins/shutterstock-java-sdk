# Editorial Images

```java
EditorialImagesApi editorialImagesApi = client.getEditorialImagesApi();
```

## Class Name

`EditorialImagesApi`

## Methods

* [Search Editorial Images](../../doc/controllers/editorial-images.md#search-editorial-images)
* [List Editorial Image Categories](../../doc/controllers/editorial-images.md#list-editorial-image-categories)
* [Get Updated Editorial Images](../../doc/controllers/editorial-images.md#get-updated-editorial-images)
* [Get Editorial Image](../../doc/controllers/editorial-images.md#get-editorial-image)
* [List Editorial Images](../../doc/controllers/editorial-images.md#list-editorial-images)
* [Get Editorial Image License List](../../doc/controllers/editorial-images.md#get-editorial-image-license-list)
* [License Editorial Images](../../doc/controllers/editorial-images.md#license-editorial-images)
* [Get Editorial Image Livefeed List](../../doc/controllers/editorial-images.md#get-editorial-image-livefeed-list)
* [Get Editorial Image Livefeed](../../doc/controllers/editorial-images.md#get-editorial-image-livefeed)
* [Get Editorial Image Livefeed Items](../../doc/controllers/editorial-images.md#get-editorial-image-livefeed-items)
* [Get Editorial Image 1](../../doc/controllers/editorial-images.md#get-editorial-image-1)
* [License Editorial Image](../../doc/controllers/editorial-images.md#license-editorial-image)
* [Get Editorial Livefeed List](../../doc/controllers/editorial-images.md#get-editorial-livefeed-list)
* [Get Editorial Livefeed](../../doc/controllers/editorial-images.md#get-editorial-livefeed)
* [Get Editorial Livefeed Items](../../doc/controllers/editorial-images.md#get-editorial-livefeed-items)
* [Search Editorial](../../doc/controllers/editorial-images.md#search-editorial)
* [Get Editorial Categories](../../doc/controllers/editorial-images.md#get-editorial-categories)
* [Get Updated Editorial Image](../../doc/controllers/editorial-images.md#get-updated-editorial-image)


# Search Editorial Images

This endpoint searches for editorial images. If you specify more than one search parameter, the API uses an AND condition. For example, if you set the `category` parameter to "Alone,Performing" and also specify a `query` parameter, the results include only images that match the query and are in both the Alone and Performing categories. You can also filter search terms out in the `query` parameter by prefixing the term with NOT.

```java
CompletableFuture<ApiResponse<EditorialSearchResults>> searchEditorialImagesAsync(
    final String country,
    final String query,
    final Sort17 sort,
    final String category,
    final List<String> supplierCode,
    final LocalDate dateStart,
    final LocalDate dateEnd,
    final Integer perPage,
    final String cursor)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `country` | `String` | Query, Required | Show only editorial content that is available for distribution in a certain country |
| `query` | `String` | Query, Optional | One or more search terms separated by spaces |
| `sort` | [`Sort17`](../../doc/models/sort-17.md) | Query, Optional | Sort by<br><br>**Default**: `Sort17.RELEVANT` |
| `category` | `String` | Query, Optional | Show editorial content with each of the specified editorial categories; specify category names in a comma-separated list |
| `supplierCode` | `List<String>` | Query, Optional | Show only editorial content from certain suppliers |
| `dateStart` | `LocalDate` | Query, Optional | Show only editorial content generated on or after a specific date |
| `dateEnd` | `LocalDate` | Query, Optional | Show only editorial content generated on or before a specific date |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 50` |
| `cursor` | `String` | Query, Optional | The cursor of the page with which to start fetching results; this cursor is returned from previous requests |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialSearchResults`](../../doc/models/editorial-search-results.md).

## Example Usage

```java
String country = "USA";
String query = "The Academy Awards";
Sort17 sort = Sort17.RELEVANT;
String category = "Alone,Performing";
LocalDate dateStart = DateTimeHelper.fromSimpleDate("2020-05-29");
LocalDate dateEnd = DateTimeHelper.fromSimpleDate("2021-05-29");
Integer perPage = 20;
String cursor = "eyJ2IjoxLCJzIjoxfQ==";

editorialImagesApi.searchEditorialImagesAsync(country, query, sort, category, null, dateStart, dateEnd, perPage, cursor).thenAccept(result -> {
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
  "per_page": 1,
  "total_count": 46845,
  "search_id": "BaMzOAkpHIvfnuWVRFs1ag",
  "next": "eyJ2IjoyLCJzIjoxLCJwIjpbMF19",
  "prev": "",
  "data": [
    {
      "id": "10687730b",
      "title": "Soccer Premier League, Manchester, United Kingdom - 11 May 2021",
      "caption": "",
      "description": "Security and stewards stand outside the Old Trafford stadium in Manchester, England, ahead of the English Premier League soccer match between Manchester United and Leicester City. This is the first Manchester United home match since fans protested against American owner Joel Glazer, forcing the postponement of the team's Premier League game against Liverpool. The protests prompted Glazer to publish a letter in which he pledged to accelerate discussions with fans about supporters being able to have a greater say at the club",
      "byline": "Jon Super/AP/Shutterstock",
      "keywords": [
        "england",
        "europe",
        "leicester city fc",
        "manchester",
        "manchester united fc",
        "men's soccer",
        "men's sports",
        "premier league",
        "professional soccer",
        "soccer",
        "sports",
        "united kingdom",
        "western europe",
        "wsoc"
      ],
      "date_taken": "2021-05-11",
      "categories": [
        {
          "name": "Sport"
        }
      ],
      "aspect": 1.621,
      "assets": {
        "thumb_170": {
          "height": 105,
          "width": 170,
          "url": "https://editorial01.shuttercorp.net/thumb/10687730b/272a999e/Shutterstock_10687730b.jpg"
        },
        "thumb_220": {
          "height": 136,
          "width": 220,
          "url": "https://editorial01.shuttercorp.net/thumb-220/10687730b/927a6ebe/Shutterstock_10687730b.jpg"
        },
        "watermark_450": {
          "height": 278,
          "width": 450,
          "url": "https://editorial01.shuttercorp.net/wm-preview-450/10687730b/ff2443ad/Shutterstock_10687730b.jpg"
        },
        "watermark_1500": {
          "height": 926,
          "width": 1500,
          "url": "https://editorial01.shuttercorp.net/wm-preview-1500/10687730b/ee2d7ae1/Shutterstock_10687730b.jpg"
        },
        "small_jpg": {
          "display_name": "Small",
          "width": 500,
          "height": 309,
          "is_licensable": true
        },
        "medium_jpg": {
          "display_name": "Med",
          "width": 1000,
          "height": 617,
          "is_licensable": true
        },
        "original": {
          "display_name": "Original",
          "height": 3693,
          "width": 5985,
          "is_licensable": true
        }
      }
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
| 406 | Not Acceptable | `ApiException` |


# List Editorial Image Categories

This endpoint lists the categories that editorial images can belong to, which are separate from the categories that other types of assets can belong to.

```java
CompletableFuture<ApiResponse<EditorialImageCategoryResults>> listEditorialImageCategoriesAsync()
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialImageCategoryResults`](../../doc/models/editorial-image-category-results.md).

## Example Usage

```java
editorialImagesApi.listEditorialImageCategoriesAsync().thenAccept(result -> {
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
      "name": "Animal"
    },
    {
      "name": "Awards"
    },
    {
      "name": "Art"
    },
    {
      "name": "Film Stills"
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


# Get Updated Editorial Images

This endpoint lists editorial images that have been updated in the specified time period to update content management systems (CMS) or digital asset management (DAM) systems. In most cases, use the date_updated_start and date_updated_end parameters to specify a range updates based on when the updates happened. You can also use the date_taken_start and date_taken_end parameters to specify a range of updates based on when the image was taken.

```java
CompletableFuture<ApiResponse<EditorialUpdatedResults>> getUpdatedEditorialImagesAsync(
    final Type15 type,
    final LocalDateTime dateUpdatedStart,
    final LocalDateTime dateUpdatedEnd,
    final String country,
    final LocalDate dateTakenStart,
    final LocalDate dateTakenEnd,
    final String cursor,
    final Sort5 sort,
    final List<String> supplierCode,
    final Integer perPage)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `type` | [`Type15`](../../doc/models/type-15.md) | Query, Required | Specify `addition` to return only images that were added or `edit` to return only images that were edited or deleted |
| `dateUpdatedStart` | `LocalDateTime` | Query, Required | Show images images added, edited, or deleted after the specified date. Acceptable range is 1970-01-01T00:00:01 to 2038-01-19T00:00:00. |
| `dateUpdatedEnd` | `LocalDateTime` | Query, Required | Show images images added, edited, or deleted before the specified date. Acceptable range is 1970-01-01T00:00:01 to 2038-01-19T00:00:00. |
| `country` | `String` | Query, Required | Show only editorial content that is available for distribution in a certain country |
| `dateTakenStart` | `LocalDate` | Query, Optional | Show images that were taken on or after the specified date; use this parameter if you want recently created images from the collection instead of updated older assets |
| `dateTakenEnd` | `LocalDate` | Query, Optional | Show images that were taken before the specified date |
| `cursor` | `String` | Query, Optional | The cursor of the page with which to start fetching results; this cursor is returned from previous requests |
| `sort` | [`Sort5`](../../doc/models/sort-5.md) | Query, Optional | Sort by<br><br>**Default**: `Sort5.NEWEST` |
| `supplierCode` | `List<String>` | Query, Optional | Show only editorial content from certain suppliers<br><br>**Constraints**: *Maximum Length*: `5` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `500`<br><br>**Constraints**: `>= 100`, `<= 500` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialUpdatedResults`](../../doc/models/editorial-updated-results.md).

## Example Usage

```java
Type15 type = Type15.EDIT;
LocalDateTime dateUpdatedStart = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
LocalDateTime dateUpdatedEnd = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
String country = "USA";
LocalDate dateTakenStart = DateTimeHelper.fromSimpleDate("2020-02-04");
LocalDate dateTakenEnd = DateTimeHelper.fromSimpleDate("2020-02-05");
String cursor = "eyJ2IjoxLCJzIjoyfQ==";
Sort5 sort = Sort5.NEWEST;
Integer perPage = 200;

editorialImagesApi.getUpdatedEditorialImagesAsync(type, dateUpdatedStart, dateUpdatedEnd, country, dateTakenStart, dateTakenEnd, cursor, sort, null, perPage).thenAccept(result -> {
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
  "per_page": 1,
  "next": "eyJ2IjoxLCJzIjoxfQ==",
  "prev": "",
  "data": [
    {
      "id": "9804979n",
      "title": "Hong Kong kicks off international e-Sports competition, China - 24 Aug 2018",
      "caption": "",
      "description": "Members of the TyLoo e-Sports team from China prepare to face off against the Kinguin e-Sports team from Poland at the ICBC (Asia) e-Sports and Music Festival Hong Kong 2018, Hong Kong, China, 24 August 2018. The festival runs from 24 to 26 August with professional gamers from around the world competing in international e-sports tournaments.",
      "byline": "ALEX HOFFORD/EPA-EFE/Shutterstock",
      "supplier_code": "EPA",
      "keywords": [],
      "date_taken": "2018-08-24",
      "categories": [],
      "aspect": 1.481,
      "assets": {
        "thumb_170": {
          "height": 115,
          "width": 170,
          "url": "https://editorial01.shutterstock.com/thumb/9804979n/c4377a53/Shutterstock_9804979n.jpg"
        },
        "thumb_220": {
          "height": 149,
          "width": 220,
          "url": "https://editorial01.shutterstock.com/thumb-220/9804979n/c57a68c7/Shutterstock_9804979n.jpg"
        },
        "watermark_450": {
          "height": 304,
          "width": 450,
          "url": "https://editorial01.shutterstock.com/wm-preview-450/9804979n/37d19dce/Shutterstock_9804979n.jpg"
        },
        "watermark_1500": {
          "height": 1500,
          "width": 1040,
          "url": "https://editorial01.shutterstock.com/wm-preview-1500/9933285a/ab82fea4/Shutterstock_9933285a.jpg"
        },
        "original": {
          "display_name": "Original",
          "height": 3263,
          "width": 4831,
          "is_licensable": true
        },
        "small_jpg": {
          "display_name": "Small",
          "height": 337,
          "width": 500,
          "is_licensable": true
        },
        "medium_jpg": {
          "display_name": "Med",
          "height": 675,
          "width": 1000,
          "is_licensable": true
        }
      },
      "updated_time": "2019-07-15T20:04:44-04:00",
      "updates": [
        "addition"
      ],
      "commercial_status": {
        "status": "available"
      },
      "rights": {
        "countries": "CAN,+DEU,+GBR,+USA,-*"
      }
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
| 406 | Not Acceptable | `ApiException` |


# Get Editorial Image

This endpoint shows information about an editorial image, including a URL to a preview image and the sizes that it is available in.

```java
CompletableFuture<ApiResponse<EditorialContent>> getEditorialImageAsync(
    final String id,
    final String country)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Editorial ID |
| `country` | `String` | Query, Required | Returns only if the content is available for distribution in a certain country |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialContent`](../../doc/models/editorial-content.md).

## Example Usage

```java
String id = "9926131a";
String country = "USA";

editorialImagesApi.getEditorialImageAsync(id, country).thenAccept(result -> {
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
  "id": "10687730b",
  "title": "Soccer Premier League, Manchester, United Kingdom - 11 May 2021",
  "caption": "",
  "description": "Security and stewards stand outside the Old Trafford stadium in Manchester, England, ahead of the English Premier League soccer match between Manchester United and Leicester City. This is the first Manchester United home match since fans protested against American owner Joel Glazer, forcing the postponement of the team's Premier League game against Liverpool. The protests prompted Glazer to publish a letter in which he pledged to accelerate discussions with fans about supporters being able to have a greater say at the club",
  "byline": "Jon Super/AP/Shutterstock",
  "keywords": [
    "england",
    "europe",
    "leicester city fc",
    "manchester",
    "manchester united fc",
    "men's soccer",
    "men's sports",
    "premier league",
    "professional soccer",
    "soccer",
    "sports",
    "united kingdom",
    "western europe",
    "wsoc"
  ],
  "date_taken": "2021-05-11",
  "categories": [
    {
      "name": "Sport"
    }
  ],
  "aspect": 1.621,
  "assets": {
    "thumb_170": {
      "height": 105,
      "width": 170,
      "url": "https://editorial01.shuttercorp.net/thumb/10687730b/272a999e/Shutterstock_10687730b.jpg"
    },
    "thumb_220": {
      "height": 136,
      "width": 220,
      "url": "https://editorial01.shuttercorp.net/thumb-220/10687730b/927a6ebe/Shutterstock_10687730b.jpg"
    },
    "watermark_450": {
      "height": 278,
      "width": 450,
      "url": "https://editorial01.shuttercorp.net/wm-preview-450/10687730b/ff2443ad/Shutterstock_10687730b.jpg"
    },
    "watermark_1500": {
      "height": 926,
      "width": 1500,
      "url": "https://editorial01.shuttercorp.net/wm-preview-1500/10687730b/ee2d7ae1/Shutterstock_10687730b.jpg"
    },
    "small_jpg": {
      "display_name": "Small",
      "width": 500,
      "height": 309,
      "is_licensable": true
    },
    "medium_jpg": {
      "display_name": "Med",
      "width": 1000,
      "height": 617,
      "is_licensable": true
    },
    "original": {
      "display_name": "Original",
      "height": 3693,
      "width": 5985,
      "is_licensable": true
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 404 | Not Found | `ApiException` |


# List Editorial Images

This endpoint lists the details of editorial images.

```java
CompletableFuture<ApiResponse<EditorialImageResults>> listEditorialImagesAsync(
    final List<String> id,
    final String country,
    final String searchId)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `List<String>` | Query, Required | ID of the editorial image to list details for |
| `country` | `String` | Query, Required | Show only editorial image content that is available for distribution in a certain country |
| `searchId` | `String` | Query, Optional | The ID of the search that is related to this request |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialImageResults`](../../doc/models/editorial-image-results.md).

## Example Usage

```java
List<String> id = Arrays.asList(
    "id0"
);

String country = "USA";
String searchId = "00000000-0000-0000-0000-000000000000";

editorialImagesApi.listEditorialImagesAsync(id, country, searchId).thenAccept(result -> {
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
      "id": "10687730b",
      "title": "Soccer Premier League, Manchester, United Kingdom - 11 May 2021",
      "caption": "",
      "description": "Security and stewards stand outside the Old Trafford stadium in Manchester, England, ahead of the English Premier League soccer match between Manchester United and Leicester City. This is the first Manchester United home match since fans protested against American owner Joel Glazer, forcing the postponement of the team's Premier League game against Liverpool. The protests prompted Glazer to publish a letter in which he pledged to accelerate discussions with fans about supporters being able to have a greater say at the club",
      "byline": "Jon Super/AP/Shutterstock",
      "keywords": [
        "england",
        "europe",
        "leicester city fc",
        "manchester",
        "manchester united fc",
        "men's soccer",
        "men's sports",
        "premier league",
        "professional soccer",
        "soccer",
        "sports",
        "united kingdom",
        "western europe",
        "wsoc"
      ],
      "date_taken": "2021-05-11",
      "categories": [
        {
          "name": "Sport"
        }
      ],
      "aspect": 1.621,
      "assets": {
        "thumb_170": {
          "height": 105,
          "width": 170,
          "url": "https://editorial01.shuttercorp.net/thumb/10687730b/272a999e/Shutterstock_10687730b.jpg"
        },
        "thumb_220": {
          "height": 136,
          "width": 220,
          "url": "https://editorial01.shuttercorp.net/thumb-220/10687730b/927a6ebe/Shutterstock_10687730b.jpg"
        },
        "watermark_450": {
          "height": 278,
          "width": 450,
          "url": "https://editorial01.shuttercorp.net/wm-preview-450/10687730b/ff2443ad/Shutterstock_10687730b.jpg"
        },
        "watermark_1500": {
          "height": 926,
          "width": 1500,
          "url": "https://editorial01.shuttercorp.net/wm-preview-1500/10687730b/ee2d7ae1/Shutterstock_10687730b.jpg"
        },
        "small_jpg": {
          "display_name": "Small",
          "width": 500,
          "height": 309,
          "is_licensable": true
        },
        "medium_jpg": {
          "display_name": "Med",
          "width": 1000,
          "height": 617,
          "is_licensable": true
        },
        "original": {
          "display_name": "Original",
          "height": 3693,
          "width": 5985,
          "is_licensable": true
        }
      }
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


# Get Editorial Image License List

This endpoint lists existing editorial image licenses.

```java
CompletableFuture<ApiResponse<DownloadHistoryDataList>> getEditorialImageLicenseListAsync(
    final String imageId,
    final String license,
    final Integer page,
    final Integer perPage,
    final Sort5 sort,
    final String username,
    final LocalDateTime startDate,
    final LocalDateTime endDate,
    final DownloadAvailability downloadAvailability,
    final Boolean teamHistory)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `imageId` | `String` | Query, Optional | Show licenses for the specified editorial image ID |
| `license` | `String` | Query, Optional | Show editorial images that are available with the specified license name |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 0`, `<= 200` |
| `sort` | [`Sort5`](../../doc/models/sort-5.md) | Query, Optional | Sort order<br><br>**Default**: `Sort5.NEWEST` |
| `username` | `String` | Query, Optional | Filter licenses by username of licensee |
| `startDate` | `LocalDateTime` | Query, Optional | Show licenses created on or after the specified date |
| `endDate` | `LocalDateTime` | Query, Optional | Show licenses created before the specified date |
| `downloadAvailability` | [`DownloadAvailability`](../../doc/models/download-availability.md) | Query, Optional | Filter licenses by download availability<br><br>**Default**: `DownloadAvailability.ALL` |
| `teamHistory` | `Boolean` | Query, Optional | Set to true to see license history for all members of your team.<br><br>**Default**: `false` |

## Requires scope

### customer_accessCode

`licenses.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DownloadHistoryDataList`](../../doc/models/download-history-data-list.md).

## Example Usage

```java
String imageId = "12345678";
String license = "premier_editorial_all_digital";
Integer page = 1;
Integer perPage = 20;
Sort5 sort = Sort5.NEWEST;
String username = "aUniqueUsername";
LocalDateTime startDate = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
LocalDateTime endDate = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
DownloadAvailability downloadAvailability = DownloadAvailability.ALL;
Boolean teamHistory = false;

editorialImagesApi.getEditorialImageLicenseListAsync(imageId, license, page, perPage, sort, username, startDate, endDate, downloadAvailability, teamHistory).thenAccept(result -> {
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
  "total_count": 2890,
  "page": 1,
  "per_page": 1,
  "data": [
    {
      "id": "e1eba3833793e77188d22caae8bac9f2cd",
      "user": {
        "username": "editorial_test_account_002"
      },
      "license": "premier_editorial_all_digital",
      "download_time": "2021-07-15T15:46:34.000Z",
      "is_downloadable": false,
      "image": {
        "id": "9763363ao",
        "format": {
          "size": "original"
        }
      },
      "subscription_id": "s12345678",
      "metadata": {
        "purchase_order": "123456",
        "client": "Company A",
        "job": "Important project",
        "other": "Important media"
      }
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


# License Editorial Images

This endpoint gets licenses for one or more editorial images. You must specify the country and one or more editorial images to license. The download links in the response are valid for 8 hours.

```java
CompletableFuture<ApiResponse<LicenseEditorialContentResults>> licenseEditorialImagesAsync(
    final LicenseEditorialContentRequest body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`LicenseEditorialContentRequest`](../../doc/models/license-editorial-content-request.md) | Body, Required | License editorial content |

## Requires scope

### customer_accessCode

`licenses.create`, `purchases.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`LicenseEditorialContentResults`](../../doc/models/license-editorial-content-results.md).

## Example Usage

```java
LicenseEditorialContentRequest body = new LicenseEditorialContentRequest.Builder(
    LicenseEditorialContentRequestCountry.fromCountry(
        Country.USA
    ),
    Arrays.asList(
        new LicenseEditorialContent.Builder(
            "10687730b",
            "premier_editorial_comp"
        )
        .metadata(ApiHelper.deserialize("{\"customer_id\":\"12345\",\"geo_location\":\"US\",\"number_viewed\":\"15\",\"search_term\":\"dog\"}"))
        .size(Size.ORIGINAL)
        .build()
    )
)
.build();

editorialImagesApi.licenseEditorialImagesAsync(body).thenAccept(result -> {
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
      "allotment_charge": 1,
      "editorial_id": "69656358",
      "download": {
        "url": "https://s3-eu-west-1.amazonaws.com/api-downloads.rexfeatures.com/[random-characters].jpg?Expires=1524717323"
      }
    }
  ],
  "page": 1,
  "per_page": 1,
  "total_count": 12
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 406 | Not Acceptable | `ApiException` |


# Get Editorial Image Livefeed List

```java
CompletableFuture<ApiResponse<EditorialImageLivefeedList>> getEditorialImageLivefeedListAsync(
    final String country,
    final Integer page,
    final Integer perPage)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `country` | `String` | Query, Required | Returns only livefeeds that are available for distribution in a certain country |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 50` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialImageLivefeedList`](../../doc/models/editorial-image-livefeed-list.md).

## Example Usage

```java
String country = "USA";
Integer page = 1;
Integer perPage = 20;

editorialImagesApi.getEditorialImageLivefeedListAsync(country, page, perPage).thenAccept(result -> {
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
  "total_count": 5300,
  "data": [
    {
      "id": "2018%2F07%2F17%2FPrince%20Charles%20and%20Camilla%20Duchess%20of%20Cornwall%20visit%20to%20Cornwall%2C%20Day%202",
      "name": "Prince Charles and Camilla Duchess of Cornwall visit to Cornwall, Day 2",
      "total_item_count": 38,
      "created_time": "2018-07-17T12:42:03+00:00",
      "cover_item": {
        "height": 117,
        "width": 170,
        "url": "https://editorial01.shuttercorp.net/thumb/9763363q/51e28f39/Shutterstock_9763363q.jpg",
        "id": "9763363q"
      }
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
| 404 | Not Found | `ApiException` |


# Get Editorial Image Livefeed

```java
CompletableFuture<ApiResponse<EditorialImageLivefeed>> getEditorialImageLivefeedAsync(
    final String id,
    final String country)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Editorial livefeed ID; must be an URI encoded string |
| `country` | `String` | Query, Required | Returns only if the livefeed is available for distribution in a certain country |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialImageLivefeed`](../../doc/models/editorial-image-livefeed.md).

## Example Usage

```java
String id = "2018%2F10%2F15%2FWomen%20of%20the%20Year%20Lunch%20%26%20Awards%2C%20London";
String country = "USA";

editorialImagesApi.getEditorialImageLivefeedAsync(id, country).thenAccept(result -> {
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
  "id": "2018%2F07%2F17%2FPrince%20Charles%20and%20Camilla%20Duchess%20of%20Cornwall%20visit%20to%20Cornwall%2C%20Day%202",
  "name": "Prince Charles and Camilla Duchess of Cornwall visit to Cornwall, Day 2",
  "total_item_count": 38,
  "created_time": "2018-07-17T12:42:03+00:00",
  "cover_item": {
    "height": 117,
    "width": 170,
    "url": "https://editorial01.shuttercorp.net/thumb/9763363q/51e28f39/Shutterstock_9763363q.jpg",
    "id": "9763363q"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 404 | Not Found | `ApiException` |


# Get Editorial Image Livefeed Items

```java
CompletableFuture<ApiResponse<EditorialContentDataList>> getEditorialImageLivefeedItemsAsync(
    final String id,
    final String country)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Editorial livefeed ID; must be an URI encoded string |
| `country` | `String` | Query, Required | Returns only if the livefeed items are available for distribution in a certain country |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialContentDataList`](../../doc/models/editorial-content-data-list.md).

## Example Usage

```java
String id = "2018%2F10%2F15%2FWomen%20of%20the%20Year%20Lunch%20%26%20Awards%2C%20London";
String country = "USA";

editorialImagesApi.getEditorialImageLivefeedItemsAsync(id, country).thenAccept(result -> {
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
      "id": "10687730b",
      "title": "Soccer Premier League, Manchester, United Kingdom - 11 May 2021",
      "caption": "",
      "description": "Security and stewards stand outside the Old Trafford stadium in Manchester, England, ahead of the English Premier League soccer match between Manchester United and Leicester City. This is the first Manchester United home match since fans protested against American owner Joel Glazer, forcing the postponement of the team's Premier League game against Liverpool. The protests prompted Glazer to publish a letter in which he pledged to accelerate discussions with fans about supporters being able to have a greater say at the club",
      "byline": "Jon Super/AP/Shutterstock",
      "keywords": [
        "england",
        "europe",
        "leicester city fc",
        "manchester",
        "manchester united fc",
        "men's soccer",
        "men's sports",
        "premier league",
        "professional soccer",
        "soccer",
        "sports",
        "united kingdom",
        "western europe",
        "wsoc"
      ],
      "date_taken": "2021-05-11",
      "categories": [
        {
          "name": "Sport"
        }
      ],
      "aspect": 1.621,
      "assets": {
        "thumb_170": {
          "height": 105,
          "width": 170,
          "url": "https://editorial01.shuttercorp.net/thumb/10687730b/272a999e/Shutterstock_10687730b.jpg"
        },
        "thumb_220": {
          "height": 136,
          "width": 220,
          "url": "https://editorial01.shuttercorp.net/thumb-220/10687730b/927a6ebe/Shutterstock_10687730b.jpg"
        },
        "watermark_450": {
          "height": 278,
          "width": 450,
          "url": "https://editorial01.shuttercorp.net/wm-preview-450/10687730b/ff2443ad/Shutterstock_10687730b.jpg"
        },
        "watermark_1500": {
          "height": 926,
          "width": 1500,
          "url": "https://editorial01.shuttercorp.net/wm-preview-1500/10687730b/ee2d7ae1/Shutterstock_10687730b.jpg"
        },
        "small_jpg": {
          "display_name": "Small",
          "width": 500,
          "height": 309,
          "is_licensable": true
        },
        "medium_jpg": {
          "display_name": "Med",
          "width": 1000,
          "height": 617,
          "is_licensable": true
        },
        "original": {
          "display_name": "Original",
          "height": 3693,
          "width": 5985,
          "is_licensable": true
        }
      }
    }
  ],
  "page": 1,
  "per_page": 1,
  "total_count": 23
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 404 | Not Found | `ApiException` |


# Get Editorial Image 1

**This endpoint is deprecated.**

Deprecated; use `GET /v2/editorial/images/{id}` instead to show information about an editorial image, including a URL to a preview image and the sizes that it is available in.

```java
CompletableFuture<ApiResponse<EditorialContent>> getEditorialImage1Async(
    final String id,
    final String country,
    final String searchId)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Editorial ID |
| `country` | `String` | Query, Required | Returns only if the content is available for distribution in a certain country |
| `searchId` | `String` | Query, Optional | The ID of the search that is related to this request |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialContent`](../../doc/models/editorial-content.md).

## Example Usage

```java
String id = "9926131a";
String country = "USA";
String searchId = "00000000-0000-0000-0000-000000000000";

editorialImagesApi.getEditorialImage1Async(id, country, searchId).thenAccept(result -> {
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
  "id": "10687730b",
  "title": "Soccer Premier League, Manchester, United Kingdom - 11 May 2021",
  "caption": "",
  "description": "Security and stewards stand outside the Old Trafford stadium in Manchester, England, ahead of the English Premier League soccer match between Manchester United and Leicester City. This is the first Manchester United home match since fans protested against American owner Joel Glazer, forcing the postponement of the team's Premier League game against Liverpool. The protests prompted Glazer to publish a letter in which he pledged to accelerate discussions with fans about supporters being able to have a greater say at the club",
  "byline": "Jon Super/AP/Shutterstock",
  "keywords": [
    "england",
    "europe",
    "leicester city fc",
    "manchester",
    "manchester united fc",
    "men's soccer",
    "men's sports",
    "premier league",
    "professional soccer",
    "soccer",
    "sports",
    "united kingdom",
    "western europe",
    "wsoc"
  ],
  "date_taken": "2021-05-11",
  "categories": [
    {
      "name": "Sport"
    }
  ],
  "aspect": 1.621,
  "assets": {
    "thumb_170": {
      "height": 105,
      "width": 170,
      "url": "https://editorial01.shuttercorp.net/thumb/10687730b/272a999e/Shutterstock_10687730b.jpg"
    },
    "thumb_220": {
      "height": 136,
      "width": 220,
      "url": "https://editorial01.shuttercorp.net/thumb-220/10687730b/927a6ebe/Shutterstock_10687730b.jpg"
    },
    "watermark_450": {
      "height": 278,
      "width": 450,
      "url": "https://editorial01.shuttercorp.net/wm-preview-450/10687730b/ff2443ad/Shutterstock_10687730b.jpg"
    },
    "watermark_1500": {
      "height": 926,
      "width": 1500,
      "url": "https://editorial01.shuttercorp.net/wm-preview-1500/10687730b/ee2d7ae1/Shutterstock_10687730b.jpg"
    },
    "small_jpg": {
      "display_name": "Small",
      "width": 500,
      "height": 309,
      "is_licensable": true
    },
    "medium_jpg": {
      "display_name": "Med",
      "width": 1000,
      "height": 617,
      "is_licensable": true
    },
    "original": {
      "display_name": "Original",
      "height": 3693,
      "width": 5985,
      "is_licensable": true
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 404 | Not Found | `ApiException` |


# License Editorial Image

**This endpoint is deprecated.**

Deprecated; use `POST /v2/editorial/images/licenses` instead to get licenses for one or more editorial images. You must specify the country and one or more editorial images to license. The download links in the response are valid for 8 hours.

```java
CompletableFuture<ApiResponse<LicenseEditorialContentResults>> licenseEditorialImageAsync(
    final LicenseEditorialContentRequest body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`LicenseEditorialContentRequest`](../../doc/models/license-editorial-content-request.md) | Body, Required | License editorial content |

## Requires scope

### customer_accessCode

`licenses.create`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`LicenseEditorialContentResults`](../../doc/models/license-editorial-content-results.md).

## Example Usage

```java
LicenseEditorialContentRequest body = new LicenseEditorialContentRequest.Builder(
    LicenseEditorialContentRequestCountry.fromCountry(
        Country.USA
    ),
    Arrays.asList(
        new LicenseEditorialContent.Builder(
            "10687730b",
            "premier_editorial_comp"
        )
        .metadata(ApiHelper.deserialize("{\"customer_id\":\"12345\",\"geo_location\":\"US\",\"number_viewed\":\"15\",\"search_term\":\"dog\"}"))
        .size(Size.ORIGINAL)
        .build()
    )
)
.build();

editorialImagesApi.licenseEditorialImageAsync(body).thenAccept(result -> {
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
      "editorial_id": "69656358",
      "download": {
        "url": "https://s3-eu-west-1.amazonaws.com/api-downloads.rexfeatures.com/[random-characters].jpg?Expires=1524717323"
      }
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
| 406 | Not Acceptable | `ApiException` |


# Get Editorial Livefeed List

**This endpoint is deprecated.**

Deprecated; use `GET /v2/editorial/images/livefeeds` instead to get a list of editorial livefeeds.

```java
CompletableFuture<ApiResponse<EditorialImageLivefeedList>> getEditorialLivefeedListAsync(
    final String country,
    final Integer page,
    final Integer perPage)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `country` | `String` | Query, Required | Returns only livefeeds that are available for distribution in a certain country |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 50` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialImageLivefeedList`](../../doc/models/editorial-image-livefeed-list.md).

## Example Usage

```java
String country = "USA";
Integer page = 1;
Integer perPage = 20;

editorialImagesApi.getEditorialLivefeedListAsync(country, page, perPage).thenAccept(result -> {
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
      "id": "2018%2F07%2F17%2FPrince%20Charles%20and%20Camilla%20Duchess%20of%20Cornwall%20visit%20to%20Cornwall%2C%20Day%202",
      "name": "Prince Charles and Camilla Duchess of Cornwall visit to Cornwall, Day 2",
      "total_item_count": 38,
      "created_time": "2018-07-17T12:42:03+00:00",
      "cover_item": {
        "height": 117,
        "width": 170,
        "url": "https://editorial01.shuttercorp.net/thumb/9763363q/51e28f39/Shutterstock_9763363q.jpg",
        "id": "9763363q"
      }
    }
  ],
  "page": 1,
  "per_page": 1,
  "total_count": 56
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 406 | Not Acceptable | `ApiException` |


# Get Editorial Livefeed

**This endpoint is deprecated.**

Deprecated: use `GET /v2/editorial/images/livefeeds/{id}` instead to get an editorial livefeed.

```java
CompletableFuture<ApiResponse<EditorialImageLivefeed>> getEditorialLivefeedAsync(
    final String id,
    final String country)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Editorial livefeed ID; must be an URI encoded string |
| `country` | `String` | Query, Required | Returns only if the livefeed is available for distribution in a certain country |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialImageLivefeed`](../../doc/models/editorial-image-livefeed.md).

## Example Usage

```java
String id = "2018%2F10%2F15%2FWomen%20of%20the%20Year%20Lunch%20%26%20Awards%2C%20London";
String country = "USA";

editorialImagesApi.getEditorialLivefeedAsync(id, country).thenAccept(result -> {
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
  "id": "2018%2F07%2F17%2FPrince%20Charles%20and%20Camilla%20Duchess%20of%20Cornwall%20visit%20to%20Cornwall%2C%20Day%202",
  "name": "Prince Charles and Camilla Duchess of Cornwall visit to Cornwall, Day 2",
  "total_item_count": 38,
  "created_time": "2018-07-17T12:42:03+00:00",
  "cover_item": {
    "height": 117,
    "width": 170,
    "url": "https://editorial01.shuttercorp.net/thumb/9763363q/51e28f39/Shutterstock_9763363q.jpg",
    "id": "9763363q"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 406 | Not Acceptable | `ApiException` |


# Get Editorial Livefeed Items

**This endpoint is deprecated.**

Deprecated; use `GET /v2/editorial/images/livefeeds/{id}/items` instead to get editorial livefeed items.

```java
CompletableFuture<ApiResponse<EditorialContentDataList>> getEditorialLivefeedItemsAsync(
    final String id,
    final String country)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Editorial livefeed ID; must be an URI encoded string |
| `country` | `String` | Query, Required | Returns only if the livefeed items are available for distribution in a certain country |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialContentDataList`](../../doc/models/editorial-content-data-list.md).

## Example Usage

```java
String id = "2018%2F10%2F15%2FWomen%20of%20the%20Year%20Lunch%20%26%20Awards%2C%20London";
String country = "USA";

editorialImagesApi.getEditorialLivefeedItemsAsync(id, country).thenAccept(result -> {
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
      "id": "10687730b",
      "title": "Soccer Premier League, Manchester, United Kingdom - 11 May 2021",
      "caption": "",
      "description": "Security and stewards stand outside the Old Trafford stadium in Manchester, England, ahead of the English Premier League soccer match between Manchester United and Leicester City. This is the first Manchester United home match since fans protested against American owner Joel Glazer, forcing the postponement of the team's Premier League game against Liverpool. The protests prompted Glazer to publish a letter in which he pledged to accelerate discussions with fans about supporters being able to have a greater say at the club",
      "byline": "Jon Super/AP/Shutterstock",
      "keywords": [
        "england",
        "europe",
        "leicester city fc",
        "manchester",
        "manchester united fc",
        "men's soccer",
        "men's sports",
        "premier league",
        "professional soccer",
        "soccer",
        "sports",
        "united kingdom",
        "western europe",
        "wsoc"
      ],
      "date_taken": "2021-05-11",
      "categories": [
        {
          "name": "Sport"
        }
      ],
      "aspect": 1.621,
      "assets": {
        "thumb_170": {
          "height": 105,
          "width": 170,
          "url": "https://editorial01.shuttercorp.net/thumb/10687730b/272a999e/Shutterstock_10687730b.jpg"
        },
        "thumb_220": {
          "height": 136,
          "width": 220,
          "url": "https://editorial01.shuttercorp.net/thumb-220/10687730b/927a6ebe/Shutterstock_10687730b.jpg"
        },
        "watermark_450": {
          "height": 278,
          "width": 450,
          "url": "https://editorial01.shuttercorp.net/wm-preview-450/10687730b/ff2443ad/Shutterstock_10687730b.jpg"
        },
        "watermark_1500": {
          "height": 926,
          "width": 1500,
          "url": "https://editorial01.shuttercorp.net/wm-preview-1500/10687730b/ee2d7ae1/Shutterstock_10687730b.jpg"
        },
        "small_jpg": {
          "display_name": "Small",
          "width": 500,
          "height": 309,
          "is_licensable": true
        },
        "medium_jpg": {
          "display_name": "Med",
          "width": 1000,
          "height": 617,
          "is_licensable": true
        },
        "original": {
          "display_name": "Original",
          "height": 3693,
          "width": 5985,
          "is_licensable": true
        }
      }
    }
  ],
  "page": 1,
  "per_page": 5,
  "total_count": 16
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 406 | Not Acceptable | `ApiException` |


# Search Editorial

**This endpoint is deprecated.**

Deprecated; use `GET /v2/editorial/images/search` instead to search for editorial images.

```java
CompletableFuture<ApiResponse<EditorialSearchResults>> searchEditorialAsync(
    final String country,
    final String query,
    final Sort17 sort,
    final String category,
    final List<String> supplierCode,
    final LocalDate dateStart,
    final LocalDate dateEnd,
    final Integer perPage,
    final String cursor)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `country` | `String` | Query, Required | Show only editorial content that is available for distribution in a certain country |
| `query` | `String` | Query, Optional | One or more search terms separated by spaces |
| `sort` | [`Sort17`](../../doc/models/sort-17.md) | Query, Optional | Sort by<br><br>**Default**: `Sort17.RELEVANT` |
| `category` | `String` | Query, Optional | Show editorial content within a certain editorial category; specify by category name |
| `supplierCode` | `List<String>` | Query, Optional | Show only editorial content from certain suppliers |
| `dateStart` | `LocalDate` | Query, Optional | Show only editorial content generated on or after a specific date |
| `dateEnd` | `LocalDate` | Query, Optional | Show only editorial content generated on or before a specific date |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 50` |
| `cursor` | `String` | Query, Optional | The cursor of the page with which to start fetching results; this cursor is returned from previous requests |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialSearchResults`](../../doc/models/editorial-search-results.md).

## Example Usage

```java
String country = "USA";
Sort17 sort = Sort17.RELEVANT;
Integer perPage = 20;

editorialImagesApi.searchEditorialAsync(country, null, sort, null, null, null, null, perPage, null).thenAccept(result -> {
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
  "per_page": 1,
  "total_count": 46845,
  "search_id": "BaMzOAkpHIvfnuWVRFs1ag",
  "next": "eyJ2IjoyLCJzIjoxLCJwIjpbMF19",
  "prev": "",
  "data": [
    {
      "id": "10687730b",
      "title": "Soccer Premier League, Manchester, United Kingdom - 11 May 2021",
      "caption": "",
      "description": "Security and stewards stand outside the Old Trafford stadium in Manchester, England, ahead of the English Premier League soccer match between Manchester United and Leicester City. This is the first Manchester United home match since fans protested against American owner Joel Glazer, forcing the postponement of the team's Premier League game against Liverpool. The protests prompted Glazer to publish a letter in which he pledged to accelerate discussions with fans about supporters being able to have a greater say at the club",
      "byline": "Jon Super/AP/Shutterstock",
      "keywords": [
        "england",
        "europe",
        "leicester city fc",
        "manchester",
        "manchester united fc",
        "men's soccer",
        "men's sports",
        "premier league",
        "professional soccer",
        "soccer",
        "sports",
        "united kingdom",
        "western europe",
        "wsoc"
      ],
      "date_taken": "2021-05-11",
      "categories": [
        {
          "name": "Sport"
        }
      ],
      "aspect": 1.621,
      "assets": {
        "thumb_170": {
          "height": 105,
          "width": 170,
          "url": "https://editorial01.shuttercorp.net/thumb/10687730b/272a999e/Shutterstock_10687730b.jpg"
        },
        "thumb_220": {
          "height": 136,
          "width": 220,
          "url": "https://editorial01.shuttercorp.net/thumb-220/10687730b/927a6ebe/Shutterstock_10687730b.jpg"
        },
        "watermark_450": {
          "height": 278,
          "width": 450,
          "url": "https://editorial01.shuttercorp.net/wm-preview-450/10687730b/ff2443ad/Shutterstock_10687730b.jpg"
        },
        "watermark_1500": {
          "height": 926,
          "width": 1500,
          "url": "https://editorial01.shuttercorp.net/wm-preview-1500/10687730b/ee2d7ae1/Shutterstock_10687730b.jpg"
        },
        "small_jpg": {
          "display_name": "Small",
          "width": 500,
          "height": 309,
          "is_licensable": true
        },
        "medium_jpg": {
          "display_name": "Med",
          "width": 1000,
          "height": 617,
          "is_licensable": true
        },
        "original": {
          "display_name": "Original",
          "height": 3693,
          "width": 5985,
          "is_licensable": true
        }
      }
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
| 406 | Not Acceptable | `ApiException` |


# Get Editorial Categories

**This endpoint is deprecated.**

Deprecated; use `GET /v2/editorial/images/categories` instead. This endpoint lists the categories that editorial images can belong to, which are separate from the categories that other types of assets can belong to.

```java
CompletableFuture<ApiResponse<EditorialCategoryResults>> getEditorialCategoriesAsync()
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialCategoryResults`](../../doc/models/editorial-category-results.md).

## Example Usage

```java
editorialImagesApi.getEditorialCategoriesAsync().thenAccept(result -> {
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
      "name": "Animal"
    },
    {
      "name": "Awards"
    },
    {
      "name": "Art"
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


# Get Updated Editorial Image

**This endpoint is deprecated.**

Deprecated; use `GET /v2/editorial/images/updated` instead to get recently updated items.

```java
CompletableFuture<ApiResponse<EditorialUpdatedResults>> getUpdatedEditorialImageAsync(
    final Type15 type,
    final LocalDateTime dateUpdatedStart,
    final LocalDateTime dateUpdatedEnd,
    final String country,
    final LocalDate dateTakenStart,
    final LocalDate dateTakenEnd,
    final String cursor,
    final Sort5 sort,
    final List<String> supplierCode,
    final Integer perPage)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `type` | [`Type15`](../../doc/models/type-15.md) | Query, Required | Specify `addition` to return only images that were added or `edit` to return only images that were edited or deleted |
| `dateUpdatedStart` | `LocalDateTime` | Query, Required | Show images images added, edited, or deleted after the specified date. Acceptable range is 1970-01-01T00:00:01 to 2038-01-19T00:00:00. |
| `dateUpdatedEnd` | `LocalDateTime` | Query, Required | Show images images added, edited, or deleted before the specified date. Acceptable range is 1970-01-01T00:00:01 to 2038-01-19T00:00:00. |
| `country` | `String` | Query, Required | Show only editorial content that is available for distribution in a certain country |
| `dateTakenStart` | `LocalDate` | Query, Optional | Show images that were taken on or after the specified date; use this parameter if you want recently created images from the collection instead of updated older assets |
| `dateTakenEnd` | `LocalDate` | Query, Optional | Show images that were taken before the specified date |
| `cursor` | `String` | Query, Optional | The cursor of the page with which to start fetching results; this cursor is returned from previous requests |
| `sort` | [`Sort5`](../../doc/models/sort-5.md) | Query, Optional | Sort by<br><br>**Default**: `Sort5.NEWEST` |
| `supplierCode` | `List<String>` | Query, Optional | Show only editorial content from certain suppliers<br><br>**Constraints**: *Maximum Length*: `5` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `500`<br><br>**Constraints**: `>= 100`, `<= 500` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialUpdatedResults`](../../doc/models/editorial-updated-results.md).

## Example Usage

```java
Type15 type = Type15.EDIT;
LocalDateTime dateUpdatedStart = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
LocalDateTime dateUpdatedEnd = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
String country = "USA";
LocalDate dateTakenStart = DateTimeHelper.fromSimpleDate("2020-02-04");
LocalDate dateTakenEnd = DateTimeHelper.fromSimpleDate("2020-02-05");
String cursor = "eyJ2IjoxLCJzIjoyfQ==";
Sort5 sort = Sort5.NEWEST;
Integer perPage = 200;

editorialImagesApi.getUpdatedEditorialImageAsync(type, dateUpdatedStart, dateUpdatedEnd, country, dateTakenStart, dateTakenEnd, cursor, sort, null, perPage).thenAccept(result -> {
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
  "per_page": 1,
  "next": "eyJ2IjoxLCJzIjoxfQ==",
  "prev": "",
  "data": [
    {
      "id": "9804979n",
      "title": "Hong Kong kicks off international e-Sports competition, China - 24 Aug 2018",
      "caption": "",
      "description": "Members of the TyLoo e-Sports team from China prepare to face off against the Kinguin e-Sports team from Poland at the ICBC (Asia) e-Sports and Music Festival Hong Kong 2018, Hong Kong, China, 24 August 2018. The festival runs from 24 to 26 August with professional gamers from around the world competing in international e-sports tournaments.",
      "byline": "ALEX HOFFORD/EPA-EFE/Shutterstock",
      "supplier_code": "EPA",
      "keywords": [],
      "date_taken": "2018-08-24",
      "categories": [],
      "aspect": 1.481,
      "assets": {
        "thumb_170": {
          "height": 115,
          "width": 170,
          "url": "https://editorial01.shutterstock.com/thumb/9804979n/c4377a53/Shutterstock_9804979n.jpg"
        },
        "thumb_220": {
          "height": 149,
          "width": 220,
          "url": "https://editorial01.shutterstock.com/thumb-220/9804979n/c57a68c7/Shutterstock_9804979n.jpg"
        },
        "watermark_450": {
          "height": 304,
          "width": 450,
          "url": "https://editorial01.shutterstock.com/wm-preview-450/9804979n/37d19dce/Shutterstock_9804979n.jpg"
        },
        "watermark_1500": {
          "height": 1500,
          "width": 1040,
          "url": "https://editorial01.shutterstock.com/wm-preview-1500/9933285a/ab82fea4/Shutterstock_9933285a.jpg"
        },
        "original": {
          "display_name": "Original",
          "height": 3263,
          "width": 4831,
          "is_licensable": true
        },
        "small_jpg": {
          "display_name": "Small",
          "height": 337,
          "width": 500,
          "is_licensable": true
        },
        "medium_jpg": {
          "display_name": "Med",
          "height": 675,
          "width": 1000,
          "is_licensable": true
        }
      },
      "updated_time": "2019-07-15T20:04:44-04:00",
      "updates": [
        "addition"
      ],
      "commercial_status": {
        "status": "available"
      },
      "rights": {
        "countries": "CAN,+DEU,+GBR,+USA,-*"
      }
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
| 406 | Not Acceptable | `ApiException` |

