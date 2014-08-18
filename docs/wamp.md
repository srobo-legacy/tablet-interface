# WAMP Specification

## General Information

 - `board`s are referenced by their part code, not the index.

## Pub/Sub

When you subscribe to a message queue, you will receive the last message as the
first publish event you will get.

## Definitions

### RPC org.srobo.hello(`client_version`)

Called by the client when it first loads and is used to check whether the
server and the client are running on compatible versions.

The server should return an object containing a `compatible` key with either
`true` or `false` as the value. If the value is `false` the client will do
something appropriate, usually just reloading the page.


### RPC org.srobo.zone

Return the current zone the robot is configured to be in.

### PUB/SUB org.srobo.zone(`zone`)

When the zone changes.

### RPC org.srobo.mode

Return the current mode the robot is configured as. Mode is one of `comp` or `dev`.

### PUB/SUB org.srobo.mode(`mode`)

When the mode changes.


### PUB/SUB org.srobo.logs.append(`log`, `entry`)

When a single entry in the log has been added.

### RPC org.srobo.logs.all

Return a list of log objects (`{'type': type, 'title': title, 'name': name, 'contents': ['...', ...]}`).

### RPC org.srobo.logs.get(`name`)

Return a single log object.


### RPC org.srobo.start

Start the robot.

### RPC org.srobo.stop

Stop the robot.

### RPC org.srobo.state

Return the state of the robot, which can be one of `booting`, `started`, `stopping`, `stopped`.

### PUB/SUB org.srobo.state(`state`)

When the state changes.


### RPC org.srobo.pyenv.version

Return the current pyenv version.


### RPC org.srobo.project.name

Return the current project name.

### RPC org.srobo.project.version

Return the current project version.


### PUB/SUB org.srobo.power.output_state(`index`, `state`)

When the state of a power output on the power board has changed.

### RPC org.srobo.power.get_output_state(`index`)

Return the state of a power output on the power board.


### PUB/SUB org.srobo.servos.servo_value(`board`, `index`, `value`)

When a value on a servo has changed.

### RPC org.srobo.servos.get_servo(`board`, `index`)

Return a servo object (`{'value': value}`) about the requested servo.

### RPC org.srobo.servos.get_board(`serial_number`)

Return a servo board object (`{'servos': [<servo_object>, ...]}`) about the requested board.

### RPC org.srobo.servos.all_boards

Return a dictionary of serial number to servo board objects.


### PUB/SUB org.srobo.motors.motor_value(`board`, `index`, `value`)

When a value on a motor has changed.

### RPC org.srobo.motors.get_motor(`board`, `index`)

Return a motor object (`{'value': value}`) about the requested motor.

### RPC org.srobo.motors.get_board(`serial_number`)

Return a motor board object (`{'motors': [<motor_object>, ...]}`) about the requested board.

### RPC org.srobo.motors.all_boards

Return a dictionary of serial number to motor board objects.


### PUB/SUB org.srobo.ruggeduinos.pin_mode(`board`, `index`, `mode`)

When a pin mode has changed. Mode is one of `input`, `output`, `input_pullup`.

### PUB/SUB org.srobo.ruggeduinos.pin_value(`board`, `index`, `mode`)

When a pin value has changed.

### RPC org.srobo.ruggeduinos.get_pin(`board`, `index`)

Return a pin object (`{'mode': mode, 'type': type, 'value': value}`) for the requested pin. Type is one of `digital` or `analogue`.

### RPC org.srobo.ruggeduinos.get_board(`serial_number`)

Return a ruggeduino board object (`{'pins': [<pin_object>, ...]}`) for the requested board.

### RPC org.srobo.ruggeduinos.all_boards

Return a dictionary mapping serial numbers to ruggeduino board objects.


### PUB/SUB org.srobo.camera.image(`image_url`)

When a new camera image is available.
