<!-- loio3c6458c09a844cd59b64d39c7e3c631b -->

# Enabling Authentication for Servlet Based Adapters



## Context

Both Basic and Certificate based authentication can be enabled by performing the steps described here:



<a name="loio3c6458c09a844cd59b64d39c7e3c631b__steps_k3n_14r_52b"/>

## Procedure

1.  Open the `web.xml` file and add the filter definition given below:

    > ### Source Code:  
    > ```xml
    > <filter>
    >     <filter-name>ADKAuthenticationFilter</filter-name>
    >     <filter-class>com.sap.it.api.asdk.cloud.authentication.ADKAuthenticationFilter</filter-class>
    > </filter>
    > <filter-mapping>
    >     <filter-name>ADKAuthenticationFilter</filter-name>
    >     <url-pattern>/*</url-pattern>
    > </filter-mapping>
    > ```

2.  Open the `pom.xml` file and include the below import package instruction in the maven-bundle-plugin:

    > ### Source Code:  
    > ```xml
    > <Import-Package>com.sap.it.api.asdk.cloud.authentication,*</Import-Package>
    > ```

3.  Save the changes.




<a name="loio3c6458c09a844cd59b64d39c7e3c631b__result_zdn_ypr_52b"/>

## Results

Now you can connect to the adapter's endpoint either using Basic or Certificate based authentication.

