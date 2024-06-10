<!-- loio8518837062c14315a2a6bb281e04fba6 -->

# Accessing Trust and Key Managers



## Context

Follow the procedure below to get trust and key managers in an ADK project.



## Procedure

1.  Add the `com.sap.it.public` group ID to the `<excludeGroupIds>`.

2.  Depending on your requirements, add the code below to either the `*Producer.java` \(receiver adapter\) or `*Consumer.java` \(sender adapter\) file. This allows you to import all the trust managers.

    > ### Source Code:  
    > ```java
    > KeystoreService keyStoreService = ITApiFactory.getService(KeystoreService.class, null);
    > TrustManager[] trustmanager = keyStoreService.getTrustManagers();
    > /**
    > *Provide an alias name in getTrustManagers()
    > */
    > ```

    Add the following import declarations:

    > ### Source Code:  
    > ```java
    > import javax.net.ssl.TrustManager;
    > import com.sap.it.api.ITApiFactory;
    > import com.sap.it.api.exception.InvalidContextException;
    > import com.sap.it.api.keystore.KeystoreService;
    > import com.sap.it.api.keystore.exception.KeystoreException;
    > 
    > ```

3.  To import all the key managers, use the code below:

    > ### Source Code:  
    > ```java
    > KeystoreService keyStoreService = ITApiFactory.getService(KeystoreService.class, null);
    > KeyManager[] keymanagers = keyStoreService.getKeyManagers();
    > /**
    > *Provide an alias name in getKeyManagers()
    > */
    > ```

    Add the following declaration:

    > ### Source Code:  
    > ```java
    > import javax.net.ssl.KeyManager;
    > ```


