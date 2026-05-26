# IsaacSim-Hello-World
This tutorial will show you how to import a robot asset to IsaacSim

# Pre-Requisites
Install IsaacSim: https://github.com/marcelpatrick/IsaacSim-IsaacLab-installation-for-Windows-Easy-Tutorial

# Load IsaacSim
- Activate your Anaconda python environment with IsaacSim installed. If you haven't created one see here: https://github.com/marcelpatrick/IsaacSim-IsaacLab-installation-for-Windows-Easy-Tutorial#step-3--create-a-clean-python-311-environment 
- Open Anaconda Prompt, type `conda activate [your env name]`
- Open IsaacSim: type `isaacsim`

# Load Robot
- On the upper bar, click on "window" > Examples > Robotics Examples. This will open a window on the bottom of the screen "Robotics Examples."
- Select Import Robots > Carter URDF > Load
- If you press play the robot will start moving forward if left and right wheels joints taget velocity > 0 or if left and right wheel links angular or linear velocity > 0
