What should you install? 
I strongly recommend you to use the Jackal robot + the Jackal world. It's free, easy to use (Cartographer is already integrated), and very popular in the ROS community. To do so, you have to: 
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install ros-kinetic-jackal-gazebo ros-kinetic-jackal-desktop ros-kinetic-jackal-simulator ros-kinetic-jackal-viz ros-kinetic-jackal-description ros-kinetic-jackal-navigation (you can also install all the Jackal packages, except the 'cartographer-navigation' one)

You may have some problems while doing this, because these packages require some libraries that very specific and you probably don't have then pre-installed.


What next?
cd ~
mkdir -p <name of your workspace>/src
cd <name of your workspace> 
catkin_make
cd src
git clone https://github.com/jackal/jackal_cartographer_navigation.git

Now you should have everything you need to run the Cartographer with Jackal. You could try if everything works out by doing:
Terminal 1: roscore
Terminal 2: roslaunch jackal_gazebo jackal_world.launch
Terminal 3: roslaunch jackal_viz view_robot.launch
Terminal 4: roslaunch jackal_cartographer_navigation cartographer_demo.launch 

The first two roslaunch commands will execute the files you've installed at the beginning, whereas the last one relies on the files you've cloned. If you've managed to successfully launch all these ROS nodes, I recommend you to copy the launch file that I left here to make your life easier. 
