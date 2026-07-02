<!-- loiofd8f054b986c45aea656246f5ed318ef -->

# Working with Code Value Mappings

Integration Advisor supports code value mappings and global code value mappings.



<a name="loiofd8f054b986c45aea656246f5ed318ef__section_ysb_dll_zfc"/>

## Code Value Mappings

Code value mappings represent the transformation of a code value that is set at the source element into a code value that is required at the target element. The strings for each element can be different, but the semantics and definition of both elements should be the same.



<a name="loiofd8f054b986c45aea656246f5ed318ef__section_dqj_2tf_zfc"/>

## 1:1 and N:1 Cardinality

You can create code value mappings with both 1:1 and n:1 cardinality:

-   A **1:1 relationship** enables you to define mappings between predefined code values from a source codelist and a target codelist. Each code value in the source codelist is uniquely mapped to a corresponding code value in the target codelist, establishing a 1:1 relationship.

-   An **n:1 relationship** supports more complex scenarios in which multiple source codelists, each with their own predefined code values, are mapped to a single target codelist. This is referred to as an n:1 relationship, allowing for the transformation of data from various sources into the target source.

    You can map more than one source node with a target node for both local and global code value mapping.


Furthermore, in these two cases, you can set a **default value**. This allows you to set a default value for the mapping in case no specific values are configured for the target code value.

> ### Note:  
> Code value mappings allow you to only map between pre-defined sets of values and doesn't support mapping a non-value. If you want to use your own implementation, it's recommended to create an XSLT code. See [Functions](functions-2ea22d0.md).



<a name="loiofd8f054b986c45aea656246f5ed318ef__section_hgw_2tf_zfc"/>

## Code Value Mapping and Global Code Value Mapping

**Code value mappings** are created within a specific MAG, accessible only by a particular node of that MAG. They're stored as part of the MAG and follow its versioning control. See [Code Value Mapping](code-value-mapping-eb6dad8.md).

In contrast, **global code value mappings** are created independently, outside of any MAG, and can be utilized by multiple MAGs. They have their own version controlling and each version can be reused across multiple nodes within a MAG. See [Global Code Value Mappings](global-code-value-mappings-fd1d3ff.md).

You can convert a local code value mapping into a global code value mapping, whether it's a 1:1 or an n:1 code value mapping.

**Related Information**  


[Code Value Mapping](code-value-mapping-eb6dad8.md "Code value mappings represent the transformation of a code value that is set at the source element into a code value that is required at the target element. They're created within a specific MAG, accessible only by a particular node of that MAG, and are stored them as well.")

[Global Code Value Mappings](global-code-value-mappings-fd1d3ff.md "Learn more about the Code Value Mappings tab in the Mapping Guidelines page.")

