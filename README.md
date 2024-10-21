# teleop_twist_keyboard_for_azerty

Keyboard Teleoperation for ROS 2 adapted for more coherence with AZERTY keyboards.

## Run

```sh
ros2 run teleop_twist_keyboard_for_azerty teleop_twist_keyboard_for_azerty
```

Publishing to a different topic (in this case `my_cmd_vel`):

```sh
ros2 run teleop_twist_keyboard_for_azerty teleop_twist_keyboard_for_azerty --ros-args --remap cmd_vel:=my_cmd_vel
```

## Usage

```txt
This node takes keypresses from the keyboard and publishes them as Twist
messages. It is optimized for an AZERTY keyboard layout.
---------------------------
Moving around:
   a    z    e
   q    s    d
   w    c

For Holonomic mode (strafing), hold down the shift key:
---------------------------
   A    Z    E
   Q    S    D
   W    C

t : up (+z)
g : down (-z)

anything else : stop

r/f : increase/decrease max speeds by 10%
t/g : increase/decrease only linear speed by 10%
y/h : increase/decrease only angular speed by 10%

CTRL-C to quit
```

## Parameters

- `stamped (bool, default: false)`
  - If false (the default), publish a `geometry_msgs/msg/Twist` message.  If true, publish a `geometry_msgs/msg/TwistStamped` message.
- `frame_id (string, default: '')`
  - When `stamped` is true, the frame_id to use when publishing the `geometry_msgs/msg/TwistStamped` message.
