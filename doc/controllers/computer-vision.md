# Computer Vision

```java
ComputerVisionApi computerVisionApi = client.getComputerVisionApi();
```

## Class Name

`ComputerVisionApi`

## Methods

* [Upload Image](../../doc/controllers/computer-vision.md#upload-image)
* [Get Similar Images](../../doc/controllers/computer-vision.md#get-similar-images)
* [Get Similar Videos](../../doc/controllers/computer-vision.md#get-similar-videos)
* [Get Keywords](../../doc/controllers/computer-vision.md#get-keywords)


# Upload Image

This endpoint uploads an image for reverse image or video search. Images must be in JPEG or PNG format. To get the search results, pass the upload ID that this endpoint returns to the GET /v2/cv/similar/images or GET /v2/cv/similar/videos endpoints. Contact us for access to this endpoint.

```java
CompletableFuture<ApiResponse<ComputerVisionImageCreateResponse>> uploadImageAsync(
    final ImageCreateRequest body)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ImageCreateRequest`](../../doc/models/image-create-request.md) | Body, Required | A Base 64 encoded jpeg or png; images can be no larger than 10mb and can be no larger than 10,000 pixels in width or height |

## Response Type

**201**: Created

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ComputerVisionImageCreateResponse`](../../doc/models/computer-vision-image-create-response.md).

## Example Usage

```java
ImageCreateRequest body = new ImageCreateRequest.Builder(
    "R0lGODlhgACAAPcAAEwiBLyaLOzNUNmWFNjOrNSuN7x6PPzqeOTMgfKSDMyuTPzwsdi2dHwuBPzbVu"
)
.build();

computerVisionApi.uploadImageAsync(body).thenAccept(result -> {
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
  "upload_id": "Udb14e1c3540bdbf82b4b3fe12d3a44f2"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 413 | Payload Too Large | `ApiException` |
| 415 | Unsupported Media Type | `ApiException` |


# Get Similar Images

This endpoint returns images that are visually similar to an image that you specify or upload.

```java
CompletableFuture<ApiResponse<ImageSearchResults>> getSimilarImagesAsync(
    final String assetId,
    final List<License9> license,
    final Boolean safe,
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
| `assetId` | `String` | Query, Required | The asset ID or upload ID to find similar images for |
| `license` | [`List<License9>`](../../doc/models/license-9.md) | Query, Optional | Show only images with the specified license |
| `safe` | `Boolean` | Query, Optional | Enable or disable safe search<br><br>**Default**: `true` |
| `language` | [`Language`](../../doc/models/language.md) | Query, Optional | Language for the keywords and categories in the response |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 500` |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.MINIMAL` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ImageSearchResults`](../../doc/models/image-search-results.md).

## Example Usage

```java
String assetId = "U6ba16262e3bc2db470b8e3cfa8aaab25";
Boolean safe = true;
Language language = Language.ES;
Integer page = 1;
Integer perPage = 20;
View2 view = View2.MINIMAL;

computerVisionApi.getSimilarImagesAsync(assetId, null, safe, language, page, perPage, view).thenAccept(result -> {
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
      "id": "1572478477",
      "aspect": 1.5,
      "assets": {
        "preview": {
          "height": 300,
          "url": "https://image.shutterstock.com/display_pic_with_logo/250738318/1572478477/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
          "width": 450
        },
        "small_thumb": {
          "height": 67,
          "url": "https://thumb7.shutterstock.com/thumb_small/250738318/1572478477/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
          "width": 100
        },
        "large_thumb": {
          "height": 100,
          "url": "https://thumb7.shutterstock.com/thumb_large/250738318/1572478477/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
          "width": 150
        },
        "mosaic": {
          "height": 167,
          "url": "https://image.shutterstock.com/image-photo/stock-photo-cropped-image-of-woman-gardening-250nw-1572478477.jpg",
          "width": 250
        },
        "huge_thumb": {
          "height": 260,
          "url": "https://image.shutterstock.com/image-photo/cropped-image-woman-gardening-260nw-1572478477.jpg",
          "width": 390
        },
        "preview_1000": {
          "url": "https://ak.picdn.net/shutterstock/photos/1572478477/watermark_1000/1706028c641ea2f443057287c67d9b91/preview_1000-1572478477.jpg",
          "width": 1000,
          "height": 667
        },
        "preview_1500": {
          "url": "https://image.shutterstock.com/z/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
          "width": 1500,
          "height": 1000
        }
      },
      "contributor": {
        "id": "250738318"
      },
      "description": "cropped image of woman gardening",
      "image_type": "photo",
      "has_model_release": true,
      "media_type": "image"
    }
  ],
  "page": 1,
  "per_page": 5,
  "search_id": "749090bb-2967-4a20-b22e-c800dc845e10",
  "spellcheck_info": {},
  "total_count": 45
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Get Similar Videos

This endpoint returns videos that are visually similar to an image that you specify or upload.

```java
CompletableFuture<ApiResponse<VideoSearchResults>> getSimilarVideosAsync(
    final String assetId,
    final List<License9> license,
    final Boolean safe,
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
| `assetId` | `String` | Query, Required | The asset ID or upload ID to find similar videos for |
| `license` | [`List<License9>`](../../doc/models/license-9.md) | Query, Optional | Show only videos with the specified license |
| `safe` | `Boolean` | Query, Optional | Enable or disable safe search<br><br>**Default**: `true` |
| `language` | [`Language`](../../doc/models/language.md) | Query, Optional | Language for the keywords and categories in the response |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 200` |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.MINIMAL` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`VideoSearchResults`](../../doc/models/video-search-results.md).

## Example Usage

```java
String assetId = "U6ba16262e3bc2db470b8e3cfa8aaab25";
Boolean safe = true;
Language language = Language.ES;
Integer page = 1;
Integer perPage = 20;
View2 view = View2.MINIMAL;

computerVisionApi.getSimilarVideosAsync(assetId, null, safe, language, page, perPage, view).thenAccept(result -> {
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


# Get Keywords

This endpoint returns a list of suggested keywords for a media item that you specify or upload.

```java
CompletableFuture<ApiResponse<KeywordDataList>> getKeywordsAsync(
    final GetKeywordsAssetId assetId)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `assetId` | [`GetKeywordsAssetId`](../../doc/models/containers/get-keywords-asset-id.md) | Query, Required | This is a container for one-of cases. |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`KeywordDataList`](../../doc/models/keyword-data-list.md).

## Example Usage

```java
GetKeywordsAssetId assetId = GetKeywordsAssetId.fromString(
    "U6ba16262e3bc2db470b8e3cfa8aaab25"
);

computerVisionApi.getKeywordsAsync(assetId).thenAccept(result -> {
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
    "nature",
    "wildlife",
    "animal",
    "cute",
    "bamboo",
    "panda",
    "china",
    "wild",
    "endangered",
    "black",
    "bear"
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |
| 415 | Unsupported Media Type | `ApiException` |

