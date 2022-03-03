# FSSIM Setup Guide
Instructions to setup AMZ-Driverless Formula Student SIMulator

# Step 1: Launch an Ubuntu VM
1. Download VirtualBox here. If you already have it downloaded, make sure you have the latest version.
2. Download Ubuntu 16.04 here. Make sure to download a Desktop Image NOT a Server Install Image.
3. Click “New” on VirtualBox and select all standard options.
4. Before starting the VM:
    a) Go to Settings-> Display and make sure the Video Memory Slider is all the way up
    b) Go to Settings->System and unselect floppy disk 
    c) Go to Settings->Storage and click on the CD icon underneath “Controller: IDE”. Choose your Ubuntu file. 
5. Start the VM and follow the instructions here under “Install Ubuntu”. Due to compatibility issues between VirtualBox and Ubuntu 16.04, you may notice that the buttons don’t receive input. Use your enter key.

# Step 2: Resize to Fit Screen (Optional)
1. On the top bar, go to Devices and click “Insert Guest Additions CD Image…”
2. After it automatically restarts, go to View and click on Scaled mode.

# Step 3: Installing ROS
1. Please follow the instructions here BUT read the pointers below in parallel.
    a) Make sure that you are at the “/” level NOT “/home” when you follow the Environment Setup instructions. Recognize that the “opt” folder is at the computer level, not in your home directory. 
    b) After running the echo command, please open your ./bashrc file (run “vi ./bashrc”) and scroll to the bottom to see if your command worked.
    c)Make sure to run **source /opt/ros/kinetic/setup.bash** at the root level
2. Make sure you are at “/home/your_name” for the following steps
    a) Run **sudo apt install python-catkin-tools**
    b) Make a new directory and run **catkin_make** inside it (you may need to install some more catkin packages at request)
    c) “Cd ~/home/your_name/workspace/src” and clone this repo (use https not ssh) in this folder
    d) “Cd ..” (so you are in your workspace level) and then run **source devel/setup.bash**
    e) “Cd fssim” and make sure to run **./update_dependencies.sh**
    f) Cd .. (into your workspace folder) and run **roslaunch fssim auto_fssim.launch**
3. Make sure you run the source commands and have installed the necessary catkin dependencies. If you’re getting issues saying roslaunch is not installed, it most likely is a sourcing issue.

