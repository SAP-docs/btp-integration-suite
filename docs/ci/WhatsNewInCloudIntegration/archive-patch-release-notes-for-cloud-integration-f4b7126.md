<!-- loiof4b7126c524e4126b54fc7b4a34cadc0 -->

# Archive - Patch Release Notes for Cloud Integration

This page contains a historical archive of all patch release notes for Cloud Integration.



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_nk3_lmj_qqb"/>

## 16 August 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.16.23

5.24.21

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

When using the OpenConnectors adapter, there have been issues handing responses from the connected system. The system raised error messages that contained the following string: `org.apache.http.TruncatedChunkException: Truncated chunk`.

The issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_fmn_lxd_4qb"/>

## 10 August 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.24.20

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

AMQP connections to a AWS hosted ActiveMQ broker fail with a TLS handshake fatal alert .

A new system property is introduced with this patch, that allows to limit the allowed TLS versions for the AMQP adapter to 1.2, since the issue only happens with TLS 1.3. If the system property is not set, the change has not impact at all.

The reported issue is fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_zpx_jl5_mqb"/>

## 05 August 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.24.19

6.16.21

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Kafka sender adapters leak file descriptors in case of poll exceptions.

If a Kafka sender runs into an exception during consumer.poll\(\), the consumer is not properly closed. Still, a new one is instantiated and the old one leaks. The old consumer holds up to 4 file descriptors, which is a limited resource. As this resource is much more limited on CF, customers running on CF have a higher risk to run into a subsequent “too many files” exception. Once the node reaches this state, it needs to be restarted.

This issue is fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_jlx_f3v_kqb"/>

## 28 July 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.24.17

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Logging Improvement**

There is an issue after a node restart: in some cases the authentication filter for the CXF servlet does not get registered on some worker instances. As a consequence all incoming SOAP calls to the affected workers requiring any type of role based authentication fail with a 401 response. \(This issue can be resolved through a restart of the affected worker node.\)

The patch improves logging for the servlet filter registration to help further analysis of the actual primary issue.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_gy3_dhv_kqb"/>

## 28 July 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.24.17

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Feature Revert**

HTTP OAuth Client was changed with 2016 release for better and robust error handling. The older OAuth client used to continue the message processing despite OAuth errors, eventually to fail in the actual HTTP call. This approach coincidentally worked well and the iflow executions were successful till our recent software update. The changes were proactively reverted to avoid further issues.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_bbr_yym_3qb"/>

## 21 July 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.23.16

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Performance Issue**

Cleanup Monitoring Data Job is not able to cope with the load on that tenant and DB Space tends to get exhausted. This issue is fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_fp3_dtx_hqb"/>

## 15 July 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.15.17

5.23.15

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch fixes the issue of socket factory reset during disconnection of the FTP adapter in between subsequent requests.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_fdm_zsx_hqb"/>

## 15 July 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.15.16

5.23.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch fixes the transport failure at target tenant during import phase, which was caused by the missing ACL role for technical user in transport service configuration.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_q5y_xqv_gqb"/>

## 15 July 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.15.15

5.23.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

If an exception occurred during the closing of an aggregate, in certain cases locks from the in-progress repository haven't been removed, leading to aggregates that have been kept open for long time. This patch ensures that in such exceptional cases the locks are removed from the in-progress repository.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_tcy_d1y_2qb"/>

## 08 July 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.15.14

5.23.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

When you use uppercase letters to configure key aliases in SFTP adapter, the integration flow failed to deploy because the alias was not found in the keystore anymore. This casing-related problem with the keystore entries is now fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_p1l_zzx_2qb"/>

## 08 July 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.15.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Software update was failing for tenants deployed on Cloud Foundry environment. With this patch, a code fix was provided to resolve the issue.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_hn2_3vv_2qb"/>

## 07 July 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.15.12

5.23.11

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Intermittent failure with OData v4 adapter was being improperly logged. This patch fixes this issue with the OData v4 adapter for better logging in case of runtime errors.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_yhv_dzb_2qb"/>

## 02 July 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.15.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The tenant provisioning is unsuccessful, and the tenant URL is exposed to the customer. When you click the URL the tenant does not work as expected.

This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_pqw_3ff_dqb"/>

## 01 July 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.15.11

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Tenant Provisioning Issue**

The timeout value for tenant provisioning has been made configurable.

This has been done with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_a24_dmq_cqb"/>

## 30 June 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.15.10

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

There were thread problems occuring under high load.

This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_jqd_xcy_1qb"/>

## 22 June 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.22.15

6.14.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

There has been an issue with the FTP adapter when using it with the Cloud Connector \(*Proxy Type* set to *On-Premise*\). Due to problems establishing the connection through the Cloud Connector, certain files haven't been stored on the FTP server.

This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_jrh_x3z_ypb"/>

## 16 June 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.14.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Deployment of integration flows took an unexpected long time or even failed in certain special situations. This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_r1w_frm_ypb"/>

## 14 June 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.22.14

6.14.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issues have been fixed with this patch:

-   Processing of integration flows using JMS queues has been stopped, undeployment failed, and the affected runtime node had to be restarted.

-   When using integration flows with a JMS sender adapter, messages went into blocked state if multiple large messages were processed in parallel.




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_cvx_yhg_ypb"/>

## 14 June 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.22.13

6.14.11

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

There have been issues when deploying integration flows that contained message mappings using WSDL/XSD with external references.

Further-on, issues have been reported related to the deployment of OAuth2 Client Credentials Artifacts. Both issues have been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_i5s_r5t_wpb"/>

## 09 June 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.22.12

6.14.10

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Integration scenarios configured with XI adapter against a PO adapter engine stopped working because of a null pointer exception. With this patch, we’ve removed the null pointer exception.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_jfc_dvh_5pb"/>

## 31 May 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.22.11

6.14.9

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Size of package increased after export. This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_kwk_chw_spb"/>

## 23 May 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Integration Advisor

</td>
<td valign="top">

1.47.3

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

While generating runtime artifacts in Cloud Integration, you would have encountered an error in IDoc preprocessing. This was because the preprocessing XSLT was not generated in a way the messages with nested qualifiers could be processed correctly. This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_o2x_5yg_ppb"/>

## 16 May 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.13.16

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix and Performance Improvement**

With this patch, we have provided the following:

-   Added additional processing steps for better analysis, when you face a problem while storing MPLs.

-   A video on SAP Integration Suite, appearing on the Suite dashboard, was locked as private as part of content clean-up. Now, we have changed the video’s privacy settings and is made public.




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_uxf_z1h_ppb"/>

## 16 May 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.21.8

6.13.16

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Enhancement**

After the recent software update, you’ve encountered an error while transporting integration packages between Cloud Integration tenants. The error here was displayed when you did a configuration check.

*Unable to fetch OAuth Token, Token value is null*

A bug in the code was identified and is fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ffw_ysx_4pb"/>

## 16 May 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.13.15

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Enhancement**

With this patch, we have now enabled the Database \(DB\) connection pool for the tenant deployed on Cloud Foundry environment and the connections to the DB are regulated.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_rds_swl_4pb"/>

## 9 May 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.13.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

With this patch, we have resolved an issue with the wrong user view of designer workspace generated in message monitoring. This issue was fixed by using the ID to calculate the URL instead of name.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_vz4_ryl_4pb"/>

## 9 May 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Integration Advisor

</td>
<td valign="top">

