## RDSim 

![small_sim_world](./fig/small_sim_world.png)
![gazebo_screen](./fig/gazebo_screen.png)
![sensor_display_rviz](./fig/sensor_display_rviz.png)

### Install && build

```bash
export ${HOME}/auturbo_ws >> ./bashrc
cd ~/${WORKSPACE}/src 
git clone https://github.com/kimku-0112/RDSim.git
cd ~/${WORKSPACE} && colcon build --symlink-install && source install/local_setup.bash
```

```bash
sudo apt-get update
sudo apt install -y ros-humble-robot-localization
sudo apt install -y ros-humble-imu-filter-madgwick
sudo apt install -y ros-humble-controller-manager
sudo apt install -y ros-humble-controller-manager
sudo apt install -y ros-humble-diff-drive-controller
sudo apt install -y ros-humble-imu-filter-madgwick
sudo apt install -y ros-humble-interactive-marker-twist-server
# jackal-description 패키지는 아래의 추가 사항 참고
sudo apt install -y ros-humble-joint-state-broadcaster
sudo apt install -y ros-humble-joint-trajectory-controller
sudo apt install -y ros-humble-joy
sudo apt install -y ros-humble-robot-localization
sudo apt install -y ros-humble-robot-state-publisher
sudo apt install -y ros-humble-teleop-twist-joy
sudo apt install -y ros-humble-twist-mux
```

### Gazebo world launch

> Gazebo 맵만 실행시킬 경우
> 

```bash
ros2 launch rdsim_gazebo rdsim_gazebo_world.launch.py  
```

Robot Display launch 

> Gazebo 없이 로봇의 tf를 확인하고 싶을 경우
> 

```bash
ros2 launch rdsim_description rdsim_description.launch.py 
```

---

### Sim launch

```bash
ros2 launch rdsim_description rdsim_gazebo.launch.py 
```

### Jackal Controller launch

```bash
ros2 launch jackal_control control.launch.py 
```

### Jackal cmd 2 teleop cmd

```bash
ros2 launch jackal_control teleop_base.launch.py 
```
