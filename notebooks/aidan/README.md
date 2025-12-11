# **AIDAN VELDMAN NOTEBOOK**

## **9/12/2025 FRIDAY**

Today we met with the pitchers of our project and discussed a lot about what the design and ultimate goals of the projeect will entail. 
We were able to obtain the tube that the camera will travel down in the root system, which should help for our own visualization and further development of the design.

A major thing of note: I at the moment believe the focus of the project should be on the imaging portion of the camera, as the rest are achievable solutions that other root imaging cameras tackle,
but our current design would solve a lot of other issues. Also, if we can make a cheaper manufacturable variation of the camera it could be further developed for longer exposure in the accrylic tubes and maybe lessen manual interaction.

DESIGN NOTES: PCB will most likely have to be thin and vertical, on-board battery is most likely the less preffered method, since root images will want to be observed immediately after recording, so a usb interface to interect with a laptop is ideal.
              How the camera will be lowered will also be very important, as manual rappelling is significantly less complex but will have to be accounted for elsewhere, as the moment when images should be captured is tied to the location of the camera and speed it descends.
              We have discussed multiple ways to do this but ultimately there is not too much of a consensus yet. An encoder that tracks the location of the wheels may be preffered but implementation is questionable.

## **9/18/2025 THURSDAY**

We met again today with John and Jeremy (the pitchers), as well as Sam who is heavily involved in the scanning and research of the plants. We discussed similar things 
to our first meeting but went more in depth in the expected outcome of the project.

The biggest deliverables is a reduced time in taking the images (CID scanners take 4 minutes per picture), and more reliability and ease of use.

We are going to meet with them for an on-site demonstration of the current field equipment tomorrow.

## **9/19/2025 FRIDAY**

We went down to the SoyFACE fields in the late morning and got to see a demonstration of Both the currently used CID scanner and the older BART scanner
from the 80s. See attached images and video for reference.

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/IMG_2007.HEIC "Logo Title Text 1")

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/IMG_2008.HEIC "Logo Title Text 1")

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/IMG_2009.HEIC "Logo Title Text 1")

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/IMG_2011.HEIC "Logo Title Text 1")

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/IMG_2012.HEIC "Logo Title Text 1")

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/Photo%202025-09-19%2003.21.43%20PM.heic "Logo Title Text 1")

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/9-19%20Field%20Pics%20and%20Videos/20jun2025%20camera%201v7%20ilje%20kk%201-5_T86_L3_20.06.25_174843_1_Untitled.png "Sample CID Scanner imagee 1")

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/9-19%20Field%20Pics%20and%20Videos/20jun2025%20camera%201v7%20ilje%20kk%201-5_T86_L4_20.06.25_174910_1_Untitled.png "Sample CID Scanner imagee 2")

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/9-19%20Field%20Pics%20and%20Videos/20jun2025%20camera%201v7%20ilje%20kk%201-5_T87_L1_20.06.25_174342_1_Untitled.png "Sample CID Scanner imagee 3")

Biggest things taken from this meeting are taking the best of both scanners and combining them in a much more common sense implementation. A gear rack use like the
BART combined with much better scanning and encasing of the CID. Both have poor cable output, and a single attachment of a USB to a computer as a data output and
Power supply input is pretty much a requirement.

Afterwards we met with Greg in the ECEB Machine shop and were able to iron out and focus on design details. We were able to discern that this is going to be a
very involved and difficult to pull off project, but after lots of discussion our current best design is as follow:

-The camera will still be pointed at a conical reflective surface, whether it be polished metal, glass, mirror, or window tints. A ring of led's will be supported above the camera illuminating the surroundings, and all this will be encapsulated in a transparent tubing. The camera will have a telecentric lens pointed down a the reflective cone, which should then be able to extrapolate a ring of useful imagery that can be further proccessed and stitched together with other pictures it takes into a rectangular one.

-The tube will then also be capped, and on said caps will be wheels with flexible o-rings in order to fit snugly within the tube and to discourage wobble and       uneven placement.

-The output of this will be cords from the top of the tube, following up a gear shaft at the top, of which the cords will be positioned and flow out the top of the 6-foot gear shaft containment to the main pcb located at the cap affixment. These cords will contain power to the camera and LED's as well as control signals for when to act. Outputting through this cord will be the camera data sent back to the microcontroller. 

-The main pcb will have the connections to the LEDs and camera, the microcontroller, a USB connection to be supplied power and to output data, and connections to a motor and encoder for controlling and measuring movement of the system.

-The motor will move the gear along the gear shaft, pushing the camera down/up and with an encoder tracking its movement, sending signals to the microcontroller to calculate control signals for the rest of the system (when to take pictures, motor speed, etc.).

