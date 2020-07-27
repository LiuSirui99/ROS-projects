<bold>ROS Notes</bold>

1. create the workspace:
   $ mkdir -p <link:url>~/catkin_ws/src</link:url>
 *** place where we put the packages
   $ cd <link:url>~/catkin_ws/</link:url>
 *** workspace itself
   $ catkin_make: initialate workspace 
   
2. sudo apt install tree 
	( for betther structure visualization)

3. package has 2 OBLIGATORY components:
    i) <bold>CMakeLists.txt</bold> : define the package name, dependencies, source file, destination file and so on 
    ii) <bold>package.xml</bold>:     describe the package name, version number, maintainer, dependencies.
    iii) src/:   store the ROS source files, including .cpp, .py
    iv) include/ :   headers
    v)  scripts/ : store the .sh, .py
    vi)  models/: store the machine animate 3D models (.sda, .stl, .dae....)
    vii) <bold>urdf</bold>/:  store the describtions of robot models ( .urdf or .xacro) 定义了机器人的连杆和关节的信息，位置，角度等，可在可视化调试和仿真中显示
    viii) <bold>launch</bold>/: store the launch files (.launch or .xml) 对ROS 需要运行哪些package下的哪些可执行程序及参数命令等进行了打包
	
4. Create a test package:
	$  catkin_create_pkg test_pkg roscpp rospy std_msgs
	其中 <highlight>catkin_create_pkg</highlight> 帮助完成了软件包的初始化，并填充好了CMakelist.txt &amp;&amp; package.xml，以及相关的依赖项

5.  package 相关命令：
     <bold>rospack</bold>： rospack list ( list all packages)
		     rospack depends [package] (show the package's dependencies)
                    rospack find [package] ( locate the package)
                    rospack profile ( fresh all packages location records)
   
     <bold>roscd</bold>: similar to cd but we can cd the package's path
		$ roscd [package]
 
     <bold>rosls</bold>: similar to ls but operate to the package 
     		$ rosls [package] : list the files under the package

     <bold>rosdep</bold>:  managing the package dependencies
	  	$ rosdep check [package]: check dep whether satisfied
		$ rosdep install [package]: 安装依赖
		$ rosdep db: 生成和显示依赖数据库
		$ rosdep init: 初始化 <link:url>/etc/ros/rosdep</link:url> 中的源
		$ rosdep keys: 检测 package 依赖是否满足
		$ rosdep update: 更新本地rosdep的数据库

<italic><highlight>rosdep install --from-paths src --ignore-src --rosdistro=kinetic -y	 </highlight></italic> 安装src下所有package的依赖项


*** metapackage 是一个功能包集，将多个功能相近，甚至互相依赖的软件包放到一个集合中去。
	常见的名称有：
	1. navigation: 导航相关的功能包集 <link:url>https://github.com/ros-planning/navigation</link:url>
	2. moveit: 运动规划相关的（机械臂） <link:url>https://github.com/ros-planning/moveit</link:url>
	3. image_pipeline: 图像获取、处理相关 <link:url>https://github.com/ros-perception/image_common</link:url>
	4. vision_opencv: 与opencv交互 <link:url>https://github.com/ros-perception/vision_opencv</link:url>
	5. turtlebot: turtlebot 机器人相关 <link:url>https://github.com/turtlebot/turtlebot</link:url>



ROS 通信架构



     


	</note-content>
</text><last-change-date>2020-07-27T16:32:13.041387Z</last-change-date><last-metadata-change-date>2020-07-27T16:32:13.042068Z</last-metadata-change-date><create-date>2020-07-27T15:48:42.438436Z</create-date><cursor-position>145</cursor-position><selection-bound-position>2360</selection-bound-position><width>450</width><height>400</height><tags><tag>system:notebook:ROS</tag></tags></note>

