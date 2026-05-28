# IsaacSim-Hello-World
This tutorial will guide you through the easiest project you can run on IsaacSim (a "hello world" project) to quickly give you a notion of what IsaacSim is and does. It will show you how to import a robot asset to IsaacSim.
-> It is based on IsaacSim 5.1

# Pre-Requisites
Install IsaacSim 5.1: https://github.com/marcelpatrick/IsaacSim-IsaacLab-installation-for-Windows-Easy-Tutorial

# Load IsaacSim
- Activate your Anaconda python environment with IsaacSim installed. If you haven't created one see here: https://github.com/marcelpatrick/IsaacSim-IsaacLab-installation-for-Windows-Easy-Tutorial#step-3--create-a-clean-python-311-environment 
- Open Anaconda Prompt, type `conda activate [your env name]`
- Open IsaacSim: type `isaacsim`

# Load Robot
- On the upper bar, click on "window" > Examples > Robotics Examples. This will open a window on the bottom of the screen "Robotics Examples."
- Select Import Robots > Carter URDF > Load
- If you press play the robot will simply drop to the ground plane and not do anything. This is because there are no movement (velocity) parameters to it. Let's try moving it.
<img width="2682" height="619" alt="image" src="https://github.com/user-attachments/assets/dabaeb30-a964-46fe-a7d0-cbaf621304af" />

# Move the Robot
There are 2 ways to move the robot:

## Velocity parameters
-> By assigning values to the velocity parameters in its wheels and joints
- On the IsaacSim UI, go to the right-hand panel "Stage" where the assets are listed and select: carter > joints > left_wheel and right_wheel (you can hols Ctrl and select both to change parameters on both at the same time.
- In Property > Drive > Angular, change Target Velocity to 200 and Damping to 10000
- Push play. You will see the carter robot moving forward.
<img width="1113" height="421" alt="image" src="https://github.com/user-attachments/assets/5e7e8b26-7ad0-4431-a318-713567eec66b" />

### Explaining the parameters

- **Angular Velocity vs Linear Velocity**: Linear velocity measures how fast something moves on a straight line (translational). Angular velocity measures how fast something spins (like the speed at which wheels spin), measured in radians per second (rad/s). 
- **Max Force**: Upper torque limit the drive can produce. Caps how hard the motor can push to hit its target. Too low = drive can't overcome inertia/friction. inf = unlimited
- **Target Position**: The angle you want the joint to rotate to and stop there once it reaches it. Used for arms, not wheels. 
- **Target Velocity**: The speed you want the joint to rotate (in rads/sec) and maintain it once it reaches it.  
- **Damping**: With how much "power" the motor pushes the wheels towards the desired target angular velocity. -> even if target velocity = 20, if damping = 0 the robot will not move
- **Stiffness**: How strongly it holds the target position. If stiffness is low, joints are wobbly. Used for arms, not wheels.

## Using your keyboard: Differential Controller
-> Let's configure a differential controller so you can use the WASD keys on your keyboard to control the robot's movement

- Go to the Top menu: Tools → Robotics → OmniGraph Controllers → Differential Controller
- On the pop-up window, select:
- **Robot prim**: click on add, select the Carter robot prim from the list
- **wheel radius**: on the asset panel on the right ("stage"): Carter > chassis link > left wheel link (can be either left or right) > collisions > mesh > cylinder > property (lower panel) > geometry > mesh > radius: copy the number there (**0.24**) into the "wheel radius" field
- **distance between wheels**: Calculate the difference between the coordinate number on the Y-axis between the 2 wheels. left wheel link > property > transform > translate > Y (**0.31**). same for right wheel link > Y (**-0.31**). Distance = 31 - -31 = **0.62**. Enter 0.62 on the distance between wheels param.
- **right/left joint names**: give names to the joints: right_wheel, left_wheel
- select "use keyboard control (WASD)
- Click Play
Now you'll be able to control the robot with your WASD keys.
<img width="608" height="771" alt="image" src="https://github.com/user-attachments/assets/1d28df16-3bd2-4e83-b5ce-eb9a99dad769" />


To make the torque smoother: 
- On the "Stage" panel: Graphs > differential_controller > DifferentialController > define max linear and angular speeds to 0.5
<img width="1119" height="1219" alt="image" src="https://github.com/user-attachments/assets/9f3c5db1-4741-44ee-a0d5-d63185c3c4b8" />



