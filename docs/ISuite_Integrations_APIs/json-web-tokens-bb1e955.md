<!-- loiobb1e955b36454330b2270b8afcac45a1 -->

# JSON Web Tokens

This topic describes about JSON Web Tokens \(JWT\) policies available in API Management.

JSON Web Tokens, or JWT, are commonly used to share claims or assertions between connected applications. The JWT policies enable API proxies to:

-   Generate signed JWTs.

-   Verify digitally signed JWTs and claims within those JWTs.

-   Decode signed JWTs without validating signatures on the token.


> ### Note:  
> If this policy is not visible, then it is yet to be enabled for your data center and it will be enabled shortly.

**Algorithms used in JWT policy**

-   HMAC algorithm: The HMAC algorithm uses a secret key for creating and verifying signatures.
-   RSA algorithm: The RSA algorithm uses a public/private key pair for the cryptographic signature. With RSA signatures, the signing party uses a private key to sign the JWT, and the verifying party uses the matching public key to verify the signature on the JWT.

**Parts of a JWT**

A signed JWT encodes information in three parts:

-   Header
-   Payload
-   Signature

Generate JWT policy creates all the parts, Verify JWT policy examines all the parts, and Decode JWT policy examines the header and payload.

**JSON Web Key Set \(JWKS\)**

A JSON Web Key Set \(JWKS\) is a JSON structure that represents a set of JSON Web Keys. A JSON Web Key \(JWK\) is a JSON data structure that represents a cryptographic key.

JWKS structure: Each key element in the JWKS must include these attributes.

-   kty - Must be set to RSA.

-   kid \(the key id\) - Arbitrary value \(no duplicates within a key set\). If the inbound JWT bears a key ID, which is present in the set of JWKS, then the policy will use the correct public key to verify the JWT signature.

-   n - The RSA key value "modulus".

-   e - The RSA key value "exponent".


Following are optional elements and their required values:

-   alg - If present, must be RS256.

-   use - If present, must be sig.


The following JWKS includes the required elements and values

> ### Sample Code:  
> ```
> 
> {  
>    "keys":[  
>       {  
>          "kty":"RSA",
>          "alg":"RS256",
>          "use":"sig",
>          "kid":"ca04df587b5a7cead80abee9ea8dcf7586a78e01",
>          "n":"iXn-WmrwLLBa-QDiToBozpu4Y4ThKdwORWFXQa9I75pKOvPUjUjE2Bk05TUSt7-V7KDjCq0_Nkd-X9rMRV5LKgCa0_F8YgI30QS3bUm9orFryrdOc65PUIVFVxIwMZuGDY1hj6HEJVWIr0CZdcgNIll06BasclckkUK4O-Eh7MaQrqb646ghFlG3zlgk9b2duHbDOq3s39ICPinRQWC6NqTYfqg7E8GN_NLY9srUCc_MswuUfMJ2cKT6edrhLuIwIj_74YGkpOwilr2VswKsvJ7dcoiJxheKYvKDKtZFkbKrWETTJSGX2Xeh0DFB0lqbKLVvqkM2lFU2Qx1OgtTnrw",
>          "e":"AQAB"
>       },
>       {  
>          "kty":"RSA",
>          "alg":"RS256",
>          "use":"sig",
>          "kid":"91412840c1019dedff1854b89938ad0a9078b871",
>          "n":"veQQDTKL8UKIRIuWxHLeRH0umTHtnm2LXej56MungXuFZwmk_xccvsMpCtXmqhvEmHyAmKF06YRRWAomHIwC7IBz9BsIjPYtOkvVkff_SCFoyuyDFkNsDsbTydIDUFAV5YlhZOvgq1PJCzu8AfU9HoRf0WIEnexpTDyWzlqNbg0b94Tlmw01C5kDRGDD33v8i-RM4xXXyovBA_8R8D9t0aIzC9iVL418E0FOXAQ5xvrbvTXAkr17U4yIINUZ03q7i5tOxSA1z0s_-CK6NNoLZcDQXddBFCCYXNmfhaiu-NeSVePZMmDZGIFZIhIvagPcs3pZfSC5ysyo3tu3r16tdw",
>          "e":"AQAB"
>       },
>       {  
>          "kty":"RSA",
>          "alg":"RS256",
>          "use":"sig",
>          "kid":"f5010d8a5353b010c81fa45f1e43d2789b18bc9c",
>          "n":"2_jAH07j0ufDhv3sE2ky4m7w7xWbOZfMa1EI3MAOMdAcskKGDlv67sN8OKTo3B8uDLIx8F8lfGToG4hUr8N08YYXFzqRpXk3b8_kzVDrF1Z7dSi_OhQXkXsnEdUPAn3CQu6a_ObQ7XAyrr2eF0L_unptoQhanYte78LwOrPGKZTEKN6MEwHxz1yTR37yl88VNoV3WsLoeuDxhomgtSD5liFGBFuJt5-f5x-ZwXdDKgNgdIA7k8YYw246o47OKrb9xGR62qi0Mahxot_523BLyY18CUgbpb-VBPpVyseNOrpUQarEFcAi3Pab4vwAzZoA8NVyvl7aF2QRdIMIXoDmPw",
>          "e":"AQAB"
>       }
>    ]
> }
> 
> ```

**Related Information**  


[Generate JWT](generate-jwt-c28be0e.md "This topic describes about Generate JSON Web Token(JWT) Policy.")

[Verify JWT](verify-jwt-277635d.md "This policy describes about Verify JSON Web Token(JWT) Policy.")

[Decode JWT](decode-jwt-2d79eba.md "This policy describes about Decode JSON Web Token(JWT) Policy.")

