
# Redownload Video

Data required to redownload a video

*This model accepts additional fields of type Object.*

## Structure

`RedownloadVideo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AuthCookie` | [`AuthCookie6`](../../doc/models/auth-cookie-6.md) | Optional | (Deprecated) | AuthCookie6 getAuthCookie() | setAuthCookie(AuthCookie6 authCookie) |
| `ShowModal` | `Boolean` | Optional | (Deprecated) | Boolean getShowModal() | setShowModal(Boolean showModal) |
| `Size` | [`Size11`](../../doc/models/size-11.md) | Optional | Size of the video | Size11 getSize() | setSize(Size11 size) |
| `VerificationCode` | `String` | Optional | (Deprecated) | String getVerificationCode() | setVerificationCode(String verificationCode) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.RedownloadVideo;
import com.shutterstock.api.models.Size11;
import java.io.IOException;

RedownloadVideo redownloadVideo = new RedownloadVideo.Builder()
    .authCookie(null)
    .showModal(false)
    .size(Size11.WEB)
    .verificationCode("verification_code0")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

