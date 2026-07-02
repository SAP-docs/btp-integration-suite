<!-- loio7b97f5b862644ca7b46142e18f77ba35 -->

# MIG/MAG Envelope Handling

Learn how MIGs containing envelopes are handled in B2B transactions

Integration Advisor offers pre-built envelope structures for ASC X12 and UN/EDIFACT. The Message Implementation Guideline \(MIG\) provides an option to combine envelope and message components into a single, consolidated structure. To know more, refer to this [blog](https://community.sap.com/t5/technology-blogs-by-sap/using-edi-envelopes-in-integration-advisor/ba-p/13915328).

**Envelope Handling in B2B**

Trading Partner Management \(TPM\) automatically handles envelope structures without requiring specific configuration in **Interchange** or **Mapping** Steps within Agreements and their respective B2B Scenarios.

When a target Message Implementation Guideline \(MIG\) and its corresponding Mapping Guideline \(MAG\) are selected for use with envelopes, TPM bypasses standard envelope assembly logic, with a few exceptions \(outlined in the table below\) applicable to X12 and EDIFACT. However, the remaining elements must be configured in the MAG or during post-processing.

1.  **UN/EDIFACT:**

    1.  S\_UNT/D\_0074 \(Number of segments in the message\)

    2.  S\_UNZ/D\_0036 \(Interchange Control Count\)
    3.  S\_UNB/D\_0020 \(Interchange control reference\)
    4.  S\_UNZ/D\_0020 \(Interchange control reference\)

2.  **ASC X12:**
    1.  S\_IEA/D\_I16 \(Number of Included Functional Groups\)

    2.  S\_SE/D\_96 \(Number of Included Segments\)
    3.  S\_ISA/D\_I12 \(Interchange Control Number\)
    4.  S\_GS/D\_28 \(Group Control Number\)


If MIG/MAG envelopes are not selected for use in Integration Advisor, TPM utilizes the assembly step in integration flow **Step 2 - Interchange Processing Flow** to populate the envelope nodes. The table below shows the Envelope structure and nodes filled through this process:

**ASC X12 Envelope XML Message**


<table>
<tr>
<th valign="top">

Envelope XML Message Structure

</th>
<th valign="top">

Node Structure

</th>
<th valign="top">

Node Name Description

</th>
<th valign="top">

Comment

</th>
</tr>
<tr>
<td valign="top">

<ns1:Interchange xmlns:ns1="urn:sap.com:typesystem:b2b:116:asc-x12"\>

</td>
<td valign="top">

Interchange

</td>
<td valign="top">

Interchange

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<S\_ISA\>

</td>
<td valign="top">

ISA

</td>
<td valign="top">

Interchange Control Header

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I01/\>

</td>
<td valign="top">

I01

</td>
<td valign="top">

Authorization Information Qualifier

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I02/\>

</td>
<td valign="top">

I02

</td>
<td valign="top">

Authorization Information

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I03/\>

</td>
<td valign="top">

I03

</td>
<td valign="top">

Security Information Qualifier

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I04/\>

</td>
<td valign="top">

I04

</td>
<td valign="top">

Security Information

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I05/\><!--type system verison great than 004010--\>

</td>
<td valign="top">

I05

</td>
<td valign="top">

Interchange ID Qualifier

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I05\_1/\><!--type system verison not great than 004010--\>

</td>
<td valign="top">

I05\_1

</td>
<td valign="top">

Interchange ID Qualifier

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I06/\>

</td>
<td valign="top">

I06

</td>
<td valign="top">

Interchange Sender ID

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I05\_2/\>

</td>
<td valign="top">

I05\_2

</td>
<td valign="top">

Interchange ID Qualifier

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I07/\>

</td>
<td valign="top">

I07

</td>
<td valign="top">

Interchange Receiver ID

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I08/\>

</td>
<td valign="top">

I08

</td>
<td valign="top">

Interchange Date

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I09/\>

</td>
<td valign="top">

I09

</td>
<td valign="top">

Interchange Time

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I65/\><!--type system verison great than 004010--\>

</td>
<td valign="top">

I65

</td>
<td valign="top">

Repetition Separator

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I10/\><!--type system verison not great than 004010--\>

</td>
<td valign="top">

I10

</td>
<td valign="top">

Interchange Control Standards Identifier

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I11/\>

</td>
<td valign="top">

I11

</td>
<td valign="top">

Interchange Control Version Number

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I12/\>

</td>
<td valign="top">

I12

</td>
<td valign="top">

Interchange Control Number

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I13/\>

</td>
<td valign="top">

I13

</td>
<td valign="top">

Acknowledgment Requested

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I14/\>

</td>
<td valign="top">

I14

</td>
<td valign="top">

Usage Indicator

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I15/\>

</td>
<td valign="top">

I15

</td>
<td valign="top">

Component Element Separator

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</S\_ISA\>

</td>
<td valign="top">

ISA

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<FunctionalGroup\>

</td>
<td valign="top">

Functional Group

</td>
<td valign="top">

Functional Group

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<S\_GS\>

</td>
<td valign="top">

GS

</td>
<td valign="top">

Functional Group Header

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_479/\>

</td>
<td valign="top">

479

</td>
<td valign="top">

Functional Identifier Code

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_142/\>

</td>
<td valign="top">

142

</td>
<td valign="top">

Application Sender's Code

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_124/\>

</td>
<td valign="top">

124

</td>
<td valign="top">

Application Receiver's Code

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_373/\>

</td>
<td valign="top">

373

</td>
<td valign="top">

Date

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_337/\>

</td>
<td valign="top">

337

</td>
<td valign="top">

Time

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_28/\>

</td>
<td valign="top">

28

</td>
<td valign="top">

Group Control Number

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_455/\>

</td>
<td valign="top">

455

</td>
<td valign="top">

Responsible Agency Code

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_480/\>

</td>
<td valign="top">

480

</td>
<td valign="top">

Version / Release / Industry Identifier Code

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</S\_GS\>

</td>
<td valign="top">

GS

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<M\_\(Message Type\)\>

</td>
<td valign="top">

Message Type

</td>
<td valign="top">

Message Type

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<S\_ST\>

</td>
<td valign="top">

ST

</td>
<td valign="top">

Transaction Set Header

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_143/\>

</td>
<td valign="top">

143

</td>
<td valign="top">

Transaction Set Identifier Code

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_329/\>

</td>
<td valign="top">

329

</td>
<td valign="top">

Transaction Set Control Number

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</S\_ST\>

</td>
<td valign="top">

ST

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<S\_SE\>

</td>
<td valign="top">

SE

</td>
<td valign="top">

Transaction Set Trailer

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_96/\>

</td>
<td valign="top">

96

</td>
<td valign="top">

Number of Included Segments

</td>
<td valign="top">

Always filled via TPM Assembly

</td>
</tr>
<tr>
<td valign="top">

<D\_329/\>

</td>
<td valign="top">

329

</td>
<td valign="top">

Transaction Set Control Number

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</S\_SE\>

</td>
<td valign="top">

SE

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</M\_\(Message Type\)\>

</td>
<td valign="top">

Message Type

</td>
<td valign="top">

Message Type

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<S\_GE\>

</td>
<td valign="top">

GE

</td>
<td valign="top">

Functional Group Trailer

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_97/\>

</td>
<td valign="top">

97

</td>
<td valign="top">

Number of Transaction Sets Included

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_28/\>

</td>
<td valign="top">

28

</td>
<td valign="top">

Group Control Number

</td>
<td valign="top">

Always filled via TPM Assembly

</td>
</tr>
<tr>
<td valign="top">

</S\_GE\>

</td>
<td valign="top">

GE

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</FunctionalGroup\>

</td>
<td valign="top">

FunctionalGroup

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<S\_IEA\>

</td>
<td valign="top">

IEA

</td>
<td valign="top">

Interchange Control Trailer

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_I16/\>

</td>
<td valign="top">

I16

</td>
<td valign="top">

Number of Included Functional Groups

</td>
<td valign="top">

Always filled via TPM Assembly

</td>
</tr>
<tr>
<td valign="top">

<D\_I12/\>

</td>
<td valign="top">

I12

</td>
<td valign="top">

Interchange Control Number

</td>
<td valign="top">

Always filled via TPM Assembly

</td>
</tr>
<tr>
<td valign="top">

</S\_IEA\>

</td>
<td valign="top">

IEA

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</ns1:Interchange\>

</td>
<td valign="top">

Interchange

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
</table>

**UN/EDIFACT Envelope XML Message**


<table>
<tr>
<th valign="top">

Envelope XML Message Structure

</th>
<th valign="top">

Node Structure

</th>
<th valign="top">

Node Name Description

</th>
<th valign="top">

Comment

</th>
</tr>
<tr>
<td valign="top">

<ns1:Interchange xmlns:ns1="urn:sap.com:ica:typesystem:6:un-edifact"\>

</td>
<td valign="top">

Interchange

</td>
<td valign="top">

Interchange

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<S\_UNB\>

</td>
<td valign="top">

UNB

</td>
<td valign="top">

Interchange header

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<C\_S001\>

</td>
<td valign="top">

S001

</td>
<td valign="top">

Syntax identifier

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0001/\>

</td>
<td valign="top">

0001

</td>
<td valign="top">

Syntax identifier

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0002/\>

</td>
<td valign="top">

0002

</td>
<td valign="top">

Syntax version number

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</C\_S001\>

</td>
<td valign="top">

S001

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<C\_S002\>

</td>
<td valign="top">

S002

</td>
<td valign="top">

Interchange sender

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0004/\>

</td>
<td valign="top">

0004

</td>
<td valign="top">

Sender identification

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0007/\>

</td>
<td valign="top">

0007

</td>
<td valign="top">

Partner identification code qualifier

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0008/\>

</td>
<td valign="top">

0008

</td>
<td valign="top">

Address for reverse routing

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</C\_S002\>

</td>
<td valign="top">

S002

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<C\_S003\>

</td>
<td valign="top">

S003

</td>
<td valign="top">

Interchange recipient

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0010/\>

</td>
<td valign="top">

0010

</td>
<td valign="top">

Recipient identification

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0007/\>

</td>
<td valign="top">

0007

</td>
<td valign="top">

Partner identification code qualifier

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0014/\>

</td>
<td valign="top">

0014

</td>
<td valign="top">

Routing address

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</C\_S003\>

</td>
<td valign="top">

S003

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<C\_S004\>

</td>
<td valign="top">

S004

</td>
<td valign="top">

Date/time of preparation

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0017/\>

</td>
<td valign="top">

0017

</td>
<td valign="top">

Date of preparation

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0019/\>

</td>
<td valign="top">

0019

</td>
<td valign="top">

Time of preparation

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</C\_S004\>

</td>
<td valign="top">

S004

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0020/\>

</td>
<td valign="top">

0020

</td>
<td valign="top">

Interchange control reference

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<C\_S005\>

</td>
<td valign="top">

S005

</td>
<td valign="top">

Recipient's reference, password

</td>
<td valign="top">

Always filled via TPM Assembly

</td>
</tr>
<tr>
<td valign="top">

<D\_0022/\>

</td>
<td valign="top">

0022

</td>
<td valign="top">

Recipient's reference/password

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0025/\>

</td>
<td valign="top">

0025

</td>
<td valign="top">

Recipient's reference/password qualifier

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</C\_S005\>

</td>
<td valign="top">

S005

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0026/\>

</td>
<td valign="top">

0026

</td>
<td valign="top">

Application reference

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0029/\>

</td>
<td valign="top">

0029

</td>
<td valign="top">

Processing priority code

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0031/\>

</td>
<td valign="top">

0031

</td>
<td valign="top">

Acknowledgement request

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0032/\>

</td>
<td valign="top">

0032

</td>
<td valign="top">

Communications agreement ID

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0035/\>

</td>
<td valign="top">

0035

</td>
<td valign="top">

Test indicator

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</S\_UNB\>

</td>
<td valign="top">

UNB

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<M\_\(Message Type\)\>

</td>
<td valign="top">

Message Type

</td>
<td valign="top">

Message Type

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<S\_UNH\>

</td>
<td valign="top">

UNH

</td>
<td valign="top">

Message header

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0062/\>

</td>
<td valign="top">

0062

</td>
<td valign="top">

Message reference number

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<C\_S009\>

</td>
<td valign="top">

S009

</td>
<td valign="top">

Message identifier

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0065/\>

</td>
<td valign="top">

0065

</td>
<td valign="top">

Message type

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0052/\>

</td>
<td valign="top">

0052

</td>
<td valign="top">

Message version number

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0054/\>

</td>
<td valign="top">

0054

</td>
<td valign="top">

Message release number

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0051/\>

</td>
<td valign="top">

0051

</td>
<td valign="top">

Controlling agency

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0057/\>

</td>
<td valign="top">

0057

</td>
<td valign="top">

Association assigned code

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</C\_S009\>

</td>
<td valign="top">

S009

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0068/\>

</td>
<td valign="top">

0068

</td>
<td valign="top">

Common access reference

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</S\_UNH\>

</td>
<td valign="top">

UNH

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<S\_UNT\>

</td>
<td valign="top">

UNT

</td>
<td valign="top">

Message trailer

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0074/\>

</td>
<td valign="top">

0074

</td>
<td valign="top">

Number of segments in the message

</td>
<td valign="top">

Always filled via TPM Assembly

</td>
</tr>
<tr>
<td valign="top">

<D\_0062/\>

</td>
<td valign="top">

0062

</td>
<td valign="top">

Message reference number

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</S\_UNT\>

</td>
<td valign="top">

UNT

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</M\_\(Message Type\)\>

</td>
<td valign="top">

Message Type

</td>
<td valign="top">

Message Type

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<S\_UNZ\>

</td>
<td valign="top">

UNZ

</td>
<td valign="top">

Interchange trailer

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

<D\_0036/\>

</td>
<td valign="top">

0036

</td>
<td valign="top">

Interchange control count

</td>
<td valign="top">

Always filled via TPM Assembly

</td>
</tr>
<tr>
<td valign="top">

<D\_0020/\>

</td>
<td valign="top">

0020

</td>
<td valign="top">

Interchange control reference

</td>
<td valign="top">

Always filled via TPM Assembly

</td>
</tr>
<tr>
<td valign="top">

</S\_UNZ\>

</td>
<td valign="top">

UNZ

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

</ns1:Interchange\>

</td>
<td valign="top">

Interchange

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
</table>

