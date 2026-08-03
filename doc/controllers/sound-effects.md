# Sound Effects

```java
SoundEffectsApi soundEffectsApi = client.getSoundEffectsApi();
```

## Class Name

`SoundEffectsApi`

## Methods

* [Search SFX](../../doc/controllers/sound-effects.md#search-sfx)
* [Get Sfx Details](../../doc/controllers/sound-effects.md#get-sfx-details)
* [Get Sfx List Details](../../doc/controllers/sound-effects.md#get-sfx-list-details)
* [Get Sfx License List](../../doc/controllers/sound-effects.md#get-sfx-license-list)
* [Licenses SFX](../../doc/controllers/sound-effects.md#licenses-sfx)
* [Download Sfx](../../doc/controllers/sound-effects.md#download-sfx)


# Search SFX

This endpoint searches for sound effects. If you specify more than one search parameter, the API uses an AND condition.

```java
CompletableFuture<ApiResponse<SfxSearchResults>> searchSfxAsync(
    final LocalDate addedDate,
    final LocalDate addedDateStart,
    final LocalDate addedDateEnd,
    final Integer duration,
    final Integer durationFrom,
    final Integer durationTo,
    final Integer page,
    final Integer perPage,
    final String query,
    final Boolean safe,
    final Sort15 sort,
    final View2 view,
    final Language language)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `addedDate` | `LocalDate` | Query, Optional | Show sound effects added on the specified date |
| `addedDateStart` | `LocalDate` | Query, Optional | Show sound effects added on or after the specified date |
| `addedDateEnd` | `LocalDate` | Query, Optional | Show sound effects added before the specified date |
| `duration` | `Integer` | Query, Optional | Show sound effects with the specified duration in seconds |
| `durationFrom` | `Integer` | Query, Optional | Show sound effects with the specified duration or longer in seconds |
| `durationTo` | `Integer` | Query, Optional | Show sound effects with the specified duration or shorter in seconds |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 500` |
| `query` | `String` | Query, Optional | One or more search terms separated by spaces |
| `safe` | `Boolean` | Query, Optional | Enable or disable safe search<br><br>**Default**: `true` |
| `sort` | [`Sort15`](../../doc/models/sort-15.md) | Query, Optional | Sort by<br><br>**Default**: `Sort15.POPULAR` |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.MINIMAL` |
| `language` | [`Language`](../../doc/models/language.md) | Query, Optional | Set query and result language (uses Accept-Language header if not set) |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`SfxSearchResults`](../../doc/models/sfx-search-results.md).

## Example Usage

```java
LocalDate addedDate = DateTimeHelper.fromSimpleDate("2022-09-23");
LocalDate addedDateStart = DateTimeHelper.fromSimpleDate("2021-03-29");
LocalDate addedDateEnd = DateTimeHelper.fromSimpleDate("2021-03-29");
Integer duration = 180;
Integer durationFrom = 30;
Integer durationTo = 180;
Integer page = 1;
Integer perPage = 1;
String query = "drum";
Boolean safe = true;
Sort15 sort = Sort15.POPULAR;
View2 view = View2.FULL;
Language language = Language.CS;

soundEffectsApi.searchSfxAsync(addedDate, addedDateStart, addedDateEnd, duration, durationFrom, durationTo, page, perPage, query, safe, sort, view, language).thenAccept(result -> {
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
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 503 | Service Unavailable | `ApiException` |


# Get Sfx Details

This endpoint shows information about a sound effect.

```java
CompletableFuture<ApiResponse<Sfx>> getSfxDetailsAsync(
    final int id,
    final Language language,
    final View2 view,
    final Library2 library,
    final String searchId)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `int` | Template, Required | Audio track ID |
| `language` | [`Language`](../../doc/models/language.md) | Query, Optional | Language for the keywords and categories in the response |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.MINIMAL` |
| `library` | [`Library2`](../../doc/models/library-2.md) | Query, Optional | Which library to fetch from |
| `searchId` | `String` | Query, Optional | The ID of the search that is related to this request |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`Sfx`](../../doc/models/sfx.md).

## Example Usage

```java
int id = 442583;
Language language = Language.CS;
View2 view = View2.FULL;
Library2 library = Library2.SHUTTERSTOCK;
String searchId = "00000000-0000-0000-0000-000000000000";

soundEffectsApi.getSfxDetailsAsync(id, language, view, library, searchId).thenAccept(result -> {
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
  "id": "123",
  "media_type": "sfx",
  "contributor": {
    "id": "1234"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 503 | Service Unavailable | `ApiException` |


# Get Sfx List Details

This endpoint shows information about sound effects.

```java
CompletableFuture<ApiResponse<SfxDataList>> getSfxListDetailsAsync(
    final List<String> id,
    final View2 view,
    final Language language,
    final Library2 library,
    final String searchId)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `List<String>` | Query, Required | One or more sound effect IDs<br><br>**Constraints**: *Maximum Items*: `500` |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.MINIMAL` |
| `language` | [`Language`](../../doc/models/language.md) | Query, Optional | Language for the keywords and categories in the response |
| `library` | [`Library2`](../../doc/models/library-2.md) | Query, Optional | Which library to fetch from |
| `searchId` | `String` | Query, Optional | The ID of the search that is related to this request |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`SfxDataList`](../../doc/models/sfx-data-list.md).

## Example Usage

```java
List<String> id = Arrays.asList(
    "1110335168",
    "465011609"
);

View2 view = View2.MINIMAL;
Language language = Language.CS;
Library2 library = Library2.SHUTTERSTOCK;
String searchId = "00000000-0000-0000-0000-000000000000";

soundEffectsApi.getSfxListDetailsAsync(id, view, language, library, searchId).thenAccept(result -> {
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
      "id": "123",
      "media_type": "sfx",
      "contributor": {
        "id": "1234"
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


# Get Sfx License List

This endpoint lists existing licenses.

```java
CompletableFuture<ApiResponse<DownloadHistoryDataList>> getSfxLicenseListAsync(
    final String sfxId,
    final String license,
    final Integer page,
    final Integer perPage,
    final Sort5 sort,
    final String username,
    final LocalDateTime startDate,
    final LocalDateTime endDate,
    final String licenseId,
    final DownloadAvailability downloadAvailability,
    final Boolean teamHistory)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sfxId` | `String` | Query, Optional | Show licenses for the specified sound effects ID<br><br>**Constraints**: *Pattern*: `^[1-9]\d*$` |
| `license` | `String` | Query, Optional | Show sound effects that are available with the specified license, such as `standard` or `enhanced`<br><br>**Constraints**: *Pattern*: `^.+$` |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 200` |
| `sort` | [`Sort5`](../../doc/models/sort-5.md) | Query, Optional | Sort order<br><br>**Default**: `Sort5.NEWEST` |
| `username` | `String` | Query, Optional | Filter licenses by username of licensee<br><br>**Constraints**: *Pattern*: `^.+$` |
| `startDate` | `LocalDateTime` | Query, Optional | Show licenses created on or after the specified date |
| `endDate` | `LocalDateTime` | Query, Optional | Show licenses created before the specified date |
| `licenseId` | `String` | Query, Optional | Filter by the license ID<br><br>**Constraints**: *Pattern*: `^.+$` |
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
String sfxId = "12345678";
String license = "standard";
Integer page = 1;
Integer perPage = 20;
Sort5 sort = Sort5.NEWEST;
String username = "aUniqueUsername";
LocalDateTime startDate = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
LocalDateTime endDate = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
DownloadAvailability downloadAvailability = DownloadAvailability.ALL;
Boolean teamHistory = false;

soundEffectsApi.getSfxLicenseListAsync(sfxId, license, page, perPage, sort, username, startDate, endDate, null, downloadAvailability, teamHistory).thenAccept(result -> {
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


# Licenses SFX

This endpoint licenses sounds effect assets.

```java
CompletableFuture<ApiResponse<LicenseSfxResultDataList>> licensesSfxAsync(
    final LicenseSfxRequest body)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`LicenseSfxRequest`](../../doc/models/license-sfx-request.md) | Body, Required | - |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`LicenseSfxResultDataList`](../../doc/models/license-sfx-result-data-list.md).

## Example Usage

```java
LicenseSfxRequest body = new LicenseSfxRequest.Builder(
    Arrays.asList(
        new LicenseSfx.Builder(
            "123456789",
            "s12345678"
        )
        .format(Format11.WAV)
        .additionalProperty("metadata", ApiHelper.deserialize("{\"customer_id\":\"12345\",\"geo_location\":\"US\",\"number_viewed\":\"15\",\"search_term\":\"dog\"}"))
        .additionalProperty("show_modal", ApiHelper.deserialize("true"))
        .additionalProperty("size", ApiHelper.deserialize("\"ambisonic\""))
        .build()
    )
)
.build();

soundEffectsApi.licensesSfxAsync(body).thenAccept(result -> {
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
      "download": {
        "url": "https://download.shutterstock.com/gatekeeper/[random-characters]/shutterstock_59656357.mp3"
      },
      "sfx_id": "123456789"
    }
  ],
  "page": 1,
  "per_page": 5,
  "total_count": 123455
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Download Sfx

This endpoint redownloads sound effects that you have already received a license for. The download links in the response are valid for 8 hours.

```java
CompletableFuture<ApiResponse<SfxUrl>> downloadSfxAsync(
    final String id)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | License ID |

## Requires scope

### customer_accessCode

`licenses.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`SfxUrl`](../../doc/models/sfx-url.md).

## Example Usage

```java
String id = "123";

soundEffectsApi.downloadSfxAsync(id).thenAccept(result -> {
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
  "url": "http://download.dev.shutterstock.com/gatekeeper/abc/shutterstock_id.wav"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |

