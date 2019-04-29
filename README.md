# AMC-NANO_Firmware
Firmware updates for the AMC-NANO

##Firmware procedure video for AMC-NANO:
https://www.youtube.com/watch?v=VA3Wm23lna4


### ======= enc_4dof_AMC-NANO_v1b =======
```
release date: 03/27/2019: 
Basic firmware with new IF (FF FF) and support for 4DOF
```


### ======= enc_4dof_AMC-NANO_v1d AutoPark =======
```
release date: 04/29/2019: 
-Added automatic return to Park position (low position)
-Added manual Park/Standy/Emergency input
-Added manual Force Offline input (can be used to park the platform during gameplay).
-Easy reset to default parameters byt holding Ready button while pressing Reset button.
  The LED will blink 5 times to indicate parameters were restored to default.
-The four buttons do what they supposed to (move UP, move DOWN, Ready position, Park position).
  The actuators keep moving up or down smooth as long you hold each button.
```
##The parameters can be changed via terminal (250000 bps)
```
 ---List of commands---
CMD01 Motornumber: spv012-spv018
*CMD02 Dataformat: spv021-spv022
*CMD03 Print Feedback: spv031-spv032
CMD04 Park Position: spv04001-spv04254
CMD05 Park Move Speed: spv05001-spv05100
CMD06 Park Move Timeout: spv0601-spv0690
CMD07 Standby Position:  spv07010-spv07245
CMD08 Standby Speed: spv08000-spv08100
CMD09 Standby Timeout: spv0901-spv0990
CMD10 Disable park type: spv111-spv114
*CMD11 Output type: spv111-spv114
*CMD12 Output mode: spv121-spv124
CMD13 Actuator Limits:  spv1300-spv1350
CMD14 Kill switch mode:  spv141-spv142
CMD44 Display all parameters values
CMD45 Print this help page
spv45 Saves all parameters at once
RQM - Displays model,revision and number of motors
Park - Parks the actuators if in standby mode

  *Commands with asterisk in front may not change value

The CMD$$ displays each parameter, and spv$$### saves each parameter with the value indicated. 
To actually store the parameters in the flash memory you need to send "spv45" to save all 
parameters at once. The "$$" on the spv is the command number, and the "###" is the value, 
Some prameters have single digit value, some two digit value and some 3 digit value. 
All values are characters!

Here is a list of the default parameters values you should get when you issue the CMD44 command
(if not like this, you may reset the default parameters via button combination)

01.Motornumber 2-8: 4
02.Dataformat 1-2: 1
03.Print Feedback 1-2: 1
04.Park Position 0-254: 10
05.Park_Move_Speed 1-100%: 5
06.Park_Move_Timeout 1-90: 10
07.Standby Position 10-245: 127
08.Standby Speed 0-100%: 20
09.Standby Timeout 1-90: 10
10.Disable park type 1-4: 1
11.Output type 1-4: 4
12.Output mode 1-4: 3
13.Actuator Limits 0-50%: 1
14.Kill switch mode 1-2: 1
```

##Wiring Diagram for emergency buttons and switches

![Alt Text](https://github.com/tronicgr/AMC-NANO_Firmware/blob/master/AMC-NANO%20park-standby-emergency-force-offline%20diagram.jpg)
