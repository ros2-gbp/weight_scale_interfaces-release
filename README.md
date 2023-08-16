# weight_scale_interfaces

## install
```.sh
cd ~/dev_ws
colcon build --cmake-clean-first --symlink-install --packages-select weight_scale_interfaces
. install/local_setup.zsh
```
## weight_scale_interfaces/msg/Weight
| type | name | explanation |
|:---|:---|:---|
| builtin_interfaces/Time | stamp | Measurement time |
| bool | stable | State of the scale (for example measurement is stable or fluctuating) |
| bool | overload | Couldn't measure due to overweight |
| float64 | weight | weight |
| string | unit | unit of measurement result (kg, g, oz, ...) |

## weight_scale_interfaces/action/SetZero
| type | name | explanation |
|:---|:---|:---|
||| Goal |
| float64 | timeout | timeout(sec) |
| --- || Result |
| bool | success | True/False |
| string | message | result message |
| --- || Feedback |
| weight_scale_interfaces/Weight | weight | |

## weight_scale_interfaces/action/GetWeight
| type | name | explanation |
|:---|:---|:---|
||| Goal |
| float64 | timeout | timeout(sec) |
| --- || Result |
| weight_scale_interfaces/Weight | weight |
| bool | success | succeeded in obtaining a stable weight |
| string | message | result message |
| --- || Feedback |
| weight_scale_interfaces/Weight | weight ||
