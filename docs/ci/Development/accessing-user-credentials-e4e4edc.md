<!-- loioe4e4edc53bef4208a26f399d3d7ded75 -->

# Accessing User Credentials



## Context

Follow the procedure below to get user credentials in an ADK project.



## Procedure

1.  Download the latest ADK API from the [Adapter Development Kit](https://tools.hana.ondemand.com/#cloudintegration) section.

2.  Add the `com.sap.it.public.generic.api.jar` file to the `resources` folder that is in your ADK project.

3.  Open the `pom.xml` file and add the dependency below:

    > ### Source Code:  
    > ```xml
    > <dependency>
    >  <groupId>com.sap.it.public</groupId>
    >  <artifactId>api</artifactId>
    >  <version>2.8.0</version>
    >  <scope>system</scope>
    >  <systemPath>${project.basedir}/src/main/resources/com.sap.it.public.generic.api-2.8.0.jar</systemPath>
    > </dependency>
    > 
    > ```

4.  Add the `com.sap.it.public` group ID to the `<excludeGroupIds>`.

5.  To import user credentials, use the code below:

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