1.47.2

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

There was an issue with breadcrumbs navigation from MAG Details screen. The screen was retaining the information related to the previously opened MAG’s model and was giving incorrect results or proposals during runtime. With this patch, the issue has been fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_fgy_vjj_4pb"/>

## 1 May 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.21.06

6.13.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

With this patch, we have:

-   Fixed the synchronization issue caused by duplicate sequence numbers of NRO that got generated because of the race condition. This issue was fixed by introducing Postgres Advisory locks.

-   Improvised the outbound error handling. Now, you can view the details of the outbound errors, which were displayed directly in MPLs.

-   Fixed an issue that occurred while deploying security materials. You couldn’t earlier deploy security materials of the type *OAuth2 SAML bearer assertion* for target systems of type **SAP BTP, Neo and **SAP BTP, Cloud Foundry.




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_lmn_5w4_lpb"/>

## 28 April 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.36.8

5.20.10

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

There have been issues with correct charging of test connections with the purchased SAP Cloud Integration tenant.

These issues have been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_bvt_j4j_lpb"/>

## 28 April 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Integration Advisor

</td>
<td valign="top">

1.46.4

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

There was an issue with integration content development using SAP Integration Advisor.

The mapping list table wasn't loaded with mapping information. Instead of this, the message `No Data` was shown. This patch contains the fix that gracefully handles a key customer scenario affected by this issue.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_cmm_c4j_lpb"/>

## 21 April 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Integration Advisor

</td>
<td valign="top">

1.46.3

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

There was an issue when SAP Integration Advisor loaded a message implementation guideline \(MIG\) or a mapping guideline \(MAG\) with a property of type `direction` or `status`. In certain cases, a health check was caused and an alert in Service Provider Cockpit was initiated. This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_kwj_fnq_hpb"/>

## 16 April 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.36.7

5.20.9

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

Deployment of OData APIs failed.

This issue is fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_b5f_sx2_dpb"/>

## 09 April 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.12.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Performance issue** 

There was an XSUAA service broker issue.

This issue is fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_mns_tv2_dpb"/>

## 31 March 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.35.9

5.19.9

6.11.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

Update `XStream` to version 1.14.16.

The issue is fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_lmr_1v2_dpb"/>

## 31 March 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.11.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

The OData v4 adapter couldn't serialize decimal values less than "0.1". Any payload containing valid decimal values less than "0.1" was being invalidated by olingo and as such the customer was blocked.

This issue is fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_lhh_xh5_bpb"/>

## 25 March 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

1.45.4

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

Customer reported an issue in integration as well as unavailability of Integration Advisor.

This issue is fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_mfs_234_bpb"/>

## 25 March 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.11.11

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

When using AS2 sender channels with Quality of Service *Best effort*, negative MDN has been received. This was also the case when the integration flows have been processed successfully and messages have been reaching the target system.

This issue is fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_chf_bqs_1pb"/>

## 17 March 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.11.10

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Performance Issue** 

Customer has reported performance problems using ProcessDirect call.

These issues are fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_lx5_dbh_z4b"/>

## 16 March 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.19.6

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

Customers have reported performance problems processing files via the SFTP adapter.

These problems are fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_jm2_fyz_y4b"/>

## 15 March 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.11.9

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

Problems with the access policies update \(for JMS queues and data store content\) are fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ck3_11x_x4b"/>

## 15 March 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.11.8

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

Issues with the Web user interface \(problems with filter and search in *Discover* section\) are fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_mtv_xbh_z4b"/>

## 10 March 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.35.5

5.19.5

6.11.8

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

