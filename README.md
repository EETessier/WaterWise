<br />
<br />
<h1>WaterWise</h1>
<h2>Industrial Irrigation SCADA System</h2>

### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)
<br />
<br />
<h2>Description</h2>
WaterWise is a Python-based smart irrigation system utilizing Modbus TCP to control a pump with variable output and valves supplying five zones. It allows an operator to set targets for flow rate and soil moisture, while staying within regulatory limits for water usage. The program provides the option to automatically adjust the valves and pump output in response to current soil moisture and flow rates, or manually set them as may be needed for testing and troubleshooting.
<br />
<br />
<br />
<br />
<h2>Program Walk-Through</h2>

<p align="center">
<br />
<br />
<br />
Ensure screen resolution is set to an aspect ratio of 16:10. Common resolutions include 1920x1200 and 1680x1050. <br/>
<br />
<img src="https://imgur.com/G0uKDam.png" height="80%" width="80%" alt="WaterWise"/>
<br />
<br />
<br />
<br />
Open the WaterWise.exe program.  <br/>
<br />
<img src="https://imgur.com/4xZ7gCt.png" height="80%" width="80%" alt="WaterWise"/>
<br />
<br />
<br />
Notice several notifications pop up quickly, saying there is low moisture on all 10 soil moisture sensors. This is because the program does not control soil moisture data, it only controls a pump and 5 valves, responding to moisture data it receives from the Modbus PLC simulator. Since there are no actual soil moisture sensors or flow sensors connected to the system, it is best to activate a side program that automatically changes moisture readings according to flow rates over time, and sets flow rates to reasonable numbers based on current valve levels and pump output. To activate this side program, click on the Simulate System Input button, and select Auto. The program may take up to 20 seconds to open. <br/>
<br />
<img src="https://imgur.com/OBRMsAk.png" height="80%" width="80%" alt="WaterWise"/>
<br />
<br />
<br />
<br />
Set target flow rates using the Flow Rate Manager. The system will open valves and adjust pump output as needed to ensure target flow rates are met without the pump working harder than it needs to. With 100% pump output and all valves 100% open, each zone will reach 10 kL/min (10 000 L/min). With other valves closed, and one open, more water will be channeled through the open valve, sometimes allowing a flow rate over 10 kL/min in one zone.  <br/>
<br />
<img src="https://imgur.com/QOVXi0F.png" height="80%" width="80%" alt="WaterWise"/>
<br />
<br />
<br />
<br />
Set varying soil saturation goals. The margin ensures mechanical arms don't unnecessarily turn on as soon as the moisture falls slightly under the setpoint. Instead, after a moisture setpoint is reached, the zone will not be watered until its average moisture falls outside the margin.  <br/>
<br />
<img src="https://imgur.com/QrFRxh9.png" height="80%" width="80%" alt="WaterWise"/>
<br />
<br />
<br />
<br />
Zone and Pump Info buttons provide data on all areas of the system. Observe gradual adjustments in pump output and valves in order to meet new goals.  <br/>
<br />
<img src="https://imgur.com/W8RZMIQ.png" height="80%" width="80%" alt="WaterWise"/>
<br />
<br />
<br />
<br />
Click on Maintenance to view all data from the entire system. <br/>
<br />
<img src="https://imgur.com/jPl38Pk.png" height="20%" width="20%" alt="WaterWise"/>
<br />
<br />
<br />
<br />
The system integrates weather and forecast data, and just like the soil moisture, it is all zeros by default. Without configuring anything to give weather data to the Modbus PLC, the program will run on the unrealistic assumption that it is 0 degrees Celcius, 0% humidity, and 0 rainfall expected. In concept, if it is raining, the system should not be running, even if an area is currently quite dry. Most likely, it will just waste power, and overwater the field. If a little bit of rain is forecasted, and a spot is almost fully watered, it may stop watering on the assumption that the rain will be enough. This effectively lowers the setpoint depending on the amount of forecasted rain. In a similar way, the setpoints may need to be raised to account for forecasted hot and/or dry weather, as water may quickly evaporate from soil. The simplest way to adjust the weather data is to select Simulate System Input, and choose Manual. When the Manual Field Device Simulation program opens, select Weather Input, and adjust factors as you wish. <br/>
<br/>
<img src="https://imgur.com/y9pokwZ.png" height="80%" width="80%" alt="WaterWise"/>
<br/>
<br/>
<br/>
<br/>
Observe changes in appearance with increased moisture, and ceased watering on zones where setpoints have been reached. <br/>
<br />
<img src="https://imgur.com/u9zzI8J.png" height="80%" width="80%" alt="WaterWise"/>
<br />
<br />
<br />
<br />
Due to the dry climates where irrigation systems are used, water shortages are a real concern, bringing the necessity of water usage limits. The system will automatically turn off when the water use limit as set in the Water Use Manager is reached. The operator may change the usage period, as some areas are regulated by daily usage limits, others have weekly or monthly limits, and so on. For convenience, it will be simplest to set the water use period to a number of minutes, so that it does not have to run for hours before resetting. The operator may also set the water use limit. Water Use This Period is shown in the Maintenance frame, so the operator can monitor it actively.  <br/>
<br />
<img src="https://imgur.com/JFUtVZt.png" height="40%" width="40%" alt="WaterWise"/>
<br />
<br />
<br />
<br />
If water use period is set to 1 minute, and the water use limit is 18 kL, the pump will change to IDLE if the total water to flow through the pump surpasses 18 kL in less than 1 minute, and switch back to Pump ON after that 1 minute period expires. <br/>
<br />
<img src="https://imgur.com/3LSXfeq.png" height="40%" width="40%" alt="WaterWise"/>
<br />
<br />
<br />
<br />
All system data can be easily reviewed by selecting View History, and choosing the required data. <br/>
<br />
<img src="https://imgur.com/amXJNQc.png" height="30%" width="30%" alt="WaterWise"/>
<br />
<br />
<img src="https://imgur.com/aEeDYcO.png" height="80%" width="80%" alt="WaterWise"/>
<br />
<br />
<br />
<br />
Upon new installation, the system may require testing, making it desirable to manually open or close valves, and set the pump output. To do this, select Manual System Control, and click Yes to the confirmation message. Pump output and valves will not be automatically adjusted, they will maintain current levels until manually changed. The pump will still turn off if the water use limit is reached. <br/>
<br />
<img src="https://imgur.com/Lkl8uUi.png" height="40%" width="40%" alt="WaterWise"/>
<br />
<br />
<img src="https://imgur.com/E6mC3rz.png" height="80%" width="80%" alt="WaterWise"/>
<br />
<br />
<br />
<br />
To allow the system to adjust valves and pump output again, simply select the Flow Rate Manager. Since the system cannot adjust flow rates while controls are manually set, it will require the operator to return to automatic adjustment of valves and pump output in order to proceed to the Flow Rate Manager. <br/>
<br />
<img src="https://imgur.com/uIXNZWD.png" height="30%" width="30%" alt="WaterWise"/>
<img src="https://imgur.com/UYaTfk9.png" height="30%" width="30%" alt="WaterWise"/>
<br />
<br />
<br />
<br />
To close the program, the user may simply press Shut Down, or press the X button on the top right of the main control panel. The user may also close the field device simulation programs at any time. Do not close the Modbus PLC. Closing the main program will close all attached programs including the Modbus PLC, but it sequences the closing of programs in a way that avoids any errors. In the worse case, if the Modbus PLC is closed first, it may freeze the main program, and it will not close or respond until it is forced to close by Task Manager. <br/>
<br />
<img src="https://imgur.com/kuAEJGT.png" height="20%" width="20%" alt="WaterWise"/>
<br />
<br />
<img src="https://imgur.com/0jcrhPf.png" height="80%" width="80%" alt="WaterWise"/>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
