# Darknet YOLO with ROS 1

## Build:
1. Make a directory `ROS1_WS` to act as your ROS 1 workspace.
    ```bash
    $ mkdir -p ~/ROS1_WS/src/
    ```
2. Clone this repository:
    ```bash
    $ git clone https://github.com/Tinker-Twins/YOLO-ROS-1.git
    ```
3. Install [`OpenCV`](https://opencv.org) (or [build from source](https://docs.opencv.org/3.4/d7/d9f/tutorial_linux_install.html)).
    ```bash
    $ sudo apt update
    $ sudo apt install libopencv-dev python3-opencv
    ```
4. Build [`boost`](https://www.boost.org).
    ```bash
    $ cd YOLO-ROS-1/boost
    $ ./bootstrap.sh
    $ ./b2 headers
    ```
5. Build the ROS packages (build in `Release` mode to maximize performance).
    ```bash
    $ cd ~/ROS1_WS
    $ catkin_make -DCMAKE_BUILD_TYPE=Release
    ```
6. Source the `setup.bash` file of your `ROS1_WS`.
    ```bash
    $ echo "source ~/ROS1_WS/devel/setup.bash" >> ~/.bashrc
    $ source ~/.bashrc
    ```

## Execute:
```bash
$ roslaunch darknet_ros darknet_ros.launch
```