Usage of the OData V4 adapter `$batch` feature was affected due to an issue with the Olingo libraries \(hard-coded timeout configured for requests that can't be overridden today\).

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ffw_tck_x4b"/>

## 03 March 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.34.11

5.18.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

This patch was provided to enable the JMS retry behavior.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_m5q_kck_x4b"/>

## 02 March 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.10.15

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

The patch was released to mitigate an issue with the Kafka Root Certification.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_mhk_bck_x4b"/>

## 26 February 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.34.10

5.18.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Security fix** 

A security vulnerability was found with XMLBeans \(2.6. 0 version\) and it didn't protect the user from malicious XML input. To prevent such attacks, the XMLBeans was upgraded to 4.0.0.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_mc1_xbk_x4b"/>

## 26 February 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.10.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

High usage of CPU and thread exhaustion was leading to downtime of those microservices that were consuming configuration services. This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_x5s_qbk_x4b"/>

## 23 February 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.10.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

A bug was discovered with the Solace message broker. With this patch, a fix is applied.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_yhl_cbk_x4b"/>

## 22 February 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.34.8

5.18.10

6.10.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

The patch fixes the following issues:

-   Users with zonified account type were unable to make RFC connections. This was because the RFC connection was using the Tenant ID instead of Subaccount ID.

-   Escape character “\_” is not handled properly during migration from Process Integration system to a Cloud Integration tenant.




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_gbd_1w1_s4b"/>

## 19 February 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.10.11

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

The URL in instances for OData sender response contained wrong HTTP scheme and port.

This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_tvn_5t1_s4b"/>

## 10 February 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.33.13

5.17.16

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

There was an issue with repeated deployments of artifacts \(for example, integration flows\) on the worker nodes resulting in system downtimes.

This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_etc_msn_p4b"/>

## 9 February 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.10.10

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

There was an issue with the creation of service instances for your tenant.

This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_d4v_sv1_s4b"/>

## 9 February 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.10.8

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

There was an issue with getting updates for integration packages \(copied via the OData API\) after migration to Cloud Foundry.

This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_tbr_y4v_n4b"/>

## 3 February 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.33.12

5.17.15

6.9.22

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

The following issues have been fixed with this patch:

-   The system by default appended a charset parameter in the `Content-Type` header when the content-type was `text/*`.

    This caused problems for endpoints that do not expect charset parameter.

-   In certain cases, scenarios using the Mail sender adapter run into concurrency problems that delayed message processing. It could happen, that unrelated integration flows with a Mail sender adapter shared the same lock. Note that the Mail sender adapter requires a lock in order to poll messages \(*Lock Timeout* parameter\).




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_l4r_zj1_n4b"/>

## 1 February 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.9.20

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

The issue with system deployment getting stuck in the step for the App Router is solved.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_xgk_fhw_l4b"/>

## 28 January 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.9.19

3.33.11

5.17.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

The issue with the "parser expanding external entities by default. An attacker can nest external entities in what is known as a "Billion Laughs Attack" that causes excessive memory consumption and potentially crash the Jersey instance" has been fixed.

Furthermore, a Job Scheduler issue has been fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_yy2_hfw_l4b"/>

## 27 January 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.9.18

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Design issue fix** 

We provide the patch for : "the lack of loading of the keys of resources in the root web app in the corresponding framework".

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ryq_r3r_j4b"/>

## 20 January 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.31.29

5.15.30

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

When a GET request is triggered for OData Sender, integration flow for different operation is getting triggered. Logs have been added to analyze the issue.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_fc4_hhr_j4b"/>

## 20 January 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.31.28

5.15.29

6.7.44

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix and Performance improvement** 

We improved the performance and the fix solves the issue with integration flow deployment stuck in "starting" state.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_fx1_tbc_j4b"/>

## 18 January 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.15.28

6.7.43

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

The fix ensures that no Empty Cookie header is populated. Cookie header is added only when there are valid cookies stored for the endpoint.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_zy5_gpz_h4b"/>

## 14 January 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.31.27

5.15.26

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

A new system property is set on the worker nodes of the customer tenant, to be able to update the customer to the newer CPI release.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_c22_lmb_j4b"/>

## 09 January 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.15.25

6.7.40

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

An integration flow deployed with the HTTP Receiver adapter \(version: 5.x\) encountered an error stating “Too many open files”. This error occurred when the file descriptors upper limit is reached. With this patch, the issue has been fixed by sharing the resources across all adapters in the tenant.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_gdf_3lb_j4b"/>

## 08 January 2021

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.31.25

5.15.24

6.7.39

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

When you encounter the *UniquenessViolationException* while importing an integration package from TMS/CTS+, the package and artifacts gets locked. As a result, the subsequent import fails and throws an “Could not acquire lock” error. You can release the lock by logging in to your Cloud Integration tenant and unlocking the package and the artifacts.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_kml_4n5_b4b"/>

## 21 December 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.31.23

5.15.22

6.7.37

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

In version 1.0 of the ProcessDirect adapter, a regex constraint check was provided for the *Address* field that didn't allow the address to end with a special character. This check has been removed in version 1.1 of the adapter.

Assume that before the bugfix the address `MY_ADDRESS_{{My_ID}}` has been specified. In that case, the value `My_ID` couldn't be found by the system, which resulted in an effective address `MY_ADDRESS_`. As a consequence, an infinite regex check loop crashed the design service.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_sf3_nnm_b4b"/>

## 18 December 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.31.22

5.15.21

6.7.36

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

TLS connection error occurred when you deployed an integration flow that had OData orAS2 receiver adapter. This error was caused when the tenant keystore contained multiple key pairs. We have resolved this error by changing the keystore \(from the JCEKS keystore to the IAIKKeyStore\).

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ajn_lzj_14b"/>

## 18 December 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.7.35

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

Fixed: Ongoing issues with outbound message failures. \(AS2 & OData receiver adapter \)

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_o1j_tl4_znb"/>

## 15 December 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.7.35

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

This patch fixes the issue with the software update \(DB call\).

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ydz_h1x_xnb"/>

## 09 December 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.7.31

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

There were issues with `xstream` version 1.4.11. Upgrade to version 1.4.14 fixes this issue.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_r4l_3zw_xnb"/>

## 09 December 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

6.7.31

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

This patch fixes an issue in message mapping. \(An error message came up if the number of nodes in message mapping was greater than 10\).

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_jwv_yqv_5nb"/>

## 26 November 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.14.18

6.6.20

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Code Change** 

Content-Length entity header belong to an HTTP request didn’t pass through the HTTP servers leading to a failure of an integration scenario. With this patch, a code fix was provided to the library used by the HTTP Receiver adapter to rectify the failure.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_o1d_vpv_5nb"/>

## 24 November 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.30.22

5.14.18

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

When using RFC adapter, you would have encountered “Maximum number of RFC connections reached” error. This patch enables JCo connections log for monitoring the connections. The information in the log helps you to troubleshoot the reason during communication.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_wnt_xkq_snb"/>

## 20 November 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.30.21

5.14.17

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Code Change** 

An error occurred while accessing the data source configuration due to absence of null check. With this patch fix, null check is implemented along with the necessary actions to be performed upon a null value detection. Even if data source configuration is not redeployed after software update, the system will work as expected without any error.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_xzg_tgs_rnb"/>

## 12 November 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.30.20

5.14.16

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

This patch resolves issues with delayed message processing in case JDBC data sources are involved.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_oqr_pyh_qnb"/>

## 11 November 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.30.18

5.14.14

6.6.18

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

This patch resolves an issue with the number range service \(returned duplicate number in concurrent scenarios\).

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_kk5_zdp_4nb"/>

## 3 November 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.30.17

5.14.13

6.6.17

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Code Change** 

This patch fixes an issue found when you use JDBC Receiver adapter to execute stored procedure on SAP ASE database.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_mr4_1cp_4nb"/>

## 29 October 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.30.16

5.14.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Code Change** 

Japanese characters were lost from the payload when UPSERT requests and responses are made to SuccessFactors system from an integration flow. The SuccessFactors OData Adapter didn’t correctly handle the UTF-8 encoding of Japanese characters in the payload. The issue is resolved with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_bft_51p_4nb"/>

## 28 October 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

5.14.11

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

This patch resolves an incompatibility of Java Cryptography Extension \(JCE\) policy with newer version of Apache Karaf runtime 2.56.0.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ctp_5y4_4nb"/>

## 27 October 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.30.15

5.14.10

6.6.16

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Design Change** 

This patch resolves the issue related with JDBC Receiver adapter. Now a mechanism is introduced to handle the situation wherein the Kafka event is not received while creating a data source. This makes the adapter more robust at runtime.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_dph_kx4_4nb"/>

## 21 October 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.30.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

An error occurred while deploying credentials from Data Store at runtime. When you edit and save the credentials in the Data Store, the credentials where supposed to remain in the password storage. But during deployment these credentials were deleted from the password storage. This issue is resolved with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_l5w_vfq_4nb"/>

## 20 October 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.30.12

5.14.10

6.6.15

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Code Change** 

This patch provides an update for the following adapters:

-   OData V2

-   SuccessFactors OData V2

-   OData V4


The OData query had generated a faulty XSD schema and the schema was unusable in the mapping step modeled in an integration flow. With this patch, the fault in XSD has been fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_dzl_3xp_hnb"/>

## 10 October 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.29.24

5.13.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Design Change** 

With this patch update, we have now optimized the credential deployment to reduce the delay in refreshing the credentials during runtime.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_njn_pw5_gnb"/>

## 07 October 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

4.16.26

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

This patch solves the CPI Number Range Service Duplicate issue.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_yph_xrf_gnb"/>

## 07 October 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

4.16.25

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Design Change** 

The TRM now aborts the software update task for a tenant that has been stuck in a particular state for a certain amount of time, in order not to block other tenants. This issue is resolved with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_wgq_lnr_fnb"/>

## 01 October 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.29.23

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

This patch fixes the issue with the mailbox locking mechanism: the username will now be considered for the lock, so that there will be no concurrent polling of the mailbox.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_shx_plr_fnb"/>

## 01 October 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.29.23

5.13.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix** 

This patch fixes the issue with the SFTP server: temporary file name will now be set correctly on SFTP server.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_trk_thr_fnb"/>

## 29 September 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.29.22

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Feature Gap**

This patch

-   allows you to handle endpoints in exception subprocesses.

-   improves parent-child relationship in case of multiple nesting levels between the main integration process and the local integration process.

-   allows to treat all as single connection based on property if property names are same, but with lowercase/uppercase letters in between.

-   allows the handling of SAP endpoints originating form the same tenant host.

-   fixes the issues related to the parsing host `https://host:port/${property.path}`

-   allows the adding of integration flow details along with sender adapter type/receiver adapter type info, if multiple connections exist in the same integration flow.




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ils_h5x_cnb"/>

## 25 September 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.29.21

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Feature Gap** 

Ensured UTF-8 encoding was being honored while providing argument to XML Parser. The default encoding of the library ISO-8859-1 was being followed before.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ebw_2gx_cnb"/>

## 25 September 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.29.20

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Feature Gap** 

The new alert for critical Solace queue capacity does now also yield when APIs throw an exception.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ckb_5rw_cnb"/>

## 25 September 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.29.19

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Extended Feature**

JMS move feature was extended by adding short sleep statements and optimized connection handling . The patch enables the extended move feature.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_yyc_w4c_cnb"/>

## 23 September 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

4.16.21

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This fix removes the validation on parameter length that was introduced as part of a security feedback for the Content Transport implementation in CF, and allows now SAP shipped standard content being transported in customer's QA tenant if the package ID is larger than 190 characters.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_t4l_cwy_1nb"/>

## 18 September 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

4.16.20

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch allows the outbound communication to work on the tenants using sap\_cloudintegration certification \(with an SAP provided keypair\), by identifying and migrating all certificates without complete chain to have the complete chain.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_v53_2pq_1nb"/>

## 16 September 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.17.4

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch removes the incompatible change introduced by platform with CIS 2.0.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_grr_gnq_1nb"/>

## 16 September 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.17.4

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch updates the `sap_cloudintegrationcertificate` with missing certificate chain.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_wjy_dyd_ymb"/>

## 08 September 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.29.17

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch release fixed an issue related to the cluster lock mechanism \(logging has been improved\).

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_slh_11n_wmb"/>

## 02 September 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.29.15

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch release provides the following bug fixes:

-   Platform resiliency related to temporary network unavailability has been improved. In particular, temporary network unavailability for the password store caused the caller applications to fail. With this fix, there won't be any downtime any more caused by such issues. Before the fix, calls to the password store used to fail with this exception: `[CONTENT][CONTENT_DEPLOY][ErrorRetrievePassword]:Error retrieving password for alias: <alias_name>, An error occured while trying to get password with alias.`

-   A two-minutes spike has been observed in every call that is made to the platform in a high fidelity usage \(where accuracy on the retrieval of password fetch in a high load situation is expected\). This issue reduced the turnaround time and induced delays in message processing. With the patch, the performance has been improved. As a result, you do not face any delay in a continuous message processing load any more.

-   A change has been made in the data store coding that might work around an issue with the JDBC driver for the tenant database \(error message: `Cursor 'jconnect_implicit_17' was declared with a FOR UPDATE clause. This cursor was found to be read only.`\).




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_e44_qbf_wmb"/>

## 31 August 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.29.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The fix is related to the ELSTER adapter. The version of the ERiC libraries has been updated to 31.7.8.0 according to a requirement by the German Tax authorities.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_xlc_fjy_4mb"/>

## 06 August 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

4.15.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

1. Life time reduction of refresh token issue

With the fix on expiry of the refresh token, a new token will be requested for all CF Trial and Prod. customers.

2. Software update got stuck due to unreceived notifications of deleted CPI tenants.

The fix avoids calling CIS and update task can be performed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_qmc_d3y_4mb"/>

## 06 August 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.28.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

When high number of rfc calls are executed in parallel\(more than 50\),it can be that response for two different requests are getting mixed up

Code is now more threadsafe using threadlocal variable.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ctf_4tp_4mb"/>

## 04 August 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

4.15.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfixes**

The fix is to construct always CMDVariantUri instead of using already existing one

Regeneration of Custom Adapter & fetch All Capabilities APIs has to be thread Safe in Regeneration Tool. The fix makes those APIs Thread Safe.

In Message Flow Check there is a Validation to check whether Nested Externalized Values are present in Prop file or not. Parameterized Values are coming as empty to Message Flow Check because the values are not set. The fix is we set the values so that the Validation Error doesn’t occur.

Application logs have been strenghthened.

IFLW file doesn’t have BPMNElementId for BPMNPlane, this value is collaborationId. Due to this, there is a Null Pointer Exception. The fix adds a Null check. If collaborationId is null, then the will be from Collaboration Model.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_zdy_lzk_mmb"/>

## 28 July 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

4.14.17

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfixes**

With this patch, the "Retry Exhausted" issue on the SAP Integration Suite is fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_h5k_rx1_jmb"/>

## 15 July 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.27.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

With this patch, the JDBC adapter has been enabled to support batch processing using PreparedStatement objects for sending SQL statements to the database, provided the system property for alias has been set.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ujp_hnz_hmb"/>

## 9 July 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.27.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

When you use a Parallel Splitter step in an integration flow configured with an OData v4 receiver adapter, the message splitting fails due to the sharing of tenant resources by these multiple split messages. The issue with parallel processing is fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_lyt_rjz_hmb"/>

## 7 July 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.27.11

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Uploading key-pairs into your tenant keystore using the signature algorithm *SHA256withRSAandMGF1* in the X.509 certificate was not possible. But now with this patch you can upload them to the keystore.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ww5_2kz_hmb"/>

## 7 July 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.27.10

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

An exception occurred while processing message in JDBC adapter. This was caused due to high memory consumption from the destination database. To resolve this `PreparedStatement` was used and `dynamic_prepare` property was enabled. This patch contains these changes made to the JDBC adapter.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_qhx_tcz_hmb"/>

## 30 June 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

4.14.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

-   Software update/rollback was failing for couple of tenants deployed on Cloud Foundry environment. With this patch this issue is resolved.
-   A bug was found while instantiating the configuration service. This issue occurred due to a bug in the code and with this patch the issue has been fixed.




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_drg_dly_hmb"/>

## 30 June 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.27.6

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Umlaut or special characters, found in the request and response payloads, are not supported by OData v4 receiver adapter. Earlier these characters where replaced by some unknow values. With this patch OData v4 receiver adapter supports umlaut characters.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_hh3_53g_bmb"/>

## 16 June 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.26.9

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The enhancements for session csrf reuse which cause intermittent failure with session reuse are reverted with this patch version.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_fg5_1r2_bmb"/>

## 16 June 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

4.13.17

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Downport of prescript**

Format has been adapted: additional lines were removed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ocr_hyx_1mb"/>

## 15 June 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.26.8

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issue has been solved:

Issue in the mail adapter. A configuration change solved the issue.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_c4r_cjs_rlb"/>

## 07 May 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.24.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issue has been solved:

In case of an error with a connection using the OData Sender adapter, incorrect JSON content has been returned.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_j5z_4yc_rlb"/>

## 04 May 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.24.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

API used to perform `DELETE` operation for removing integration packages \(configure-only content\) from your workspace failed to respond. This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_djd_bd1_glb"/>

## 03 April 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.22.17

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

When inputs for the ASE database service \(connected with the JDBC adapter\) occurred at a high rate, in certain cases the database pool reached its limit and caused an insufficient procedure cache error. With this patch the issue has been fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_n31_1df_flb"/>

## 25 March 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.22.16

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issues have been solved:

-   You encountered an error while configuring the *Key Info Content* parameter in XML Digital Signer \(version 1.2\). Now this error is fixed.

-   A bug was noticed while configuring relative XPath expression in General Splitter. As per the configuration the splitter processed only the first entries of the payload and the rest of the entries in the payload were ignored. The bug has been fixed now.




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_hx5_tv2_flb"/>

## 20 March 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.22.15

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Database query timeout value was changed from seconds to milliseconds causing the DB index update job to fail. This was also the cause of incompatibility issue with the EclipseLink update. With this patch the issue has been fixed by setting the unit of time to seconds.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_hxh_vbd_flb"/>

## 17 March 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.22.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Refer resolution provided for OData Sender adapter on 6 March, 2020 \(version 3.21.23\).

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_lz1_hhf_ykb"/>

## 6 March 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.21.23

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issues have been solved with this patch:

-   When using an OData Sender adapter, the conversion of the original request payload to XML was not working as expected. This was because the EDMX schema of the OData Sender had same navigation property name for different navigation entities.

-   During high load message processing scenarios, BAT worker nodes used to get into out of memory state. Unfortunately, proper logs weren’t generated to analysis the issue. With this patch we put a mechanism in place to capture the runtime behavior logs for better analysis.




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_a1b_ftz_wkb"/>

## 28 February 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.21.21

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

When sending an acknowledgment, the AS4 adapter was failing while parsing the document. This was due to the fact that the incoming document did not contain a namespace prefix. With this patch, this condition is now handled in the right way.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_bp2_ppz_wkb"/>

## 27 February 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.21.20

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Processing of integration flows that contained HTTPS sender adapter version 1.0.0 failed.

With this patch, this issue has been fixed

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_l12_bpz_wkb"/>

## 21 February 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.21.18

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Messages \(containing mail attachments\) were not processed by the receiver system due to wrong transfer encoding on mail attachments.

With this patch, this issue has been fixed

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ks2_fyj_rkb"/>

## 11 February 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.20.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Scenarios using AS4 in the PEPPOL network were failing after partner AS4 endpoints have been updated with the eDelivery profile. With this patch, this issue has been fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_bdj_kfh_qkb"/>

## 09 February 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.20.11

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

As per the security configuration or requirement you must allowlist XML namespaces used in an integration flow. The new version of XML to CSV converter \(1.1\) introduced validation to support only the allowlisted namespace. But if you have the older version of the converter \(1.0\), then the validation caused an issue and the payload returned empty from the converter. With this patch, we have enhanced the versioning of the feature to support your existing integration scenario.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_trc_yqc_pkb"/>

## 26 January 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

4.8.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Access was denied to Cloud Integration service broker instance while performing authorization using User Account and Authentication \(UAA\)-API. This issue is fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_xlw_4kl_mkb"/>

## 24 January 2020

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.20.8

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch contains a correction of a connectivity problem with the XI receiver adapter that may have occurred under specific circumstances.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_yrg_qnq_ckb"/>

## 20 November 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.18.10 or 5.3.9

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Runtime node \(worker node\) crashed when integration flow using ELSTER receiver adapter was deployed. With this patch update, the issue has been fixed and now you can send tax documents to the ELSTER server.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_l3p_5hy_rjb"/>

## 06 November 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.17.11 or 5.2.9

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issues have been solved with this patch:

-   Integration flow CRUD actions have been blocked, and customers were unable to modify their integration flows caused by an issue with the handling of the related OSGi bundles of the SAP Cloud Integration framework.

-   A memory shortage issue has been solved which was caused by a high number of SAP Cloud Integration OData API requests and a memory leak in the OData API framework.




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_q3v_vhb_t3b"/>

## 21 August 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

4.2.0

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch improves the stability of the tenant onboarding process.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_lyq_vhb_t3b"/>

## 24 July 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.13.9

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

There have been inconsistencies in the infrastructure caused additional nodes being launched after restart of multiple runtime nodes. This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_khv_pfp_m3b"/>

## 18 July 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.13.8

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

An error occurred in the design workspace when you imported an earlier version of an integration package, and the actual integration package \(to be overwritten by the import\) had some unsaved changes. This error was due to an issue with the auto-save functionality and has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_fmz_hgj_k3b"/>

## 09 July 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.13.7

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Tenant update failed because latest tenant cluster model was unavailable in the tenant management node. This issue has been resolved with this patch and now the latest tenant cluster is available on the tenant management node.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_zrd_svp_f3b"/>

## 30 June 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.11.26

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

You would have encountered 403 Forbidden error while connecting with SAP’s Europe data center. The cause of the error was due to a problem occurred while establishing TSL/SSL communication. With this patch the issue has been resolved.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_umx_1fp_c3b"/>

## 14 June 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.11.24

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch fixes the issue that the rendering of the mapping editor depended on the order in which mapping steps are performed. A possible implication was that when the customer modified its mapping, the editor stopped opening.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_jyq_rbx_13b"/>

## 11 June 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.11.22

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

After updating the tenant with the latest Cloud Integration software version, the following improvements are available:

-   Integration flows are deployed faster on the runtime node \(worker node\) during software update and unplanned restarts or crashes.

-   The length of the key material supported has been increased.

-   Memory-related crashes with the tenant management node due to incorrectly deployed content has been fixed.




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ocm_jhw_13b"/>

## 4 June 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

3.11.21

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Deployment of integration content was failing due to an issue with persisting a certain artifact in the runtime.

This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_okr_kbx_13b"/>

## 31 May 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.53.19 or 3.11.20

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

You have integrated a Cloud Integration tenant with Ariba system and have experienced a missing multipart payload during inbound AS2 communication. This issue was caused while verifying the signature of the multipart files and it was found that a mandatory **AS2 header: Content-Description** was missing. With this patch, the header is made optional and the error is resolved.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_rjm_g52_b3b"/>

## 23 May 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.53.18 or 3.11.19

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

With this patch, the size limitation of the keystore and certificate-to-user mapping \(originally, 1 MB\) has been increased to 2 MB.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_g1d_tvd_b3b"/>

## 21 May 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.53.17 or 3.11.18

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The optional *Scope* parameter has been added to the *OAuth2 Credentials* artifact \(when as *Grant Type* the option *OAuth2SAMLBearerAssertion* is selected\).

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_bnh_1pf_xhb"/>

## 17 May 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.53.16 or 3.11.17

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

If you have experienced integration flows in failed state after deployment with an error `class not found exception javax.sql.Datasource` , this issue occurred due to an error in the backend. With this patch, the issue is fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_tkq_qpz_5hb"/>

## 16 May 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.53.15 or 3.11.16

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

If you use XSLT mapping version 1.2 for processing a payload that has an attachment exceeding 100 KB, then the message processing goes to failed state. This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_lwx_24z_5hb"/>

## 15 May 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.53.14 or 3.11.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch fixes all performance related issues experienced during monitoring phase. Due to this issue, the integration flow deployment took longer than usual time.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_anx_by1_thb"/>

## 14 May 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.53.13 or 3.11.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Due to a recent change in software, if there are multiple components with same name then the integration flows corresponding to those components stay in STARTING state. This patch version fixes this issue.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_em3_xbb_rhb"/>

## 4 May 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.52.12 or 3.10.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

If you store JSON attachment in a message using Content Modifier, the content of the attachment was not being displayed on the monitoring page. This issue has been resolved with this patch. Now the content of the attachment is being displayed in the monitoring page.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_gfb_ydx_hhb"/>

## 3 April 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.51.13 or 3.9.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Recent optimizations to the message mapping feature missed to account for an edge case with variables. Due to this, the XPath expressions used in the variables got corrupted on edit and save of mappings. The patch fixes this problem.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_wmf_qph_hhb"/>

## 2 April 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.51.12 or 3.9.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

You would have encountered a failure while deploying an integration flow. This issue is due to a limitation in the field size for artifact metadata \(to be stored during deployment\). The patch fixes this problem.

</td>
</tr>
</table>





<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_phl_ct1_1hb"/>

## 7 March 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.50.16 or 3.8.15

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

You would have encountered a failure while deploying an integration flow. This issue is due to the incompatibility of the manifest file \(version 1\) with Karaf runtime. Now the issue is fixed with this patch update and you need to redeploy the integration flow.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_xzp_v1t_xgb"/>

## 27 February 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.50.15 or 3.8.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

During integration flow deployment the file upload scanner was rejecting the integration flow bundle. The issue occurred because the file upload scanner identified the bundle as corrupted and rejected the bundle. The issue has been resolved with this patch release.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_wpf_ffn_xgb"/>

## 24 February 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.50.14 or 3.8.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

`IntegrationRuntimeArtifacts` API was designed to deploy the integration flow bundle sent through the API at runtime. It was found during deployment it was not considering the configured values. This bug has been fixed in this patch.

It is recommended to deploy any design time integration flow artifact by using `DeployIntegrationDesigntimeArtifact` entity found in `IntegrationDesigntimeArtifact` API.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_t3z_1yn_vgb"/>

## 19 February 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.50.13 or 3.8.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The design time page was not responding after the content package update. This issue affected all SAP Cloud Integration tenants. It occurred due to an unexpected code error in the back end. A patch has been released and the issue is resolved.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_wxq_n5p_vgb"/>

## 16 February 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.50.12 or 3.8.11

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

User was not able to set the scope for *Oauth2* client credentials due to a bug. This issue has been fixed now.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_z33_hvm_qgb"/>

## 31 January 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.49.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

You were unable to open Message Mapping and an error was displayed. This issue was caused because the schema contained a definition that had a very huge value, such as “maxOccurs=9999999”. This issue has been fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_vxr_15m_qgb"/>

## 30 January 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.49.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Integration flows were not getting deployed if the HTTPS Sender endpoint contained “\*”, because the wildcard was not recognized. This issue has been fixed now.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_kc2_xdt_ngb"/>

## 22 January 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.49.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

An issue was found in integration flow scenarios connected to an OData API using OData Receiver adapter. During Update or Delete operations the adapter encountered issues when the Entity set had a composite key. The message processing log, returns an error with the message “The request URI contains an invalid key predicate”. This issue has been fixed with this patch.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_vzx_hdh_kgb"/>

## 7 January 2019

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.48.8

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

In HTTP receiver adapter, when you use Client Certificate Authentication and provide a private key alias as a dynamic expression, for example $\{header.abcd\}. The timeout provided by the customer was not working. The default timeout of 60 seconds was getting automatically applied. This issue has been fixed and timeout provided by the customer is being applied.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_g3z_3fs_dgb"/>

## 17 December 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.47.20

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The patch fixes an issue where integration flow endpoints were not accessible for a certain time period due to redeployment by the system.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_q1b_rp4_1gb"/>

## 05 December 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.47.16

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The patch fixes the WSDL download for SOAP adapter endpoints. The error was that the downloaded WSDL did not contain the generated policies anymore.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ntj_pp4_1gb"/>

## 05 December 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.47.15

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch fixes the following issue with integration content transport:

During the export of a package that contains an artifact that was auto-saved, the auto-saved one is also exported along with the package. This should not be case.

With the patch we have fixed the export of the content package. Also in case the package was previously exported, the system will not allow that the package is imported.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_j2w_dvh_1gb"/>

## 04 December 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.47.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch fixes an issue with the WebService interoperability with the tax authority of the Canary Islands.

Furthermore, the following issue has been fixed:

When a tenant has more than one runtime nodes and when an AS2 adapter is involved, it can happen that updates to message processing logs get lost. This is due to the fact that in such a scenario messages can be written to and read from a JMS queue during a short time period where, parallel to this, the processing of the integration flow continues. As such steps are logged in different message processing log \(MPL\) runs, the involvement of multiple runtime nodes could imply that different MPLs are written nearly at the same time \(leading to a Duplicate Key exception\).



</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_jrm_x21_1gb"/>

## 03 December 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.47.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch fixes the problem that the import of an integration package fails in case the package contains auto-saved artifacts.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_agq_rw1_1gb"/>

## 30 November 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.47.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch fixes the following problem: The alias for data source was on class level, which was not working on further calls to an endpoint. This was changed to local variable.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_f2t_gnr_yfb"/>

## 29 November 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.47.11

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This patch fixes a problem that occurs when you use the SOAP receiver adapter in conjunction with the trace feature \(that enables the tracing of the processed payload\). Certain combinations of elements in an integration flow can cause a type conversion error during message processing if the message processing log level *Trace* has been activated. The error occurs in the SOAP receiver channel. An example for such a combination is an HTTP call via HTTP adapter before the SOAP call. This can block the integration flow development process.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_cnk_kz1_yfb"/>

## 26 November 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.47.10

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The new version of the OData V2 adapter \(adapter version 1.12\) overwrote the existing version \(1.11 \). Therefore, existing integration flows that contained the adapter version 1.11 generated an error during design time. This issue has been solved.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_olf_yw1_vfb"/>

## 17 November 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.46.16

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

There was a bug in the Apache Olingo library which implied the following behavior: batch responses with exactly 8192 objects resulted in a BufferOverflowException which was then followed by a failure of message processing. This issue is fixed now.

Furthermore, this patch provides a resolution for an issue reported on loading of artifact lists in the Design tab of the Web UI.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_js3_qzl_sfb"/>

## 10 November 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.46.15

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The test and production tenant configurations for ATO are different. While fetching the SAML token from Vanguard the AS4 adapter uses the destination URL. During this process, the destination URL was assigned to the*AppliesTo* field and this resulted in message failure. This issue is solved by specifying the header `SAP_AS4_Outbound_ATO_SAML_AppliesTo` with a value provided by ATO.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ffp_tn4_rfb"/>

## 30 October 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.46.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Failed Artifacts Monitor was introduced to report failed artifacts. When this monitor was applied to all clusters, there was an issue occurred to content in failed state. The alert level for failed content was raised to 'Aggregated tenant availability’. This issue is now fixed and actual alerts detected.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_d31_tn4_rfb"/>

## 29 October 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.46.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

While implementing OData APIOData API, an exception was thrown when Deep Insert functionality was used. The error was caused due a bug in the Apache Olingo library. This error has been fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_usq_tkg_mfb"/>

## 16 October 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.44.21

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

There was no mechanism to detect failed integration flows on worker nodes. Now build a managed component monitor called **ContentStateMonitor** whose display name is "Failed Artifacts Monitor" to check for failed integration flows and it reports if a failed integration flow is found.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_sgy_w41_mfb"/>

## 10 October 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.44.20

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Liquibase change logs where not getting applied to some clusters due to already held locks and issues where encountered while launching the clusters. This issue has been fixed by clearing all change logs older than 10 minutes.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ltr_gpf_3fb"/>

## 30 September 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.44.19

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

An exception was thrown when database could not save custom header attribute values exceeding 200 bytes. It was found that the database reserved only 200 bytes for specific data types. This issue has been fixed and now when characters exceed 200 bytes it is rendered to UTF-8 standards and truncated.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_kwy_fpf_3fb"/>

## 29 September 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.44.18

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

**StreamClosedException** error occurred while running the **EnrichArtifactManifestTask**. During runtime the task adds `javax.sql` in the manifest file of the OData APIs and integration flow packages. This error has been fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_sn5_2jb_ffb"/>

## 21 September 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.44.17

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

XML escape characters such as `&amp;,&lt;,and so on`, appeared as it is during runtime and this caused deployment issues. This issue is now fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_lqn_jhb_ffb"/>

## 16 September 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.44.16

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

During design when an external parameter in *Write Variable* is selected a check error was thrown. The workaround is if the integration flow is editable and not a standard content, then you must change the value in *Type* field to a constant instead of external parameter.

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

During runtime the XSLT Mapping created empty output files. This issue is now fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_qry_tws_dfb"/>

## 15 September 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.44.15

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The integration flow fails when you add ‘&’ character while externalizing the Endpoint field in a SOAP receiver adapter. This issue is now fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_tt4_lxs_dfb"/>

## 12 September 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.44.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

During runtime, integration flow sometimes do not record complete logging information in the MPL. This issue is now fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_o12_nxs_dfb"/>

## 11 September 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.44.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The route to send asynchronous messages in an XI receiver adapter is not generated during runtime. This issue is now fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_qzv_2gx_y2b"/>

## 11 August 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.43.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Before the values in the *Maximum Characters Retrieved from Tweet* field could not be externalized, but now you can externalize the values.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_zd3_yy4_t2b"/>

## 09 August 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.43.11

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Content Modifier component was not displaying headers or exchange properties for pre-externalized parameters of a Scheduler. This issue has been fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_rw3_x4p_p2b"/>

## 27 July 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.42.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This issue occurs when you have not requested for an acknowledgment and *Process Invalid Messages* option is selected during EDI Splitter runtime. If an error occurs at the interchange level of an EDIFACT message type. It was not possible for an integration developer to resolve this error because no exception was thrown. This issue has been fixed and now an exception will be thrown for every error occurring at the interchange level.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_gj4_c2b_42b"/>

## 21 July 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.42.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Intermittent calls to a Hybris OData endpoint createlatform a new session on Hybris. This causes the Hybris service to return HTTP Status **403 or 502 or Target Server Failed to Respond** errors with high load. This issue has been fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_udp_dgp_m2b"/>

## 18 July 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.42.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Integration scenarios using OData V2 adapter returned with HTTP status codes and this impacted the business logic during runtime. This issue has been fixed for OData V2 adapter from version 1.7 and above.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ull_zpv_h2b"/>

## 30 June 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.41.10

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

It was observed during OData v2 adapter runtime, **401 Unauthorized** error caused credential cache update to fail. This issue has been fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_hsm_fvq_g2b"/>

## 23 June 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.41.9

</td>
</tr>
<tr>
<td valign="top">

SAP Integration Advisor

</td>
<td valign="top">

1.9.5

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

After management node restart, the content would get stuck in *Starting* state. This issue is now fixed.

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Under heavy load, it was observed that content synchronization was taking a long time and you could not deploy new content. This issue is now fixed.

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

For SAP Integration Advisor, when a qualifier value contained invalid XML QName character, the generated mapping XSLT was invalid as it contained the invalid character. This is fixed now.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_hz5_y45_22b"/>

## 18 June 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.41.8

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Verification of incoming message signature has been reverted to the old way. It does not involve any changes to channel properties.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_lsd_2yc_b2b"/>

## 2 June 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.40.14

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

A few Ariba transactions fail with exception `com.sap.it.rt.edi.exception.EDIHandlerException: Invalid Payload: EDI EXTRACTION cannot process the payload`. Extra logs have been added to AS2 adapter for checking incoming payload/headers.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_g2w_byc_b2b"/>

## 29 May 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.40.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

This fix is applicable only for integration flows with mail sender adapter. An issue in the mail sender adapter that unpacked the performance has been fixed. Redeploy the integration flows with mail sender adapter to activate the changes.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_bm3_h4d_zdb"/>

## 26 May 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Integration Advisor

</td>
<td valign="top">

1.18.4

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Upload of new type system revision was failing due to timeout. This has been fixed now.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_rbh_2cb_wdb"/>

## 19 May 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Cloud Integration

</td>
<td valign="top">

2.40.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

When you externalize the authentication parameters of SOAP and IDoc adapters version 1.0, it was not being displayed in the integration flow quick configuration. This is now fixed.

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

In HTTP sender adapter, if you have enabled adapter tracing and send a message with empty body, the message processing would be in *Error* state. This is now fixed.

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

In case of an exception triggered by *XML Validator*, message processing log \(MPL\) attachment, which is an XML Validator error document, was not being created. This is now fixed.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ks3_xsy_sdb"/>

## 5 May 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Integration Advisor

</td>
<td valign="top">

1.7.4

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

EDI to XML converter would deliver an XML output with namespace that is incorrectly qualified. With this fix, the EDI preprocessing XSLT script corrects the document namespace.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ucl_hhq_5cb"/>

## 7 February 2018

**Software Version**


<table>
<tr>
<td valign="top">

SAP Integration Advisor

</td>
<td valign="top">

1.4.7

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

While using SAP Integration Advisor, the mapping functionality would be unavailable until you removed documentation from the message guidelines. This is fixed now.

In SAP Integration Advisor, exported mappings using the UN-EDIFACT Type System failed at runtime because the generated namespace name is incorrect.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_fvx_h2p_rcb"/>

## 27 January 2018

**Software Version**


<table>
<tr>
<td valign="top">

Node Assembly

</td>
<td valign="top">

2.36.11

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

In scenarios with Ariba receiver adapter, the CamelHttpResponseCode in the exchange was wrongly set as a string instead of an integer. This resulted in you being unable to create RFP and sourcing project. This issue is fixed now.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_okg_5rx_pcb"/>

## 23 January 2018

**Software Version**


<table>
<tr>
<td valign="top">

Node Assembly

</td>
<td valign="top">

2.36.10

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

When you try to configure integration flows in standard content like *eDocument: Electronic Invoicing for Spain* where base version of SOAP, OData or SuccessFactors adapters are used, you see an empty error and the configuration will not be possible. This is fixed now.

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

In *XML Signature* steps that use XADES-BES with *Data Object Format* element, the attribute `ObjectReference` of `Data Object Format` element was being generated without the '**\#**' character at the beginning. This is fixed now.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_rlf_rlt_gcb"/>

## 23 December 2017

**Software Version**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.35.8

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

When the SuccessFactors OData API returned a server error to SuccessFactors OData adapter, the response XML was invalid due to erroneous XML encoding. This issue is fixed now.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_vb2_2qn_1cb"/>

## 30 November 2017

**Software Version**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.34.9

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Transactions were failing for some partners due to PD cache entries. Fix is provided by invalidating PD cache in such scenarios.

</td>
</tr>
</table>

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.34.8

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

Configuration changes are made to the database to fix excessive resource consumption issue. This fix will not require any additional downtime to reflect the changes.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_x2d_pj3_rbb"/>

## 27 October 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)

</td>
<td valign="top">

1.55.5

</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.33.5

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

**Message processing error**:

The integration flow processing fails and throws stack overflow error, if the package contains more number of messages. The issue is fixed by correcting the returned metadata.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_ghw_hgt_gbb"/>

## 20 September 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)

</td>
<td valign="top">

1.54.7

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

**Quick configure on the prepackaged integration flows**:

-   If you try to configure and enter a value for the empty field, the prepackaged integration flow, all empty values for the keys of configurable parameters are updated with the new value and it leads to the wrong configuration. This causes failure during message processing.

    > ### Note:  
    > This issue has no impact on the already deployed integration flows.

-   When a custom integration flow is built with content modifier in eclipse and is configured in Web UI, the empty values are set for the externalized keys, SAP Cloud Integration throws validation error. The issue has been resolved and setting the empty values for the keys is allowed irrespective of externalizing the parameters in Eclipse or Web UI environment.




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_hwx_c4r_gbb"/>

## 20 September 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.32.10

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issues have been solved:

**Quick configure on the prepackaged integration flows**:

-   If you try to configure and enter a value for the empty field, the prepackaged integration flow, all empty values for the keys of configurable parameters are updated with the new value and it leads to the wrong configuration. This causes failure during message processing.

    > ### Note:  
    > This issue has no impact on the already deployed integration flows.

-   When a custom integration flow is built with content modifier in eclipse and is configured in Web UI, the empty values are set for the externalized keys, SAP Cloud Integration throws validation error. The issue has been resolved and setting the empty values for the keys is allowed irrespective of externalizing the parameters in Eclipse or Web UI environment.


**AS2 and JMS Sender adapter with dead letter handling**: The error occurs during processing of integration flows that may have a AS2 sender adapter and JMS sender adapter with dead letter handling feature. Due to this error, the messages remain infinitely in the processing state. The workaround in such scenario is to disable the dead letter handling feature and retry again.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_yby_gjs_2bb"/>

## 12 September 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.31.10

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issue have been solved:

-   In certain cases, the following error message is displayed: *Error during polling for JMS messagesjavax.jms.JMSException: Error creating consumer - internal error \(503: Max Client Queue and Topic Endpoint Flow Exceeded\)*.

    This error only comes up in case large messages are processed in conjunction with external problems \(for example, network issues\). It is caused by a bug in the code that is in charge of handling large messages. This bug has been removed with the patch.

-   Unprocessed messages may remain in the JMS queue.

    This situation may occur under heavy load and with several active consumers. To avoid such problems, the settings for the interaction of SAP Cloud Integration software and 3rd-party components have been optimized.

    > ### Note:  
    > In order to benefit from this correction, you need to redeploy affected integration flows.


.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_pvx_1mq_bbb"/>

## 02 September 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)

</td>
<td valign="top">

1.53.6

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issue has been solved:

Task logs have been cleaned up to prevent database bloating which can cause outage.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_cd3_mtk_z1b"/>

## 25 August 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.31.9

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issue has been solved:

**Web IDE**: Due to some unknown issues pop up appeared several times and hindered the usage of the product. Pop up is disabled now.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_dvb_fyt_v1b"/>

## 12 August 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.30.17

</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)

