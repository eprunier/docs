<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [JVM parameters](#jvm-parameters)
  - [Proxy](#proxy)
  - [Trustore](#trustore)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## JVM parameters
### Proxy

    -Dhttp.proxyHost=<hostname> -Dhttp.proxyPort=<port>
    -Dhttps.proxyHost=<hostname> -Dhttps.proxyPort=<port>
    -Dhttp.nonProxyHosts=localhost|foo|bar|192.168.*

### Trustore

    -Djavax.net.ssl.trustStore=<trustStore_path> -Djavax.net.ssl.trustStorePassword=<password>
