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

Battery currently idea is 3S Lipo Battery for 11.2V supply, but research for a more sofisticated battery is probably smart.

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