</td>
<td valign="top">

1.52.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issue has been solved:

**Web IDE**: Due to some unknown issues pop up appeared several times and hindered the usage of the product. Pop up is disabled now.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_nwz_qls_v1b"/>

## 12 August 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.30.16

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issue has been solved:

**OData Query**: In case of multilevel response, some attributes were missing when the data was received from the server via SAP Cloud Integration. The properties are now generated correctly.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_mq4_v5w_r1b"/>

## 29 July 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.29.16

</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)

</td>
<td valign="top">

1.51.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issues have been fixed:

-   **WebUI Design Time Issue:** After editing a mapping with target groupings, saving that mapping was not possible. This is fixed now and you can save the mapping.
-   **JMS Adapter Message Handling:** You would see message status as *COMPLETED* instead of *FAILED* in case of handled errors.



</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_mkq_4vy_n1b"/>

## 13 July 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.29.16

</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)

</td>
<td valign="top">

1.51.13

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issue has been solved:

-   Selecting JMS messages from a queue, in certain situations leads to a minimal or none message throughput and/or errors. This affects JMS adapters as well as monitoring like Lock- and Queue Monitor.



</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_jxm_mvy_n1b"/>

## 13 July 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.29.15

</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)

</td>
<td valign="top">

1.51.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issue has been solved:

