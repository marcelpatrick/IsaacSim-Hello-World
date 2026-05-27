# IsaacSim-Hello-World
This tutorial will guide you through the easiest project you can run on IsaacSim (a "hello world" project) to quickly give you a notion of what IsaacSim is and does. It will show you how to import a robot asset to IsaacSim

# Pre-Requisites
Install IsaacSim: https://github.com/marcelpatrick/IsaacSim-IsaacLab-installation-for-Windows-Easy-Tutorial

# Load IsaacSim
- Activate your Anaconda python environment with IsaacSim installed. If you haven't created one see here: https://github.com/marcelpatrick/IsaacSim-IsaacLab-installation-for-Windows-Easy-Tutorial#step-3--create-a-clean-python-311-environment 
- Open Anaconda Prompt, type `conda activate [your env name]`
- Open IsaacSim: type `isaacsim`

# Load Robot
- On the upper bar, click on "window" > Examples > Robotics Examples. This will open a window on the bottom of the screen "Robotics Examples."
- Select Import Robots > Carter URDF > Load
- If you press play the robot will simply drop to the ground plane and not do anything. This is because there are no movement (velocity) parameters to it. Let's try moving it.

# Move the Robot
There are 2 ways to move the robot:

## By assigning values to the velocity parameters in its wheels and joints
- On the IsaacSim UI, go to the right-hand panel "Stage" where the assets are listed and select: carter > joints > left_wheel and right_wheel (you can hols Ctrl and select both to change parameters on both at the same time.
- In Property > Drive > Angular, change Target Velocity to 200, Damping to 10000 and Stiffness to 0.
- Push play. You will see the carter robot moving forward.

### Explaining the parameters

- **Angular Velocity vs Linear Velocity**: Linear velocity measures how fast something moves on a straight line (translational). Angular velocity measures how fast something spins (like the speed at which wheels spin), measured in radians per second (rad/s). 
- **Max Force**: Upper torque limit the drive can produce. Caps how hard the motor can push to hit its target. Too low = drive can't overcome inertia/friction. inf = unlimited
- **Target Position**: The angle you want the joint to rotate to and stop there once it reaches it. Used for arms, not wheels. 
- **Target Velocity**: The speed you want the joint to rotate (in rads/sec) and maintain it once it reaches it.  
- **Damping**: With how much "power" the motor pushes the wheels towards the desired target angular velocity. -> even if target velocity = 20, if damping = 0 the robot will not move
- **Stiffness**: How strongly it holds the target position. If stiff is low, joints are wobbly. User for arms, not wheels.

## Other ways to move the robot
<img width="1063" height="891" alt="image" src="https://github.com/user-attachments/assets/64232ebd-acd1-4258-b82e-69ddf6d0be8b" />

