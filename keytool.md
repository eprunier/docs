<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Import a certificate into a JKS keystore](#import-a-certificate-into-a-jks-keystore)
  - [Recipe](#recipe)
  - [Example](#example)
- [Export a certificate from a JKS keystore](#export-a-certificate-from-a-jks-keystore)
  - [Recipe](#recipe-1)
  - [Example](#example-1)
- [Export a PKCS12 from a JKS keystore](#export-a-pkcs12-from-a-jks-keystore)
  - [Recipe](#recipe-2)
  - [Example](#example-2)
- [Import a certificate with private key into a JKS keystore](#import-a-certificate-with-private-key-into-a-jks-keystore)
  - [Recipe](#recipe-3)
  - [Example](#example-3)
- [Misc](#misc)
  - [Set output language](#set-output-language)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Import a certificate into a JKS keystore
### Recipe

    keytool -importcert -keystore <keystore> -alias <alias> -file <certificate_file>.crt.pem

### Example

    keytool -importcert -keystore foo.jks -alias bar -file bar.crt.pem

## Export a certificate from a JKS keystore
### Recipe

    keytool -exportcert -keystore <keystore> -alias <alias> -file <certificate_file> [-rfc]

If _-rfc_ is used, the certificat will be exported in base64 PEM encoded format, otherwise it will be binary DER encoded format.

### Example

    keytool -exportcert -keystore foo.jks -alias bar -file bar.crt.pem -rfc

## Export a PKCS12 from a JKS keystore
### Recipe

    keytool -importkeystore \
    -srckeystore <JKS keystore> -destkeystore <PKCS12 keysore> \
    -srcstoretype JKS -deststoretype PKCS12 \
    -srcalias <alias to export> -destalias <exported alias> \
    [-srcstorepass <src keystore password>] \
    [-deststorepass <dest keystore password>] \
    [-srckeypass <src key password>] \
    [-destkeypass <dest key password>]

### Example

    keytool -importkeystore \
    -srckeystore foo.jks -destkeystore foo.p12 \
    -srcstoretype JKS -deststoretype PKCS12 \
    -srcalias bar -destalias bar

## Import a certificate with private key into a JKS keystore
__Note:__ certificate and private key must be in a PKCS12 (.pfx/.p12) keystore (see openssl for creating a PKCS12 with a certificate and private key).

### Recipe

    keytool -importkeystore \
    -srckeystore <PKCS12 keystore> -srcstoretype pkcs12 -srcalias <alias>\
    -destkeystore <JKS keystore> -destalias <alias>

### Example

    keytool -importkeystore \
    -srckeystore foo.pfx -srcstoretype pkcs12 -srcalias foo\
    -destkeystore foo.jks -destalias foo

## Misc
### Set output language

    keytool -J-Duser.language=en -list -keystore <keystore file>