-   OData query calls are not following the metadata constraints.

    This scenario occurs when the metadata defines some property to be nullable false, but the property contains null values.




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_vfb_zfs_l1b"/>

## 07 July 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.29.13

</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)

</td>
<td valign="top">

1.51.10

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issue has been solved:

-   A cleanup job removes on a daily basis log configurations for integration flows which do no longer exist. Due to a wrong query, also for existing integration flows with different integration flow ID, the configuration gets removed.



</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_xpt_kf2_l1b"/>

## 03 July 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.29.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issue has been solved:

-   Due to buffering of JMS consumers, the number of consumers exceeded a limit in the Solace messaging service.



</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_syl_fb1_k1b"/>

## 30 June 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.29.10

</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)

</td>
<td valign="top">

1.51.8

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issue has been solved:

-   When the Data Store is locked due to long running transactions, no monitoring is possible.



</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_z3s_2tl_j1b"/>

## 28 June 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.29.8

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issues have been solved:

-   In some cases, you would see a runtime error in integration flows containing *Subprocess* with looping enabled, and invoking a *Local Integration Process* with *Multicast*.



</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_hg1_p22_c1b"/>

## 05 June 2017

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.28.10

</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)

</td>
<td valign="top">

1.50.9

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issues have been solved:

-   Unable to import integration package in WebUI workspace \(*Design* tab\)

    Due to a bug while exporting the integration package, configuration values of *Value Mapping* artifact was getting exported. Import function does not recognize the content and the action to import this package in the workspace \(*Design* tab\) fails.




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_b4d_zmk_b1b"/>

