<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Display](#display)
  - [CSR](#csr)
  - [Certificate](#certificate)
- [Create](#create)
  - [Self-signed certificate](#self-signed-certificate)
  - [Create a PKCS12 containing a private key and a certificate](#create-a-pkcs12-containing-a-private-key-and-a-certificate)
  - [Create a PKCS7 from a certificate](#create-a-pkcs7-from-a-certificate)
- [Convert](#convert)
  - [DER certificate to PEM](#der-certificate-to-pem)
  - [PKCS12 file containing certificate and private key to PEM](#pkcs12-file-containing-certificate-and-private-key-to-pem)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Display
### CSR

    $ openssl req -in <csr_file> -noout -text

### Certificate

Certificate in PEM format:

    $ openssl x509 -in <certificate_file> -noout -text

Certificate in DER format:

    $ openssl x509 -in <certificate_file> -inform der -noout -text

Certificate and private key in PKCS12 format:

    $ openssl pkcs12 -info -nodes -in <file>.pfx

## Create
### Self-signed certificate

    $ openssl req -x509 -nodes -days 365 -newkey rsa:1024 -out <path_to_certificate> -keyout <path_to_private_key>

### Create a PKCS12 containing a private key and a certificate

    $ openssl pkcs12 -export -out <name>.p12 -inkey <key>.pem -in <certificate>.pem -name <alias>

### Create a PKCS7 from a certificate

		$ openssl crl2pkcs7 -certfile <file_name> -nocrl


## Convert
### DER certificate to PEM

    $ openssl x509 -inform der -in <certificate>.crt -out <certificate>.pem

### PKCS12 file containing certificate and private key to PEM

Usual extensions for PKCS12 files: .p12 or .pfx

    $ openssl pkcs12 -in <file>.p12 -out <file>.pem -nodes
