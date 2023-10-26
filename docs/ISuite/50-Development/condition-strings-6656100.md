<!-- loio66561009a5b343658be2408981d005bb -->

# Condition Strings

Conditions enable API proxies to behave dynamically at runtime.

Conditions define operations on variables. Conditional statements are boolean and always evaluate to true or false. Developers commonly use both built-in flow variables and custom variables in conditional statements. The basic structure of a conditional statement is: `<Condition>{variable.name}{operator}{"value"}</Condition>`. In API Management, every API resource is treated as conditional flow. So for every resource, you can already see a condition defined in the policy designer.

Conditions can be chained. For example, the following condition evaluates to true only if the URI of the request matches `/statuses/user_timeline.json` and the HTTP verb of the request is GET.



## Example

`<Condition>(proxy.pathsuffix MatchesPath "/statuses/**") and (request.verb = "GET")</Condition>`



## Usage of Conditions

You can use conditions to control the following behavior in API Management:

1.  Policy execution
2.  Flow execution
3.  Target endpoint route rule execution



### Policy Execution

Using conditional statements, you can control the enforcement of policies. A common use case is conditional transformation of request/response messages, based on HTTP header or message content. For example, if you want to execute a key value map policy whenever the request has a query parameter called "country", you will attach the key value map policy to the required flow. To apply condition on this policy, you can add the following condition string in the Policy editor in the *Condition string* field:`request.queryparam.country IsNot null`



### Flow execution

Using conditional statements, you can control the execution of named flows in ProxyEndpoints and TargetEndpoints. Note that only 'named' flows can be executed conditionally. Preflows and postflows \(both request and response\) on ProxyEndpoints and TargetEndpoints execute for every transaction, and thus provide unconditional 'failsafe' capabilities.



### Target endpoint route rule execution

Using conditional statements, you can control the target endpoint launched by proxy endpoint configuration. A route rule forwards a request to a particular target endpoint. When more than one target endpoint is available, the route rule is evaluated for its condition. If it is true, the request is forwarded to the named target endpoint. For example, if you want to restrict the service access to specific country, then you can add a route rule which has NONE as the target endpoint and the following condition string: `request.queryparam.country = "IN" Or request.queryparam.country = "DE"`.

For more information on how to define multiple target endpoints using Route Rule, see [Enable Dynamic Routing](enable-dynamic-routing-49cbe91.md).



## Path Expressions

Path expressions are used for matching URI paths, using "\*" to represent a single path element and "\*\*" to represent multiple URI levels. For example:


<table>
<tr>
<th valign="top">

Pattern

</th>
<th valign="top">

Sample URI paths matched

</th>
</tr>
<tr>
<td valign="top">

/\*/a/

</td>
<td valign="top">

/x/a/ or /y/a/

</td>
</tr>
<tr>
<td valign="top">

/\*/a/\*

</td>
<td valign="top">

/x/a/b or /y/a/foo

</td>
</tr>
<tr>
<td valign="top">

/\*/a/\*\*

</td>
<td valign="top">

/x/a/b/c/d

</td>
</tr>
<tr>
<td valign="top">

/\*/a/\*/feed/

</td>
<td valign="top">

/x/a/b/feed/ or /y/a/foo/feed/

</td>
</tr>
<tr>
<td valign="top">

/a/\*\*/feed/\*\*

</td>
<td valign="top">

/a/b/feed/rss/1234

</td>
</tr>
</table>

% is treated as an escape character. The pattern %\{user%\} matches \{user\} but not user. Conditions can be categorized as follows:

1.  **Operators**: Wildcard patterns used in conditions.
2.  **Relational operands**: Evaluates whether a quantity is equal to, greater than, or less than another.
3.  **Operands**: The value of the conditions is used to determine the overall values.
4.  **Literals**: Literal values in a condition.



## Operators

When using operators, observe the following restrictions:

\- Operators cannot be used as variable names.

\- A space character is required before and after an operator.

\- To include an operator in a variable, a variable name must be enclosed in single quotes. For example, `"request.header.help!me"`.

\- Arithmetic operators \(+, \*, -, /, %\) are not supported.

\- Java precedence is used for operators.


<table>
<tr>
<th valign="top">

Symbol

