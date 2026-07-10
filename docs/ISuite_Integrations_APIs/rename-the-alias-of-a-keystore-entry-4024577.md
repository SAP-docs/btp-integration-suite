<!-- loio4024577bea17492384de9f49b7bbc036 -->

# Rename the Alias of a Keystore Entry

Rename an alias of a tenant keystore entry.



Perform the following call:


<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
</tr>
<tr>
<td valign="top">

PUT

</td>
<td valign="top">

`/KeystoreEntries('{Hexalias}')` 

</td>
</tr>
</table>

The request body must contain a property of the `KeystoreEntry` entity type with a null value. Otherwise, you get an exception.

Make sure that you specify the value for the old alias in hexadecimal format. The new alias must be URL-encoded.

Assume that your tenant keystore contains a keystore entry with alias `mykeypair` and you like to rename it to `mykeypair-new`. The hexadecimal value of `mykeypair` is: `6d796b657970616972`

Certain values \(for example, for the alias when indicated in the example request as `<hexalias>`\) need to be provided in hexadecimal notation. String characters are stored by the computer as numbers. When the hexadecimal notation is required, the text is to be provided not as decimal number but as a hexadecimal number instead. For example: The string `my alias` is expressed by the following decimal numbers: `109 121 32 97 108 105 97 115` \(because, according to the American Standard Code for Information Interchange \(ASCII \), the letter `m` is translated to the decimal number `109`, and so forth\). If you convert each number to a hexadecimal number, you get: `6D 79 20 61 6C 69 61 73`. Note that `6D` is the hexadecimal representation of `109`, and so forth. If you like to specify `my alias` in an example request, enter `6D7920616C696173`.

Therefore, you need to send the following PUT request:

`https://<host address>/api/v1/KeystoreEntries('6d796b657970616972')?renameAlias=mykeypair-new`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

