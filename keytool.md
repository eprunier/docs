<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Import a certificate into a keystore](#import-a-certificate-into-a-keystore)
  - [Recipe](#recipe)
  - [Example](#example)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Import a certificate into a keystore

### Recipe

    keytool -keystore <keystore> -importcert -alias <alias> -file <certificate_file>

### Example

    keytool -keystore foo.jks -importcert -alias bar -file bar.crt
