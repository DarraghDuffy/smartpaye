# smartpaye

This is Simple a Copy and Paste from commands file

Revenue Sample / Example for SMARTPAYE
End Of Line Settings set to LF i.e. \n aka *nix based EOL's, in otherwords not Windows based "CRLF"

The RFC[1] defines New Lines as the Ascii Linefeed
i.e. HEX 0A or DEC 10 or OCT 012.

--Revenue Test Case
1. Get Digest, defined as base64(sha512(requestBody))
cat requestBody.json | openssl sha512 | openssl base64

2. Get HTTP Message Signature,
using the Header parameters for String Signing headers="(request-target) host date digest content-type"
with RSA_SHA512, the String is located in signingString.info and then BASE64 encoded

openssl dgst -sha512 -sign private_key.pem signingString.info | openssl base64

3. CURL Command
See curl.info


4. Response From Server:
See response.json

[1] RFC HTTP Message Signature
https://tools.ietf.org/pdf/draft-cavage-http-signatures-10.pdf
