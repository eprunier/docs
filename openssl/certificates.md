# X509 certificates

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Display](#display)
  - [CSR](#csr)
  - [Certificate](#certificate)
  - [Remote certificate](#remote-certificate)
  - [Private key](#private-key)
- [Create](#create)
  - [Self-signed certificate](#self-signed-certificate)
  - [Create a PKCS12 containing a private key and a certificate](#create-a-pkcs12-containing-a-private-key-and-a-certificate)
  - [Create a PKCS7 from a certificate](#create-a-pkcs7-from-a-certificate)
- [Convert](#convert)
  - [DER certificate to PEM](#der-certificate-to-pem)
  - [PKCS12 file containing certificate and private key to PEM](#pkcs12-file-containing-certificate-and-private-key-to-pem)
- [Export](#export)
  - [Export private key from PKCS12](#export-private-key-from-pkcs12)
  - [Export certificate from PKCS12](#export-certificate-from-pkcs12)
- [Checks](#checks)
  - [Check if a certificate matches a CSR](#check-if-a-certificate-matches-a-csr)
  - [Check if a certificate matches a private key](#check-if-a-certificate-matches-a-private-key)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Display

### CSR

    openssl req -in <csr_file> -noout -text

### Certificate

Certificate in PEM format:

    openssl x509 -in <certificate_file>.crt.pem -noout -text

Certificate in DER format:

    openssl x509 -in <certificate_file>.crt -inform der -noout -text

Certificate and private key in PKCS12 format:

    openssl pkcs12 -info -nodes -in <file>.pfx

### Remote certificate

    echo 'Q' |  openssl s_client -connect <host>:<port> -showcerts 2>/dev/null | openssl x509 -inform pem -noout -text

### Private key

    openssl rsa -in <private_key_file>.key.pem -noout -text 

## Create

### Self-signed certificate

    openssl req -x509 -nodes -days 365 -newkey rsa:1024 -out <certificate_file>.crt.pem -keyout <private_key_file>.key.pem

### Create a PKCS12 containing a private key and a certificate

    openssl pkcs12 -export -out <keystore_file>.pfx -inkey <key_file>.key.pem -in <certificate_file>.crt.pem -name <alias>

### Create a PKCS7 from a certificate

    openssl crl2pkcs7 -certfile <certificate_file>.crt.pem -nocrl

## Convert

### DER certificate to PEM

    openssl x509 -inform der -in <certificate>.crt -out <certificate>.crt.pem

### PKCS12 file containing certificate and private key to PEM

Usual extensions for PKCS12 files: .pfx or .p12

    openssl pkcs12 -in <file>.pfx -out <file>.pem -nodes

## Export

### Export private key from PKCS12

    openssl pkcs12 -in <pkcs12_file>.pfx -nocerts -out <key_file>.key.pem

### Export certificate from PKCS12

    openssl pkcs12 -in <pkcs12_file>.pfx -clcerts -nokeys -out <certificate_file>.crt.pem

## Checks

### Check if a certificate matches a CSR

Compare public key hashes from certificate and CSR:

    openssl x509 -in <certificate_file> -pubkey -noout -outform pem | sha256sum
    openssl req -in <csr_file> -pubkey -noout -outform pem | sha256sum

### Check if a certificate matches a private key

Compare public key hashes from certificate and private key:

    openssl x509 -in <certificate_file> -pubkey -noout -outform pem | sha256sum 
    openssl pkey -in <private_key_file> -pubout -outform pem | sha256sum 