<!-- loio414b97de50954caf8027c5b31ae006f3 -->

# Add Partner

Add a new partner to the Partner Directory.



When you create a partner, you must specify a partner ID \(PID\) first that identifies the partner in the Partner Directory. For each partner \(with a given PID\), you can then create multiple entries for different entities \(such like string parameter, binary parameter, alternative partner, and authorized user\).



1.  Go to *Monitor* \> *Integrations and APIs*.

2.  Choose *Partner Directory*.
3.  Select *\+* \(*Add*\).

4.  On the *Create Partner Entry* dialog, specify the *PID*.

    This ID identifies the partner within the Partner Directory.

    Make sure that the entered value is unique within the Partner Directory.

5.  Specify the *Entity Type*.

6.  Specify the remaining parameters. Which parameters are available, depends on the chosen entity type \(see also: [Partner Directory Entity Types](partner-directory-entity-types-950f4b2.md)\).

    ****


    <table>
    <tr>
    <th valign="top">

    Entity Type
    
    </th>
    <th valign="top">

    Specify the Following Attributes
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *String Parameters* 
    
    </td>
    <td valign="top">
    
    -   *ID*

    -   *Value*



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Binary Parameters* 
    
    </td>
    <td valign="top">
    
    -   *ID*

    -   *Value*

    -   *Content Type*

    -   *Encoding*

        Only available if for *Content Type* one of the following options has been selected: *xml*, *xsl*, *xsd*, *json*, *text*.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Alternative Partners* 
    
    </td>
    <td valign="top">
    
    -   *Agency*

    -   *Scheme*

    -   *ID*



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Authorized Users* 
    
    </td>
    <td valign="top">
    
    *User* 
    
    </td>
    </tr>
    </table>
    
7.  Select *Create*.

    With the new partner, you have also created the first partner entity.

8.  If you like to add more entities for the partner, click and repeat the previous steps.