</th>
<th valign="top">

In words \(case insensitive\)

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

!

</td>
<td valign="top">

Not, not

</td>
<td valign="top">

Unary operator \(takes a single input\)

</td>
</tr>
<tr>
<td valign="top">

=

</td>
<td valign="top">

Equals, Is

</td>
<td valign="top">

Equals to

</td>
</tr>
<tr>
<td valign="top">

!=

</td>
<td valign="top">

NotEquals, IsNot

</td>
<td valign="top">

Not equals

</td>
</tr>
<tr>
<td valign="top">

:=

</td>
<td valign="top">

EqualsCaseInsensitive

</td>
<td valign="top">

Equals but is case insensitive

</td>
</tr>
<tr>
<td valign="top">

\>

</td>
<td valign="top">

GreaterThan

</td>
<td valign="top">

Greater than

</td>
</tr>
<tr>
<td valign="top">

\>=

</td>
<td valign="top">

GreaterThanOrEquals

</td>
<td valign="top">

Greater than or equal to

</td>
</tr>
<tr>
<td valign="top">

<

</td>
<td valign="top">

LesserThan

</td>
<td valign="top">

Lesser than

</td>
</tr>
<tr>
<td valign="top">

<=

</td>
<td valign="top">

LesserThanOrEquals

</td>
<td valign="top">

Lesser than or equal to

</td>
</tr>
<tr>
<td valign="top">

&&

</td>
<td valign="top">

And, and

</td>
<td valign="top">

And

</td>
</tr>
<tr>
<td valign="top">

||

</td>
<td valign="top">

Or

</td>
<td valign="top">

Or

</td>
</tr>
<tr>
<td valign="top">

\(

</td>
<td valign="top">



</td>
<td valign="top">

Groups an expression

</td>
</tr>
<tr>
<td valign="top">

\)

</td>
<td valign="top">



</td>
<td valign="top">

Closes an expression group

</td>
</tr>
<tr>
<td valign="top">

~~

</td>
<td valign="top">

JavaRegex

</td>
<td valign="top">

Matches a javax.util.regex compliant regular expression.

</td>
</tr>
<tr>
<td valign="top">

~

</td>
<td valign="top">

Matches, Like

</td>
<td valign="top">

Matches a glob-style pattern using the "\*" wildcard character.

</td>
</tr>
<tr>
<td valign="top">

~/

</td>
<td valign="top">

MatchesPath, LikePath

</td>
<td valign="top">

Matches a path expression.

</td>
</tr>
<tr>
<td valign="top">

=|

</td>
<td valign="top">

StartsWith

</td>
<td valign="top">

Starts with

</td>
</tr>
</table>



## Behavior of null operands in conditional statements

The following table shows the behavior when operands evaluate to null:


<table>
<tr>
<th valign="top">

Operator

</th>
<th valign="top">

LHS null

</th>
<th valign="top">

RHS null

</th>
<th valign="top">

LHS and RHS null

</th>
</tr>
<tr>
<td valign="top">

=, ==, :=

</td>
<td valign="top">

false

</td>
<td valign="top">

false

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

=|

</td>
<td valign="top">

false

</td>
<td valign="top">

false

</td>
<td valign="top">

false

</td>
</tr>
<tr>
<td valign="top">

!=

</td>
<td valign="top">

true

</td>
<td valign="top">

 

</td>
<td valign="top">

false

</td>
</tr>
<tr>
<td valign="top">

\>

</td>
<td valign="top">



</td>
<td valign="top">

false

</td>
<td valign="top">

false

</td>
</tr>
<tr>
<td valign="top">

\>=

</td>
<td valign="top">

false

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

<

</td>
<td valign="top">



</td>
<td valign="top">

false

</td>
<td valign="top">

false

</td>
</tr>
<tr>
<td valign="top">

<=

</td>
<td valign="top">



</td>
<td valign="top">

false

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

~

</td>
<td valign="top">

false

</td>
<td valign="top">

N/A

</td>
<td valign="top">

false

</td>
</tr>
<tr>
<td valign="top">

~~

</td>
<td valign="top">

false

</td>
<td valign="top">

N/A

</td>
<td valign="top">

false

</td>
</tr>
<tr>
<td valign="top">

