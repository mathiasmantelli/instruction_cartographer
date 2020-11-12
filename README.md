# What should you install?
I strongly recommend you to use the Jackal robot + the Jackal world. It's free, easy to use (Cartographer is already integrated), and very popular in the ROS community. To do so, you have to:
```python
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install ros-kinetic-jackal-gazebo ros-kinetic-jackal-desktop ros-kinetic-jackal-simulator ros-kinetic-jackal-viz ros-kinetic-jackal-description ros-kinetic-jackal-navigation (you can also install all the Jackal packages, except the 'cartographer-navigation' one)
```

You may have some problems while doing this, because these packages require some libraries that very specific and you probably don't have then pre-installed.


# What next?
```python
cd ~
mkdir -p <name of your workspace>/src
cd <name of your workspace> 
catkin_make
cd src
git clone https://github.com/jackal/jackal_cartographer_navigation.git
```
Now you should have everything you need to run the Cartographer with Jackal. You could try if everything works out by doing:<br />
Terminal 1: roscore<br />
Terminal 2: roslaunch jackal_gazebo jackal_world.launch<br />
Terminal 3: roslaunch jackal_viz view_robot.launch<br />
Terminal 4: roslaunch jackal_cartographer_navigation cartographer_demo.launch<br />
<br />
The first two roslaunch commands will execute the files you've installed at the beginning, whereas the last one relies on the files you've cloned. If you've managed to successfully launch all these ROS nodes, I recommend you to copy the launch file that is here within this repository, to make your life easier. It launches at once all the ROS nodes that are launched by the aforementioned launch files.<br />
<br />
I also recommend you to check out the following pages: <br />
The [list of Jackal](https://github.com/jackal) repositories on GitHub. Here you can find all the packages you've install at the beginning;<br />
The [Jackal tutorial](http://www.clearpathrobotics.com/assets/guides/kinetic/jackal/simulation.html) provided by ClearPath. Here you can find some step-by-step tutorials to make Jackal environment works in your computer.  
