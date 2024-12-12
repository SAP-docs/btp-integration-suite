<!-- loioec605c708daf4c7fb56b456345a2c43a -->

# Creating X.509 Keys

You need X.509 keys to configure communication with certificate-based authentication over HTTPS and if you want to configure digital encryption and signing of messages with security standards PKCS\#7 and XML Digital Signature.

1.  Generate a key pair.

    See: [Generating a Key Pair](generating-a-key-pair-abb324d.md)

2.  Upload the signing response that you receive from the CA to the keystore.

    See:  <?sap-ot O2O class="- topic/xref " href="f50c159542f04f888424bdbc6a4e203f.xml" text="" desc="" xtrc="xref:2" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/ec605c708daf4c7fb56b456345a2c43a.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

3.  Request a signed certificate from a certification authority

    To enable the tenant to communicate as client with the customer system, you have to import a client certificate to the tenant client keystore. This certificate has to be signed by a certification authority \(CA\). The procedure depends on the CA and is not documented here.

4.  Upload the signing response that you received from the CA to the keystore.

    See: [Updating a Key Pair with a Signing Response](../50-Development/updating-a-key-pair-with-a-signing-response-4242f01.md)


