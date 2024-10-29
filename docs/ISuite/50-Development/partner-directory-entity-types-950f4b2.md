<!-- loio950f4b2141284de285df414e6ea6009d -->

# Partner Directory Entity Types

Learn more about tha Partner Directory entity types.

Each entry in the Partner Directory is identified by a partner ID *PID* which is unique within the Partner Directory.

The *PID* may consist of alphanumeric characters \(A-Z, a-z, 0-9\), as well as the following special characters: '-', '.', '\_', '~', '<', '\>', and '@'.

The Partner Directory has different entity types. In addition to the *PID*, each entry comes with additional attributes. The set of additional attributes and their meaning depend on the entity type:

****


<table>
<tr>
<th valign="top">

Entity Type

</th>
<th valign="top">

Specific Attributes

</th>
</tr>
<tr>
<td valign="top">

*String Parameters*

Use this entity type to define a user string parameter associated with a partner.

Use this content type if you like to represent the partner by textual data, such as words, sentences, or any other kind of character sequence.

> ### Note:  
> A Partner Directory parameter has a value and a type. The currently supported predefined types are Binary and String.



</td>
<td valign="top">

-   *ID*

    An identifier for the string parameter.

    The ID of this entity may consist of alphanumeric characters \(A-Z, a-z, 0-9\), as well as the following special characters: '-', '.', '\_', '~', '<', '\>', and '@'.

-   *Value*

    The value associated with the string parameter.

    A string parameter has a maximum length of 4000 characters.




</td>
</tr>
<tr>
<td valign="top">

*Binary Parameters*

Use this entity type to define a binary parameter associated with a partner.

Use this content type if you like to represent the partner by binary data, such as files, or any other non-textual data.

A binary parameter has a maximum size of 1,5 MB.

> ### Note:  
> A Partner Directory parameter has a value and a type. The currently supported predefined types are Binary and String.



</td>
<td valign="top">

-   *ID*

    An identifier for the binary parameter.

    The ID of this entity may consist of alphanumeric characters \(A-Z, a-z, 0-9\), as well as the following special characters: '-', '.', '\_', '~', '<', '\>', and '@'.

-   *Value*

    The value \(file\) associated with the binary parameter.

    For this entity type, you can upload a file from your computer.

    The parameter `Value` of this entity can have a maximum length of 262144 bytes.

-   *Content Type*

    Specifies the type of content, for example, xml or json.

    The following content types are supported \(defined by the `ContentType` parameter\): xml, xsl, xsd, json, text, zip, gz \(for GZIP files\), zlib, crt \(for DER encoded X.509 certificates\).

-   *Encoding*

    There are the following options:

    -   *US-ASCII*

    -   *ISO-8859-1*

    -   *UTF-8*

    -   *UTF-16BE*

    -   *UTF-16LE*

    -   *UTF-16*





</td>
</tr>
<tr>
<td valign="top">

*Alternative Partners*

Use this entity type to define an alternative identifier of a partner.

> ### Note:  
> Examples for use cases where an entity can be defined by different identifiers:
> 
> -   A bank can be identified by the German bank code number \(Bankleitzahl or: BLZ\) or the international Bank Identifier Code \(BIC\).
> 
> -   A person can be identified in many different ways, for example, by their customer number at a mail order company, or their name or employee number at their place of work. To able to identify a person uniquely, it isn't sufficient to just know the customer number, for example, you must know that **this** number is a customer number. Only once the frame of reference \(the identification scheme `Customer Number` \) is also known can a person be identified uniquely \(by using the number\). In the example, the agency `Mail Order Company` manages the identification scheme `Customer Number` . Different customers are issued unique names \(customer numbers\) within this scheme.



</td>
<td valign="top">

-   *Agency*

    Abbreviation for the organization that defines the identification scheme and that issues names for the partner to be identified \(maximum length of 120 characters\).

-   *Scheme*

    Reference framework within which partners are uniquely identified by names \(maximum length of 120 characters\).

-   *ID*

    Identifier for the partner \(issued by the agency\) \(maximum length of 225 characters\).

    This is an ID or name that identifies the partner within the given scheme.


> ### Note:  
> Restriction:
> 
> -   The triple `Agency`, `Scheme`, `Id` must be unique.
> 
> -   The triple `Agency`, `Scheme`, `Pid` must be unique \(only then you can look up the alternative partner Id from such a triple\).



</td>
</tr>
<tr>
<td valign="top">

*Authorized Users*

Use this entity type to define a user with which a partner sender system can log in into Cloud Integration.

This entity is required for the authorization of the partner sender system when calling Cloud Integration.

An *Authorized Users* entry provides information on the authorized message sender and the unique Partner ID \(PID\) linked to the partner in the Partner Directory.

</td>
<td valign="top">

*User*

The user authorized to send messages.

</td>
</tr>
</table>

