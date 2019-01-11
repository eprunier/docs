# GPG

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [GPG](#gpg)
  - [Encryption](#encryption)
    - [AES-256](#aes-256)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Encryption

List of supported algorithms:

    gpg --version

### AES-256

    gpg [-o <output_file>] --symmetric --cipher-algo AES256 <file>

To define AES-256 as default cipher algo, add _cipher-algo AES256_ in _~/.gnupg/gpg.conf_
