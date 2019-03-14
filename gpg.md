# GPG

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Encryption](#encryption)
  - [AES-256](#aes-256)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Encryption

List of supported algorithms:

    gpg --version

### AES-256

To define AES-256 as default cipher algo, add _cipher-algo AES256_ in _~/.gnupg/gpg.conf_

Encrypt

    gpg --symmetric --cipher-algo AES256 [--passphrase <passphrase>] -o <pgp_file> <source_file>
    gpg2 --symmetric --cipher-algo AES256 [--passphrase <passphrase> --batch [--yes]] -o <pgp_file> <source_file>

Decrypt

    gpg --decrypt [--passphrase <passphrase>] --quiet -o <output_file> <gpg_file>
    gpg2 --decrypt [--passphrase <passphrase> --batch [--yes]] --quiet -o <output_file> <gpg_file>
