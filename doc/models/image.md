
# Image

Information about an image

*This model accepts additional fields of type Object.*

## Structure

`Image`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AddedDate` | `LocalDate` | Optional | Date that the image was added by the contributor | LocalDate getAddedDate() | setAddedDate(LocalDate addedDate) |
| `AffiliateUrl` | `String` | Optional | Affiliate referral link; appears only for registered affiliate partners | String getAffiliateUrl() | setAffiliateUrl(String affiliateUrl) |
| `Aspect` | `Double` | Optional | Aspect ratio of the image in decimal format, such as 0.6667 | Double getAspect() | setAspect(Double aspect) |
| `Assets` | [`Assets3`](../../doc/models/assets-3.md) | Optional | Image asset information | Assets3 getAssets() | setAssets(Assets3 assets) |
| `Categories` | [`List<Category>`](../../doc/models/category.md) | Optional | Categories that this image is a part of | List<Category> getCategories() | setCategories(List<Category> categories) |
| `Contributor` | [`Contributor`](../../doc/models/contributor.md) | Required | Information about a contributor | Contributor getContributor() | setContributor(Contributor contributor) |
| `Description` | `String` | Optional | Detailed description of the image | String getDescription() | setDescription(String description) |
| `HasModelRelease` | `Boolean` | Optional | Indicates whether there are model releases for the image | Boolean getHasModelRelease() | setHasModelRelease(Boolean hasModelRelease) |
| `HasPropertyRelease` | `Boolean` | Optional | Indicates whether there are property releases for the image | Boolean getHasPropertyRelease() | setHasPropertyRelease(Boolean hasPropertyRelease) |
| `Id` | `String` | Required | Image ID | String getId() | setId(String id) |
| `ImageType` | `String` | Optional | Type of image | String getImageType() | setImageType(String imageType) |
| `IsAdult` | `Boolean` | Optional | Whether or not this image contains adult content | Boolean getIsAdult() | setIsAdult(Boolean isAdult) |
| `IsEditorial` | `Boolean` | Optional | Whether or not this image is editorial content | Boolean getIsEditorial() | setIsEditorial(Boolean isEditorial) |
| `IsIllustration` | `Boolean` | Optional | Whether or not this image is an illustration | Boolean getIsIllustration() | setIsIllustration(Boolean isIllustration) |
| `Keywords` | `List<String>` | Optional | Keywords associated with the content of this image | List<String> getKeywords() | setKeywords(List<String> keywords) |
| `MediaType` | `String` | Required | Media type of this image, should always be "image" | String getMediaType() | setMediaType(String mediaType) |
| `ModelReleases` | [`List<ModelRelease>`](../../doc/models/model-release.md) | Optional | List of model releases | List<ModelRelease> getModelReleases() | setModelReleases(List<ModelRelease> modelReleases) |
| `Models` | [`List<Model>`](../../doc/models/model.md) | Optional | List of models | List<Model> getModels() | setModels(List<Model> models) |
| `Releases` | `List<String>` | Optional | List of all releases of this image | List<String> getReleases() | setReleases(List<String> releases) |
| `Url` | `String` | Optional | Link to image information page; included only for certain accounts | String getUrl() | setUrl(String url) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.DateTimeHelper;
import com.shutterstock.api.models.Assets3;
import com.shutterstock.api.models.Category;
import com.shutterstock.api.models.Contributor;
import com.shutterstock.api.models.Image;
import com.shutterstock.api.models.Thumbnail;
import java.io.IOException;
import java.util.Arrays;

Image image = new Image.Builder(
    new Contributor.Builder(
        "250738318"
    )
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build(),
    "1572478477",
    "image"
)
.addedDate(DateTimeHelper.fromSimpleDate("2016-03-13"))
.affiliateUrl("affiliate_url2")
.aspect(1.5D)
.assets(new Assets3.Builder()
        .hugeJpg(null)
        .hugeThumb(new Thumbnail.Builder(
            260,
            "https://image.shutterstock.com/image-photo/cropped-image-woman-gardening-260nw-1572478477.jpg",
            390
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
        .largeThumb(new Thumbnail.Builder(
            100,
            "https://thumb7.shutterstock.com/thumb_large/250738318/1572478477/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
            150
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
        .mediumJpg(null)
        .preview(new Thumbnail.Builder(
            300,
            "https://image.shutterstock.com/display_pic_with_logo/250738318/1572478477/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
            450
        )
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
        .preview1000(new Thumbnail.Builder(
            667,
            "https://ak.picdn.net/shutterstock/photos/1572478477/watermark_1000/1706028c641ea2f443057287c67d9b91/preview_1000-1572478477.jpg",
            1000
        )
        .build())
        .preview1500(new Thumbnail.Builder(
            1000,
            "https://image.shutterstock.com/z/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
            1500
        )
        .build())
        .smallThumb(new Thumbnail.Builder(
            67,
            "https://thumb7.shutterstock.com/thumb_small/250738318/1572478477/stock-photo-cropped-image-of-woman-gardening-1572478477.jpg",
            100
        )
        .build())
        .mosaic(new Thumbnail.Builder(
            167,
            "https://image.shutterstock.com/image-photo/cropped-image-woman-gardening-250nw-1572478477.jpg",
            250
        )
        .build())
    .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
        .build())
.categories(Arrays.asList(
        new Category.Builder()
            .id("id8")
            .name("name8")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
        new Category.Builder()
            .id("id8")
            .name("name8")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build(),
        new Category.Builder()
            .id("id8")
            .name("name8")
        .additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
            .build()
    ))
.description("cropped image of woman gardening")
.hasModelRelease(true)
.imageType("photo")
.additionalProperty("original_filename", ApiHelper.deserialize("\"123.jpg\""))
.build();
```

