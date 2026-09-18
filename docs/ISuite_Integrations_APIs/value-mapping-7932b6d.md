<!-- loio7932b6df6a7346079eedb4d62e67aaff -->

# Value Mapping

A *Value Mapping* artifact stores groups of equivalent values for the same object across different systems, enabling accurate translation in your integration flows.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

You use the value mapping artifact to represent multiple values for a single object. For example, a product in Company A is referred by the last three letters as "IDE". The same product is referred in Company B by product code ''0100IDE". When Company A sends message to Company B, it needs to take care of the difference in the representations of the same product. So, Company A defines an integration flow with a mapping element that contains reference to the value mapping definition. You create such value mapping groups in a *Value Mapping* artifact.

