# mecanumbot_ostensive repository

Requirements - A ROS2 package that
  - Takes camera stream input from /camera/image_raw (sensor_msgs.msg Image)
  - Detects people on the camera stream with their pose estimates
  - Detects a signal for attention (eg, hand/leg movement)
  - Chooses a target person after it shows the signal
  - Deciphers direction cues from the person's movement (eg, showing direction with hands)
  - keeps the person of interest in focus by calculating their position on the image and turning toward them,
                    - using the person's position relative to the camera image,
                    - the robot's current pose from the /amcl_pose  (geometry_msgs.msg PoseWithCovarianceStamped)
                    - and publishes the new pose to the goal_pose topic (geometry_msgs.msg PoseStamped)