These are the overall design ideas we have so far. A meeting will be setup between John, Jeremy, Sam, Our group, and Greg for further discussion.

## **9/23/2025 TEUSDAY**

We did the proposal, work was done on it beforehand but was pretty unsatisfactory and mainly in theory. I started to work after the fact on more grounded/quantifiable changes, mainly on power and simplifying the block diagram.

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/blockdiagram923.png "block diagram")

Connection to the motor from control will still need to be added; most likely H-Bridge control of it.
specific parts for the regulators: LM2675 Step-Down Voltage Regulator and LD1117-3.3 Linear Voltage Regulator.

Battery currently idea is 3S Lipo Battery for 11.2V supply, but research for a more sophisticated battery is probably smart.

## **9/25/2025 THURSDAY**

I had planned an earlier meeting with everbody involved so far, TA, Pitchers, and Gregg (machine shop). We met at 8:30 and discussed needs for the project.
Big takeaway is we need to get parts ordered and measurments solidified so we can get necessary machine shop additions and a prototype going for solidifying designs

Afterwards we met with the TA for a proposal rerun, where after discussed we need to do as said above, and I will focus on lumen requirements for our project so we can get a solid LED setup, and also making sure our power from the battery and connections overall is more set in stone. 

## **9/28/2025 SUNDAY**

I am currently doing lighting calculations/research on the desired lumens for inside the tube. The calculations are to optimize shutter speed (by giving the camera enough light to rapidly take pictures), but at the same time not creating too much noise from the lighting and/or preventing uneven shadings.

To get a rough feel for the lighting I am first looking at the CI-602 Manual, which is a different root imaging scanner that has a lighting system. I've downloaded the manual from this site:
https://ictinternational.com/product/ci-600-and-ci-602-in-situ-root-imagers/

^(DELAYED, DOCX FILE IS 425 MB AND I DON'T YET KNOW HOW TO OPEN, NEED TO DOWNLOAD MICROSOFT WORD)
^(microsoft word can't do it either)

The OV5640 does not have info on lighting requirements, but it does state that it has built in anti-smearing and other image distortion preventing things.
Also very useful to note and important to bring up to TA's, is that the OV5640 has a built in microcontroller that can store an image, which would alleviate some of our issues if allowed.

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/OV5640-text.png "text discussed")

it allows 256 OTP memory in total

It is also important to note that the OV5640 has built in shutter modes, however for our purposes we could ignore those and just keep the LED's on since there is no reason that we need to line up for flashes. Also, the OV4560 is more built for videos not pictures, but should be able to function still in one-pic taking by just enabling the stream, waiting for the VSYNC to communicate when the picture is done, and then disabling the stream. This works since the VSYNC defines the boundaries/is defined by the boundaries of the frame of the data, so one window of data for a frame is transmitted, then we cut off.

generally, it seems there is not any specific lighting requirement told by the OV5640, so it is hard to get a requirement. Online research seems to fair that it is very environment and camera specific, but a general estimation seems to be 50 lumens would be good. This could be achieved through a single white LED, so spreading at least six of them to disperse light evenly in all the directions should be good.

## **9/28/2025 TUESDAY**

scrap the OV5640, we are now opting for a raspberry pie and a simpler camera to interface with it. This way, we can hopefully use USB connections and not need to rely on a lot of stuff we did not realize. Now, I will also need to supply power to the other portions, but it shouldnt be too complicated, considering we already have the step downs. 

With the raspberry pi, all that will be needed to be done will have the camera interface with it via USB, where a few lines of code in the PI will activate given a control input from the Microcontroller. 

https://www.digikey.com/en/products/detail/dfrobot/FIT0701/13166487 this is a sample camera i was looking at, however I am awaiting for approval of similar cameras from the TA, as such a camera is under devboard in digikey which is a grey area in use case.

Elsewise, I am beginning a rough schematic on KiCad which I plan to bulk complete tomorrow before our meeting on thursday.

## **10/01/2025 WEDNESDAY**

I am finalizing certain parts right now, if not mainly to get at least a first CAD schematic and PCB down. Biggest issue I am facing is finding the right H-bridge, since I will probably have 5 V input for the logic gates, but will need 12-10 V transfer of the load voltage, with decent ampage of 2-4 A.

best part fitting these I have found so far is the L298N Full-Bridge Motor Driver Dual https://cdn.sparkfun.com/assets/7/1/d/6/c/Full-Bridge_Motor_Driver_Dual_-_L298N.pdf

for the 12V to 5V step down we will need, I have the LM2675-5.0 StepDown Voltage Regulator https://www.ti.com/lit/ds/symlink/lm2675.pdf?ts=1759287479536&ref_url=https%253A%252F%252Fwww.google.com%252F

FOR MYSELF (this all mostly is): INT0 is the INTERRUPT pin for any encoder since only D2 and D3 can be interrupts

### **PART LISTS:**

1uF Capacitor: 0805_2012Metric from Soldering assignment

100uF Capacitor: 1206_3216Metric 
  https://www.digikey.com/en/products/detail/samsung-electro-mechanics/CL31A107MQHNNWE/10479833

10nF Capacitor: 0402_1005Metric
  https://www.digikey.com/en/products/detail/murata-electronics/GRM155R71C103KA01D/587215

22p Capacitors (2): 0603_1608Metric
  https://www.digikey.com/en/products/detail/kemet/C0603C220J5GACTU/411055

68uF Capacitor: 1206_3216Metric
  https://www.digikey.com/en/products/detail/tdk-corporation/C3216X5R0J686M160AB/3951907

47uH Inductor: 0603_1608Metric
  https://www.digikey.com/en/products/detail/taiyo-yuden/CBMF1608T470K/1007996

10k Resistor: 0805_2012Metric from Soldering Assignment

1k Resistor: 0805_2012Metric from Soldering Assignment

16MHz Oscillating Crystal: 0.197" L x 0.126" W (5.00mm x 3.20mm)
  https://www.digikey.com/en/products/detail/abracon-llc/ABM3-16-000MHZ-D2Y-T/2344578

I have now completed the first version of the schematic, with the modules like the step down voltage regulator administered with the required components around it (added the inductor capactiors etc.).

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/schemv1.png "First Schematic")

