<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Display certificate](#display-certificate)
- [Self-signed certificate](#self-signed-certificate)
  - [Create the key and the self-signed certificate](#create-the-key-and-the-self-signed-certificate)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Display certificate

    $ openssl x509 -in <certificate_file> -noout -text

## Self-signed certificate
### Create the key and the self-signed certificate

    $ openssl req -x509 -nodes [-days 365] -newkey rsa:1024 -out <path_to_certificate> -keyout <path_to_private_key>
