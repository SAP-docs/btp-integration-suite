<!-- loio5ec68dba721f414ca532fcc62f61706a -->

# Generate OpenAPI Specification with AI Assistance

You can use AI assistance to automatically generate an OpenAPI specification while creating an API artifact. The AI analyzes your API design inputs and helps you quickly create a well-structured specification. This reduces manual effort and maintains consistency with OpenAPI standards.



## Prerequisites

You have activated the AI feature, *OpenAPI Specification Generator* for your SAP Integration Suite tenant. For more information, see [Artificial Intelligence](artificial-intelligence-6a6727c.md).

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

> ### Note:  
> AI features are accessible only with the Premium and Enhanced Editions. These are provided as a free promotion through September 2026 and will be commercialized later as AI features using AI Units. For more information on availability of these AI features across SAP BTP regions, see [3463620](https://me.sap.com/notes/3463620).



## Context

The API Management capability in SAP Integration Suite allows integration developers to generate OpenAPI specifications with *Generative AI*. Integration developers describe the API and provide any requirements. The AI tool then generates the corresponding OpenAPI specification automatically.

> ### Note:  
> The description of the API must be kept within 1500 characters. This is a mandatory requirement to ensure that the AI tool has enough information to generate the OpenAPI specification without being overwhelmed by excessive detail.

While creating an API artifact using the URL, API Specification, and API Provider \(destination flow\) method after entering all the required API details such as name, ID, URL, base path, etc., in the *API Details* dialog, choose *Next* to proceed. On the next page, you can describe your API by defining the CRUD operations it should support and specifying the standard request/response schemas. Once this information is provided, choose *Generate* to create the OpenAPI specification. For more information, see [Create an API Artifact Using a Target URL](https://help.sap.com/docs/integration-suite/sap-integration-suite/create-api-artifact-using-url?version=CLOUD),  <?sap-ot O2O class="- topic/xref " href="39c2b30f5bbc45ca9b3396a188650b7d.xml" text="" desc="" xtrc="xref:3" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiod8a6092f89b24b5e8531d35c034be3aa_en-US/src/content/localization/en-us/5ec68dba721f414ca532fcc62f61706a.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> , and [Create an API Artifact Using a Destination](create-an-api-artifact-using-a-destination-a0bdfd4.md).



## Best Practices

Here are some best practices for generating OpenAPI specifications with AI assistance:

-   **Provide a Clear and Concise API Description**: Start with a clear and concise description of the API you want the AI tool to generate the OpenAPI specification for. This should include the purpose of the API, the main resources and operations it provides, and any relevant domain-specific details.
-   **Identify the Endpoints**: List the various endpoints \(or paths\) that the API supports, along with the HTTP methods \(e.g., GET, POST, PUT, DELETE\) associated with each endpoint. Provide a brief description of the purpose and functionality of each endpoint.
-   **Specify the Request and Response Payloads**: For each endpoint, describe the expected request and response payloads, including the data structures, data types, and any required or optional parameters. Provide sample data or examples to help the AI tool understand the payload structure.

> ### Example:  
> Generate an OpenAPI specification for a Business Partner API that supports CRUD operations to create, read, update, and search business partner data, including fields like name, address, contact details, and identifiers. The API should follow REST best practices with clear request and response schemas, standard HTTP status codes, and structured error messages.

> ### Example:  
> The API is a RESTful web service that provides access to a product catalog. The main resources are 'products', 'categories', and 'reviews'. The API supports the following endpoints:
> 
> -   GET /products: Retrieves a list of all products, with optional filtering and sorting parameters.
> 
> -   GET /products/\{productId\}: Retrieves details of a specific product.
> 
> -   POST /products: Creates a new product.
> 
> -   PUT /products/\{productId\}: Updates an existing product.
> 
> -   DELETE /products/\{productId\}: Deletes a product.
> 
> -   GET /categories: Retrieves a list of all product categories.
> 
> -   GET /reviews: Retrieves a list of all product reviews.
> 
> -   POST /reviews: Creates a new product review.
> 
> 
> The request and response payloads use JSON format. Products have properties like 'name', 'description', 'price', 'category', and 'imageUrl'. Reviews have properties like 'productId', 'rating', 'comment', and 'userId'. There are also some business rules, such as a maximum of 5 reviews per user per product, and a requirement to provide a valid category ID when creating a new product.