I have also just finished routing the PCB, I am kind of iffed by it, I am definitely not a pro at this and need to ask the TA about optimizing it. 

BIG QUESTION: CAN I ROUTE GROUNDS TOGETHER AS WELL AS HAVE THE ZONE?!?!? SEE CENTER OF MCU FOR REFERENCE

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/pcbver1.png "First PCB routed")

## **10/02/2025 THURSDAY**

Our meeting today went well, I have a current camera for our raspberry pi camera subsystem for the breadboard demo, however we should get details of a lot of the specs and information of the camera down before the demo. 

I am going to swap some parts on the PCB since if they are available in the ECEB supply shop that would be loads more convienient.

### ** NEW PART LISTS:**

1uF Capacitor: 0805_2012Metric from Soldering assignment

100uF Capacitor: 1206_3216Metric 
  https://www.digikey.com/en/products/detail/samsung-electro-mechanics/CL31A107MQHNNWE/10479833

10nF Capacitor: 0402_1005Metric
  https://www.digikey.com/en/products/detail/murata-electronics/GRM155R71C103KA01D/587215

22p Capacitors (2): 75-561R10TCCQ20 

68uF Capacitor: 1206_3216Metric
  https://www.digikey.com/en/products/detail/tdk-corporation/C3216X5R0J686M160AB/3951907

47uH Inductor: 0603_1608Metric maybe 70F475AI-RC ?
  https://www.digikey.com/en/products/detail/taiyo-yuden/CBMF1608T470K/1007996

10k Resistor: 0805_2012Metric from Soldering Assignment

1k Resistor: 0805_2012Metric from Soldering Assignment

16MHz Oscillating Crystal: 520-HCA1600-SX 

FROM FURTHER LOOKING; i'll need to get a fair amount of these from Digikey, but will also check the free supply area. Both oscillating crystal would work, but id prefer one through-hole or with leads.

## **10/02/2025 FRIDAY **

forgot to get USB cable for PI, sadly progress on that will now have to wait til' saturday.

Mainly, all that was done today was going to the PCB review to make sure my PCB is all in order. And, luckily it seems to be according to the TA's, it passed the DRC in kiCad and the PCBway audit, so here is the final PCB for our first version design of it:

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/pcb1.png "PCB ver 1")

## **10/05/2025 SUNDAY **
Okay, so the raspberry pi also needed a microSD card, and so I had to again wait till this sunday night till I could start. I began by onloading the OS onto the microSD via an adapter on my laptop, following the instructions in this tutorial (forum) for a headless installation (since i have no means to connect it to a microHDMI).

https://forums.raspberrypi.com/viewtopic.php?t=359482

afterwards, I plugged in the webcam and was able to test it out using the fswebcam command on putty, which was able to take pictures and store them on the microSD. This all took a while mainly because I was following online steps through forums, but it was simple.

