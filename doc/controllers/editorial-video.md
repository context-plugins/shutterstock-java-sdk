# Editorial Video

```java
EditorialVideoApi editorialVideoApi = client.getEditorialVideoApi();
```

## Class Name

`EditorialVideoApi`

## Methods

* [Search Editorial Videos](../../doc/controllers/editorial-video.md#search-editorial-videos)
* [List Editorial Video Categories](../../doc/controllers/editorial-video.md#list-editorial-video-categories)
* [Get Editorial Video](../../doc/controllers/editorial-video.md#get-editorial-video)
* [List Editorial Videos](../../doc/controllers/editorial-video.md#list-editorial-videos)
* [Get Editorial Video License List](../../doc/controllers/editorial-video.md#get-editorial-video-license-list)
* [License Editorial Video](../../doc/controllers/editorial-video.md#license-editorial-video)


# Search Editorial Videos

This endpoint searches for editorial videos. If you specify more than one search parameter, the API uses an AND condition. For example, if you set the `category` parameter to "Alone,Performing" and also specify a `query` parameter, the results include only videos that match the query and are in both the Alone and Performing categories.  You can also filter search terms out in the `query` parameter by prefixing the term with NOT.

```java
CompletableFuture<ApiResponse<EditorialVideoSearchResults>> searchEditorialVideosAsync(
    final String country,
    final String query,
    final Sort17 sort,
    final String category,
    final List<String> supplierCode,
    final LocalDate dateStart,
    final LocalDate dateEnd,
    final Resolution resolution,
    final Double fps,
    final Integer perPage,
    final String cursor)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `country` | `String` | Query, Required | Show only editorial video content that is available for distribution in a certain country |
| `query` | `String` | Query, Optional | One or more search terms separated by spaces |
| `sort` | [`Sort17`](../../doc/models/sort-17.md) | Query, Optional | Sort by<br><br>**Default**: `Sort17.RELEVANT` |
| `category` | `String` | Query, Optional | Show editorial content with each of the specified editorial categories; specify category names in a comma-separated list |
| `supplierCode` | `List<String>` | Query, Optional | Show only editorial video content from certain suppliers |
| `dateStart` | `LocalDate` | Query, Optional | Show only editorial video content generated on or after a specific date |
| `dateEnd` | `LocalDate` | Query, Optional | Show only editorial video content generated on or before a specific date |
| `resolution` | [`Resolution`](../../doc/models/resolution.md) | Query, Optional | Show only editorial video content with specific resolution |
| `fps` | `Double` | Query, Optional | Show only editorial video content generated with specific frames per second |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 50` |
| `cursor` | `String` | Query, Optional | The cursor of the page with which to start fetching results; this cursor is returned from previous requests |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialVideoSearchResults`](../../doc/models/editorial-video-search-results.md).

## Example Usage

```java
String country = "USA";
String query = "The Academy Awards";
Sort17 sort = Sort17.RELEVANT;
String category = "Alone,Performing";
LocalDate dateStart = DateTimeHelper.fromSimpleDate("2020-05-29");
LocalDate dateEnd = DateTimeHelper.fromSimpleDate("2021-05-29");
Resolution resolution = Resolution.ENUM_4K;
Double fps = 24D;
Integer perPage = 20;
String cursor = "eyJ2IjoxLCJzIjoxfQ==";

editorialVideoApi.searchEditorialVideosAsync(country, query, sort, category, null, dateStart, dateEnd, resolution, fps, perPage, cursor).thenAccept(result -> {
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
      "id": "10679854a",
      "title": "Peeps the Goose Has a Blast on a Jet Ski, Prior Lake, Minnesota, USA - 13 Nov 2020",
      "caption": "",
      "description": "Info from Licensor: \"Peeps the Canadian Goose has been raised with our family since a gosling. Peeps has made appearances on our local news channels, TV shows, and local newspapers. He has been trained to fly next to four wheelers, jet ski's, and boats. He has brought joy to many people during the pandemic including those with cancer.\"",
      "byline": "ViralHog/Shutterstock",
      "keywords": [
        "2020",
        "adorable",
        "birds",
        "bizarre",
        "canadian goose",
        "cute",
        "domesticated animals",
        "entertainment",
        "feel good",
        "flew",
        "flies",
        "fly",
        "flying",
        "fun",
        "goose",
        "jet skis",
        "nature",
        "odd",
        "pets",
        "played",
        "playing",
        "plays",
        "prior lake",
        "sports",
        "strange",
        "sweet",
        "usa",
        "viralhog",
        "virals",
        "water sports",
        "weird"
      ],
      "date_taken": "2020-11-13",
      "categories": [],
      "aspect": 1,
      "assets": {
        "preview_mp4": {
          "url": "https://editorial-cdn.shuttercorp.net/wm-preview-mp4/10679854a/M0T7A13aNej2g82bMTI4NjY=/Shutterstock_10679854a.mp4"
        },
        "preview_webm": {
          "url": "https://editorial-cdn.shuttercorp.net/wm-preview-webm/10679854a/M4T6A63fN2j5g929MTI4NjY=/Shutterstock_10679854a.webm"
        },
        "thumb_jpg": {
          "url": "https://editorial-cdn.shuttercorp.net/thumb-1/10679854a/M5TcAf30Ncjcge2eMTI4NjY=/Shutterstock_10679854a.jpg"
        },
        "original": {
          "height": 1080,
          "width": 1080,
          "fps": 30,
          "format": "avc1",
          "file_size": 82233387,
          "display_name": "HD",
          "is_licensable": true
        }
      }
    }
  ],
  "per_page": 1,
  "total_count": 331,
  "search_id": "zhmz9zLmpQehdTPvg8cacQ",
  "next": "eyJ2IjoyLCJzIjoyMCwicCI6WzBdfQ==",
  "prev": ""
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 406 | Not Acceptable | `ApiException` |


# List Editorial Video Categories

This endpoint lists the categories that editorial videos can belong to, which are separate from the categories that other types of assets can belong to.

```java
CompletableFuture<ApiResponse<EditorialVideoCategoryResults>> listEditorialVideoCategoriesAsync()
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialVideoCategoryResults`](../../doc/models/editorial-video-category-results.md).

## Example Usage

```java
editorialVideoApi.listEditorialVideoCategoriesAsync().thenAccept(result -> {
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


# Get Editorial Video

This endpoint shows information about an editorial image, including a URL to a preview image and the sizes that it is available in.

```java
CompletableFuture<ApiResponse<EditorialVideoContent>> getEditorialVideoAsync(
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialVideoContent`](../../doc/models/editorial-video-content.md).

## Example Usage

```java
String id = "9926131a";
String country = "USA";
String searchId = "00000000-0000-0000-0000-000000000000";

editorialVideoApi.getEditorialVideoAsync(id, country, searchId).thenAccept(result -> {
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
  "id": "10679854a",
  "title": "Peeps the Goose Has a Blast on a Jet Ski, Prior Lake, Minnesota, USA - 13 Nov 2020",
  "caption": "",
  "description": "Info from Licensor: \"Peeps the Canadian Goose has been raised with our family since a gosling. Peeps has made appearances on our local news channels, TV shows, and local newspapers. He has been trained to fly next to four wheelers, jet ski's, and boats. He has brought joy to many people during the pandemic including those with cancer.\"",
  "byline": "ViralHog/Shutterstock",
  "keywords": [
    "2020",
    "adorable",
    "birds",
    "bizarre",
    "canadian goose",
    "cute",
    "domesticated animals",
    "entertainment",
    "feel good",
    "flew",
    "flies",
    "fly",
    "flying",
    "fun",
    "goose",
    "jet skis",
    "nature",
    "odd",
    "pets",
    "played",
    "playing",
    "plays",
    "prior lake",
    "sports",
    "strange",
    "sweet",
    "usa",
    "viralhog",
    "virals",
    "water sports",
    "weird"
  ],
  "date_taken": "2020-11-13",
  "categories": [],
  "aspect": 1,
  "assets": {
    "preview_mp4": {
      "url": "https://editorial-cdn.shuttercorp.net/wm-preview-mp4/10679854a/M0T7A13aNej2g82bMTI4NjY=/Shutterstock_10679854a.mp4"
    },
    "preview_webm": {
      "url": "https://editorial-cdn.shuttercorp.net/wm-preview-webm/10679854a/M4T6A63fN2j5g929MTI4NjY=/Shutterstock_10679854a.webm"
    },
    "thumb_jpg": {
      "url": "https://editorial-cdn.shuttercorp.net/thumb-1/10679854a/M5TcAf30Ncjcge2eMTI4NjY=/Shutterstock_10679854a.jpg"
    },
    "original": {
      "height": 1080,
      "width": 1080,
      "fps": 30,
      "format": "avc1",
      "file_size": 82233387,
      "display_name": "HD",
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
| 406 | Not Acceptable | `ApiException` |


# List Editorial Videos

This endpoint lists the details of editorial videos by ID list.

```java
CompletableFuture<ApiResponse<EditorialVideoResults>> listEditorialVideosAsync(
    final List<String> id,
    final String country,
    final String searchId)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `List<String>` | Query, Required | ID of the editorial video to list details for |
| `country` | `String` | Query, Required | Show only editorial video content that is available for distribution in a certain country |
| `searchId` | `String` | Query, Optional | The ID of the search that is related to this request |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`EditorialVideoResults`](../../doc/models/editorial-video-results.md).

## Example Usage

```java
List<String> id = Arrays.asList(
    "id0"
);

String country = "USA";
String searchId = "00000000-0000-0000-0000-000000000000";

editorialVideoApi.listEditorialVideosAsync(id, country, searchId).thenAccept(result -> {
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
      "id": "10679854a",
      "title": "Peeps the Goose Has a Blast on a Jet Ski, Prior Lake, Minnesota, USA - 13 Nov 2020",
      "caption": "",
      "description": "Info from Licensor: \"Peeps the Canadian Goose has been raised with our family since a gosling. Peeps has made appearances on our local news channels, TV shows, and local newspapers. He has been trained to fly next to four wheelers, jet ski's, and boats. He has brought joy to many people during the pandemic including those with cancer.\"",
      "byline": "ViralHog/Shutterstock",
      "keywords": [
        "adorable",
        "birds",
        "goose"
      ],
      "date_taken": "2020-11-13",
      "categories": [],
      "aspect": 1,
      "assets": {
        "preview_mp4": {
          "url": "https://editorial-cdn.shuttercorp.net/wm-preview-mp4/10679854a/M0T7A13aNej2g82bMTI4NjY=/Shutterstock_10679854a.mp4"
        },
        "preview_webm": {
          "url": "https://editorial-cdn.shuttercorp.net/wm-preview-webm/10679854a/M4T6A63fN2j5g929MTI4NjY=/Shutterstock_10679854a.webm"
        },
        "thumb_jpg": {
          "url": "https://editorial-cdn.shuttercorp.net/thumb-1/10679854a/M5TcAf30Ncjcge2eMTI4NjY=/Shutterstock_10679854a.jpg"
        },
        "original": {
          "height": 1080,
          "width": 1080,
          "fps": 30,
          "format": "avc1",
          "file_size": 82233387,
          "display_name": "HD",
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


# Get Editorial Video License List

This endpoint lists existing editorial video licenses.

```java
CompletableFuture<ApiResponse<DownloadHistoryDataList>> getEditorialVideoLicenseListAsync(
    final String videoId,
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
| `videoId` | `String` | Query, Optional | Show licenses for the specified editorial video ID |
| `license` | `String` | Query, Optional | Show editorial videos that are available with the specified license name |
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
String videoId = "12345678";
String license = "premier_editorial_all_media";
Integer page = 1;
Integer perPage = 20;
Sort5 sort = Sort5.NEWEST;
String username = "aUniqueUsername";
LocalDateTime startDate = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
LocalDateTime endDate = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
DownloadAvailability downloadAvailability = DownloadAvailability.ALL;
Boolean teamHistory = false;

editorialVideoApi.getEditorialVideoLicenseListAsync(videoId, license, page, perPage, sort, username, startDate, endDate, downloadAvailability, teamHistory).thenAccept(result -> {
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
      "id": "e1dbb15d5384725d292cf64f793ac45062",
      "user": {
        "username": "username1"
      },
      "license": "premier_editorial_all_digital",
      "download_time": "2020-12-18T02:22:56.000Z",
      "is_downloadable": false,
      "video": {
        "id": "11231389im",
        "format": {
          "size": "original"
        }
      },
      "subscription_id": "s12345678",
      "metadata": {
        "client": "Company A",
        "other": "Important media",
        "purchase_order": "457234",
        "job": "Important project"
      }
    },
    {
      "id": "e1dbb15d5384725d292cf64f793ac45114",
      "user": {
        "username": "username2"
      },
      "license": "premier_editorial_all_digital",
      "download_time": "2020-12-11T01:24:22.000Z",
      "is_downloadable": false,
      "video": {
        "id": "11231442aa",
        "format": {
          "size": "original"
        }
      },
      "subscription_id": "s12345678",
      "metadata": {
        "client": "Company B",
        "other": "Important image",
        "purchase_order": "5583831",
        "job": "Important project"
      }
    }
  ],
  "page": 1,
  "per_page": 2
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# License Editorial Video

This endpoint gets licenses for one or more editorial videos. You must specify the country and one or more editorial videos to license. The download links in the response are valid for 8 hours.

```java
CompletableFuture<ApiResponse<LicenseEditorialContentResults>> licenseEditorialVideoAsync(
    final LicenseEditorialVideoContentRequest body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`LicenseEditorialVideoContentRequest`](../../doc/models/license-editorial-video-content-request.md) | Body, Required | License editorial video content |

## Requires scope

### customer_accessCode

`licenses.create`, `purchases.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`LicenseEditorialContentResults`](../../doc/models/license-editorial-content-results.md).

## Example Usage

```java
LicenseEditorialVideoContentRequest body = new LicenseEditorialVideoContentRequest.Builder(
    LicenseEditorialVideoContentRequestCountry.fromCountry(
        Country.USA
    ),
    Arrays.asList(
        new LicenseEditorialVideoContent.Builder(
            "10679854a",
            License3.PREMIER_EDITORIAL_VIDEO_DIGITAL_ONLY
        )
        .metadata(ApiHelper.deserialize("{\"purchase_order\":\"12345\"}"))
        .size(Size2.ORIGINAL)
        .build()
    )
)
.build();

editorialVideoApi.licenseEditorialVideoAsync(body).thenAccept(result -> {
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
        "url": "https://s3-eu-west-1.amazonaws.com/api-downloads.rexfeatures.com/[random-characters].mov?Expires=1524717323"
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

