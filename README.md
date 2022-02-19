# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

Step1:start

Step2:from robo master import robr

Step3:instalize the type

Step4:run the program to move the robo master throgh our conditons

Step5:close 

## Program
from robomaster import robot
import time
from robomaster import camera

if name == 'main':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis
    ep_camera = ep_robot.camera
    ep_led = ep_robot.led    
    '''
    x = x-axis movement distance,( meters) [-5,5]
    y = y-axis movement distance,( meters) [-5,5]
    z = rotation about z axis ( degree)[-180,180]
    xy_speed = xy axis movement speed,( unit meter/second) [0.5,2]
    '''
    print("Camera streaming started...")
    ep_camera.start_video_stream(display=True, resolution=camera.STREAM_360P)    
        
    ep_chassis.move(x=1, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0.5, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=-1, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0.5, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=1, y=0 , z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0.5, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=-1, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0.5, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=2, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0, z=90, xy_speed=0.75).wait_for_completed()

    ep_led.set_led(comp="all",r=255,g=0,b=0,effect="on")   
    time.sleep(2)    

    ep_chassis.move(x=2, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_camera.stop_video_stream()
    print("Stopped video streaming...")

    ep_robot.close()

## MobileRobot Movement Image:
![robo](./img/robomaster.png)
![output](https://github.com/VINUTHNA-2004/mobilerobot-openloopcontrol/blob/main/ss.jpeg?raw=true)
![output](https://github.com/VINUTHNA-2004/mobilerobot-openloopcontrol/blob/main/e.jpeg?raw=true)

## MobileRobot Movement Video:
https://youtu.be/-7BQaHyh0xc


## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.


<br/>
<br/>

```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
