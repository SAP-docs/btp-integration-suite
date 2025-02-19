<!-- loio5e2f272c8aa3481cb60181f2c53ed996 -->

# Understanding Quota Time Notation

All Quota times are set to the **Coordinated Universal Time \(UTC\)** time zone.

Quota time notation follows the international standard date notation defined in International Standard ISO 8601.

Dates are defined as year, month, and day, in the following format: **YYYY-MM-DD**. For example, 2024-03-05 represents March 5, 2024.

Time of day is defined as hours, minutes, and seconds in the following format: **hours:minutes:seconds**. For example, **23:59:59** represents the time one second before midnight.

Note that two notations, **00:00:00** and **24:00:00**, are available to distinguish the two midnights that can be associated with one date. Therefore **2024-03-05 24:00:00** is the same date and time as **2024-03-06 00:00:00**. The latter is usually the preferred notation.

**Related Information**  


[Quota](quota-1f742c1.md "The Quota policy defines the number of request messages an application can submit to an API over a given period of time.")