!~

</td>
<td valign="top">



</td>
<td valign="top">

false

</td>
<td valign="top">

false

</td>
</tr>
<tr>
<td valign="top">

~/

</td>
<td valign="top">

false

</td>
<td valign="top">

N/A

</td>
<td valign="top">

false

</td>
</tr>
</table>



## Operands

API Management adapts operands to a common data type before comparing them. For example, if the response status code is 404, the expression response.status.code = "400" and the response.status.code = 400 are equivalent. For numeric operands, the data type is interpreted as integer unless the value is terminated as follows:

\- f" or "F" \(float, for example, 3.142f, 91.1F\)

\- "d" or "D" \(double, for example, 3.142d, 100.123D\)

\- "l" or "L" \(long, for example, 12321421312L\)

In these cases, the system performs the adaptations shown in the following table.

> ### Note:  
> The dash character \( - \) in this table implies that the comparison is not performed, so the comparison is false.


<table>
<tr>
<th valign="top">

RHS LHS

</th>
<th valign="top">

Boolean

</th>
<th valign="top">

Integer

</th>
<th valign="top">

Long

</th>
<th valign="top">

Float

</th>
<th valign="top">

Double

</th>
<th valign="top">

String

</th>
<th valign="top">

Comparable

</th>
<th valign="top">

Object

</th>
</tr>
<tr>
<td valign="top">

Boolean

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Long

</td>
<td valign="top">

Float

</td>
<td valign="top">

Double

</td>
<td valign="top">

String

</td>
<td valign="top">

 

</td>
<td valign="top">

\-

</td>
</tr>
<tr>
<td valign="top">

Integer

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Long

</td>
<td valign="top">

Float

</td>
<td valign="top">

Double

</td>
<td valign="top">

String

</td>
<td valign="top">

Comparable

</td>
<td valign="top">

\-

</td>
</tr>
<tr>
<td valign="top">

Long

</td>
<td valign="top">

Long

</td>
<td valign="top">

Long

</td>
<td valign="top">

Long

</td>
<td valign="top">

Float

</td>
<td valign="top">

Double

</td>
<td valign="top">

String

</td>
<td valign="top">

Comparable

</td>
<td valign="top">

\-

</td>
</tr>
<tr>
<td valign="top">

Float

</td>
<td valign="top">

Float

</td>
<td valign="top">

Float

</td>
<td valign="top">

Float

</td>
<td valign="top">

Float

</td>
<td valign="top">

Double

</td>
<td valign="top">

String

</td>
<td valign="top">

Comparable

</td>
<td valign="top">

\-

</td>
</tr>
<tr>
<td valign="top">

Double

</td>
<td valign="top">

Double

</td>
<td valign="top">

Double

</td>
<td valign="top">

Double

</td>
<td valign="top">

Double

</td>
<td valign="top">

Double

</td>
<td valign="top">

String

</td>
<td valign="top">

Comparable

</td>
<td valign="top">

\-

</td>
</tr>
<tr>
<td valign="top">

String

</td>
<td valign="top">

String

</td>
<td valign="top">

String

</td>
<td valign="top">

String

</td>
<td valign="top">

String

</td>
<td valign="top">

String

</td>
<td valign="top">

String

</td>
<td valign="top">

Comparable

</td>
<td valign="top">

\-

</td>
</tr>
<tr>
<td valign="top">

Comparable

</td>
<td valign="top">

Comparable

</td>
<td valign="top">

Comparable

</td>
<td valign="top">

Comparable

</td>
<td valign="top">

Comparable

</td>
<td valign="top">

Comparable

</td>
<td valign="top">

Comparable

</td>
<td valign="top">

Comparable

</td>
<td valign="top">

\-

</td>
</tr>
<tr>
<td valign="top">

Object

</td>
<td valign="top">

\-

</td>
<td valign="top">

\-

</td>
<td valign="top">

\-

</td>
<td valign="top">

\-

</td>
<td valign="top">

\-

</td>
<td valign="top">

\-

</td>
<td valign="top">

\-

</td>
<td valign="top">

\-

</td>
</tr>
</table>



## Literals

null, true, and false are the literals available in conditions. For example: `request.header.host is null` and `flow.cachehit is true`.

