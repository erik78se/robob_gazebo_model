# robob_gazebo_model

Contains the ROS .sdf gazebo model of the "robob" robot.

NOTE! Launch gazebo from the directory where the robob model is. Otherwise it cant find the robot model in gazebo.

Collada models needs to be found by gazebo as

Any package using "collada" models, must also do this: https://answers.ros.org/question/212113/problems-viewing-collada-files-in-gazebo-ros/

In package.xml

```
<export>
    <gazebo_ros gazebo_model_path="${prefix}/models"/> 
</export>
  
<run_depend>gazebo_ros</run_depend>
<build_depend>gazebo_ros</build_depend>
 ```

And in CMakeLists:
```
find_package(catkin REQUIRED gazebo_ros)
```

Then "catkin_make" to make sure nothing breaks.

