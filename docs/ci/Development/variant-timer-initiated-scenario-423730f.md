<!-- loio423730f0c524490fb4b0cefb5609fac4 -->

# Variant: Timer-Initiated Scenario

Deploy a timer-initiated integration flow that writes an entry to the data store.

See the *Modeling Basics - Timer-Initiated Scenario* integration flow.

![The Start Timer is set according to your settings. Then, the integration flow will start. Next, the Define message body defines a hard-coded message body. The following step which is called Write data store entry takes the message body and writes it to the data store.](images/Learn_the_Basics_Variant_Timer-Initiated_Scenario_053b390.png)

The integration flow is timer-initiated and writes a simple message \("Hello World!"\) to the data store.

The *Start Timer* is set to *Run Once*, so upon deployment, the integration flow starts. Optionally, you can schedule the timer to initiate the integration flow for a specific day or for a specific number of occurrences.

The *Define message body* defines a hard-coded message body that reads `Hello World!`.

The Write step *Write data store entry* takes the message body and writes it to the data store.

After you've deployed the integration flow, go to *Operations View* \> *Manage Integration Content* to review your data store entry from *Modeling Basics - Timer-Initiated Scenario*.