## 01 June 2017 - SAP Cloud Integration

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.28.9

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issues have been solved:

-   Problem with state transitions for nodes

    There was no transition from ERROR state to LIVE state for a node. Therefore, a node that had moved to ERROR state always remained in state ERROR even after it was restarted and working without an error \(since there was no transition to move it back to LIVE\). Due to this, component monitors generated alerts.

-   Problems when using Multicast in a looping process




</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_rbv_2dn_xz"/>

## 18 May 2017 - SAP Cloud Integration

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.27.12

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issue has been solved:

Decryption of large PGP messages that are encrypted on the file system during streaming is not possible.

</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_hpx_xp3_wz"/>

## 12 May 2017 - SAP Cloud Integration

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)

</td>
<td valign="top">

1.49.8

</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.27.11

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following issues have been solved:

-   Deployment of scenario fails due to checks error.
-   PGP Secret Keyring Artifact synchronization issue.

The following issues have been fixed in the OData adapter:

-   Adding a tag `xsi:nil=”true”` to explicitly set a field as null on the server is now allowed.

    **Example:** <DiscontinuedDate xsi:nil="true" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"/\>

-   Support of format HH:mm:ss\(12 Hours\)



</td>
</tr>
</table>



<a name="loiof4b7126c524e4126b54fc7b4a34cadc0__section_hjq_h3j_lz"/>

## 10 May 2017 - SAP Cloud Integration

**Software Version**

**Patched Component**


<table>
<tr>
<td valign="top">

Node Assembly \(Cluster 1.x\)

</td>
<td valign="top">

1.49.6

</td>
</tr>
<tr>
<td valign="top">

Node Assembly \(Cluster 2.x\)

</td>
<td valign="top">

2.27.9

</td>
</tr>
</table>


<table>
<tr>
<td valign="top">

 

</td>
<td valign="top" colspan="2">

**Bugfix**

The following bug has been fixed: If one integration flow contains the following elements \(in conjunction\), deploying the integration flow was not possible:

-   Multicast

-   Exception Subprocess

-   Send




</td>
</tr>
</table>

