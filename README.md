Divide.io Server Sample
====================
Built on Jersey, it can be deployed to any J2EE server that supports javax.ws.rs.core.Application. DAO implementations are independent and can be written/plugged in for the situation.

### Getting Started
[Deploy on App Engine](https://github.com/HiddenStage/divide-docs/blob/master/getting-started/getting_started_app_engine.md)

AWS and more server examples coming soon!

### Basic Usage
```java
public class SomeApplication extends AuthApplication<OrientDBDao> {

    private String encryptionKey = "someKeyForSynchronousEncryption";

    public SomeApplication() {
    	// dao class
        super(OrientDBDao.class, encryptionKey);
    }
    
    public SomeApplication() {
        // dao instance
        super(new OrientDBDao(), encryptionKey);
    }
}
```
**Be sure to change the encryption key before using in production!** We recommend using a random password generator.
