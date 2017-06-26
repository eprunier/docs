<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Authentication with client certificate](#authentication-with-client-certificate)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Authentication with client certificate

    curl -E <certificate_file>.crt.pem --key <private_key_file>.key.pem <url>
