<!-- loioc16258e9957b42cda929076f888b3bfd -->

# Key Characteristics

Key characteristics are criteria that help enterprise architects and integration architects to map integration styles to relevant capabilities of integration technologies.

Integration Assessment comes with the following key characteristic groups:

****


<table>
<tr>
<th valign="top">

Key Characteristic Group

</th>
<th valign="top">

Key Characteristic Examples

</th>
</tr>
<tr>
<td valign="top">

Connectivity

Contains criteria important to implement connections between the systems of the enterprise landscape.

</td>
<td valign="top">

-   Connectors

    Provide connectivity with remote systems such as business applications or data sources.

-   Protocol conversion

    Converts the protocol of the source system to a protocol supported by the target system to achieve interoperability.




</td>
</tr>
<tr>
<td valign="top">

Integration use cases

Contains patterns, or reusable solutions for recurring integration problems, for the data integration and process integration style.

</td>
<td valign="top">

Patterns relevant for the data integration style: Common use case patterns \(including relevant cross use cases\) for data integration.

</td>
</tr>
<tr>
<td valign="top">

Metadata management

</td>
<td valign="top">

Data Cataloging: Allows you to discover, classify, and profile data to be stored in one central data catalog.

</td>
</tr>
<tr>
<td valign="top">

Monitoring and operations

</td>
<td valign="top">

Business-oriented monitoring: Allows business users to monitor the execution status \(including errors\) of integration scenarios.

</td>
</tr>
<tr>
<td valign="top">

Transformations

</td>
<td valign="top">

Data transformation: Level of data structure transformation \(such as mappings\) and/or data translation that is required for the receiving system to consume the data.

</td>
</tr>
</table>

When assessing your integration strategy, you analyze which integration technology is possible or supported for dedicated key characteristics relevant for your organization.

Integration Assessment uses key characteristics as a basis for questionnaires that guide you through the interface request process \(during the requirement analysis phase\).

There are two different key characteristic types:

-   *Multi*

    The associated question can have multiple answers.

-   *Single*

    You can answer the associated question only with *Yes* or *No*.


> ### Example:  
> The predefined *Connectors* key characteristic has the type *Multi*.
> 
> The associated question is:
> 
> *Which type of connectors does your integration scenario require to integrate with remote systems \(such as business applications, data sources, trading partners\)?*
> 
> It can have the following answers:
> 
> -   *Technology Connectors*
> -   *Application Connectors*
> 
> The predefined *Business-Oriented Monitoring* key characteristic has the type *Single*.
> 
> You can answer it only with **Yes** or **No** .
> 
> The associated question is:
> 
> *Do you also want business users to monitor your integration scenario at runtime?*

See: [Questionnaires](questionnaires-da3f7d8.md)

