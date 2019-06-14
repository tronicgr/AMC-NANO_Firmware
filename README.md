# AMC-NANO_Firmware
Firmware updates for the AMC-NANO

##Firmware procedure video for AMC-NANO:
https://www.youtube.com/watch?v=VA3Wm23lna4


##You can use the AMC config utility to access and modify the important parameters in the AMC-NANO:
https://github.com/tronicgr/AMC-NANO_Firmware/blob/master/AMC_Config_Utility.zip


### ======= enc_4dof_AMC-NANO_v1e AutoPark =======
```
release date: 06/12/2019: 
-Fixed serial command set for better integration with Simtools control software
-Added new Simtools interface plugin
```

### ======= enc_4dof_AMC-NANO_v1d AutoPark =======
```
release date: 04/29/2019: 
-Added automatic return to Park position (low position)
-Added manual Park/Standy/Emergency input
-Added manual Force Offline input (can be used to park the platform during gameplay).
-Easy reset to default parameters by holding Ready button while pressing Reset button.
  The LED will blink 5 times to indicate parameters were restored to default.
-The four buttons do what they supposed to (move UP, move DOWN, Ready position, Park position).
  The actuators keep moving up or down smooth as long you hold each button.
```

### watch video that describe the new functions:
https://www.youtube.com/watch?v=lP70oLAv00g

### watch video of the power up sequence on the linear servomotor:
https://www.youtube.com/watch?v=yuvV4GP_SdY

### The parameters can be changed via terminal (250000 bps)

### ---List of commands---

Command Number | Display Parameter | Save Parameter
------------| ------------ | -------------
CMD01 |Motornumber: | spv012-spv018
CMD04 |Park Position: | spv04001-spv04254
CMD05 |Park Move Speed: | spv05001-spv05100
CMD06 |Park Move Timeout: | spv0601-spv0690
CMD07 |Standby Position: | spv07010-spv07245
CMD08 |Standby Speed: | spv08000-spv08100
CMD09 |Standby Timeout: | spv0901-spv0990
CMD10 |Disable park type: | spv111-spv114
CMD13 |Actuator Limits: | spv1300-spv1350
CMD14 |Kill switch mode: | spv141-spv142
CMD44 |Display all parameters 
CMD45 |Print this help page 
CMD55 |Print delimited parameter list for simtools
spv45 |Saves all parameters at once
RQM |  Displays model,revision and number of motors
Park | Parks the actuators if in standby mode

```
  Some Commands may not change value - locked

The CMD$$ displays each parameter, and spv$$### saves each parameter with the value indicated. 
To actually store the parameters in the flash memory you need to send "spv45" to save all 
parameters at once. The "$$" on the spv is the command number, and the "###" is the value, 
Some parameters have single digit value, some two digit value and some 3 digit value. 
All values are characters!

Here is a list of the default parameters values you should get when you issue the CMD44 command
(if not like this, you may reset the default parameters via button combination)

01.Motornumber 2-8: 4
04.Park Position 0-254: 1
05.Park_Move_Speed 1-100%: 11
06.Park_Move_Timeout 1-90: 5
07.Standby Position 10-245: 127
08.Standby Speed 0-100%: 24
09.Standby Timeout 1-90: 5
10.Disable park type 1-4: 1
13.Actuator Limits 0-50%: 1
14.Kill switch mode 1-2: 1

CMD55 returns the following numeric values separated by colon ( : ) punctuation mark:
"data:" <Motornumber> ":" <Parkposition> ":" <Parkmovespeed> ":" <Parkmovetimeout> ":" <StandbyPosition> ":" <StandbySpeed> ":"<StandbyTimeout> ":" <Disableparktype> ":" <ActuatorLimits> ":" <Killswitchmode> ":" <Firmwareversion> ":" <AMCModel>

```

##Wiring Diagram for emergency buttons and switches

![Alt Text](https://github.com/tronicgr/AMC-NANO_Firmware/blob/master/AMC-NANO%20park-standby-emergency-force-offline%20diagram.jpg)


### ======= enc_4dof_AMC-NANO_v1b =======
```
release date: 03/27/2019: 
Basic firmware with new IF (FF FF) and support for 4DOF
```


