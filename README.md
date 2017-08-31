# robob_gazebo_model

# Background reading
A great place to start all this with models and gazebo
 http://moorerobots.com/blog

# Workflow
* Create a model for your robot or use/clone an existing
* Modify your package.xml if needed (See below)
* Add joints/links for any moving parts, like wheels and scanners
* Add plugins for those objects wheels/driving which might publish stuff to ROS topics.

# Content of this repo
Contains the ROS .sdf gazebo model of the "robob" robot.

NOTE! Launch gazebo from the directory where the robob model is. Otherwise it cant find the robot model in gazebo.

# Modify Collada models 
Any package using "collada" models, must also do this: https://answers.ros.org/question/212113/problems-viewing-collada-files-in-gazebo-ros/

To make collada models be found by gazebo.

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

