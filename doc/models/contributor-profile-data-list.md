
# Contributor Profile Data List

List of contributor profiles

*This model accepts additional fields of type Object.*

## Structure

`ContributorProfileDataList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Data` | [`List<ContributorProfile>`](../../doc/models/contributor-profile.md) | Optional | Conributor profiles | List<ContributorProfile> getData() | setData(List<ContributorProfile> data) |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | Error list; appears only if there was an error | List<Error> getErrors() | setErrors(List<Error> errors) |
| `Message` | `String` | Optional | Error message | String getMessage() | setMessage(String message) |
| `Page` | `Integer` | Optional | Page of response | Integer getPage() | setPage(Integer page) |
| `PerPage` | `Integer` | Optional | Number of contributors per page | Integer getPerPage() | setPerPage(Integer perPage) |
| `TotalCount` | `Integer` | Optional | Total count of contributors for this request | Integer getTotalCount() | setTotalCount(Integer totalCount) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.ContributorProfile;
import com.shutterstock.api.models.ContributorProfileDataList;
import com.shutterstock.api.models.ContributorProfileSocialMedia;
import com.shutterstock.api.models.Error;
import java.io.IOException;
import java.util.Arrays;

ContributorProfileDataList contributorProfileDataList = new ContributorProfileDataList.Builder()
    .data(Arrays.asList(
        new ContributorProfile.Builder(
            "12345678"
        )
        .about("John Doe's photographs")
        .contributorType(Arrays.asList(
                "photographer"
            ))
        .displayName("John Doe")
        .equipment(Arrays.asList(
                "Nikon",
                "Fuji"
            ))
        .location("US")
        .portfolioUrl("https://www.shutterstock.com/g/jdoe")
        .socialMedia(new ContributorProfileSocialMedia.Builder()
                .facebook("http://example.com/jdoe")
                .googlePlus("http://example.com/jdoe")
                .linkedin("http://example.com/jdoe")
                .pinterest("http://example.com/jdoe")
                .tumblr("http://example.com/jdoe")
                .twitter("http://example.com/jdoe")
                .build())
        .styles(Arrays.asList(
                "landscape",
                "nature",
                "footage_travel"
            ))
        .subjects(Arrays.asList(
                "animals",
                "landmarks",
                "nature",
                "objects",
                "recreation"
            ))
        .website("http://example.com/profiles/jdoe")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ))
    .errors(Arrays.asList(
        new Error.Builder(
            "message0"
        )
        .code("code8")
        .data("data0")
        .items(Arrays.asList(
                ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}")
            ))
        .path("path4")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build(),
        new Error.Builder(
            "message0"
        )
        .code("code8")
        .data("data0")
        .items(Arrays.asList(
                ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}")
            ))
        .path("path4")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build()
    ))
    .message("message4")
    .page(1)
    .perPage(5)
    .totalCount(15)
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

