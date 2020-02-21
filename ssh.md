<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Start ssh-agent on Windows and load key](#start-ssh-agent-on-windows-and-load-key)
- [SSH tunnel](#ssh-tunnel)
- [Specify private key](#specify-private-key)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Start ssh-agent on Windows and load key

    $ eval `ssh-agent`
    $ ssh-add

## SSH tunnel

    $ ssh -L <local_port>:<target_host>:<target_port> <user>@<ssh_server_host>

## Specify private key

    $ ssh -i /path/to/key_rsa <user>@<ssh_server_host>
