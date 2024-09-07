
## Included packages

* `alpha_bot_description` - holds the sdf description of the simulated system and any other assets.

* `alpha_bot_gazebo` - holds gazebo specific code and configurations. Namely this is where systems end up.

* `alpha_bot_application` - holds ros2 specific code and configurations.

* `alpha_bot_bringup` - holds launch files and high level utilities.

### Requirements
This project was made for ros2 jazzy and gazebo harmonic

1. Install necessary tools

    ```bash
    sudo apt install python3-vcstool python3-colcon-common-extensions git wget
    ```

### Create workspace

   ```bash
   mkdir -p alpha_bot_ws/src
   cd alpha_bot_ws/src
   ```

## Usage

1. Install dependencies

    ```bash
    cd alpha_bot_ws
    source /opt/ros/jazzy/setup.bash
    sudo rosdep init
    rosdep update
    rosdep install --from-paths src --ignore-src -r -i -y --rosdistro jazzy
    ```

2. Build the project

    ```bash
    colcon build --cmake-args -DBUILD_TESTING=ON
    ```

3. Source the workspace

    ```bash
    source install/setup.sh
    ```

4. Launch the simulation

    ```bash
    ros2 launch alpha_bot_bringup diff_drive.launch.py
    ```
