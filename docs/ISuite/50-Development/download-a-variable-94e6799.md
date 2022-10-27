<!-- loio94e6799d9fe04aac8e6c6862bd860c99 -->

# Download a Variable



To download a single variable, perform the following call:


<table>
<tr>
<th valign="top">

Method



</th>
<th valign="top">

Resource Path



</th>
<th valign="top">

Purpose



</th>
</tr>
<tr>
<td valign="top">

GET



</td>
<td valign="top">

 `​/Variables(VariableName='{VariableName}',IntegrationFlow='{IntegrationFlowName}')/$value` 



</td>
<td valign="top">

Downloads a single variable.



</td>
</tr>
</table>

To download variable `timestamp` for integration flow `MyIntegrationFlow`, perform the following request:

`https://<host address>/api/v1​/Variables(VariableName='timestamp',IntegrationFlow='MyIntegrationFlow')/$value`

