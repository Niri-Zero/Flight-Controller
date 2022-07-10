# Flight-Controller
All of Niri's control theory code is stored here!

### Basic Theory
The flight controller runs on an Arduino Mega. In addition, there is a local IMU (MPU6050) that is used to figure out yaw, pitch, and roll. The core concept is for the user to provide target yaw, pitch, and roll. The controller then uses a PID controller to achieve the desired state.

1. Calculate yaw, pitch, roll data using algorithm described in the Odometry repository
2. Recieve iBus data from the RC controller, and set the desired states
3. Calculate the PID outputs based on the current state, current error, net error, and the change in error
4. Output the values to the motor, using a motor mixing algorithm
