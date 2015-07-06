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

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Import a certificate into a JKS keystore
### Recipe

    keytool -keystore <keystore> -importcert -alias <alias> -file <certificate_file>

### Example

    keytool -keystore foo.jks -importcert -alias bar -file bar.crt

## Export a certificate from a JKS keystore
### Recipe

    keytool -keystore <keystore> -exportcert -alias <alias> -file <certificate_file> [-rfc]

If _-rfc_ is used, the certificat will be exported in base64 PEM encoded format, otherwise it will be binary DER encoded format.

### Example

    keytool -keystore foo.jks -exportcert -alias bar -file bar.crt [-rfc]

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
