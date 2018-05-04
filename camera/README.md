# Cameras

For a simple example of robot-agnostic code, run:

```
python camera_simple.py --robot X
```

where `X` should be replaced with `hsr` or `fetch`, depending on your robot.
This will run some code and save some images from the robot's camera. See
`RESULTS.md` for more detailed examples.

In order for this to do something interesting, you need to start the Gazebo
simulator so that a ROS master exists. For the Fetch, one possibility is to run:
  
```
roslaunch fetch_gazebo playground.launch
```

in one tab, *then* run the python script in a separate tab. For the HSR, one
possibility is:

```
roslaunch hsrb_gazebo_launch hsrb_mock_home_world.launch
```

and then run the camera script.

Important Points:

- The `rospy.sleep(x)` code will hang if the Gazebo simulator is not running. In
  some cases you need to click the 'start' button (lower left corner) in the
  simulator before the robot's cameras see anything. It seems like the simulator
  is paused by default for the HSR, but runs automatically for the Fetch.

- It is helpful to adjust the gazebo simulator so that the robot is seeing
  something interesting. You can move the robot to a more interesting starting
  pose.

- Unfortunately, the Fetch documentation has some outdated topics listed, and
  seems to be shorter. [I filed an older issue about this here][1] which I've
  figured out.


[1]:https://github.com/fetchrobotics/fetch_ros/issues/74