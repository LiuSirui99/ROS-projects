# ROS-projects


# Title

My learning process in ROS， including the setting and debugging processes. 


## Installation

### Clone

- Clone this repo to your local machine using `https://github.com/LiuSirui99/ROS-projects.git`

### Setup

- **For MacOS:** :white_check_mark:

    Build with docker. 
    ```
   $  docker pull ct2034/vnc-ros-kinetic-full
    ```
    In case of `error : unauthorized: incorrect username or password`
    ```
     $ docker logout
     $ docker login
     ```
     Run the server in the terminal:
     ```
     $ docker run -it --rm -p 6080:80 ct2034/vnc-ros-kinetic-full
     ```
     Then Browse <a href="http://127.0.0.1:6080/" target="_blank">`http://127.0.0.1:6080/`</a>.
     
     In case of `error: ROS waiting for master`
     ```
     $ roscore
     ```
     

- **For Ubuntu:**
    
    Because I am using the ubuntu VM in MacOs, which is 32-bit. But ROS only supports amd64, which is 64-bit, so I can only install it from source. You can see the detailed process at <a href="https://opencv.org/releases/" target="_blank">`http://wiki.ros.org/melodic/Installation/Source`</a> 
    
    
    **The steps**:
    
    1. Set the Ubuntu universe repositories enabled
    
    2. Set up the souces.list
    ```
    $ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
    ```
    3. Set up your keys
    ```
    $ sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
    ```
    4. Installing bootstrap dependencies
    ```
    $ sudo apt-get install python-rosdep python-rosinstall-generator python-vcstool python-rosinstall build-essential
    ```
    5. Initializing rosdep
    ```
    $ sudo rosdep init
    $ rosdep update
    ```
    6. Create a catkin Workspace
    ```
    $ mkdir ~/ros_catkin_ws
    $ cd ~/ros_catkin_ws
    ```
    7. Next we will want to fetch the core packages so we can build them. 
    
    We will use vcstool for this
    ```
    $ sudo apt install python3-vcstool
    $ rosinstall_generator desktop_full --rosdistro melodic --deps --tar > melodic-desktop-full.rosinstall
    $ vcs import src < melodic-desktop-full.rosinstall
    ```
    In case of `error: 'src not found'`
    ```
    $ mkdir src
    $ cd src
    ```
    8. Resolving Dependencies
    ```
    rosdep install --from-paths src --ignore-src --rosdistro melodic -y
    ```
    9. Building the catkin Workspace
    ```
    $ ./src/catkin/bin/catkin_make_isolated --install -DCMAKE_BUILD_TYPE=Release
    ```
    10. Now the packages should have been installed to `~/ros_catkin_ws/install_isolated` or to wherever you specified with the --install-space argument. 
    
    If you look in that directory you will see that a `setup.bash` file have been generated. 
    
    To utilize the things installed there simply source that file like so: 
    ```
    $ source ~/ros_catkin_ws/install_isolated/setup.bash
    ```
    

## Contributing

> To get started...

### Step 1

- **Option 1**
    - 🍴 Fork this repo!

- **Option 2**
    - 👯 Clone this repo to your local machine using `https://github.com/LiuSirui99/ROS-projects.git`

### Step 2

- **HACK AWAY!** 🔨🔨🔨

### Step 3

- 🔃 Create a new pull request using <a href="https://github.com/LiuSirui99/ROS-projects/compare/" target="_blank">`https://github.com/LiuSirui99/ROS-projects/compare/`</a>.

---

## Usage

```
Follow the step by step ROS installation, env setting and project codding process. 

Hope I will keep pushing.

```


## License

Liu Sirui (liusirui1234@gmail.com)
