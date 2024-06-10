<!-- loioe4e4edc53bef4208a26f399d3d7ded75 -->

# Accessing User Credentials



## Context

Follow the procedure below to get user credentials in an ADK project.



## Procedure

1.  Add the `com.sap.it.public` group ID to the `<excludeGroupIds>`.

2.  To import user credentials, use the code below:

    > ### Source Code:  
    > ```java
    > SecureStoreService secureStoreService = ITApiFactory.getService(SecureStoreService.class, null);
    > UserCredential userCredential = secureStoreService.getUserCredential();
    > 
    > /**
    > *Provide an alias name in getUserCredential()
    > */
    > ```

    Add the following import declarations:

    > ### Source Code:  
    > ```java
    > import com.sap.it.api.securestore.SecureStoreService;
    > import com.sap.it.api.securestore.UserCredential;
    > import com.sap.it.api.securestore.exception.SecureStoreException;
    > import com.sap.it.api.ITApiFactory;
    > 
    > ```


