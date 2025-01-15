<!-- loiod50613e9f37444de8f370548aa86f762 -->

# Data Protection and Privacy for API Management



<a name="loiod50613e9f37444de8f370548aa86f762__section_fgx_xv5_fcb"/>

## Glossary


<table>
<tr>
<th valign="top">

Term

</th>
<th valign="top">

Definition

</th>
</tr>
<tr>
<td valign="top">

**Blocking** 

</td>
<td valign="top">

A method of restricting access to data for which the primary business purpose has ended.

</td>
</tr>
<tr>
<td valign="top">

**Business purpose** 

</td>
<td valign="top">

A legal, contractual, or otherwise justified reason for the processing of personal data. The assumption is that any purpose has an end that is usually already defined when the purpose starts.

</td>
</tr>
<tr>
<td valign="top">

**Consent** 

</td>
<td valign="top">

The action of the data subject confirming that the usage of his or her personal data shall be allowed for a given purpose. A consent functionality allows the storage of a consent record in relation to a specific purpose and shows if a data subject has granted, withdrawn, or denied consent.

</td>
</tr>
<tr>
<td valign="top">

**Deletion** 

</td>
<td valign="top">

Deletion of **personal data** so that the data is no longer available.

</td>
</tr>
<tr>
<td valign="top">

**End of business** 

</td>
<td valign="top">

Date where the business with a data subject ends, for example the order is completed, the subscription is canceled, or the last bill is settled.

</td>
</tr>
<tr>
<td valign="top">

**End of purpose \(EoP\)** 

</td>
<td valign="top">

End of purpose and start of blocking period. The point in time, when the primary processing purpose ends \(e.g. contract is fulfilled\).

</td>
</tr>
<tr>
<td valign="top">

**End of purpose \(EoP\) check** 

</td>
<td valign="top">

A method of identifying the point in time for a data set when the processing of **personal data** is no longer required for the primary **business purpose**. After the **EoP** has been reached, the data is **blocked** and can only be accessed by users with special authorization \(for example, tax auditors\).

</td>
</tr>
<tr>
<td valign="top">

**Personal data** 

</td>
<td valign="top">

Any information relating to an identified or identifiable natural person \("data subject"\). An identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or one or more factors specific to the physical, physiological, genetic, mental, economic, cultural, or social identity of that natural person.

Any information relating to the application developer or the Cloud Foundry developer using API Management service.

</td>
</tr>
<tr>
<td valign="top">

**Residence period** 

</td>
<td valign="top">

The period of time between the end of business and the end of purpose \(EoP\) for a data set during which the data remains in the database and can be used in case of subsequent processes related to the original purpose. At the end of the longest configured residence period, the data is blocked or deleted. The residence period is part of the overall retention period.

</td>
</tr>
<tr>
<td valign="top">

**Retention period** 

</td>
<td valign="top">

The period of time between the end of the last business activity involving a specific object \(for example, a business partner\) and the deletion of the corresponding data, subject to applicable laws. The retention period is a combination of the residence period and the blocking period. API Management has a retention period of six months and all the data is automatically cleaned up after the retention period.

</td>
</tr>
<tr>
<td valign="top">

**Referenced data** 

</td>
<td valign="top">

Any information relating to application developer's application.

</td>
</tr>
</table>



<a name="loiod50613e9f37444de8f370548aa86f762__section_cxt_tv5_fcb"/>

## User Consent

Various types of customer data are processed by and stored on API Management at different times. This data gets the highest level of protection, and SAP takes dedicated measures to guarantee this security level.

To comply with user consent, SAP customers should customize the API Management to use their own identity provider. SAP customers using the custom identity provider should ensure that the necessary mechanism for user consent is available to allow personal data \(of a natural person such as a customer, contact, or account\) to be collected as well as transferred to the solution.



<a name="loiod50613e9f37444de8f370548aa86f762__section_mwj_dw5_fcb"/>

## Read-Access Logging

Read Access Logging \(RAL\) is used to monitor and log read access to sensitive data. Data may be categorized as sensitive by law, by external company policy, or by internal company policy.

API Management does not store any sensitive personal data.



<a name="loiod50613e9f37444de8f370548aa86f762__section_kx4_xw5_fcb"/>

## Information Report

The only personal data of data subjects stored in API Management is the user ID. This user ID is stored whenever a user creates an API artifact, for example an API proxy or API product, and this user ID can be obtained \(read\) only from that artifact.

To enable data subjects to obtain information about their personal data in the Developer Hub, we provide the following service to retrieve their personal information:

-   [Service to View User Details on Developer Hub](service-to-view-user-details-on-developer-hub-a49c05f.md)



<a name="loiod50613e9f37444de8f370548aa86f762__section_nsx_cx5_fcb"/>

## Erasure

When handling personal data, consider the legislation in the different countries where your organization operates. After the data has passed the end of purpose, regulations may require you to delete the data. However, additional regulations may require you to keep the data longer. During this period you must block access to the data by unauthorized persons until the end of the six months retention period, when the data is finally deleted.

Personal data can also include referenced data. The challenge for deletion and blocking is to first handle referenced data and then other data, such as business partner data.

API Management stores the API portal administrator’s user ID. Storing the user ID is a business requirement and the user ID is deleted when the resources created by the API portal administrator are removed.

API Management stores personal information such as first name, last name, user ID, and e-mail ID of users who have logged on to the Developer Hub. All the personal information stored in the application is deleted when the access for the corresponding user is revoked.

In API Management, application developers can contact their Developer Hub administrators to have their personal data erased and access revoked. For more information, see [Revoke Access](../50-Development/revoke-access-ce609bb.md) and [Delete Data of Unregistered Users](../50-Development/delete-data-of-unregistered-users-d548233.md).



<a name="loiod50613e9f37444de8f370548aa86f762__section_bzm_by5_fcb"/>

## Change Log

For auditing purposes or for legal requirements, changes made to personal data should be logged, making it possible to monitor who made changes and when.

API Management does not allow users to make any changes to their personal data via the API Management application. However, changes made in the identity provider are synced to the API Management application and the sync operation is logged by API Management. Changes made in the identity provider should be logged by the identity provider.

