<!-- loio2714db1701114de4ab5ffd1bebd0c4de -->

# Tasks and Permissions for Migration Assessment 

Learn about security-related topics like users and authorizations.



There are two role collections available for Migration Assessment that cover different personas and responsibilities:

-   the *PIMAS\_Admin* performs administrative tasks, like configuring system settings

-   the *PIMAS\_IntegrationAnalyst* performs executive tasks, like reading and running evaluations as well as downloading results


The following table provides an overview of the role templates and role collections users need to accomplish the various tasks related to Migration Assessment.

**Tasks and Roles**


<table>
<tr>
<th valign="top">

Area

</th>
<th valign="top">

Task

</th>
<th valign="top">

Roles \(Scopes\)

</th>
<th valign="top">

Role Template

</th>
<th valign="top">

Role Collection

</th>
</tr>
<tr>
<td valign="top">

Settings

</td>
<td valign="top">

Read System Data

</td>
<td valign="top">

PimasSystem.Read

</td>
<td valign="top">

PimasSystemRead

</td>
<td valign="top">

PIMAS\_Admin

PIMAS\_IntegrationAnalyst

</td>
</tr>
<tr>
<td valign="top">

Settings

</td>
<td valign="top">

CUD System Data

</td>
<td valign="top">

PimasSystem.Read

PimasSystem.Write

PimasSystem.Delete

</td>
<td valign="top">

PimasSystemWrite

</td>
<td valign="top">

PIMAS\_Admin

</td>
</tr>
<tr>
<td valign="top">

Settings

</td>
<td valign="top">

Read Rule Data

</td>
<td valign="top">

PimasRule.Read

</td>
<td valign="top">

PimasRuleRead

</td>
<td valign="top">

PIMAS\_Admin

PIMAS\_IntegrationAnalyst

</td>
</tr>
<tr>
<td valign="top">

Settings

</td>
<td valign="top">

Activate/Deactivate/Add Rule Data

</td>
<td valign="top">

PimasRule.Read

PimasRule.Write

PimasRule.Delete

</td>
<td valign="top">

PimasRuleWrite

</td>
<td valign="top">

PIMAS\_Admin

</td>
</tr>
<tr>
<td valign="top">

Settings

</td>
<td valign="top">

Read TShirtSize Data

</td>
<td valign="top">

PimasEffort.Read

</td>
<td valign="top">

PimasEffortRead

</td>
<td valign="top">

PIMAS\_Admin

PIMAS\_IntegrationAnalyst

</td>
</tr>
<tr>
<td valign="top">

Settings

</td>
<td valign="top">

Edit / delete TShirtSize Data

</td>
<td valign="top">

PimasEffort.Read

PimasEffort.Write

PimasEffort.Delete

</td>
<td valign="top">

PimasEffortWrite

</td>
<td valign="top">

PIMAS\_Admin

</td>
</tr>
<tr>
<td valign="top">

Data Request

</td>
<td valign="top">

Read Data Extraction

</td>
<td valign="top">

PimasExtract.Read

</td>
<td valign="top">

PimasExtractRead

</td>
<td valign="top">

PIMAS\_IntegrationAnalyst

</td>
</tr>
<tr>
<td valign="top">

Data Request

</td>
<td valign="top">

CUD Data Extraction

</td>
<td valign="top">

PimasExtract.Read

PimasExtract.Write

PimasExtract.Delete

</td>
<td valign="top">

PimasExtractWrite

</td>
<td valign="top">

PIMAS\_IntegrationAnalyst

</td>
</tr>
<tr>
<td valign="top">

Evaluation Request

</td>
<td valign="top">

Read Scenario Evaluation + Run

</td>
<td valign="top">

PimasEvaluation.Read

</td>
<td valign="top">

PimasEvaluationRead

</td>
<td valign="top">

PIMAS\_IntegrationAnalyst

</td>
</tr>
<tr>
<td valign="top">

Evaluation Request

</td>
<td valign="top">

CUD Scenario Evaluation + Run

</td>
<td valign="top">

PimasEvaluation.Write

PimasEvaluation.Delete

</td>
<td valign="top">

PimasEvaluationWrite

</td>
<td valign="top">

PIMAS\_IntegrationAnalyst

</td>
</tr>
<tr>
<td valign="top">

Evaluation Request

</td>
<td valign="top">

Read Data Extract Monitoring Data

</td>
<td valign="top">

PimasExtractMonitoring.Read

</td>
<td valign="top">

PimasExtractRead

</td>
<td valign="top">

PIMAS\_IntegrationAnalyst

</td>
</tr>
<tr>
<td valign="top">

Evaluation Request

</td>
<td valign="top">

Read Scenario Evaluation Monitoring Data

</td>
<td valign="top">

PimasEvaluationMonitoring.Read

</td>
<td valign="top">

PimasEvaluationRead

</td>
<td valign="top">

PIMAS\_IntegrationAnalyst

</td>
</tr>
<tr>
<td valign="top">

Evaluation Request

</td>
<td valign="top">

Download of Excel

</td>
<td valign="top">

PimasEvaluation.Read

</td>
<td valign="top">

PimasEvaluationRead

</td>
<td valign="top">

PIMAS\_IntegrationAnalyst

</td>
</tr>
<tr>
<td valign="top">

Evaluation Request

</td>
<td valign="top">

Download of PDF

</td>
<td valign="top">

PimasEvaluation.Read

</td>
<td valign="top">

PimasEvaluationRead

</td>
<td valign="top">

PIMAS\_IntegrationAnalyst

</td>
</tr>
</table>

