<!-- loio6de5869b77b0468db601494e75862e04 -->

# Supported Dynamic Expressions for API Artifacts

Only a limited set of Camel expressions is supported across policies and integration steps in API artifacts. This restriction ensures consistent handling of expressions during API artifact execution.



This section lists the supported expressions and highlights certain special expressions that are applicable only to specific policies.

****


<table>
<tr>
<th valign="top">

Type

</th>
<th valign="top">

Details

</th>
<th valign="top">

Valid Expressions

</th>
<th valign="top">

Invalid Expressions

</th>
</tr>
<tr>
<td valign="top">

Body Expression

</td>
<td valign="top">

`${body}` and `${in.body}` are allowed expressions.

> ### Note:  
> Some integration steps, such as the Router step, explicitly disallow the use of `${body}`.

> ### Note:  
> The expression `${in.body}` is deprecated and might stop working in future major releases of Apache Camel. Use `${body}` instead to ensure future compatibility. For more information, see SAP Note [3383659](https://me.sap.com/notes/3383659).



</td>
<td valign="top">

`${body}`

`${in.body}`

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Header Expressions

</td>
<td valign="top">

-   Header expressions are allowed to be used across various integration steps and even adapters.

-   It must be followed by a header key and optionally, a chain of supported functions.

-   The header key can contain alphanumeric characters, hyphens, and underscores only.

-   The header key cannot be another Camel expression.

-   List of supported functions includes:

    -   toUpperCase
    -   toLowerCase
    -   trim
    -   substring
    -   replace
    -   contains
    -   startsWith
    -   endsWith
    -   equals
    -   equalsIgnoreCase
    -   getClientID\(\)


For a detailed list of supported functions, refer to [Supported Functions](supported-dynamic-expressions-for-api-artifacts-6de5869.md#loio6de5869b77b0468db601494e75862e04__section_x2k_5r4_bjc) section below.

</td>
<td valign="top">

```
${header.abc}
${header.client-id}
${header.client-user_key}
${header.client-id.substring(2, 1)}

```

> ### Note:  
> The policy modeller does not allow double opening or closing curly braces \(\{\{ or \}\}\) used as part of any expression, as these are reserved for externalization. If your expression includes such characters, please add a space between them.



</td>
<td valign="top">

```
${header.ab c}
${header.a$bc}
${header.abc.toString()}
${header.abc.substring()}
${header.abc.startsWith(2}}
${header.${header.clientHeader}}
${header.${property.clientHeader}.substring(2, 1)}
```



</td>
</tr>
<tr>
<td valign="top">

Property Expressions

</td>
<td valign="top">

-   Property expressions are allowed to be used across various integration steps and even adapters. The property expressions must either start with `${property.*}` or `${exchangeProperty.*}`

    > ### Note:  
    > Use `${exchangeProperty.*}` instead of `${property.*}`, which might not work with later versions of Apache Camel.

-   It must be followed by a property key and optionally, a chain of supported functions.

-   The property key can contain alphanumeric characters, hyphens, and underscores only

-   The property key cannot be another Camel expression.

-   List of supported functions includes:

    -   toUpperCase
    -   toLowerCase
    -   trim
    -   substring
    -   replace
    -   contains
    -   startsWith
    -   endsWith
    -   equals
    -   equalsIgnoreCase
    -   getClientID\(\)


For a detailed list of supported functions, refer to [Supported Functions](supported-dynamic-expressions-for-api-artifacts-6de5869.md#loio6de5869b77b0468db601494e75862e04__section_x2k_5r4_bjc) section below.

</td>
<td valign="top">

```
${property.abc}
${exchangeProperty.client-id}
${property.client-id}
${property.client-user_key}
${property.client-id.substring(2, 1)}

```



</td>
<td valign="top">

```

${property.ab c}
${property.a$bc}
${property.abc.toString()}
${property.abc.substring()}
${property.abc.startsWith(2}}
${property.${property.clientHeader}}
${property.${header.clientHeader}.substring(2, 1)}
${exchangeProperty.client-id.toStringValue()}
```



</td>
</tr>
<tr>
<td valign="top">

Date Expressions

</td>
<td valign="top">

-   Date expressions are also supported across various integration steps and even adapters.

-   Currently, the **Date-with-timezone** expression is not supported for API artifacts.

-   Currently, we only support the usage of *now* in date commands. *Example*:`${date:now}`

-   Date expressions can have an optional offset

    -   `${date:now+1h-2m+200}`

    -   Allowed offset units include:

        -   Hours: h/hour/hours
        -   Minutes: m/min/minute/minutes

        -   Sseconds: s/sec/second/seconds
        -   Default: if no unit is provided, millisecond value is considered


-   Date expressions have a default pattern, but one can also have an optional pattern:
    -   Default pattern: yyyy-MM-dd HH:mm:ss

    -   Allowed characters include: Hyphen, Dot, Space, Colon only.

    -   Allowed pattern identifiers: For a detailed list of allowed pattern identifiers, refer to [Pattern Identifiers for Date Expressions](supported-dynamic-expressions-for-api-artifacts-6de5869.md#loio6de5869b77b0468db601494e75862e04__section_fg5_xy4_bjc) section below.





</td>
<td valign="top">

```
${date:now}
${date:now:yyyy-MM-dd}
${date:now:HH-mm-ss}
${date:now:yyyy-MM-dd HH:mm:ss}
${date:now+1h:yyyy-MM-dd}
${date:now-30m:yyyy-MM-dd}
${date:now+1h-5m+30s}
${date:now+0h}
${date:now+1hour:yyyy}
${date:now+1hours:yyyy}
${date:now+5min:yyyy}
${date:now+5minute:yyyy}
${date:now+5minutes:yyyy}
${date:now+10sec:yyyy}
${date:now+10second:yyyy}
${date:now+10seconds:yyyy}
${date:now+500}
${date:now:yyyy.MM.dd}
${date:now:HH:mm:ss}
${date:now:yyyy}
${date:now:yy}
${date:now:MM}
${date:now:MMM}
${date:now:MMMM}
${date:now:dd}
${date:now:d}
${date:now:HH}
${date:now:hh}
${date:now:mm}
${date:now:ss}
${date:now:SSS}
${date:now:E}
${date:now:EE}
${date:now:EEE}
${date:now:EEEE}
${date:now:a}
${date:now:hh:mm a}
${date:now:m}
${date:now:s}
${date:now+1h-5m+1000s-900:yyyy-MM-dd}
${date:now:yyyyMMdd HHmmss}
${date:now:yyyy-MM-dd-HH-mm-ss}
${date:now:yyyy.MM.dd.HH.mm.ss}
```



</td>
<td valign="top">

```
${date: now:yyyy}
${date:now :yyyy}
${date:NOW:yyyy}

${date:now+1d:yyyy}
${date:now+1ms:yyyy}
${date:now+1hs:yyyy}

${date:}
${date:invalid}
${date:yesterday}
${date:now:}
${date:now:ZZZZ}
${date:now:yyyy/MM/dd}
${date:now:abc}
${date:now:MMMMM}
${date:now:EEEEE}
${date:now:SS}
${date:now:SSSS}
${date:now+abc:yyyy}
${date:now+:yyyy}
${date:now+1x:yyyy}
```



</td>
</tr>
</table>



<a name="loio6de5869b77b0468db601494e75862e04__section_x2k_5r4_bjc"/>

## Supported Functions

The following table lists the supported functions for header and property expressions:


<table>
<tr>
<th valign="top">

Supported Functions

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

toUpperCase

</td>
<td valign="top">

No argument allowed

</td>
</tr>
<tr>
<td valign="top">

toLowerCase

</td>
<td valign="top">

No argument allowed

</td>
</tr>
<tr>
<td valign="top">

trim

</td>
<td valign="top">

No argument allowed

</td>
</tr>
<tr>
<td valign="top">

substring

</td>
<td valign="top">

-   Minimum number of arguments allowed: 1 argument
-   Maximum number of arguments allowed: 2 arguments
-   Argument type:
    1.  First argument: integer or another valid Camel expression.
    2.  Second argument: integer or another valid Camel expression.




</td>
</tr>
<tr>
<td valign="top">

replace

</td>
<td valign="top">

-   Minimum number of aruguments allowed: 2 arguments
-   Maximum number of arugements allowed: 2 arguments
-   Argument type:
    1.  First argument: string or another valid Camel expression.
    2.  Second argument: string or another valid Camel expression.




</td>
</tr>
<tr>
<td valign="top">

contains

</td>
<td valign="top">

-   Minimum number of arguments allowed: 1 argument
-   Maximum number of arguments allowed: 1 argument
-   Argument type:
    -   First argument: string or another valid Camel expression.




</td>
</tr>
<tr>
<td valign="top">

startsWith

</td>
<td valign="top">

-   Minimum number of arugements allowed: 1 argument
-   Maximum number of arguments allowed: 1 argument
-   Argument type:
    -   First argument: string or another valid Camel expression.




</td>
</tr>
<tr>
<td valign="top">

endsWith

</td>
<td valign="top">

-   Minimum number of arguments allowed: 1 argument
-   Maximum number of arguments allowed: 1 argument
-   Argument type:
    -   First argument: string or another valid Camel expression.




</td>
</tr>
<tr>
<td valign="top">

equalsIgnoreCase

</td>
<td valign="top">

-   Minimum number of arguments allowed: 1 argument
-   Maximum number of arguments allowed: 1 argument
-   Argument type:
    -   First argument: string or another valid Camel expression.




</td>
</tr>
<tr>
<td valign="top">

getClientID\(\)

</td>
<td valign="top">

No argument allowed

</td>
</tr>
</table>



<a name="loio6de5869b77b0468db601494e75862e04__section_fg5_xy4_bjc"/>

## Pattern Identifiers for Date Expressions

The following table lists the allowed pattern identifiers for date expressions:


<table>
<tr>
<th valign="top">

Identifier

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

yyyy

</td>
<td valign="top">

4-digit year

Example: 2026

</td>
</tr>
<tr>
<td valign="top">

yy

</td>
<td valign="top">

2-digit year

Example: 26

</td>
</tr>
<tr>
<td valign="top">

MM

</td>
<td valign="top">

2-digit month

Example: 03, 10

</td>
</tr>
<tr>
<td valign="top">

MMM

</td>
<td valign="top">

3-character month abbreviation

Example: Jan, Feb

</td>
</tr>
<tr>
<td valign="top">

MMMM

</td>
<td valign="top">

Full-length month name

Example: January, March

</td>
</tr>
<tr>
<td valign="top">

d

</td>
<td valign="top">

Day of month \(1-31\)

Example: 1, 24

</td>
</tr>
<tr>
<td valign="top">

dd

</td>
<td valign="top">

Day of month \(01-31\)

Example: 1 or 25

</td>
</tr>
<tr>
<td valign="top">

HH

</td>
<td valign="top">

Hour in 24-hour format \(00-23\)

Example: 01 or 22

</td>
</tr>
<tr>
<td valign="top">

hh

</td>
<td valign="top">

Hour in 12-hour format \(01-12\)

Example: 02 or 10

</td>
</tr>
<tr>
<td valign="top">

m

</td>
<td valign="top">

Single-digit minute \(0-59\)

Example: 1 or 58

</td>
</tr>
<tr>
<td valign="top">

mm

</td>
<td valign="top">

Double-digit minute \(00-59\)

Example: 01 or 58

</td>
</tr>
<tr>
<td valign="top">

s

</td>
<td valign="top">

Single digit second \(0-59\)

Example: 1 or 58

</td>
</tr>
<tr>
<td valign="top">

ss

</td>
<td valign="top">

Double-digit second \(00-59\)

Example: 01 or 58

</td>
</tr>
<tr>
<td valign="top">

SSS

</td>
<td valign="top">

Millisecond in three digits

Example: 120

</td>
</tr>
<tr>
<td valign="top">

E

</td>
<td valign="top">

Day of the month abbreviation

Example: Mon, Tue

</td>
</tr>
<tr>
<td valign="top">

EE

</td>
<td valign="top">

Same as E

</td>
</tr>
<tr>
<td valign="top">

EEE

</td>
<td valign="top">

Same as E

</td>
</tr>
<tr>
<td valign="top">

EEEE

</td>
<td valign="top">

Full day of the month

Example: Monday, Tuesday

</td>
</tr>
<tr>
<td valign="top">

a

</td>
<td valign="top">

AM or PM marker

</td>
</tr>
</table>

> ### Note:  
> Concatenated identifiers are not considered valid. Identifiers are matched greedily, that is, the longest match is applied first. For example, **EEEEE** is an invalid format and will cause an error; however, **EEEE E** \(with a space separator\) is a valid format.



<a name="loio6de5869b77b0468db601494e75862e04__section_zns_vy4_bjc"/>

## Policy-Specific Camel Expression Support

> ### Note:  
> Not all Camel expressions listed above are supported across all fields in policy steps. Each field in a policy supports only a specific set of allowed expressions.

The following table lists the supported expressions for each policy and its relevant fields:


<table>
<tr>
<th valign="top">

Policy

</th>
<th valign="top">

Field

</th>
<th valign="top">

Allowed List

</th>
<th valign="top">

Valid Examples

</th>
<th valign="top">

Invalid Examples

</th>
</tr>
<tr>
<td valign="top">

Quota

</td>
<td valign="top">

Quota identifier

\(or counter key\)

</td>
<td valign="top">

Supported Camel expressions include:

1.  Limited support for header expressions:

    -   Header expression with the header key is supported.

    -   Header key can contain alphanumeric characters, hyphens, or underscores.

    -   No nested expressions are allowed.

    -   No function call is allowed on the header key.


2.  Support for `${context.authn.getClientID()}`

    -   **context:** The root object used to access runtime information available during policy execution, including policy-specific data and, in the future, custom variables.

    -   **authn:** Represents the authentication context of the request. It provides access to details populated by supported authentication mechanisms.

    -   getClientID\(\): A function that retrieves the client ID from the incoming request token when the authentication policy was executed.



> ### Note:  
> For EIC, support for expressions containing `${request.header.<key-name>}` is deprecated and will be discontinued in a future release. API developers must migrate to the current list of allowed expressions.

> ### Note:  
> For EIC, support for simple strings in the quota identifier is deprecated and will be discontinued in a future release. API developers must migrate to the current list of allowed expressions.



</td>
<td valign="top">

-   `${header.abc}`

-   `${header.user_key}`

-   `${context.authn.getClientID()}`




</td>
<td valign="top">

-   `${header.abc.toUpperCase()}`

-   `${property.abc}`

-   `${date:now}`

-   `${request.header.abc} (deprecated)`

-   `'abc' (simple string usage is now deprecated)`

-   `${context.authentication-policy.getClientID()}`




</td>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

ClientID key

</td>
<td valign="top">

Supported Camel expressions include:

-   `${authn.oidc.jwt.<key>}`

-   `${authn.oidc.userinfo.<key>}`


You can use any of the above expressions. The key can contain only alphanumeric characters, hyphens, or underscores. The key cannot be any other expression.

</td>
<td valign="top">

-   `${authn.oidc.jwt.clientid}`

-   `${authn.oidc.userinfo.client_id}`




</td>
<td valign="top">

-   `${header.abc}`

-   `${ authn.oidc.jwt.${header.abc} }`

-   `${authn.${header.oidc}.jwt.clientid}`




</td>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

UserInfo Key

</td>
<td valign="top">

Same as ClientID Key

</td>
<td valign="top">



</td>
<td valign="top">



</td>
</tr>
</table>

> ### Note:  
> The list of supported Camel expressions is subject to change. More expressions may be added for both policy steps and integration steps in future releases. If an expression does not work as expected or is not allowed despite being listed in the above table, raise an incident with SAP Support.

