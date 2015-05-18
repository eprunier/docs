<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [SSH tunnel with Socat](#ssh-tunnel-with-socat)
  - [Recipe](#recipe)
  - [Example](#example)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## SSH tunnel with Socat

### Recipe

    $ socat TCP4-LISTEN:<port> SOCKS4A:<tor-host>:<dest-host>:<dest-port>,socksport=<tor-port>
    $ ssh <user>@<tor-host> -p <port>

- Socat is listening for requests on port &lt;port&gt; (IPv4 protocol).
- Socat is connected to &lt;dest-host&gt;:&lt;dest-port&gt; via the socks v4 proxy on &lt;tor-host&gt;:&lt;tor-port&gt;

### Example

We assume that Tor is running on localhost and is listening on port 9050.


    $ socat TCP4-LISTEN:4242 SOCKS4A:localhost:example.com:22,socksport=9050
    $ ssh user@localhost -p 4242
