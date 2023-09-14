<!-- loio1f9e87975f03433b9855bf9e760b1060 -->

# Updating your Existing Integration Flow

Some new features might not be available for your current integration flow due to the following reason:

A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.

You have the following options:

-   You can continue using the older version of the integration flow shape \(adapter or step\).

-   You can use the new integration flow shape \(adapter or step\).

    To do this, you first have to delete the old flow step or channel and then create it again.


> ### Caution:  
> *Updating & Redeploying Your Integration Flow* 
> 
> To minimize disruptions of the message processing during updating or redeploying active integration flows, redeployments are postponed up to 1 min after redeployment has been triggered manually. This set-up allows Cloud Integration enough time to finish the current message processing.
> 
> If the message processing cannot be completed within 1 min, an error is thrown. In exceptional cases, the integration flow needs to be redeployed again.

**Related Information**  


[Versioning of Artifacts](versioning-of-artifacts-cb536a3.md "Cloud Integration offers an easy version management capability for your integration artifacts.")

