# UR Scooter GUI
GUI application to integrate the UMLxNE Scooter software with a modern GUI interface.
Relies on TKinter and ROS. Designed for ROS Kinetic (partial testing done on Noetic).

**ROS Topics**  

**Subscribers**  
**/gui_wait**  
This will be pulled high by this program. Once the system is ready to move to the next state you must pull the topic
low.  
(Example: Once image of environment is ready, open the image. Once system finishes grasp pull it low, etc.)

**/success**  
This is published by the researched performing the subject. Determine whether the trial was a success or failure.

**Publishers**  
**/point**
Publishes a UInt32MultiArray with X at position zero and Y at position 1. This is the point the user clicked relative to
the original image

# Running Code
* git clone https://github.com/PatrickCPE/ur_scooter_gui.git ~/catkin_ws/src/
* cd ~/catkin_ws
* catkin build
* rosrun ur_scooter_gui ur_gui.py

# Requirements
For Python 2.7
* pip install python-tk
* pip install opencv-python

For Python 3.8
* pip3 install python3-tk    (Should be installed by default)
* pip3 install opencv-python    (Should be installed by default)

To you want to build docs   (Docs only built on python3)
* pip install -U python3-sphinx
* pip install -U groundwork-sphinx-theme    (Or switch for default themes: Alabaster)

**Build the docs**
* cd ur_scooter_gui/docs/
* make html
* Open the index.html in the _build folder with your preferred viewer

Can also generate pdf/latex/etc. version of the same docs