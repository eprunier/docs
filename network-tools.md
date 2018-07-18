# Network tools

## nc

Test if remote TCP port is open

    nc -zv <host> <port>

## socat

Test if remote port is open

    socat - TCP4:<host>:<port>,connect-timeout=2
