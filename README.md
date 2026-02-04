# Docker
# Noetic Container
./start noetic_dev_fixed --homedir ./Noetic_Projects/ --name noetic_dev_fixed --rosip 10.104.144.3 --rosmasteruri http://10.104.144.3:11311<br>
# Jazzy Container
./start jazzy --homedir ./Jazzy_Projects/ --name jazzy --extra "-e ROS_DOMAIN_ID=10"<br>
# Bridge Container
./start ros-jazzy-ros1-bridge-builder:latest \
    --name ros1_bridge \
    --homedir ./Bridge_Projects/ \
    --rosip 10.104.144.3 \
    --rosmasteruri http://10.104.144.3:11311 \
    --extra "-e ROS_DOMAIN_ID=10"<br>
source /opt/ros/jazzy/setup.bash<br>
source /ros-jazzy-ros1-bridge/install/local_setup.bash<br>
ros2 run ros1_bridge dynamic_bridge --bridge-all-topics<br>


