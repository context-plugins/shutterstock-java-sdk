
# License Image Request Images

## Class Name

`LicenseImageRequestImages`

## Cases

| Type | Factory Method |
|  --- | --- |
| [`LicenseImage`](../../../doc/models/license-image.md) | LicenseImageRequestImages.fromLicenseImage(LicenseImage licenseImage) |
| [`LicenseImageVector`](../../../doc/models/license-image-vector.md) | LicenseImageRequestImages.fromLicenseImageVector(LicenseImageVector licenseImageVector) |

## LicenseImage

### Initialization Code

#### Example

```java
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
```

## LicenseImageVector

### Initialization Code

#### Example

```java
LicenseImageRequestImages.fromLicenseImageVector(
        new LicenseImageVector.Builder(
            "123456789"
        )
        .editorialAcknowledgement(true)
        .format(Format9.EPS)
        .metadata(ApiHelper.deserialize("{\"customer_id\":\"12345\",\"geo_location\":\"US\",\"number_viewed\":\"15\",\"search_term\":\"dog\"}"))
        .price(12.34D)
        .showModal(true)
        .size(Size6.VECTOR)
        .subscriptionId("s12345678")
        .build()
    )
```

