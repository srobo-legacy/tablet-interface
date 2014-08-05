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

## Logs

### PUB/SUB org.srobo.log(`entry`)

When a single entry in the log has been added.

### RPC org.srobo.logs.current

Return the entire contents of the current log.

### RPC org.srobo.logs.all_old

Return a list of all the old logs.

### RPC org.srobo.logs.get_old(`index`)

Return the contents of a single old log.
