<!-- loio72a8e9e8ca19495baaf748cde400e7a5 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Primitive Data Types

Primitive data types are the basic building blocks that you use to define entities or structure types within a MIG.

You can set the data type of a node under the *Primitive Type* field in the *Simple Type Properties* section.



<a name="loio72a8e9e8ca19495baaf748cde400e7a5__section_txn_xry_dnb"/>

## Date Time Type

-   *Date*: The Date data type consists of year, month, and day information to represent a date value.

-   *Time*: The Time data type consists of hour, minute, and second to represent a time value.
-   *DateTime*: The DateTime data type consists of date and time information.

There are various supported formats for this type and you can set the required format under the *Date Time Format* field. The terms used under each type is explained here:

-   Date

    -   *CC* : Century

    -   *YY* : Year \(00-99\)
    -   *MM* : Month \(01-12\)
    -   *DD* : Day \(01-31\)
    -   Example for *CCYYMMDD*: 20210731

-   Time
    -   *hh* : hour \(00-23\)

    -   *mm* = Minute \(00-59\)
    -   *ss* = Second \(00-59\)
    -   *f* = Fractional Second \(0-9\)
    -   Example for *hhmmss*: 180545

-   Timezone offset
    -   *\(+|-\)* : plus or minus sign

    -   *hh* : hour \(00-12\)

    -   *mm* : Minute \(00-30\)
    -   *Z* : short form for UTC timezone
    -   Example for *\(+|-\)hhmm*: +0100

-   *‘…’*: Fixed literals
    -   Example for *CCYY’-‘MM’-‘DD*: 2021-07-31


-   *\[…\]* : Optional value
    -   Example for *hhmm\[ss\]*: 180545 or 1805


-   *\(…|…\)*: Alternative values
    -   Example for *\(+|-\)hhmm*: +0100 or -0100


-   *\** : Repeating parts \(0 or more repetitions\)
    -   Example for *hhmmss.ff\**: 180545.9 or 180545.99 or 180545.999 etc. \(any number of fraction digits allowed\)



Apart from thhe supported formats, the following are the list of *Date Time Format* descriptions that is used to provide additional input for a selected type system:

-   **XML-based Type Systems**: Elements based on special primitive types such as **xsd:dateTime** or **xsd:date**

-   **Edifact \(including Edifact subsets\)**: Data Elements with format defined by code values in Codelist 2379. Example values: 102 or 204
-   **X12**: Data Elements with format defined by code values in Codelist 1250. Example values: D8 or DT
-   **X12**: Data Elements based on special X12 data types of a certain length For example, DT6..6 or TM4..6
-   **IDoc**: Data Elements based on special ABAP built-in data types. For example, DATS or TIMS

The <span class="SAP-icons-V5"></span> button allows you to set examples using *Add Example Values* and also use user-defined format provided in the *Format* field using *Use Format* option. The example values can also be later used in getting proposals during MAG simulation.

> ### Note:  
> The input field supports search by both *Format* and *Format Description*. So for example, if you type in 102, you will be directly guided to the date time format corresponding to Edifact code 102.
> 
> This type is also used in the mapping of Date Time Conversion. See: [Value Transformations](value-transformations-19f8374.md)



<a name="loio72a8e9e8ca19495baaf748cde400e7a5__section_zz3_bcz_dnb"/>

## Other Data Types

Numeric Data Type: The supported types are:

-   Decimal

-   Integer
-   Float

Character String Type:

-   String

-   NumericChar

Boolean: Represents the concept of binary-valued logic

