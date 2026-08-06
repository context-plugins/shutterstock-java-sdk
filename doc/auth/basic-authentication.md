
# Basic Authentication



Documentation for accessing and setting credentials for basic.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| Username | `String` | The username to use with basic authentication | `username` | `getUsername()` |
| Password | `String` | The password to use with basic authentication | `password` | `getPassword()` |



**Note:** Auth credentials can be set using `basicCredentials` in the client builder and accessed through `getBasicCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```java
import com.shutterstock.api.ShutterstockClient;
import com.shutterstock.api.authentication.BasicModel;

public class Program {
    public static void main(String[] args) {
        ShutterstockClient client = new ShutterstockClient.Builder()
            .basicCredentials(new BasicModel.Builder(
                    "Username",
                    "Password"
                )
                .build())
            .build();
    }
}
```


