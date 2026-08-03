# Videos

```java
VideosApi videosApi = client.getVideosApi();
```

## Class Name

`VideosApi`

## Methods

* [Search Videos](../../doc/controllers/videos.md#search-videos)
* [Get Video Suggestions](../../doc/controllers/videos.md#get-video-suggestions)
* [Get Video List](../../doc/controllers/videos.md#get-video-list)
* [Get Video](../../doc/controllers/videos.md#get-video)
* [License Videos](../../doc/controllers/videos.md#license-videos)
* [Get Video License List](../../doc/controllers/videos.md#get-video-license-list)
* [Download Videos](../../doc/controllers/videos.md#download-videos)
* [Create Video Collection](../../doc/controllers/videos.md#create-video-collection)
* [Get Video Collection List](../../doc/controllers/videos.md#get-video-collection-list)
* [Get Video Collection](../../doc/controllers/videos.md#get-video-collection)
* [Rename Video Collection](../../doc/controllers/videos.md#rename-video-collection)
* [Delete Video Collection](../../doc/controllers/videos.md#delete-video-collection)
* [List Video Categories](../../doc/controllers/videos.md#list-video-categories)
* [Add Video Collection Items](../../doc/controllers/videos.md#add-video-collection-items)
* [Get Video Collection Items](../../doc/controllers/videos.md#get-video-collection-items)
* [Delete Video Collection Items](../../doc/controllers/videos.md#delete-video-collection-items)
* [Find Similar Videos](../../doc/controllers/videos.md#find-similar-videos)
* [Get Updated Videos](../../doc/controllers/videos.md#get-updated-videos)


# Search Videos

This endpoint searches for videos. If you specify more than one search parameter, the API uses an AND condition. Array parameters can be specified multiple times; in this case, the API uses an AND or an OR condition with those values, depending on the parameter. You can also filter search terms out in the `query` parameter by prefixing the term with NOT.

```java
CompletableFuture<ApiResponse<VideoSearchResults>> searchVideosAsync(
    final LocalDate addedDate,
    final LocalDate addedDateStart,
    final LocalDate addedDateEnd,
    final AspectRatio aspectRatio,
    final String category,
    final List<String> contributor,
    final List<String> contributorCountry,
    final Integer duration,
    final Integer durationFrom,
    final Integer durationTo,
    final Double fps,
    final Double fpsFrom,
    final Double fpsTo,
    final Boolean keywordSafeSearch,
    final Language language,
    final List<License9> license,
    final List<String> model,
    final Orientation2 orientation,
    final Integer page,
    final Integer perPage,
    final PeopleAge2 peopleAge,
    final List<PeopleEthnicity5> peopleEthnicity,
    final PeopleGender2 peopleGender,
    final Integer peopleNumber,
    final Boolean peopleModelReleased,
    final String query,
    final Resolution resolution,
    final Boolean safe,
    final Sort2 sort,
    final View2 view)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `addedDate` | `LocalDate` | Query, Optional | Show videos added on the specified date |
| `addedDateStart` | `LocalDate` | Query, Optional | Show videos added on or after the specified date |
| `addedDateEnd` | `LocalDate` | Query, Optional | Show videos added before the specified date |
| `aspectRatio` | [`AspectRatio`](../../doc/models/aspect-ratio.md) | Query, Optional | Show videos with the specified aspect ratio |
| `category` | `String` | Query, Optional | Show videos with the specified Shutterstock-defined category; specify a category name or ID |
| `contributor` | `List<String>` | Query, Optional | Show videos with the specified artist names or IDs |
| `contributorCountry` | `List<String>` | Query, Optional | Show videos from contributors in one or more specified countries |
| `duration` | `Integer` | Query, Optional | (Deprecated; use duration_from and duration_to instead) Show videos with the specified duration in seconds |
| `durationFrom` | `Integer` | Query, Optional | Show videos with the specified duration or longer in seconds |
| `durationTo` | `Integer` | Query, Optional | Show videos with the specified duration or shorter in seconds |
| `fps` | `Double` | Query, Optional | (Deprecated; use fps_from and fps_to instead) Show videos with the specified frames per second |
| `fpsFrom` | `Double` | Query, Optional | Show videos with the specified frames per second or more |
| `fpsTo` | `Double` | Query, Optional | Show videos with the specified frames per second or fewer |
| `keywordSafeSearch` | `Boolean` | Query, Optional | Hide results with potentially unsafe keywords<br><br>**Default**: `true` |
| `language` | [`Language`](../../doc/models/language.md) | Query, Optional | Set query and result language (uses Accept-Language header if not set) |
| `license` | [`List<License9>`](../../doc/models/license-9.md) | Query, Optional | Show only videos with the specified license or licenses |
| `model` | `List<String>` | Query, Optional | Show videos with each of the specified models |
| `orientation` | [`Orientation2`](../../doc/models/orientation-2.md) | Query, Optional | Search for videos in a specific orientation |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 0`, `<= 500` |
| `peopleAge` | [`PeopleAge2`](../../doc/models/people-age-2.md) | Query, Optional | Show videos that feature people of the specified age range |
| `peopleEthnicity` | [`List<PeopleEthnicity5>`](../../doc/models/people-ethnicity-5.md) | Query, Optional | Show videos with people of the specified ethnicities |
| `peopleGender` | [`PeopleGender2`](../../doc/models/people-gender-2.md) | Query, Optional | Show videos with people with the specified gender |
| `peopleNumber` | `Integer` | Query, Optional | Show videos with the specified number of people<br><br>**Constraints**: `>= 0`, `<= 4` |
| `peopleModelReleased` | `Boolean` | Query, Optional | Show only videos of people with a signed model release |
| `query` | `String` | Query, Optional | One or more search terms separated by spaces; you can use NOT to filter out videos that match a term |
| `resolution` | [`Resolution`](../../doc/models/resolution.md) | Query, Optional | Show videos with the specified resolution |
| `safe` | `Boolean` | Query, Optional | Enable or disable safe search<br><br>**Default**: `true` |
| `sort` | [`Sort2`](../../doc/models/sort-2.md) | Query, Optional | Sort by one of these categories<br><br>**Default**: `Sort2.POPULAR` |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.MINIMAL` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`VideoSearchResults`](../../doc/models/video-search-results.md).

## Example Usage

```java
LocalDate addedDate = DateTimeHelper.fromSimpleDate("2020-05-29");
LocalDate addedDateStart = DateTimeHelper.fromSimpleDate("2020-05-29");
LocalDate addedDateEnd = DateTimeHelper.fromSimpleDate("2020-05-29");
AspectRatio aspectRatio = AspectRatio.ENUM_4_3;
List<String> contributor = Arrays.asList(
    "contributor7"
);

Integer durationFrom = 60;
Integer durationTo = 180;
Double fpsFrom = 24D;
Double fpsTo = 60D;
Boolean keywordSafeSearch = true;
Language language = Language.CS;
List<License9> license = Arrays.asList(
    License9.COMMERCIAL,
    License9.EDITORIAL
);

List<String> model = Arrays.asList(
    "442583",
    "434750"
);

Integer page = 1;
Integer perPage = 20;
PeopleAge2 peopleAge = PeopleAge2.ENUM_20S;
PeopleGender2 peopleGender = PeopleGender2.FEMALE;
Integer peopleNumber = 2;
Boolean peopleModelReleased = true;
String query = "dogs running on the beach";
Resolution resolution = Resolution.ENUM_4K;
Boolean safe = true;
Sort2 sort = Sort2.POPULAR;
View2 view = View2.MINIMAL;

videosApi.searchVideosAsync(addedDate, addedDateStart, addedDateEnd, aspectRatio, null, contributor, null, null, durationFrom, durationTo, null, fpsFrom, fpsTo, keywordSafeSearch, language, license, model, null, page, perPage, peopleAge, null, peopleGender, peopleNumber, peopleModelReleased, query, resolution, safe, sort, view).thenAccept(result -> {
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
      "id": "1033184651",
      "aspect": 1.778,
      "aspect_ratio": "16:9",
      "assets": {
        "thumb_webm": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.webm"
        },
        "thumb_mp4": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.mp4"
        },
        "preview_webm": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/preview/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.webm"
        },
        "preview_mp4": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/preview/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.mp4"
        },
        "thumb_jpg": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/12.jpg"
        },
        "preview_jpg": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/12.jpg"
        }
      },
      "contributor": {
        "id": "4411978"
      },
      "description": "Camera follows hipster millennial young woman in orange jacket running up on top of mountain summit at sunset, jumps on top of rocks, raises arms into air, happy and drunk on life, youth and happiness",
      "duration": 14.081,
      "has_model_release": true,
      "media_type": "video"
    }
  ],
  "page": 1,
  "per_page": 5,
  "total_count": 123,
  "search_id": "749090bb-2967-4a20-b22e-c800dc845e10"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 404 | Not found | `ApiException` |


# Get Video Suggestions

This endpoint provides autocomplete suggestions for partial search terms.

```java
CompletableFuture<ApiResponse<Suggestions>> getVideoSuggestionsAsync(
    final String query,
    final Integer limit)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `query` | `String` | Query, Required | Search term for which you want keyword suggestions |
| `limit` | `Integer` | Query, Optional | Limit the number of the suggestions<br><br>**Default**: `10`<br><br>**Constraints**: `>= 1`, `<= 25` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`Suggestions`](../../doc/models/suggestions.md).

## Example Usage

```java
String query = "cats";
Integer limit = 10;

videosApi.getVideoSuggestionsAsync(query, limit).thenAccept(result -> {
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
    "cat scan",
    "cats and dogs",
    "cats playing",
    "catsuit",
    "cat silhouette",
    "catskills",
    "cats eyes",
    "cat sitting",
    "cat sleeping",
    "cats eye"
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Get Video List

This endpoint lists information about one or more videos, including the aspect ratio and URLs to previews.

```java
CompletableFuture<ApiResponse<VideoDataList>> getVideoListAsync(
    final List<String> id,
    final View2 view,
    final String searchId)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `List<String>` | Query, Required | One or more video IDs<br><br>**Constraints**: *Minimum Items*: `1`, *Maximum Items*: `500` |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.MINIMAL` |
| `searchId` | `String` | Query, Optional | The ID of the search that is related to this request |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`VideoDataList`](../../doc/models/video-data-list.md).

## Example Usage

```java
List<String> id = Arrays.asList(
    "639703",
    "993721"
);

View2 view = View2.MINIMAL;
String searchId = "00000000-0000-0000-0000-000000000000";

videosApi.getVideoListAsync(id, view, searchId).thenAccept(result -> {
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
      "id": "1033184651",
      "added_date": "2019-07-13",
      "aspect": 1.778,
      "aspect_ratio": "16:9",
      "assets": {
        "thumb_webm": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.webm"
        },
        "thumb_mp4": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.mp4"
        },
        "preview_webm": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/preview/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.webm"
        },
        "preview_mp4": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/preview/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.mp4"
        },
        "thumb_jpgs": {
          "urls": [
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/1.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/2.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/3.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/4.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/5.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/6.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/7.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/8.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/9.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/10.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/11.jpg",
            "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/12.jpg"
          ]
        },
        "thumb_jpg": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/12.jpg"
        },
        "preview_jpg": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/12.jpg"
        },
        "sd": {
          "height": 480,
          "width": 852,
          "fps": 29.97,
          "format": "mov",
          "file_size": 4577280,
          "display_name": "Standard Definition MPEG",
          "is_licensable": true
        },
        "web": {
          "height": 240,
          "width": 426,
          "fps": 29.97,
          "format": "mov",
          "file_size": 1291264,
          "display_name": "Low Resolution MPEG",
          "is_licensable": true
        },
        "hd": {
          "height": 1080,
          "width": 1920,
          "fps": 29.97,
          "format": "avc1",
          "file_size": 110359552,
          "display_name": "Original HD",
          "is_licensable": true
        }
      },
      "categories": [
        {
          "name": "Nature",
          "id": "12"
        },
        {
          "name": "People",
          "id": "13"
        }
      ],
      "contributor": {
        "id": "4411978"
      },
      "description": "Camera follows hipster millennial young woman in orange jacket running up on top of mountain summit at sunset, jumps on top of rocks, raises arms into air, happy and drunk on life, youth and happiness",
      "duration": 14.081,
      "has_model_release": true,
      "has_property_release": false,
      "is_adult": false,
      "is_editorial": false,
      "keywords": [
        "active",
        "activity",
        "adventure",
        "arms",
        "backpacker",
        "carefree",
        "celebrating",
        "cliff",
        "climate",
        "cloud",
        "discovery",
        "escape",
        "explore",
        "extreme",
        "free",
        "freedom",
        "girl",
        "happy",
        "high",
        "hiker",
        "hiking",
        "hill",
        "independent",
        "inspiration",
        "landscape",
        "leisure",
        "lifestyle",
        "mountain",
        "mountains",
        "nature",
        "outdoor",
        "peak",
        "person",
        "rock",
        "scenic",
        "sky",
        "sport",
        "success",
        "summer",
        "summit",
        "sun",
        "sunset",
        "top",
        "tourism",
        "travel",
        "trekking",
        "vacation",
        "view",
        "winning",
        "woman"
      ],
      "media_type": "video",
      "models": [
        {
          "id": "33233810"
        },
        {
          "id": "25487168"
        }
      ]
    }
  ],
  "page": 1,
  "per_page": 5,
  "total_count": 25
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Get Video

This endpoint shows information about a video, including URLs to previews and the sizes that it is available in.

```java
CompletableFuture<ApiResponse<Video>> getVideoAsync(
    final String id,
    final Language language,
    final View2 view,
    final String searchId)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Video ID |
| `language` | [`Language`](../../doc/models/language.md) | Query, Optional | Language for the keywords and categories in the response |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.FULL` |
| `searchId` | `String` | Query, Optional | The ID of the search that is related to this request |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`Video`](../../doc/models/video.md).

## Example Usage

```java
String id = "639703";
Language language = Language.ES;
View2 view = View2.FULL;
String searchId = "00000000-0000-0000-0000-000000000000";

videosApi.getVideoAsync(id, language, view, searchId).thenAccept(result -> {
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
  "id": "1033184651",
  "added_date": "2019-07-13",
  "aspect": 1.778,
  "aspect_ratio": "16:9",
  "assets": {
    "thumb_webm": {
      "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.webm"
    },
    "thumb_mp4": {
      "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.mp4"
    },
    "preview_webm": {
      "url": "https://ak.picdn.net/shutterstock/videos/1033184651/preview/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.webm"
    },
    "preview_mp4": {
      "url": "https://ak.picdn.net/shutterstock/videos/1033184651/preview/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.mp4"
    },
    "thumb_jpgs": {
      "urls": [
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/1.jpg",
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/2.jpg",
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/3.jpg",
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/4.jpg",
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/5.jpg",
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/6.jpg",
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/7.jpg",
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/8.jpg",
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/9.jpg",
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/10.jpg",
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/11.jpg",
        "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/12.jpg"
      ]
    },
    "thumb_jpg": {
      "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/12.jpg"
    },
    "preview_jpg": {
      "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/12.jpg"
    },
    "sd": {
      "height": 480,
      "width": 852,
      "fps": 29.97,
      "format": "mov",
      "file_size": 4577280,
      "display_name": "Standard Definition MPEG",
      "is_licensable": true
    },
    "web": {
      "height": 240,
      "width": 426,
      "fps": 29.97,
      "format": "mov",
      "file_size": 1291264,
      "display_name": "Low Resolution MPEG",
      "is_licensable": true
    },
    "hd": {
      "height": 1080,
      "width": 1920,
      "fps": 29.97,
      "format": "avc1",
      "file_size": 110359552,
      "display_name": "Original HD",
      "is_licensable": true
    }
  },
  "categories": [
    {
      "name": "Nature",
      "id": "12"
    },
    {
      "name": "People",
      "id": "13"
    }
  ],
  "contributor": {
    "id": "4411978"
  },
  "description": "Camera follows hipster millennial young woman in orange jacket running up on top of mountain summit at sunset, jumps on top of rocks, raises arms into air, happy and drunk on life, youth and happiness",
  "duration": 14.081,
  "has_model_release": true,
  "has_property_release": false,
  "is_adult": false,
  "is_editorial": false,
  "keywords": [
    "active",
    "activity",
    "adventure",
    "arms",
    "backpacker",
    "carefree",
    "celebrating",
    "cliff",
    "climate",
    "cloud",
    "discovery",
    "escape",
    "explore",
    "extreme",
    "free",
    "freedom",
    "girl",
    "happy",
    "high",
    "hiker",
    "hiking",
    "hill",
    "independent",
    "inspiration",
    "landscape",
    "leisure",
    "lifestyle",
    "mountain",
    "mountains",
    "nature",
    "outdoor",
    "peak",
    "person",
    "rock",
    "scenic",
    "sky",
    "sport",
    "success",
    "summer",
    "summit",
    "sun",
    "sunset",
    "top",
    "tourism",
    "travel",
    "trekking",
    "vacation",
    "view",
    "winning",
    "woman"
  ],
  "media_type": "video",
  "models": [
    {
      "id": "33233810"
    },
    {
      "id": "25487168"
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
| 404 | Not found | `ApiException` |


# License Videos

This endpoint gets licenses for one or more videos. You must specify the video IDs in the body parameter and the size and subscription ID either in the query parameter or with each video ID in the body parameter. Values in the body parameter override values in the query parameters. The download links in the response are valid for 8 hours.

```java
CompletableFuture<ApiResponse<LicenseVideoResultDataList>> licenseVideosAsync(
    final LicenseVideoRequest body,
    final String subscriptionId,
    final Size16 size,
    final String searchId)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`LicenseVideoRequest`](../../doc/models/license-video-request.md) | Body, Required | List of videos to request licenses for and information about each license transaction; these values override the defaults in the query parameters |
| `subscriptionId` | `String` | Query, Optional | The subscription ID to use for licensing |
| `size` | [`Size16`](../../doc/models/size-16.md) | Query, Optional | The size of the video to license<br><br>**Default**: `Size16.WEB` |
| `searchId` | `String` | Query, Optional | The Search ID that led to this licensing event |

## Requires scope

### customer_accessCode

`licenses.create`, `purchases.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`LicenseVideoResultDataList`](../../doc/models/license-video-result-data-list.md).

## Example Usage

```java
LicenseVideoRequest body = new LicenseVideoRequest.Builder(
    Arrays.asList(
        new LicenseVideo.Builder(
            "2140697"
        )
        .size(Size8.HD)
        .subscriptionId("s12345678")
        .build()
    )
)
.build();


videosApi.licenseVideosAsync(body, null, null, null).thenAccept(result -> {
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
        "url": "https://download.shutterstock.com/gatekeeper/[random-characters]/shutterstock_59656357.mp4"
      },
      "price": {
        "local_amount": 12.34,
        "local_currency": "EUR"
      },
      "video_id": "123456789"
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


# Get Video License List

This endpoint lists existing licenses.

```java
CompletableFuture<ApiResponse<DownloadHistoryDataList>> getVideoLicenseListAsync(
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
| `videoId` | `String` | Query, Optional | Show licenses for the specified video ID<br><br>**Constraints**: *Pattern*: `^[1-9]\d*$` |
| `license` | `String` | Query, Optional | Show videos that are available with the specified license, such as `standard` or `enhanced`<br><br>**Constraints**: *Pattern*: `^.+$` |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 200` |
| `sort` | [`Sort5`](../../doc/models/sort-5.md) | Query, Optional | Sort by oldest or newest videos first<br><br>**Default**: `Sort5.NEWEST` |
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
String license = "standard";
Integer page = 1;
Integer perPage = 20;
Sort5 sort = Sort5.NEWEST;
String username = "aUniqueUsername";
LocalDateTime startDate = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
LocalDateTime endDate = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
DownloadAvailability downloadAvailability = DownloadAvailability.ALL;
Boolean teamHistory = false;

videosApi.getVideoLicenseListAsync(videoId, license, page, perPage, sort, username, startDate, endDate, downloadAvailability, teamHistory).thenAccept(result -> {
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
      "id": "e121",
      "user": {
        "username": "myusername"
      },
      "license": "footage_premier",
      "subscription_id": "s12345678",
      "download_time": "2018-05-24T14:26:25-04:00",
      "is_downloadable": true,
      "metadata": {
        "customer_id": "12345",
        "geo_location": "US",
        "number_viewed": "15",
        "search_term": "dog"
      },
      "video": {
        "id": "2140697",
        "format": {
          "size": "sd"
        }
      }
    }
  ],
  "page": 1,
  "per_page": 20
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Download Videos

This endpoint redownloads videos that you have already received a license for.

```java
CompletableFuture<ApiResponse<Url>> downloadVideosAsync(
    final String id,
    final RedownloadVideo body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | The license ID of the item to (re)download. The download links in the response are valid for 8 hours. |
| `body` | [`RedownloadVideo`](../../doc/models/redownload-video.md) | Body, Required | Information about the videos to redownload |

## Requires scope

### customer_accessCode

`licenses.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`Url`](../../doc/models/url.md).

## Example Usage

```java
String id = "e123";
RedownloadVideo body = new RedownloadVideo.Builder()
    .size(Size11.WEB)
    .build();

videosApi.downloadVideosAsync(id, body).thenAccept(result -> {
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
  "url": "https://download1.shutterstock.com/gatekeeper/W3siZSI6MTUzMzMzMzUzMCwiayI6InZpZGVvLzM5NjU4ODEvaGQubW92IiwibSI6MSwiZCI6InNodXR0ZXJzdG9jay1tZWRpYSJ9LCJjZ2lvRU14T09hNWZGTHZsN21iTWVPRVQ3MFEiXQ/shutterstock_v3965881.mov"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Create Video Collection

This endpoint creates one or more collections (clipboxes). To add videos to collections, use `POST /v2/videos/collections/{id}/items`.

```java
CompletableFuture<ApiResponse<CollectionCreateResponse>> createVideoCollectionAsync(
    final CollectionCreateRequest body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CollectionCreateRequest`](../../doc/models/collection-create-request.md) | Body, Required | Collection metadata |

## Requires scope

### customer_accessCode

`collections.edit`

## Response Type

**201**: Successfully created video collection

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CollectionCreateResponse`](../../doc/models/collection-create-response.md).

## Example Usage

```java
CollectionCreateRequest body = new CollectionCreateRequest.Builder(
    "Test Collection 19cf"
)
.build();

videosApi.createVideoCollectionAsync(body).thenAccept(result -> {
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
  "id": "48433105"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Get Video Collection List

This endpoint lists your collections of videos and their basic attributes.

```java
CompletableFuture<ApiResponse<CollectionDataList>> getVideoCollectionListAsync(
    final Integer page,
    final Integer perPage,
    final List<Embed> embed)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `100`<br><br>**Constraints**: `>= 1`, `<= 150` |
| `embed` | [`List<Embed>`](../../doc/models/embed.md) | Query, Optional | Which sharing information to include in the response, such as a URL to the collection |

## Requires scope

### customer_accessCode

`collections.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CollectionDataList`](../../doc/models/collection-data-list.md).

## Example Usage

```java
Integer page = 1;
Integer perPage = 100;
videosApi.getVideoCollectionListAsync(page, perPage, null).thenAccept(result -> {
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


# Get Video Collection

This endpoint gets more detailed information about a collection, including the timestamp for its creation and the number of videos in it. To get the videos in collections, use GET /v2/videos/collections/{id}/items.

```java
CompletableFuture<ApiResponse<MCollection>> getVideoCollectionAsync(
    final String id,
    final List<Embed> embed,
    final String shareCode)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | The ID of the collection to return |
| `embed` | [`List<Embed>`](../../doc/models/embed.md) | Query, Optional | Which sharing information to include in the response, such as a URL to the collection |
| `shareCode` | `String` | Query, Optional | Code to retrieve a shared collection |

## Requires scope

### customer_accessCode

`collections.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`MCollection`](../../doc/models/m-collection.md).

## Example Usage

```java
String id = "17555176";

videosApi.getVideoCollectionAsync(id, null, null).thenAccept(result -> {
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
| 404 | Collection not found | `ApiException` |


# Rename Video Collection

This endpoint sets a new name for a collection.

```java
CompletableFuture<ApiResponse<Void>> renameVideoCollectionAsync(
    final String id,
    final CollectionUpdateRequest body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | The ID of the collection to rename |
| `body` | [`CollectionUpdateRequest`](../../doc/models/collection-update-request.md) | Body, Required | The new name for the collection |

## Requires scope

### customer_accessCode

`collections.edit`

## Response Type

**204**: Successfully updated collection

`void`

## Example Usage

```java
String id = "17555176";
CollectionUpdateRequest body = new CollectionUpdateRequest.Builder(
    "My collection with a new name"
)
.build();

videosApi.renameVideoCollectionAsync(id, body).thenAccept(result -> {
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
| 404 | Collection not found | `ApiException` |


# Delete Video Collection

This endpoint deletes a collection.

```java
CompletableFuture<ApiResponse<Void>> deleteVideoCollectionAsync(
    final String id)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | The ID of the collection to delete |

## Requires scope

### customer_accessCode

`collections.edit`

## Response Type

**204**: Successfully deleted collection

`void`

## Example Usage

```java
String id = "17555176";

videosApi.deleteVideoCollectionAsync(id).thenAccept(result -> {
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
| 404 | Collection not found | `ApiException` |


# List Video Categories

This endpoint lists the categories (Shutterstock-assigned genres) that videos can belong to.

```java
CompletableFuture<ApiResponse<CategoryDataList>> listVideoCategoriesAsync(
    final Language language)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `language` | [`Language`](../../doc/models/language.md) | Query, Optional | Language for the keywords and categories in the response |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CategoryDataList`](../../doc/models/category-data-list.md).

## Example Usage

```java
Language language = Language.ES;

videosApi.listVideoCategoriesAsync(language).thenAccept(result -> {
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
      "id": "1",
      "name": "Animals/Wildlife"
    },
    {
      "id": "11",
      "name": "The Arts"
    }
  ],
  "page": 1,
  "per_page": 2,
  "total_count": 13
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Add Video Collection Items

This endpoint adds one or more videos to a collection by video IDs.

```java
CompletableFuture<ApiResponse<Void>> addVideoCollectionItemsAsync(
    final String id,
    final CollectionItemRequest body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | The ID of the collection to which items should be added |
| `body` | [`CollectionItemRequest`](../../doc/models/collection-item-request.md) | Body, Required | Array of video IDs to add to the collection |

## Requires scope

### customer_accessCode

`collections.edit`

## Response Type

**204**: Successfully added collection items

`void`

## Example Usage

```java
String id = "17555176";
CollectionItemRequest body = new CollectionItemRequest.Builder(
    Arrays.asList(
        new CollectionItem.Builder(
            "10120264"
        )
        .build(),
        new CollectionItem.Builder(
            "24419024"
        )
        .build()
    )
)
.build();

videosApi.addVideoCollectionItemsAsync(id, body).thenAccept(result -> {
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
| 404 | Collection not found | `ApiException` |


# Get Video Collection Items

This endpoint lists the IDs of videos in a collection and the date that each was added.

```java
CompletableFuture<ApiResponse<CollectionItemDataList>> getVideoCollectionItemsAsync(
    final String id,
    final Integer page,
    final Integer perPage,
    final String shareCode,
    final Sort5 sort)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Collection ID |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `100`<br><br>**Constraints**: `>= 1`, `<= 150` |
| `shareCode` | `String` | Query, Optional | Code to retrieve the contents of a shared collection |
| `sort` | [`Sort5`](../../doc/models/sort-5.md) | Query, Optional | Sort order<br><br>**Default**: `Sort5.OLDEST` |

## Requires scope

### customer_accessCode

`collections.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CollectionItemDataList`](../../doc/models/collection-item-data-list.md).

## Example Usage

```java
String id = "17555176";
Integer page = 1;
Integer perPage = 100;
Sort5 sort = Sort5.OLDEST;

videosApi.getVideoCollectionItemsAsync(id, page, perPage, null, sort).thenAccept(result -> {
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
      "id": "1690105108",
      "added_time": "2021-07-08T12:33:37.000Z",
      "media_type": "image"
    },
    {
      "id": "1468703072",
      "added_time": "2021-07-08T12:31:43.000Z",
      "media_type": "image"
    }
  ],
  "page": 1,
  "per_page": 2,
  "total_count": 82
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 404 | Collection not found | `ApiException` |


# Delete Video Collection Items

This endpoint removes one or more videos from a collection.

```java
CompletableFuture<ApiResponse<Void>> deleteVideoCollectionItemsAsync(
    final String id,
    final List<String> itemId)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | The ID of the Collection from which items will be deleted |
| `itemId` | `List<String>` | Query, Optional | One or more video IDs to remove from the collection |

## Requires scope

### customer_accessCode

`collections.edit`

## Response Type

**204**: Successfully removed collection items

`void`

## Example Usage

```java
String id = "17555176";
videosApi.deleteVideoCollectionItemsAsync(id, null).thenAccept(result -> {
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
| 404 | Collection not found | `ApiException` |


# Find Similar Videos

This endpoint searches for videos that are similar to a video that you specify.

```java
CompletableFuture<ApiResponse<VideoSearchResults>> findSimilarVideosAsync(
    final String id,
    final Language language,
    final Integer page,
    final Integer perPage,
    final View2 view)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | The ID of a video for which similar videos should be returned |
| `language` | [`Language`](../../doc/models/language.md) | Query, Optional | Language for the keywords and categories in the response |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 500` |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.MINIMAL` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`VideoSearchResults`](../../doc/models/video-search-results.md).

## Example Usage

```java
String id = "2140697";
Language language = Language.ES;
Integer page = 1;
Integer perPage = 20;
View2 view = View2.MINIMAL;

videosApi.findSimilarVideosAsync(id, language, page, perPage, view).thenAccept(result -> {
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
      "id": "1033184651",
      "aspect": 1.778,
      "aspect_ratio": "16:9",
      "assets": {
        "thumb_webm": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.webm"
        },
        "thumb_mp4": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.mp4"
        },
        "preview_webm": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/preview/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.webm"
        },
        "preview_mp4": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/preview/stock-footage-camera-follows-hipster-millennial-young-woman-in-orange-jacket-running-up-on-top-of-mountain-summit.mp4"
        },
        "thumb_jpg": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/12.jpg"
        },
        "preview_jpg": {
          "url": "https://ak.picdn.net/shutterstock/videos/1033184651/thumb/12.jpg"
        }
      },
      "contributor": {
        "id": "4411978"
      },
      "description": "Camera follows hipster millennial young woman in orange jacket running up on top of mountain summit at sunset, jumps on top of rocks, raises arms into air, happy and drunk on life, youth and happiness",
      "duration": 14.081,
      "has_model_release": true,
      "media_type": "video"
    }
  ],
  "page": 1,
  "per_page": 5,
  "total_count": 123,
  "search_id": "749090bb-2967-4a20-b22e-c800dc845e10"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Get Updated Videos

This endpoint lists videos that have been updated in the specified time period to update content management systems (CMS) or digital asset management (DAM) systems. In most cases, use the `interval` parameter to show videos that were updated recently, but you can also use the `start_date` and `end_date` parameters to specify a range of no more than three days. Do not use the `interval` parameter with either `start_date` or `end_date`.

```java
CompletableFuture<ApiResponse<UpdatedMediaDataList>> getUpdatedVideosAsync(
    final String startDate,
    final String endDate,
    final String interval,
    final Integer page,
    final Integer perPage,
    final Sort5 sort)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `startDate` | `String` | Query, Optional | Show videos updated on or after the specified date. The API will default to UTC (00:00:00) if no specific time is provided, ensuring consistency. |
| `endDate` | `String` | Query, Optional | Show videos updated before the specified date. The API will default to UTC (00:00:00) if no specific time is provided, ensuring consistency. Please note that the end date must be at least 5 minutes after the start date. |
| `interval` | `String` | Query, Optional | Show videos updated in the specified time period, where the time period is an interval (like SQL INTERVAL) such as 1 DAY, 6 HOUR, or 30 MINUTE; the default is 1 HOUR, which shows videos that were updated in the hour preceding the request<br><br>**Default**: `"1 HOUR"` |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `100`<br><br>**Constraints**: `>= 1`, `<= 2000` |
| `sort` | [`Sort5`](../../doc/models/sort-5.md) | Query, Optional | Sort by oldest or newest videos first<br><br>**Default**: `Sort5.NEWEST` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UpdatedMediaDataList`](../../doc/models/updated-media-data-list.md).

## Example Usage

```java
String startDate = "2021-03-29T00:00:00Z OR 2021-03-29";
String endDate = "2021-03-29T23:59:59Z OR 2021-03-29";
String interval = "1 HOUR";
Integer page = 1;
Integer perPage = 100;
Sort5 sort = Sort5.NEWEST;

videosApi.getUpdatedVideosAsync(startDate, endDate, interval, page, perPage, sort).thenAccept(result -> {
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
      "id": "123456789",
      "updated_time": "2020-05-29T12:10:22-05:00",
      "updates": [
        "addition",
        "edit"
      ]
    }
  ],
  "page": 1,
  "per_page": 5,
  "total_count": 13
}
```

