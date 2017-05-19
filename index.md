# Semi-Autonomous RC Car 
## Bates Raspberry Pi Short Term Class 2017


### May 3 2017
This is the first day we have really begun to work on the project. The goal for today was to take apart the RC car we bought and begin to understand how it works. Because some of our parts were still in the mail we spent a good portion of the day reading tutorials and working with OpenCV. By the end of the session our Pi's camera could recognize faces using OpenCv.
- Tutorial we used for OpenCV [Link](https://pythonprogramming.net/loading-images-python-opencv-tutorial/)




### May 8 2017
Since our last update we have ordered all the parts and successfully taken apart the car. We have taken apart the car so we can control both the motor that turns the front wheels, and the motor that controls forward and reverse.
    
Our next goal is to set up our Raspberry Pi to the Bates wifi network. Once that is done we are following this tutorial to control our car through a python script with the Pi.

- Tutorials we are using for the seting up the car - [Link](http://www.instructables.com/id/Controlling-a-Raspberry-Pi-RC-Car-With-a-Keyboard/)
[Link](http://www.instructables.com/id/Raspberry-Pi-2-WiFi-RC-Car/)
- Tutorial with helpful diagrams for hardware - [Link](http://forums.parallax.com/discussion/156410/how-to-use-a-l298n-dual-h-bridge-with-a-microcontroller-quickstart-board)

Once we took apart the car we started to hook up the L298D chip to the car motors and battery. 



As today wraps up our goals are to connect the motors to the Pi. Most of our wires are now set up and good to go. 

Notes: We are being extremely careful to label and track all the screws we are using. Each RC car is different, so we need to be careful with the car and its parts since there is no clear way to take it apart and put it back together. When hardwiring the car we are careful with the live wires, as we are trying to avoid any sparks. 

### May 9, 2017

We finally configured all the motors, pi and L298D chip. 

Once this was done we set up a python file to run each motor for a set period of time. Using this file we can get the car to run the motors using the pi.

- Tutorial we used for code [link](http://deepaksinghviblog.blogspot.com/2014/08/raspberrypi-to-run-dc-motor-using-l298n.html)
- This tutorial was helpful with the coding but we had to add extra lines for the second motor, as it controlled each motor individually.

The next step is to rebuild the car and set up the sensor.  

Here is a video of us running the python file to start each motor. Notice how the motors go in each direction for 3 seconds. 
(Video 8850 here) 

### May 10, 20

Today we rebuild the car. This took a lot of troubleshooting and time, so we could not accomplish much today. The car is now ready to drive using our python script. We corrupted our first SD card so we will be using the one Bates provided us.

GPIO pins (for just the motors):

2(red)
4
6(gray)
8
10
12
14
16
1
3
5
7(purple)
9
11(blue)
13(green)
15(yellow)



###May 11, 2017

Brown-red-red is 330 Ohms

Resistor color code: https://sub.allaboutcircuits.com/images/11066.png

We attached our first sensor to the car. This proved to be quite complicated because we had to use the breadboard, wires, and resistors. 



We are using an HC-SR04 sensor. These are the tutorials we are using to wire the sensor. 
- [Linkl(https://www.modmypi.com/blog/hc-sr04-ultrasonic-range-sensor-on-the-raspberry-pi)
- [Linkl(https://www.raspberrypi.org/learning/physical-computing-with-python/distance/)

### May 12, 2017 

We got the sensor working today using the code in following link. We disconnected the pi from the L298D chip, so that the sensor was the only thing connected to the pi. Once we got the sensor working, we connected the chip back to the pi and made sure that the sensor and motors were working. 

[Link](http://www.knight-of-pi.org/ultrasonic-range-detection-with-the-raspberry-pi/)

We are now working on combining both our functions to run them through one script. 

### May 15, 2017

Sensor now works while motor is running. However, we encountered some bugs when stopping the program (the wheel was still turning after the program was killed).

In our picar.py file we controlled the car as such. If object detected using HC-Sr04 sensor within 10cm, the car will reverse. If object detected within 10-20cm, the car will turn right. If object detected at a greater than 20cm distance, continue straight. This worked as anticipated, however we were unable to break out of the while loop.  

To fix this, Matt tried to write a function which starts/stops the program from running using the keyboard.  We will finalize the object detection tomorrow.  

### May 16 and 17, 2017

May 16th was tough because some of our wires started to melt. We spent most of the day rewiring and trouble shooting. 

May 17 was a much more successful day. We used the code file test1.py to get the car to run. Using the sensor which is now much more accurate and our newly re-wired motors, we were able to get the car to move forward on its on and stop if it detected something in front of the car within 50cm it stops. We stop the car by reversing it for 1 second. 

[insert video here]

###May 18, 2017:

Installed OpenCV using this installation guide: http://www.pyimagesearch.com/2016/04/18/install-guide-raspberry-pi-3-raspbian-jessie-opencv-3/

Installing OpenCV on Raspberry Pi takes a little over an hour and a half.  We are still waiting for installation to finish.  

While waiting, we mounted the Pi camera onto the front of the car 



Tomorrow we will use OpenCV and the pi camera to recognize a printed stop sign on a wall.  When the car ‘sees’ the sign, the car will stop moving forward.  

### May 19, 2017 

Today we finished installing OpenCV. While we were able to install OpenCV, we had trouble importing OpenCV from python in the shell. To fix this, we had to bind OpenCV to python using sudo apt-get install python-opencv. We spent the rest of the day working on the stop sign detection program. We are pulling code and files containing images of stop signs from the following link. 

- [Linkl(https://github.com/mbasilyan/Stop-Sign-Detection)






