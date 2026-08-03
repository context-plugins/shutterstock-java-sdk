
# Redownload Image

Data required to redownload an image

*This model accepts additional fields of type Object.*

## Structure

`RedownloadImage`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AuthCookie` | [`AuthCookie6`](../../doc/models/auth-cookie-6.md) | Optional | (Deprecated) | AuthCookie6 getAuthCookie() | setAuthCookie(AuthCookie6 authCookie) |
| `ShowModal` | `Boolean` | Optional | (Deprecated) | Boolean getShowModal() | setShowModal(Boolean showModal) |
| `Size` | [`Size10`](../../doc/models/size-10.md) | Optional | Size of the image | Size10 getSize() | setSize(Size10 size) |
| `VerificationCode` | `String` | Optional | (Deprecated) | String getVerificationCode() | setVerificationCode(String verificationCode) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example

```java
import com.shutterstock.api.ApiHelper;
import com.shutterstock.api.models.RedownloadImage;
import com.shutterstock.api.models.Size10;
import java.io.IOException;

RedownloadImage redownloadImage = new RedownloadImage.Builder()
    .authCookie(null)
    .showModal(false)
    .size(Size10.SMALL)
    .verificationCode("verification_code4")
.additionalProperty("exampleAdditionalProperty", ApiHelper.deserialize("{\"key1\":\"val1\",\"key2\":\"val2\"}"))
    .build();
```

