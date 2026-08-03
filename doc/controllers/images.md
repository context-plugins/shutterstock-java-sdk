# Images

```java
ImagesApi imagesApi = client.getImagesApi();
```

## Class Name

`ImagesApi`

## Methods

* [Search Images](../../doc/controllers/images.md#search-images)
* [Bulk Search Images](../../doc/controllers/images.md#bulk-search-images)
* [Get Image Suggestions](../../doc/controllers/images.md#get-image-suggestions)
* [Get Image Keyword Suggestions](../../doc/controllers/images.md#get-image-keyword-suggestions)
* [Get Image List](../../doc/controllers/images.md#get-image-list)
* [Get Image](../../doc/controllers/images.md#get-image)
* [List Image Categories](../../doc/controllers/images.md#list-image-categories)
* [List Similar Images](../../doc/controllers/images.md#list-similar-images)
* [License Images](../../doc/controllers/images.md#license-images)
* [Get Image License List](../../doc/controllers/images.md#get-image-license-list)
* [Download Image](../../doc/controllers/images.md#download-image)
* [Get Image Recommendations](../../doc/controllers/images.md#get-image-recommendations)
* [Create Image Collection](../../doc/controllers/images.md#create-image-collection)
* [Get Image Collection List](../../doc/controllers/images.md#get-image-collection-list)
* [Get Image Collection](../../doc/controllers/images.md#get-image-collection)
* [Rename Image Collection](../../doc/controllers/images.md#rename-image-collection)
* [Delete Image Collection](../../doc/controllers/images.md#delete-image-collection)
* [Add Image Collection Items](../../doc/controllers/images.md#add-image-collection-items)
* [Get Image Collection Items](../../doc/controllers/images.md#get-image-collection-items)
* [Delete Image Collection Items](../../doc/controllers/images.md#delete-image-collection-items)
* [Get Updated Images](../../doc/controllers/images.md#get-updated-images)


# Search Images

This endpoint searches for images. If you specify more than one search parameter, the API uses an AND condition. Array parameters can be specified multiple times; in this case, the API uses an AND or an OR condition with those values, depending on the parameter. You can also filter search terms out in the `query` parameter by prefixing the term with NOT. Free API accounts show results only from a limited library of media, not the full Shutterstock media library. Also, the number of search fields they can use in a request is limited.

```java
CompletableFuture<ApiResponse<ImageSearchResults>> searchImagesAsync(
    final List<Library> library,
    final LocalDate addedDate,
    final LocalDate addedDateStart,
    final Double aspectRatioMin,
    final Double aspectRatioMax,
    final Double aspectRatio,
    final LocalDate addedDateEnd,
    final String category,
    final String color,
    final List<String> contributor,
    final SearchImagesContributorCountry contributorCountry,
    final String fields,
    final Integer height,
    final Integer heightFrom,
    final Integer heightTo,
    final List<ImageType2> imageType,
    final Boolean keywordSafeSearch,
    final Language language,
    final List<License> license,
    final List<String> model,
    final Orientation2 orientation,
    final Integer page,
    final Integer perPage,
    final Boolean peopleModelReleased,
    final PeopleAge2 peopleAge,
    final List<PeopleEthnicity2> peopleEthnicity,
    final PeopleGender2 peopleGender,
    final Integer peopleNumber,
    final String query,
    final SearchImagesRegion region,
    final Boolean safe,
    final Sort2 sort,
    final Boolean spellcheckQuery,
    final View2 view,
    final Integer width,
    final Integer widthFrom,
    final Integer widthTo)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `library` | [`List<Library>`](../../doc/models/library.md) | Query, Optional | Search within different Shutterstock owned libraries |
| `addedDate` | `LocalDate` | Query, Optional | Show images added on the specified date |
| `addedDateStart` | `LocalDate` | Query, Optional | Show images added on or after the specified date |
| `aspectRatioMin` | `Double` | Query, Optional | Show images with the specified aspect ratio or higher, using a positive decimal of the width divided by the height, such as 1.7778 for a 16:9 image<br><br>**Constraints**: `> 0` |
| `aspectRatioMax` | `Double` | Query, Optional | Show images with the specified aspect ratio or lower, using a positive decimal of the width divided by the height, such as 1.7778 for a 16:9 image<br><br>**Constraints**: `> 0` |
| `aspectRatio` | `Double` | Query, Optional | Show images with the specified aspect ratio, using a positive decimal of the width divided by the height, such as 1.7778 for a 16:9 image<br><br>**Constraints**: `> 0` |
| `addedDateEnd` | `LocalDate` | Query, Optional | Show images added before the specified date |
| `category` | `String` | Query, Optional | Show images with the specified Shutterstock-defined category; specify a category name or ID |
| `color` | `String` | Query, Optional | Specify either a hexadecimal color in the format '4F21EA' or 'grayscale'; the API returns images that use similar colors |
| `contributor` | `List<String>` | Query, Optional | Show images with the specified contributor names or IDs, allows multiple |
| `contributorCountry` | [`SearchImagesContributorCountry`](../../doc/models/containers/search-images-contributor-country.md) | Query, Optional | This is a container for one-of cases. |
| `fields` | `String` | Query, Optional | Fields to display in the response; see the documentation for the fields parameter in the overview section |
| `height` | `Integer` | Query, Optional | (Deprecated; use height_from and height_to instead) Show images with the specified height |
| `heightFrom` | `Integer` | Query, Optional | Show images with the specified height or larger, in pixels |
| `heightTo` | `Integer` | Query, Optional | Show images with the specified height or smaller, in pixels |
| `imageType` | [`List<ImageType2>`](../../doc/models/image-type-2.md) | Query, Optional | Show images of the specified type |
| `keywordSafeSearch` | `Boolean` | Query, Optional | Hide results with potentially unsafe keywords<br><br>**Default**: `true` |
| `language` | [`Language`](../../doc/models/language.md) | Query, Optional | Set query and result language (uses Accept-Language header if not set) |
| `license` | [`List<License>`](../../doc/models/license.md) | Query, Optional | Show only images with the specified license |
| `model` | `List<String>` | Query, Optional | Show image results with the specified model IDs |
| `orientation` | [`Orientation2`](../../doc/models/orientation-2.md) | Query, Optional | Show image results with horizontal or vertical orientation |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 0`, `<= 500` |
| `peopleModelReleased` | `Boolean` | Query, Optional | Show images of people with a signed model release |
| `peopleAge` | [`PeopleAge2`](../../doc/models/people-age-2.md) | Query, Optional | Show images that feature people of the specified age category |
| `peopleEthnicity` | [`List<PeopleEthnicity2>`](../../doc/models/people-ethnicity-2.md) | Query, Optional | Show images with people of the specified ethnicities, or start with NOT to show images without those ethnicities |
| `peopleGender` | [`PeopleGender2`](../../doc/models/people-gender-2.md) | Query, Optional | Show images with people of the specified gender |
| `peopleNumber` | `Integer` | Query, Optional | Show images with the specified number of people<br><br>**Constraints**: `>= 0`, `<= 4` |
| `query` | `String` | Query, Optional | One or more search terms separated by spaces; you can use NOT to filter out images that match a term |
| `region` | [`SearchImagesRegion`](../../doc/models/containers/search-images-region.md) | Query, Optional | This is a container for any-of cases. |
| `safe` | `Boolean` | Query, Optional | Enable or disable safe search<br><br>**Default**: `true` |
| `sort` | [`Sort2`](../../doc/models/sort-2.md) | Query, Optional | Sort by<br><br>**Default**: `Sort2.POPULAR` |
| `spellcheckQuery` | `Boolean` | Query, Optional | Spellcheck the search query and return results on suggested spellings<br><br>**Default**: `true` |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.MINIMAL` |
| `width` | `Integer` | Query, Optional | (Deprecated; use width_from and width_to instead) Show images with the specified width |
| `widthFrom` | `Integer` | Query, Optional | Show images with the specified width or larger, in pixels |
| `widthTo` | `Integer` | Query, Optional | Show images with the specified width or smaller, in pixels |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ImageSearchResults`](../../doc/models/image-search-results.md).

## Example Usage

```java
List<Library> library = Arrays.asList(
    Library.SHUTTERSTOCK,
    Library.OFFSET
);

LocalDate addedDate = DateTimeHelper.fromSimpleDate("2021-03-29");
LocalDate addedDateStart = DateTimeHelper.fromSimpleDate("2021-03-29");
Double aspectRatioMin = 1.7778D;
Double aspectRatioMax = 1.7778D;
Double aspectRatio = 1.7778D;
LocalDate addedDateEnd = DateTimeHelper.fromSimpleDate("2021-03-29");
String color = "4F21EA";
List<String> contributor = Arrays.asList(
    "123456"
);

Integer heightFrom = 1080;
Integer heightTo = 1080;
Boolean keywordSafeSearch = true;
Language language = Language.FR;
List<String> model = Arrays.asList(
    "12345",
    "67890"
);

Orientation2 orientation = Orientation2.VERTICAL;
Integer page = 1;
Integer perPage = 50;
Boolean peopleModelReleased = true;
PeopleAge2 peopleAge = PeopleAge2.ENUM_20S;
PeopleGender2 peopleGender = PeopleGender2.BOTH;
Integer peopleNumber = 2;
String query = "dogs on the beach";
SearchImagesRegion region = SearchImagesRegion.fromString(
    "US"
);
Boolean safe = true;
Sort2 sort = Sort2.POPULAR;
Boolean spellcheckQuery = true;
View2 view = View2.MINIMAL;
Integer widthFrom = 1920;
Integer widthTo = 1920;

imagesApi.searchImagesAsync(library, addedDate, addedDateStart, aspectRatioMin, aspectRatioMax, aspectRatio, addedDateEnd, null, color, contributor, null, null, null, heightFrom, heightTo, null, keywordSafeSearch, language, null, model, orientation, page, perPage, peopleModelReleased, peopleAge, null, peopleGender, peopleNumber, query, region, safe, sort, spellcheckQuery, view, null, widthFrom, widthTo).thenAccept(result -> {
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


# Bulk Search Images

This endpoint runs up to 5 image searches in a single request and returns up to 20 results per search. You can provide global search parameters in the query parameters and override them for each search in the body parameter. The query and body parameters are the same as in the `GET /v2/images/search` endpoint.

```java
CompletableFuture<ApiResponse<BulkImageSearchResults>> bulkSearchImagesAsync(
    final List<SearchImage> body,
    final LocalDate addedDate,
    final LocalDate addedDateStart,
    final Double aspectRatioMin,
    final Double aspectRatioMax,
    final Double aspectRatio,
    final LocalDate addedDateEnd,
    final String category,
    final String color,
    final List<String> contributor,
    final BulkSearchImagesContributorCountry contributorCountry,
    final String fields,
    final Integer height,
    final Integer heightFrom,
    final Integer heightTo,
    final List<ImageType2> imageType,
    final Boolean keywordSafeSearch,
    final Language language,
    final List<License> license,
    final List<String> model,
    final Orientation2 orientation,
    final Integer page,
    final Integer perPage,
    final Boolean peopleModelReleased,
    final PeopleAge2 peopleAge,
    final List<PeopleEthnicity2> peopleEthnicity,
    final PeopleGender2 peopleGender,
    final Integer peopleNumber,
    final BulkSearchImagesRegion region,
    final Boolean safe,
    final Sort2 sort,
    final Boolean spellcheckQuery,
    final View2 view,
    final Integer width,
    final Integer widthFrom,
    final Integer widthTo)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`List<SearchImage>`](../../doc/models/search-image.md) | Body, Required | List of queries to request results for and filters to apply per query; these values override the defaults in the query parameters<br><br>**Constraints**: *Maximum Items*: `5` |
| `addedDate` | `LocalDate` | Query, Optional | Show images added on the specified date |
| `addedDateStart` | `LocalDate` | Query, Optional | Show images added on or after the specified date |
| `aspectRatioMin` | `Double` | Query, Optional | Show images with the specified aspect ratio or higher, using a positive decimal of the width divided by the height, such as 1.7778 for a 16:9 image<br><br>**Constraints**: `> 0` |
| `aspectRatioMax` | `Double` | Query, Optional | Show images with the specified aspect ratio or lower, using a positive decimal of the width divided by the height, such as 1.7778 for a 16:9 image<br><br>**Constraints**: `> 0` |
| `aspectRatio` | `Double` | Query, Optional | Show images with the specified aspect ratio, using a positive decimal of the width divided by the height, such as 1.7778 for a 16:9 image<br><br>**Constraints**: `> 0` |
| `addedDateEnd` | `LocalDate` | Query, Optional | Show images added before the specified date |
| `category` | `String` | Query, Optional | Show images with the specified Shutterstock-defined category; specify a category name or ID |
| `color` | `String` | Query, Optional | Specify either a hexadecimal color in the format '4F21EA' or 'grayscale'; the API returns images that use similar colors |
| `contributor` | `List<String>` | Query, Optional | Show images with the specified contributor names or IDs, allows multiple |
| `contributorCountry` | [`BulkSearchImagesContributorCountry`](../../doc/models/containers/bulk-search-images-contributor-country.md) | Query, Optional | This is a container for one-of cases. |
| `fields` | `String` | Query, Optional | Fields to display in the response; see the documentation for the fields parameter in the overview section |
| `height` | `Integer` | Query, Optional | (Deprecated; use height_from and height_to instead) Show images with the specified height |
| `heightFrom` | `Integer` | Query, Optional | Show images with the specified height or larger, in pixels |
| `heightTo` | `Integer` | Query, Optional | Show images with the specified height or smaller, in pixels |
| `imageType` | [`List<ImageType2>`](../../doc/models/image-type-2.md) | Query, Optional | Show images of the specified type |
| `keywordSafeSearch` | `Boolean` | Query, Optional | Hide results with potentially unsafe keywords<br><br>**Default**: `true` |
| `language` | [`Language`](../../doc/models/language.md) | Query, Optional | Set query and result language (uses Accept-Language header if not set) |
| `license` | [`List<License>`](../../doc/models/license.md) | Query, Optional | Show only images with the specified license |
| `model` | `List<String>` | Query, Optional | Show image results with the specified model IDs |
| `orientation` | [`Orientation2`](../../doc/models/orientation-2.md) | Query, Optional | Show image results with horizontal or vertical orientation |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 0`, `<= 20` |
| `peopleModelReleased` | `Boolean` | Query, Optional | Show images of people with a signed model release |
| `peopleAge` | [`PeopleAge2`](../../doc/models/people-age-2.md) | Query, Optional | Show images that feature people of the specified age category |
| `peopleEthnicity` | [`List<PeopleEthnicity2>`](../../doc/models/people-ethnicity-2.md) | Query, Optional | Show images with people of the specified ethnicities, or start with NOT to show images without those ethnicities |
| `peopleGender` | [`PeopleGender2`](../../doc/models/people-gender-2.md) | Query, Optional | Show images with people of the specified gender |
| `peopleNumber` | `Integer` | Query, Optional | Show images with the specified number of people<br><br>**Constraints**: `>= 0`, `<= 4` |
| `region` | [`BulkSearchImagesRegion`](../../doc/models/containers/bulk-search-images-region.md) | Query, Optional | This is a container for any-of cases. |
| `safe` | `Boolean` | Query, Optional | Enable or disable safe search<br><br>**Default**: `true` |
| `sort` | [`Sort2`](../../doc/models/sort-2.md) | Query, Optional | Sort by<br><br>**Default**: `Sort2.POPULAR` |
| `spellcheckQuery` | `Boolean` | Query, Optional | Spellcheck the search query and return results on suggested spellings<br><br>**Default**: `true` |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.MINIMAL` |
| `width` | `Integer` | Query, Optional | (Deprecated; use width_from and width_to instead) Show images with the specified width |
| `widthFrom` | `Integer` | Query, Optional | Show images with the specified width or larger, in pixels |
| `widthTo` | `Integer` | Query, Optional | Show images with the specified width or smaller, in pixels |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`BulkImageSearchResults`](../../doc/models/bulk-image-search-results.md).

## Example Usage

```java
List<SearchImage> body = Arrays.asList(
    new SearchImage.Builder()
        .license(Arrays.asList(
            License.EDITORIAL
        ))
        .query("cat")
        .sort(Sort.POPULAR)
        .build(),
    new SearchImage.Builder()
        .orientation(Orientation.HORIZONTAL)
        .query("dog")
        .build()
);


imagesApi.bulkSearchImagesAsync(body, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null, null).thenAccept(result -> {
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
  "results": [
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
              "url": "https://image.shutterstock.com/image-photo/cropped-image-woman-gardening-250nw-1572478477.jpg",
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
    },
    {
      "data": [],
      "page": 1,
      "per_page": 5,
      "search_id": "749090bb-2967-4a20-b22e-c800dc845e11",
      "spellcheck_info": {},
      "total_count": 0
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


# Get Image Suggestions

This endpoint provides autocomplete suggestions for partial search terms.

```java
CompletableFuture<ApiResponse<Suggestions>> getImageSuggestionsAsync(
    final String query,
    final Integer limit)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `query` | `String` | Query, Required | Search term for which you want keyword suggestions |
| `limit` | `Integer` | Query, Optional | Limit the number of suggestions<br><br>**Default**: `10`<br><br>**Constraints**: `>= 1`, `<= 25` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`Suggestions`](../../doc/models/suggestions.md).

## Example Usage

```java
String query = "cats";
Integer limit = 10;

imagesApi.getImageSuggestionsAsync(query, limit).thenAccept(result -> {
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


# Get Image Keyword Suggestions

This endpoint returns up to 10 important keywords from a block of plain text.

```java
CompletableFuture<ApiResponse<SearchEntitiesResponse>> getImageKeywordSuggestionsAsync(
    final SearchEntitiesRequest body)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SearchEntitiesRequest`](../../doc/models/search-entities-request.md) | Body, Required | Plain text to extract keywords from |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`SearchEntitiesResponse`](../../doc/models/search-entities-response.md).

## Example Usage

```java
SearchEntitiesRequest body = new SearchEntitiesRequest.Builder(
    "Planting flowers is a great way to make springtime more beautiful."
)
.build();

imagesApi.getImageKeywordSuggestionsAsync(body).thenAccept(result -> {
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
    "beach",
    "place",
    "sand",
    "ocean"
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Get Image List

This endpoint lists information about one or more images, including the available sizes.

```java
CompletableFuture<ApiResponse<ImageDataList>> getImageListAsync(
    final List<String> id,
    final View2 view,
    final String searchId)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `List<String>` | Query, Required | One or more image IDs<br><br>**Constraints**: *Maximum Items*: `500` |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.MINIMAL` |
| `searchId` | `String` | Query, Optional | The ID of the search that is related to this request |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ImageDataList`](../../doc/models/image-data-list.md).

## Example Usage

```java
List<String> id = Arrays.asList(
    "1110335168",
    "465011609"
);

View2 view = View2.MINIMAL;
String searchId = "00000000-0000-0000-0000-000000000000";

imagesApi.getImageListAsync(id, view, searchId).thenAccept(result -> {
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
          "url": "https://image.shutterstock.com/image-photo/cropped-image-woman-gardening-250nw-1572478477.jpg",
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
  "total_count": 123455
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Get Image

This endpoint shows information about an image, including a URL to a preview image and the sizes that it is available in.

```java
CompletableFuture<ApiResponse<Image>> getImageAsync(
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
| `id` | `String` | Template, Required | Image ID |
| `language` | [`Language`](../../doc/models/language.md) | Query, Optional | Language for the keywords and categories in the response |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.FULL` |
| `searchId` | `String` | Query, Optional | The ID of the search that is related to this request |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`Image`](../../doc/models/image.md).

## Example Usage

```java
String id = "465011609";
Language language = Language.ES;
View2 view = View2.FULL;
String searchId = "00000000-0000-0000-0000-000000000000";

imagesApi.getImageAsync(id, language, view, searchId).thenAccept(result -> {
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
      "url": "https://image.shutterstock.com/image-photo/cropped-image-woman-gardening-250nw-1572478477.jpg",
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
  "media_type": "image",
  "original_filename": "123.jpg"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# List Image Categories

This endpoint lists the categories (Shutterstock-assigned genres) that images can belong to.

```java
CompletableFuture<ApiResponse<CategoryDataList>> listImageCategoriesAsync(
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

imagesApi.listImageCategoriesAsync(language).thenAccept(result -> {
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


# List Similar Images

This endpoint returns images that are visually similar to an image that you specify.

```java
CompletableFuture<ApiResponse<ImageSearchResults>> listSimilarImagesAsync(
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
| `id` | `String` | Template, Required | Image ID<br><br>**Constraints**: *Pattern*: `^([1-9]\d*)\|(U[a-zA-Z0-9]+)$` |
| `language` | [`Language`](../../doc/models/language.md) | Query, Optional | Language for the keywords and categories in the response |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 500` |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.MINIMAL` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ImageSearchResults`](../../doc/models/image-search-results.md).

## Example Usage

```java
String id = "465011609";
Language language = Language.ES;
Integer page = 1;
Integer perPage = 20;
View2 view = View2.MINIMAL;

imagesApi.listSimilarImagesAsync(id, language, page, perPage, view).thenAccept(result -> {
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


# License Images

This endpoint gets licenses for one or more images. You must specify the image IDs in the body parameter and other details like the format, size, and subscription ID either in the query parameter or with each image ID in the body parameter. Values in the body parameter override values in the query parameters. The download links in the response are valid for 8 hours.

```java
CompletableFuture<ApiResponse<LicenseImageResultDataList>> licenseImagesAsync(
    final LicenseImageRequest body,
    final String subscriptionId,
    final Format15 format,
    final Size12 size,
    final String searchId)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`LicenseImageRequest`](../../doc/models/license-image-request.md) | Body, Required | List of images to request licenses for and information about each license transaction; these values override the defaults in the query parameters |
| `subscriptionId` | `String` | Query, Optional | Subscription ID to use to license the image |
| `format` | [`Format15`](../../doc/models/format-15.md) | Query, Optional | (Deprecated) Image format |
| `size` | [`Size12`](../../doc/models/size-12.md) | Query, Optional | Image size<br><br>**Default**: `Size12.HUGE` |
| `searchId` | `String` | Query, Optional | Search ID that was provided in the results of an image search |

## Requires scope

### customer_accessCode

`licenses.create`, `purchases.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`LicenseImageResultDataList`](../../doc/models/license-image-result-data-list.md).

## Example Usage

```java
LicenseImageRequest body = new LicenseImageRequest.Builder(
    Arrays.asList(
        LicenseImageRequestImages.fromLicenseImage(
            new LicenseImage.Builder(
                "123456789"
            )
            .editorialAcknowledgement(true)
            .format(Format7.JPG)
            .metadata(ApiHelper.deserialize("{\"customer_id\":\"12345\",\"geo_location\":\"US\",\"number_viewed\":\"15\",\"search_term\":\"dog\"}"))
            .price(12.34D)
            .showModal(true)
            .size(Size4.SMALL)
            .subscriptionId("s12345678")
            .build()
        )
    )
)
.build();


imagesApi.licenseImagesAsync(body, null, null, null, null).thenAccept(result -> {
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
      "image_id": "59656357",
      "download": {
        "url": "https://download.shutterstock.com/gatekeeper/[random-characters]/shutterstock_59656357.jpg"
      },
      "allotment_charge": 1
    }
  ],
  "page": 1,
  "per_page": 5,
  "total_count": 23
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Get Image License List

This endpoint lists existing licenses.

```java
CompletableFuture<ApiResponse<DownloadHistoryDataList>> getImageLicenseListAsync(
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
| `imageId` | `String` | Query, Optional | Show licenses for the specified image ID<br><br>**Constraints**: *Pattern*: `^[1-9]\d*$` |
| `license` | `String` | Query, Optional | Show images that are available with the specified license, such as `standard` or `enhanced`<br><br>**Constraints**: *Pattern*: `^.+$` |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 200` |
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
String license = "standard";
Integer page = 1;
Integer perPage = 20;
Sort5 sort = Sort5.NEWEST;
String username = "aUniqueUsername";
LocalDateTime startDate = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
LocalDateTime endDate = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
DownloadAvailability downloadAvailability = DownloadAvailability.ALL;
Boolean teamHistory = false;

imagesApi.getImageLicenseListAsync(imageId, license, page, perPage, sort, username, startDate, endDate, downloadAvailability, teamHistory).thenAccept(result -> {
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


# Download Image

This endpoint redownloads images that you have already received a license for. The download links in the response are valid for 8 hours.

```java
CompletableFuture<ApiResponse<Url>> downloadImageAsync(
    final String id,
    final RedownloadImage body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | License ID |
| `body` | [`RedownloadImage`](../../doc/models/redownload-image.md) | Body, Required | Information about the images to redownload |

## Requires scope

### customer_accessCode

`licenses.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`Url`](../../doc/models/url.md).

## Example Usage

```java
String id = "e123";
RedownloadImage body = new RedownloadImage.Builder()
    .size(Size10.SMALL)
    .build();

imagesApi.downloadImageAsync(id, body).thenAccept(result -> {
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
  "url": "https://download.shutterstock.com/gatekeeper/[random-characters]/shutterstock_59656357.jpg"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Get Image Recommendations

This endpoint returns images that customers put in the same collection as the specified image IDs.

```java
CompletableFuture<ApiResponse<RecommendationDataList>> getImageRecommendationsAsync(
    final List<String> id,
    final Integer maxItems,
    final Boolean safe)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `List<String>` | Query, Required | Image IDs |
| `maxItems` | `Integer` | Query, Optional | Maximum number of results returned in the response<br><br>**Default**: `20`<br><br>**Constraints**: `>= 1`, `<= 500` |
| `safe` | `Boolean` | Query, Optional | Restrict results to safe images<br><br>**Default**: `true` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`RecommendationDataList`](../../doc/models/recommendation-data-list.md).

## Example Usage

```java
List<String> id = Arrays.asList(
    "id0"
);

Integer maxItems = 20;
Boolean safe = true;

imagesApi.getImageRecommendationsAsync(id, maxItems, safe).thenAccept(result -> {
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
      "id": "123456789"
    },
    {
      "id": "99379946"
    },
    {
      "id": "133918412"
    }
  ],
  "page": 1,
  "per_page": 5,
  "total_count": 12
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Create Image Collection

This endpoint creates one or more image collections (lightboxes). To add images to the collections, use `POST /v2/images/collections/{id}/items`.

```java
CompletableFuture<ApiResponse<CollectionCreateResponse>> createImageCollectionAsync(
    final CollectionCreateRequest body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CollectionCreateRequest`](../../doc/models/collection-create-request.md) | Body, Required | The names of the new collections |

## Requires scope

### customer_accessCode

`collections.edit`

## Response Type

**201**: Successfully created image collection

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CollectionCreateResponse`](../../doc/models/collection-create-response.md).

## Example Usage

```java
CollectionCreateRequest body = new CollectionCreateRequest.Builder(
    "Test Collection 19cf"
)
.build();

imagesApi.createImageCollectionAsync(body).thenAccept(result -> {
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


# Get Image Collection List

This endpoint lists your collections of images and their basic attributes.

```java
CompletableFuture<ApiResponse<CollectionDataList>> getImageCollectionListAsync(
    final List<Embed> embed,
    final Integer page,
    final Integer perPage)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `embed` | [`List<Embed>`](../../doc/models/embed.md) | Query, Optional | Which sharing information to include in the response, such as a URL to the collection |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `100`<br><br>**Constraints**: `>= 1`, `<= 150` |

## Requires scope

### customer_accessCode

`collections.view`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CollectionDataList`](../../doc/models/collection-data-list.md).

## Example Usage

```java
Integer page = 1;
Integer perPage = 2;

imagesApi.getImageCollectionListAsync(null, page, perPage).thenAccept(result -> {
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


# Get Image Collection

This endpoint gets more detailed information about a collection, including its cover image and timestamps for its creation and most recent update. To get the images in collections, use `GET /v2/images/collections/{id}/items`.

```java
CompletableFuture<ApiResponse<MCollection>> getImageCollectionAsync(
    final String id,
    final List<Embed> embed,
    final String shareCode)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Collection ID |
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
String id = "126351027";

imagesApi.getImageCollectionAsync(id, null, null).thenAccept(result -> {
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


# Rename Image Collection

This endpoint sets a new name for an image collection.

```java
CompletableFuture<ApiResponse<Void>> renameImageCollectionAsync(
    final String id,
    final CollectionUpdateRequest body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Collection ID |
| `body` | [`CollectionUpdateRequest`](../../doc/models/collection-update-request.md) | Body, Required | The new name for the collection |

## Requires scope

### customer_accessCode

`collections.edit`

## Response Type

**204**: Successfully updated collection

`void`

## Example Usage

```java
String id = "126351027";
CollectionUpdateRequest body = new CollectionUpdateRequest.Builder(
    "My collection with a new name"
)
.build();

imagesApi.renameImageCollectionAsync(id, body).thenAccept(result -> {
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


# Delete Image Collection

This endpoint deletes an image collection.

```java
CompletableFuture<ApiResponse<Void>> deleteImageCollectionAsync(
    final String id)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Collection ID |

## Requires scope

### customer_accessCode

`collections.edit`

## Response Type

**204**: Successfully deleted collection

`void`

## Example Usage

```java
String id = "136351027";

imagesApi.deleteImageCollectionAsync(id).thenAccept(result -> {
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


# Add Image Collection Items

This endpoint adds one or more images to a collection by image IDs.

```java
CompletableFuture<ApiResponse<Void>> addImageCollectionItemsAsync(
    final String id,
    final CollectionItemRequest body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Collection ID |
| `body` | [`CollectionItemRequest`](../../doc/models/collection-item-request.md) | Body, Required | Array of image IDs to add to the collection |

## Requires scope

### customer_accessCode

`collections.edit`

## Response Type

**204**: Successfully added collection items

`void`

## Example Usage

```java
String id = "126351027";
CollectionItemRequest body = new CollectionItemRequest.Builder(
    Arrays.asList(
        new CollectionItem.Builder(
            "49572945"
        )
        .build()
    )
)
.build();

imagesApi.addImageCollectionItemsAsync(id, body).thenAccept(result -> {
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


# Get Image Collection Items

This endpoint lists the IDs of images in a collection and the date that each was added.

```java
CompletableFuture<ApiResponse<CollectionItemDataList>> getImageCollectionItemsAsync(
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
String id = "126351027";
Integer page = 1;
Integer perPage = 100;
Sort5 sort = Sort5.OLDEST;

imagesApi.getImageCollectionItemsAsync(id, page, perPage, null, sort).thenAccept(result -> {
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


# Delete Image Collection Items

This endpoint removes one or more images from a collection.

```java
CompletableFuture<ApiResponse<Void>> deleteImageCollectionItemsAsync(
    final String id,
    final List<String> itemId)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Collection ID |
| `itemId` | `List<String>` | Query, Optional | One or more image IDs to remove from the collection |

## Requires scope

### customer_accessCode

`collections.edit`

## Response Type

**204**: Successfully removed collection items

`void`

## Example Usage

```java
String id = "126351027";
imagesApi.deleteImageCollectionItemsAsync(id, null).thenAccept(result -> {
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


# Get Updated Images

This endpoint lists images that have been updated in the specified time period to update content management systems (CMS) or digital asset management (DAM) systems. In most cases, use the `interval` parameter to show images that were updated recently, but you can also use the `start_date` and `end_date` parameters to specify a range of no more than three days. Do not use the `interval` parameter with either `start_date` or `end_date`.

```java
CompletableFuture<ApiResponse<UpdatedMediaDataList>> getUpdatedImagesAsync(
    final List<Type14> type,
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
| `type` | [`List<Type14>`](../../doc/models/type-14.md) | Query, Optional | Show images that were added, deleted, or edited; by default, the endpoint returns images that were updated in any of these ways |
| `startDate` | `String` | Query, Optional | Show images updated on or after the specified date. The API will default to UTC (00:00:00) if no specific time is provided, ensuring consistency. |
| `endDate` | `String` | Query, Optional | Show images updated before the specified date. The API will default to UTC (00:00:00) if no specific time is provided, ensuring consistency. Please note that the end date must be at least 5 minutes after the start date. |
| `interval` | `String` | Query, Optional | Show images updated in the specified time period, where the time period is an interval (like SQL INTERVAL) such as 1 DAY, 6 HOUR, or 30 MINUTE; the default is 1 HOUR, which shows images that were updated in the hour preceding the request<br><br>**Default**: `"1 HOUR"` |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `100`<br><br>**Constraints**: `>= 1`, `<= 2000` |
| `sort` | [`Sort5`](../../doc/models/sort-5.md) | Query, Optional | Sort order<br><br>**Default**: `Sort5.NEWEST` |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UpdatedMediaDataList`](../../doc/models/updated-media-data-list.md).

## Example Usage

```java
String startDate = "2021-03-29T00:00:00Z OR 2021-03-29";
String endDate = "2021-03-29T23:59:59Z OR 2021-03-30";
String interval = "1 HOUR";
Integer page = 1;
Integer perPage = 100;
Sort5 sort = Sort5.NEWEST;

imagesApi.getUpdatedImagesAsync(null, startDate, endDate, interval, page, perPage, sort).thenAccept(result -> {
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

