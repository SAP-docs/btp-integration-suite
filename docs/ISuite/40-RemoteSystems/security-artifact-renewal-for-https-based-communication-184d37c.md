<!-- loio184d37c6d7714bdd9ca968ae49c5a897 -->

# Security Artifact Renewal for HTTPS-Based Communication

Using HTTPS, you can specify two different authentication options: certificate-based authentication and basic authentication. These options imply a different set of security artifacts for which specific renewal processes exist.

Certificate-based authentication \(through HTTPS\) involves the usage of X.509 SSL certificates both at client and server side. These certificates expire at a specified point in time. To ensure operation of scenarios using this communication type without any downtime requires the coordinated renewal of certificates both at client and server side.

Basic authentication uses credentials to allow the identification of trusted communication partners. Credentials are composed of user and password and, in case the SuccessFactors connector is involved, additional attributes. In addition to credentials, basic authentication also uses a one-way SSL connection which requires server certificates. Therefore, security artifact update involves both the update of credentials and of the involved certificates.