Main issue now arised, is the raspberry pi needs WiFi to work since i do not have the GPIO command yet working and I need to figure out how it can boot it without needing any putty commands. I will continue this work on monday.

## **10/06/2025 MONDAY **

I have now made the python script for the taking of the pictures when GPIO pin 17 is high. It compiles/throws no syntax errors, but i need to first set up a peripheral connection of power to the GPIO pin in order to see if it actually functions.

Here is a screenshot of the code from putty (i used nano in the terminal to create it, there is a "FINALLY: GPIO.Cleanup()" that is outside the screenshot)

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/script1.png "python script")

[EXPLAIN AND CITE CODE HERE]

https://www.instructables.com/Trigger-a-Webcam-with-a-button-and-Raspberry-Pi -> This was a similar case that I used for the general setup in the script

https://raspberrypi-guide.github.io/electronics/using-usb-webcams -> This was used for fswebcam setups, kind of figured out the basics from here

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/GPIO.png "GPIO pins")

I used this graphic to determine the correct GPIO pin to connect to, which is important because a lot of these pins serve other functions and the names are misleading.

## **10/07/2025 TEUSDAY **

Now, we have setup the camera for prototype for the breadboard demo which went well. Here are images to display it:

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/camsetup.jpg "Camera Setup")

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/image14.jpg "sample image")

## **10/09/2025 THURSDAY **

From here, we are mainly waiting on parts. PCBs and what not, I have ordered the PCB components

## **10/15/2025 WEDNESDAY **

I have using some online code and resources compiled a python script for unwrapping the reflected image.

Here is the script (put in some fancy online image thing to look nice):

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/code.png "unwrapping script")

And here is the output of the image taken from the breadboard demo; one has a cut of an inner circle one is uncut

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/unwrappedCut.jpg "Unwrapped with Inner radius")

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/unwrapped.jpg "Unwrapped")

## **10/17/2025 FRIDAY **

Things are slowing down are mainly waiting on parts from machine shop and orders online, we setup our H-Bridge on a breadboard to begin testing to make sure it is working.

There are a few things we forgot, mainly capacitors needed in connection to the power sources on it to stop voltage overlaod and diodes to do the same from inducted voltage from the motor.

## **10/23/2025 THURSDAY **

PCB finally came in, however there are immediately present issues with it. All almost mainly with the fact that I have designed some of these componenets WAY too small.

we have an 0403 capacitor in the power portion of the PCB, which is way way too small to be hand soldered, at least thats what it looks like. I will go and redesign the PCB soon to fix that for sure.
a few other capacitors are also small but i am more confident on tose. As well as i am not so confident in the soldering of the microcontroller, looks very difficult to hand solder.

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/unwrapped.jpg "PCB hand comparison")

As well, we now have our Motor, however it has a very very small pin connector that the department store does not have. So i have instead opted to solder all the stripped wires off of it onto rainbow jumper cables i bought from the supply center.

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/unwrapped.jpg "Motor solder joints")

## **10/24/2025 FRIDAY **

Today we have hookedx the motor up to the H-Bridge for control before our breadboard demo #2. That is about all that we did today though, waiting on parts mainly, and we have time for the demo to finish a few more implementations.

## **10/27/2025 MONDAY **

Breadboard Demo 2, we setup a ruler and our first breadboard demo, as well as Nate made a spool thing to replace our movement system for now. The images are outputted and show portions of the ruler. 

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/unwrapped.jpg "breadboard demo 2")

## **10/29/2025 WEDNESDAY **

Began soldering today, there are definitely portions that cannot be done due to the small size. Mainly the capacitors that are too small, i even dropped and lost one that was the size of a ridge of my fingerprint, but other than that was able to get some decent soldering done

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/unwrapped.jpg "PCB progress")

## **10/30/2025 WEDNESDAY and 10/31/2025 THURSDAY and 11/1/2025 FRIDAY**

We started working on the lighting system, for now i have just started straight soldering some LEDs together to act as a ring to light up the reflection on the cone in the shuttle.

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/unwrapped.jpg "LED ring")

While i was doing this, Zach was pretty confident on learning Heat gun and solder paste for the microcontroller and looks like he did it well on the microcontroller. AS well as he directly soldered a capacitor onto the pad for the one i lost.

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/unwrapped.jpg "PCB progress2")

On friday we finished a very rugged demo of the lighting system and glare diffuser, made by Nate, for a little bit of a breadboard demo 3 for rishik.

![alt text](https://github.com/aidankv2/ECE-445-Notebooks/blob/main/Images-and-videos/diagrams-and-etc/unwrapped.jpg "shuttle prototype")
