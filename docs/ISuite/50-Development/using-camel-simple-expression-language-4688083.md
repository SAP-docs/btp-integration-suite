<!-- loio4688083fad6546c1ba25a06d4ffb9fae -->

# Using Camel Simple Expression Language

Cloud Integration supports a subset of the expressions defined in Camel Simple Expression Language \(see [https://camel.apache.org/components/next/languages/simple-language.html](https://camel.apache.org/components/next/languages/simple-language.html) \).

You can use Camel Simple Expression Language when configuring the following components:

**Components that Support Camel Simple Expression Language**


<table>
<tr>
<th valign="top">

Component

</th>
<th valign="top">

Use Camel Simple Expression to ...

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Content modifier

</td>
<td valign="top">

Define:

-   Message body

-   Message header

-   Exchange property


\(*Type* parameter set to *Expression*\)

</td>
<td valign="top">

[Define Content Modifier](define-content-modifier-8f04a70.md) 

</td>
</tr>
<tr>
<td valign="top">

Write variables

</td>
<td valign="top">

Define a variable.

\(*Type* parameter set to *Expression*\)

</td>
<td valign="top">

[Define Write Variables](define-write-variables-de04b75.md) 

</td>
</tr>
<tr>
<td valign="top">

Router

</td>
<td valign="top">

Define a routing condition.

\(*Expression Type* parameter set to *Non-XML*\)

</td>
<td valign="top">

[Define Router](define-router-d7fddbd.md) 

</td>
</tr>
<tr>
<td valign="top">

Content filter

</td>
<td valign="top">

Define conditions for XPath elements.

To review some examples, see [Examples](examples-eb2e601.md).

</td>
<td valign="top">

[Define Filter](define-filter-733f8dc.md) 

</td>
</tr>
</table>



<a name="loio4688083fad6546c1ba25a06d4ffb9fae__section_egf_rnz_qsb"/>

## Expressions Supported by Content Modifier and Write Variables Step

The following table lists the expressions from Camel Simple Expression Language that are supported by the content modifier and write variables step.

****


<table>
<tr>
<th valign="top">

Expression

</th>
<th valign="top">

Description

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

`exchangeId` 

</td>
<td valign="top">

Exchange Id.

</td>
<td valign="top">

`${exchangeId}` 

</td>
</tr>
<tr>
<td valign="top">

`id` 

</td>
<td valign="top">

Message Id

</td>
<td valign="top">

`${id}` 

</td>
</tr>
<tr>
<td valign="top">

`body` 

</td>
<td valign="top">

Incoming message body

</td>
<td valign="top">

`${body}` 

</td>
</tr>
<tr>
<td valign="top">

`in.body` 

</td>
<td valign="top">

Incoming message body

> ### Note:  
> The expression `${in.body}` is deprecated and may stop working in future major releases of Apache Camel.
> 
> We recommend using `${body}` to ensure future compatibility.
> 
> For more information, see [3383659](https://me.sap.com/notes/3383659)



</td>
<td valign="top">

`${in.body}` 

</td>
</tr>
<tr>
<td valign="top">

`bodyAs(<class>` 

</td>
<td valign="top">

Message body converted to compatible class

</td>
<td valign="top">

`${bodyAs(String)}` 

</td>
</tr>
<tr>
<td valign="top">

`mandatoryBodyAs(<class>)` 

</td>
<td valign="top">

Message body is Mandatory converted to compatible class

</td>
<td valign="top">

`${mandatoryBodyAs(String)}` 

</td>
</tr>
<tr>
<td valign="top">

`in.header.fo` 

</td>
<td valign="top">

Refers to foo \(forward declaration\) in header

</td>
<td valign="top">

`${in.header.mandatory.length}` 

</td>
</tr>
<tr>
<td valign="top">

`in.header.foo.OGNL` 

</td>
<td valign="top">

Refers to foo \(forward declaration\) in header with OGNL \(Object-Graph Navigation Language\) expresssion

</td>
<td valign="top">

`${in.header.fname.split(',')[0]}` 

</td>
</tr>
<tr>
<td valign="top">

`headerAs(<key>,<class>` 

</td>
<td valign="top">

Refers to header with name `<key>` converted to compatible class

</td>
<td valign="top">

`${headerAs(name, String)}` 

</td>
</tr>
<tr>
<td valign="top">

`sys.foo` 

</td>
<td valign="top">

Refers to foo \(forward declaration\) in system \(runtime container\)

</td>
<td valign="top">

`${sys.file.separator}` 

</td>
</tr>
<tr>
<td valign="top">

`sysenv.foo` 

</td>
<td valign="top">

Refers to foo \(forward declaration\) in system enviroment

</td>
<td valign="top">

`${sysenv.property1}` 

</td>
</tr>
<tr>
<td valign="top">

`date:<command>:<pattern>` 

</td>
<td valign="top">

Creates date specified in command and uses `SimpleDateFormat` notation

</td>
<td valign="top">

`Processed at ${date:now-2h}`

Othe rexample: To write the current timestamp into a message header, define a header with the following value \(and *Type* set to *Expression*\):

`${date:now:yyyy-MM-dd HH:mm:ss}`

</td>
</tr>
<tr>
<td valign="top">

`date-with-timezone:<command>:<timezone>:<pattern>` 

</td>
<td valign="top">

Same as `date`, but with timezone

</td>
<td valign="top">

`Expires at ${date-with-timezone:now+2h30m:IST:yyyy-MM-dd'T'HH:mm:ss.SSSZ}` 

</td>
</tr>
</table>

> ### Note:  
> The content modifier does not process *Equality or Comparison* expressions.
> 
> Example: The following expression is not supported:
> 
> `${header.branch} == “HR”`

