# WAMP Specification

## Handshake

### RPC org.srobo.hello(`client_version`)

Return `true` if the client should reload the page before continuing, otherwise return `false`.

## Set up

### RPC org.srobo.zone

Return the current zone the robot is configured to be in.

### PUB/SUB org.srobo.zone(`zone`)

When the zone changes.

### RPC org.srobo.mode

Return the current mode the robot is configured as. Mode is one of `comp` or `dev`.

### PUB/SUB org.srobo.mode(`mode`)

When the mode changes.
