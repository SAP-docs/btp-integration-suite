<!-- loio8703aa88c7e14cfcaa2aafdcc5290b59 -->

# Python Script

This policy is used to configure the Python Script code to execute within the context of an API proxy.

The Python Script policy allows you to add a custom-built python functionality to your API proxy flow, wherein the functionality you need isn't supported through the existing policies available in API Management.

Jython version 2.5.2 provides the required python language support. You can find the Jython version 2.5.2 libraries in the following link:

`https://www.jython.org/jython-old-sites/docs/index.html`

> ### Note:  
> The third-party libraries you add must be implemented in pure python language only.

A Python policy contains no actual code. Instead, a Python policy references a Python 'resource' and defines the Step in the API flow where the Python script executes. The Python Script resource must always have the .py extension.

You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> <!-- This sample Python Script policy demonstrates how python scripts are executed. -->
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <Script timeLimit="200" async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <IncludeURL>py://dependency_script.py</IncludeURL>
>     <ResourceURL>py://mainscript.py</ResourceURL>
> </Script>
> 
> 
> 
> ```
> 
> An example of a mainscript.py script
> 
> > ### Code Syntax:  
> > ```
> > This is a sample mainscript.py
> > 	x = 1
> > 	if x == 1:
> >  		# indented four spaces
> >     	print "x is 1."
> > ```


<table>
<tr>
<th valign="top">

**Attribute Name**

</th>
<th valign="top">

**Description**

</th>
<th valign="top">

Required

</th>
</tr>
<tr>
<td valign="top">

`timeLimit`

</td>
<td valign="top">

Specifies the maximum time \(in milliseconds\) that the script is permitted to execute.

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

`IncludeURL`

</td>
<td valign="top">

This attribute specifies the python file to be loaded as dependency to the primary python file specified within the `ResourceURL` attribute. You can store the dependency python file under `APIProxy/FileResources/` in the API proxy bundle.

The name of the dependency python file must be of type ‘String’.

> ### Note:  
> The python libraries you add must be implemented using pure python language only.

You can include multiple dependency python files with additional `IncludeURL` attributes. The scripts are evaluated in the order in which they are listed in the policy.

</td>
<td valign="top">

Optional

</td>
</tr>
<tr>
<td valign="top">

`ResourceURL`

</td>
<td valign="top">

This attribute specifies the primary python file that executes in the API flow. You must store this python file under `/APIProxy/FileResources/` in the API proxy bundle.

The name of the primary python file must be of type ‘String’.

> ### Note:  
> The python libraries you add must be implemented using pure python language only.



</td>
<td valign="top">

Yes

</td>
</tr>
</table>

During the policy execution, the following errors can occur:


<table>
<tr>
<th valign="top">

**Attribute Name**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

`InvalidResourceUrlFormat`

</td>
<td valign="top">

This error occurs when the format of the resource URL specified within the `<ResourceURL>` or the `<IncludeURL>` attribute of the Python Script policy is invalid, resulting in the failure of API proxy deployment.

</td>
</tr>
<tr>
<td valign="top">

`InvalidResourceUrlReference`

</td>
<td valign="top">

This error occurs when the `<ResourceURL>` or the `<IncludeURL>` attributes refer to a python file that doesn't exist, resulting in failure of API proxy deployment.

</td>
</tr>
<tr>
<td valign="top">

`NoResourceForURL`

</td>
<td valign="top">

The `<ResourceURL>` and `<IncludeURL>` attributes refer to a Python Script file that doesn't exist.

</td>
</tr>
</table>

> ### Note:  
> For added security API Management python runtime executes in a restricted mode, where import is not allowed for os, sys, and java.lang.

