<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Configuration](#configuration)
  - [Sample Tor client configuration](#sample-tor-client-configuration)
- [SSH tunnel with Socat](#ssh-tunnel-with-socat)
  - [Recipe](#recipe)
  - [Example](#example)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Configuration

- [Sample torrc](https://gitweb.torproject.org/tor.git/tree/src/config/torrc.sample.in)
- [Tor manual](https://www.torproject.org/docs/tor-manual.html.en)

### Sample Tor client configuration

    ## Tor opens a SOCKS proxy on port 9050 by default -- even if you don't
    ## configure one below. Set "SOCKSPort 0" if you plan to run Tor only
    ## as a relay, and not make any local application connections yourself.
    SocksPort 9050

    ## Entry policies to allow/deny SOCKS requests based on IP address.
    ## First entry that matches wins. If no SOCKSPolicy is set, we accept
    ## all (and only) requests that reach a SOCKSPort. Untrusted users who
    ## can access your SOCKSPort may be able to learn about the connections
    ## you make.
    SOCKSPolicy accept 127.0.0.1
    SOCKSPolicy reject *

    ## The directory for keeping all the keys/etc. By default, we store
    ## things in $HOME/.tor on Unix, and in Application Data\tor on Windows.
    DataDirectory Data

    ## A comma-separated list of IP addresses and ports that your firewall
    ## allows you to connect to. The format is as for the addresses in ExitPolicy,
    ## except that "accept" is understood unless "reject" is explicitly provided.
    ## For example, 'ReachableAddresses 99.0.0.0/8, reject 18.0.0.0/8:80, accept *:80'
    ## means that your firewall allows connections to everything inside net 99,
    ## rejects port 80 connections to net 18, and accepts connections to port 80
    ## otherwise. (Default: 'accept *:*'.)
    ReachableAddresses *:80,*:443
    ReachableAddresses reject *:*

    ## Tor will make all its OR (SSL) connections through this host:port
    ## (or host:443 if port is not specified), via HTTP CONNECT rather than
    ## connecting directly to servers. You may want to set FascistFirewall
    ## to restrict the set of ports you might try to connect to, if your
    ## HTTPS proxy only allows connecting to certain ports.
    #HTTPSProxy example.com:8080

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
