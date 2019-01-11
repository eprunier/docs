# Encryption

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [AES-256](#aes-256)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## AES-256

Create a 256 bits (32 bytes) random key

    openssl rand -base64 32 > key.bin

Encrypt file

    openssl enc -aes-256-cbc -salt -in <file_to_encrypt> -out <encrypted_file> -pass file:./key.bin

Encrypt file as base64-encode (for safe transport, e.g. through email systems and such)

    openssl enc -aes-256-cbc -salt -a -in <file_to_encrypt> -out <encrypted_file> -pass file:./key.bin

Decrypt file

    openssl enc -aes-256-cbc -d -in <file_to_decrypt> -out <decrypted_file> -pass file:./key.bin

Decrypt file from base64-encode

    openssl enc -aes-256-cbc -d -a -in <file_to_decrypt> -out <decrypted_file> -pass file:./key.bin
