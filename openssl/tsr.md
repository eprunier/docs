# TSR

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [TSR](#tsr)
  - [Check](#check)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Check

If input is a response:

    openssl ts -reply -in ./input.tsr -text

If input is a token :

    openssl ts -reply -in ./input.tsr -text -token_in
