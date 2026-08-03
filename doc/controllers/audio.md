# Audio

```java
AudioApi audioApi = client.getAudioApi();
```

## Class Name

`AudioApi`

## Methods

* [Search Tracks](../../doc/controllers/audio.md#search-tracks)
* [List Genres](../../doc/controllers/audio.md#list-genres)
* [List Instruments](../../doc/controllers/audio.md#list-instruments)
* [List Moods](../../doc/controllers/audio.md#list-moods)
* [Get Track List](../../doc/controllers/audio.md#get-track-list)
* [Get Track](../../doc/controllers/audio.md#get-track)
* [License Track](../../doc/controllers/audio.md#license-track)
* [Get Track License List](../../doc/controllers/audio.md#get-track-license-list)
* [Download Tracks](../../doc/controllers/audio.md#download-tracks)
* [Create Track Collection](../../doc/controllers/audio.md#create-track-collection)
* [Get Track Collection List](../../doc/controllers/audio.md#get-track-collection-list)
* [Get Track Collection](../../doc/controllers/audio.md#get-track-collection)
* [Rename Track Collection](../../doc/controllers/audio.md#rename-track-collection)
* [Delete Track Collection](../../doc/controllers/audio.md#delete-track-collection)
* [Add Track Collection Items](../../doc/controllers/audio.md#add-track-collection-items)
* [Get Track Collection Items](../../doc/controllers/audio.md#get-track-collection-items)
* [Delete Track Collection Items](../../doc/controllers/audio.md#delete-track-collection-items)


# Search Tracks

This endpoint searches for tracks. If you specify more than one search parameter, the API uses an AND condition. Array parameters can be specified multiple times; in this case, the API uses an AND or an OR condition with those values, depending on the parameter.

```java
CompletableFuture<ApiResponse<AudioSearchResults>> searchTracksAsync(
    final List<String> artists,
    final Integer bpm,
    final Integer bpmFrom,
    final Integer bpmTo,
    final Integer duration,
    final Integer durationFrom,
    final Integer durationTo,
    final List<String> genre,
    final Boolean isInstrumental,
    final List<String> instruments,
    final List<String> moods,
    final Integer page,
    final Integer perPage,
    final String query,
    final Sort12 sort,
    final SortOrder sortOrder,
    final String vocalDescription,
    final View2 view,
    final String fields,
    final Library1 library,
    final String language)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `artists` | `List<String>` | Query, Optional | Show tracks with one of the specified artist names or IDs |
| `bpm` | `Integer` | Query, Optional | (Deprecated; use bpm_from and bpm_to instead) Show tracks with the specified beats per minute |
| `bpmFrom` | `Integer` | Query, Optional | Show tracks with the specified beats per minute or faster |
| `bpmTo` | `Integer` | Query, Optional | Show tracks with the specified beats per minute or slower |
| `duration` | `Integer` | Query, Optional | Show tracks with the specified duration in seconds |
| `durationFrom` | `Integer` | Query, Optional | Show tracks with the specified duration or longer in seconds |
| `durationTo` | `Integer` | Query, Optional | Show tracks with the specified duration or shorter in seconds |
| `genre` | `List<String>` | Query, Optional | Show tracks with each of the specified genres; to get the list of genres, use `GET /v2/audio/genres` |
| `isInstrumental` | `Boolean` | Query, Optional | Show instrumental music only |
| `instruments` | `List<String>` | Query, Optional | Show tracks with each of the specified instruments; to get the list of instruments, use `GET /v2/audio/instruments` |
| `moods` | `List<String>` | Query, Optional | Show tracks with each of the specified moods; to get the list of moods, use `GET /v2/audio/moods` |
| `page` | `Integer` | Query, Optional | Page number<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `perPage` | `Integer` | Query, Optional | Number of results per page<br><br>**Default**: `20`<br><br>**Constraints**: `>= 0`, `<= 500` |
| `query` | `String` | Query, Optional | One or more search terms separated by spaces |
| `sort` | [`Sort12`](../../doc/models/sort-12.md) | Query, Optional | Sort by |
| `sortOrder` | [`SortOrder`](../../doc/models/sort-order.md) | Query, Optional | Sort order<br><br>**Default**: `SortOrder.DESC` |
| `vocalDescription` | `String` | Query, Optional | Show tracks with the specified vocal description (male, female) |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.MINIMAL` |
| `fields` | `String` | Query, Optional | Fields to display in the response; see the documentation for the fields parameter in the overview section |
| `library` | [`Library1`](../../doc/models/library-1.md) | Query, Optional | Which library to search<br><br>**Default**: `Library1.PREMIER` |
| `language` | `String` | Query, Optional | Which language to search in |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AudioSearchResults`](../../doc/models/audio-search-results.md).

## Example Usage

```java
Integer bpmFrom = 80;
Integer bpmTo = 120;
Integer duration = 180;
Integer durationFrom = 30;
Integer durationTo = 180;
List<String> genre = Arrays.asList(
    "Classical",
    "Holiday"
);

Boolean isInstrumental = true;
List<String> instruments = Arrays.asList(
    "Trumpet",
    "Percussion"
);

List<String> moods = Arrays.asList(
    "Confident",
    "Playful"
);

Integer page = 1;
Integer perPage = 1;
String query = "drum";
Sort12 sort = Sort12.SCORE;
SortOrder sortOrder = SortOrder.DESC;
String vocalDescription = "female";
View2 view = View2.FULL;
Library1 library = Library1.PREMIER;

audioApi.searchTracksAsync(null, null, bpmFrom, bpmTo, duration, durationFrom, durationTo, genre, isInstrumental, instruments, moods, page, perPage, query, sort, sortOrder, vocalDescription, view, null, library, null).thenAccept(result -> {
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
      "added_date": "2016-08-16",
      "artists": [
        {
          "name": "Klimenko Music"
        }
      ],
      "assets": {
        "clean_audio": {
          "file_size": 35188408
        },
        "preview_mp3": {
          "file_size": 4400203,
          "url": "https://ak.picdn.net/shutterstock/audio/442583/preview/preview.mp3"
        },
        "preview_ogg": {
          "file_size": 4453197,
          "url": "https://ak.picdn.net/shutterstock/audio/442583/preview/preview.ogg"
        },
        "waveform": {
          "file_size": 18778,
          "url": "https://ak.picdn.net/shutterstock/audio/442583/waveform/waveform.png"
        }
      },
      "bpm": 110,
      "contributor": {
        "id": "2847971"
      },
      "description": "Pulsing and feel-good, featuring soaring synthesizer, groovy synth bass drums and synth drums that create a euphoric, upbeat mood.",
      "duration": 183,
      "genres": [
        "Dance/Electronic",
        "Electro Pop",
        "Pop/Rock"
      ],
      "id": "442583",
      "instruments": [
        "Piano",
        "Synth bass",
        "Synth drums",
        "Synthesizer"
      ],
      "is_adult": false,
      "is_instrumental": true,
      "isrc": "",
      "keywords": [
        "celebratory",
        "chic",
        "euphoric",
        "good times",
        "hip",
        "optimistic",
        "party",
        "soaring",
        "upbeat"
      ],
      "language": "en",
      "lyrics": "",
      "media_type": "audio",
      "moods": [
        "Bright",
        "Confident",
        "Fun",
        "Happy",
        "Inspiring",
        "Optimistic",
        "Playful",
        "Sophisticated",
        "Stylish",
        "Uplifting"
      ],
      "published_time": "2016-08-16T14:30:03-04:00",
      "recording_version": "",
      "releases": [],
      "similar_artists": [],
      "title": "Another Tomorrow",
      "updated_time": "2016-08-18T17:59:33-04:00",
      "vocal_description": "",
      "url": ""
    }
  ],
  "page": 1,
  "per_page": 5,
  "total_count": 123455,
  "search_id": "749090bb-2967-4a20-b22e-c800dc845e10"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# List Genres

This endpoint returns a list of all audio genres.

```java
CompletableFuture<ApiResponse<GenreList>> listGenresAsync(
    final String language)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `language` | `String` | Query, Optional | Which language the genres will be returned |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`GenreList`](../../doc/models/genre-list.md).

## Example Usage

```java
audioApi.listGenresAsync(null).thenAccept(result -> {
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
    "Rock",
    "Pop > Singer-Songwriter",
    "Pop > Synth Pop",
    "Production / Film Scores"
  ]
}
```


# List Instruments

This endpoint returns a list of all audio instruments.

```java
CompletableFuture<ApiResponse<InstrumentList>> listInstrumentsAsync(
    final String language)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `language` | `String` | Query, Optional | Which language the instruments will be returned in |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`InstrumentList`](../../doc/models/instrument-list.md).

## Example Usage

```java
audioApi.listInstrumentsAsync(null).thenAccept(result -> {
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
    "Orchestra",
    "Organ",
    "Oud",
    "Pads",
    "Electric Guitar"
  ]
}
```


# List Moods

This endpoint returns a list of all audio moods.

```java
CompletableFuture<ApiResponse<MoodList>> listMoodsAsync(
    final String language)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `language` | `String` | Query, Optional | Which language the moods will be returned in |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`MoodList`](../../doc/models/mood-list.md).

## Example Usage

```java
audioApi.listMoodsAsync(null).thenAccept(result -> {
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
    "Action / Sports",
    "Adventure / Discovery",
    "Aerobics / Workout",
    "Aggressive"
  ]
}
```


# Get Track List

This endpoint lists information about one or more audio tracks, including the description and publication date.

```java
CompletableFuture<ApiResponse<AudioDataList>> getTrackListAsync(
    final List<String> id,
    final View2 view,
    final String searchId)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `List<String>` | Query, Required | One or more audio IDs<br><br>**Constraints**: *Minimum Items*: `1`, *Maximum Items*: `500`, *Pattern*: `^[1-9]\d*$` |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.MINIMAL` |
| `searchId` | `String` | Query, Optional | The ID of the search that is related to this request |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AudioDataList`](../../doc/models/audio-data-list.md).

## Example Usage

```java
List<String> id = Arrays.asList(
    "442583",
    "434750"
);

View2 view = View2.FULL;
String searchId = "00000000-0000-0000-0000-000000000000";

audioApi.getTrackListAsync(id, view, searchId).thenAccept(result -> {
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
      "added_date": "2016-04-12",
      "artists": [
        {
          "name": "Fin Productions"
        }
      ],
      "assets": {
        "clean_audio": {
          "file_size": 30760372
        },
        "preview_mp3": {
          "file_size": 3846606,
          "url": "https://ak.picdn.net/shutterstock/audio/434750/preview/preview.mp3"
        },
        "preview_ogg": {
          "file_size": 4402608,
          "url": "https://ak.picdn.net/shutterstock/audio/434750/preview/preview.ogg"
        },
        "waveform": {
          "file_size": 19822,
          "url": "https://ak.picdn.net/shutterstock/audio/434750/waveform/waveform.png"
        }
      },
      "bpm": 100,
      "contributor": {
        "id": "2847971"
      },
      "description": "Pulsing and feel-good, featuring slick electric guitar, synthesizer, bass, electronic drum pads and drums that create a positive, celebratory mood.",
      "duration": 160,
      "genres": [
        "Dance/Electronic",
        "Electro Pop",
        "Pop/Rock"
      ],
      "id": "434750",
      "instruments": [
        "Bass",
        "Drums",
        "Electric guitar",
        "Pads",
        "Percussion",
        "Synthesizer"
      ],
      "is_adult": false,
      "is_instrumental": true,
      "isrc": "",
      "keywords": [
        "breezy",
        "celebration",
        "festive",
        "good times",
        "hopeful",
        "optimistic",
        "party",
        "positive",
        "reflective"
      ],
      "language": "en",
      "lyrics": "",
      "media_type": "audio",
      "moods": [
        "Bright",
        "Confident",
        "Fun",
        "Happy",
        "Inspiring",
        "Optimistic",
        "Playful",
        "Sophisticated",
        "Stylish",
        "Uplifting"
      ],
      "published_time": "2016-04-12T17:45:29-04:00",
      "recording_version": "",
      "releases": [],
      "similar_artists": [],
      "title": "Fresh Love",
      "updated_time": "2016-08-18T18:03:11-04:00",
      "vocal_description": ""
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


# Get Track

This endpoint shows information about a track, including its genres, instruments, and other attributes.

```java
CompletableFuture<ApiResponse<Audio>> getTrackAsync(
    final int id,
    final View2 view,
    final String searchId)
```

## Authentication

This endpoint requires [basic](../../doc/auth/basic-authentication.md) **OR** [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `int` | Template, Required | Audio track ID |
| `view` | [`View2`](../../doc/models/view-2.md) | Query, Optional | Amount of detail to render in the response<br><br>**Default**: `View2.FULL` |
| `searchId` | `String` | Query, Optional | The ID of the search that is related to this request |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`Audio`](../../doc/models/audio.md).

## Example Usage

```java
int id = 442583;
View2 view = View2.FULL;
String searchId = "00000000-0000-0000-0000-000000000000";

audioApi.getTrackAsync(id, view, searchId).thenAccept(result -> {
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
  "added_date": "2016-08-16",
  "artists": [
    {
      "name": "Klimenko Music"
    }
  ],
  "assets": {
    "clean_audio": {
      "file_size": 35188408
    },
    "preview_mp3": {
      "file_size": 4400203,
      "url": "https://ak.picdn.net/shutterstock/audio/442583/preview/preview.mp3"
    },
    "preview_ogg": {
      "file_size": 4453197,
      "url": "https://ak.picdn.net/shutterstock/audio/442583/preview/preview.ogg"
    },
    "waveform": {
      "file_size": 18778,
      "url": "https://ak.picdn.net/shutterstock/audio/442583/waveform/waveform.png"
    }
  },
  "bpm": 110,
  "contributor": {
    "id": "2847971"
  },
  "description": "Pulsing and feel-good, featuring soaring synthesizer, groovy synth bass drums and synth drums that create a euphoric, upbeat mood.",
  "duration": 183,
  "genres": [
    "Dance/Electronic",
    "Electro Pop",
    "Pop/Rock"
  ],
  "id": "442583",
  "instruments": [
    "Piano",
    "Synth bass",
    "Synth drums",
    "Synthesizer"
  ],
  "is_adult": false,
  "is_instrumental": true,
  "isrc": "",
  "keywords": [
    "celebratory",
    "chic",
    "euphoric",
    "good times",
    "hip",
    "optimistic",
    "party",
    "soaring",
    "upbeat"
  ],
  "language": "en",
  "lyrics": "",
  "media_type": "audio",
  "moods": [
    "Bright",
    "Confident",
    "Fun",
    "Happy",
    "Inspiring",
    "Optimistic",
    "Playful",
    "Sophisticated",
    "Stylish",
    "Uplifting"
  ],
  "published_time": "2016-08-16T14:30:03-04:00",
  "recording_version": "",
  "releases": [],
  "similar_artists": [],
  "title": "Another Tomorrow",
  "updated_time": "2016-08-18T17:59:33-04:00",
  "vocal_description": "",
  "url": ""
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# License Track

This endpoint gets licenses for one or more tracks. The download links in the response are valid for 8 hours.

```java
CompletableFuture<ApiResponse<LicenseAudioResultDataList>> licenseTrackAsync(
    final LicenseAudioRequest body,
    final License10 license,
    final String searchId)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`LicenseAudioRequest`](../../doc/models/license-audio-request.md) | Body, Required | Tracks to license |
| `license` | [`License10`](../../doc/models/license-10.md) | Query, Optional | License type |
| `searchId` | `String` | Query, Optional | The ID of the search that led to licensing this track |

## Requires scope

### customer_accessCode

`licenses.create`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`LicenseAudioResultDataList`](../../doc/models/license-audio-result-data-list.md).

## Example Usage

```java
LicenseAudioRequest body = new LicenseAudioRequest.Builder(
    Arrays.asList(
        new LicenseAudio.Builder(
            "591623"
        )
        .license(License1.AUDIO_PLATFORM)
        .additionalProperty("metadata", ApiHelper.deserialize("{\"customer_id\":\"12345\"}"))
        .build()
    )
)
.build();


audioApi.licenseTrackAsync(body, null, null).thenAccept(result -> {
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
      "audio_id": "123456789",
      "download": {
        "url": "http://download2.dev.shutterstock.com/gatekeeper/abc/original.wav"
      },
      "license_id": "abcdef123456789ghijklmn",
      "allotment_charge": 1
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


# Get Track License List

This endpoint lists existing licenses. You can filter the results according to the track ID to see if you have an existing license for a specific track.

```java
CompletableFuture<ApiResponse<DownloadHistoryDataList>> getTrackLicenseListAsync(
    final String audioId,
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
| `audioId` | `String` | Query, Optional | Show licenses for the specified track ID |
| `license` | `String` | Query, Optional | Restrict results by license. |
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
String audioId = "1";
String license = "48433107";
Integer page = 1;
Integer perPage = 20;
Sort5 sort = Sort5.NEWEST;
String username = "aUniqueUsername";
LocalDateTime startDate = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
LocalDateTime endDate = DateTimeHelper.fromRfc8601DateTime("03/29/2021 13:25:13");
DownloadAvailability downloadAvailability = DownloadAvailability.ALL;
Boolean teamHistory = false;

audioApi.getTrackLicenseListAsync(audioId, license, page, perPage, sort, username, startDate, endDate, downloadAvailability, teamHistory).thenAccept(result -> {
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
      "id": "a10b7a7a5a02113a928f13e5ba196151d6",
      "user": {
        "username": "jsmith"
      },
      "license": "premier_music_extended",
      "download_time": "2020-11-11T16:15:20.000Z",
      "metadata": {
        "purchase_order": "123"
      },
      "is_downloadable": true,
      "audio": {
        "id": "420298",
        "format": {
          "size": "clean_audio"
        }
      }
    }
  ],
  "page": 1,
  "per_page": 20,
  "total_count": 1
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Download Tracks

This endpoint redownloads tracks that you have already received a license for. The download links in the response are valid for 8 hours.

```java
CompletableFuture<ApiResponse<AudioUrl>> downloadTracksAsync(
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

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AudioUrl`](../../doc/models/audio-url.md).

## Example Usage

```java
String id = "e123";

audioApi.downloadTracksAsync(id).thenAccept(result -> {
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
  "url": "http://download2.dev.shutterstock.com/gatekeeper/abc/original.wav",
  "shorts_loops_stems": "http://download2.dev.shutterstock.com/gatekeeper/abc/original.zip"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | `ApiException` |
| 401 | Unauthorized | `ApiException` |
| 403 | Forbidden | `ApiException` |


# Create Track Collection

This endpoint creates one or more collections (soundboxes). To add tracks, use `POST /v2/audio/collections/{id}/items`.

```java
CompletableFuture<ApiResponse<CollectionCreateResponse>> createTrackCollectionAsync(
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

**201**: Successfully created audio collection

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`CollectionCreateResponse`](../../doc/models/collection-create-response.md).

## Example Usage

```java
CollectionCreateRequest body = new CollectionCreateRequest.Builder(
    "Best rock music"
)
.build();

audioApi.createTrackCollectionAsync(body).thenAccept(result -> {
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


# Get Track Collection List

This endpoint lists your collections of audio tracks and their basic attributes.

```java
CompletableFuture<ApiResponse<CollectionDataList>> getTrackCollectionListAsync(
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
audioApi.getTrackCollectionListAsync(page, perPage, null).thenAccept(result -> {
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


# Get Track Collection

This endpoint gets more detailed information about a collection, including the number of items in it and when it was last updated. To get the tracks in collections, use `GET /v2/audio/collections/{id}/items`.

```java
CompletableFuture<ApiResponse<MCollection>> getTrackCollectionAsync(
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
String id = "48433107";

audioApi.getTrackCollectionAsync(id, null, null).thenAccept(result -> {
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


# Rename Track Collection

This endpoint sets a new name for a collection.

```java
CompletableFuture<ApiResponse<Void>> renameTrackCollectionAsync(
    final String id,
    final CollectionUpdateRequest body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Collection ID |
| `body` | [`CollectionUpdateRequest`](../../doc/models/collection-update-request.md) | Body, Required | Collection changes |

## Requires scope

### customer_accessCode

`collections.edit`

## Response Type

**204**: Successfully updated collection

`void`

## Example Usage

```java
String id = "48433107";
CollectionUpdateRequest body = new CollectionUpdateRequest.Builder(
    "Best rock music"
)
.build();

audioApi.renameTrackCollectionAsync(id, body).thenAccept(result -> {
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


# Delete Track Collection

This endpoint deletes a collection.

```java
CompletableFuture<ApiResponse<Void>> deleteTrackCollectionAsync(
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
String id = "48433111";

audioApi.deleteTrackCollectionAsync(id).thenAccept(result -> {
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


# Add Track Collection Items

This endpoint adds one or more tracks to a collection by track IDs.

```java
CompletableFuture<ApiResponse<Void>> addTrackCollectionItemsAsync(
    final String id,
    final CollectionItemRequest body)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Collection ID |
| `body` | [`CollectionItemRequest`](../../doc/models/collection-item-request.md) | Body, Required | List of items to add to collection |

## Requires scope

### customer_accessCode

`collections.edit`

## Response Type

**204**: Successfully added collection items

`void`

## Example Usage

```java
String id = "48433115";
CollectionItemRequest body = new CollectionItemRequest.Builder(
    Arrays.asList(
        new CollectionItem.Builder(
            "442583"
        )
        .build(),
        new CollectionItem.Builder(
            "7491192"
        )
        .build()
    )
)
.build();

audioApi.addTrackCollectionItemsAsync(id, body).thenAccept(result -> {
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


# Get Track Collection Items

This endpoint lists the IDs of tracks in a collection and the date that each was added.

```java
CompletableFuture<ApiResponse<CollectionItemDataList>> getTrackCollectionItemsAsync(
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

audioApi.getTrackCollectionItemsAsync(id, page, perPage, null, sort).thenAccept(result -> {
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
      "id": "76688182",
      "media_type": "audio",
      "added_time": "2016-08-18T18:52:59-04:00"
    },
    {
      "id": "40005859",
      "media_type": "audio",
      "added_time": "2016-08-18T18:52:59-04:00"
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
| 404 | Collection not found | `ApiException` |


# Delete Track Collection Items

This endpoint removes one or more tracks from a collection.

```java
CompletableFuture<ApiResponse<Void>> deleteTrackCollectionItemsAsync(
    final String id,
    final List<String> itemId)
```

## Authentication

This endpoint requires [customer_accessCode](../../doc/auth/oauth-2-authorization-code-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `String` | Template, Required | Collection ID |
| `itemId` | `List<String>` | Query, Optional | One or more item IDs to remove from the collection |

## Requires scope

### customer_accessCode

`collections.edit`

## Response Type

**204**: Successfully removed collection items

`void`

## Example Usage

```java
String id = "48433119";
List<String> itemId = Arrays.asList(
    "76688182",
    "40005859"
);

audioApi.deleteTrackCollectionItemsAsync(id, itemId).thenAccept(result -> {
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

