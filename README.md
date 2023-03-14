# Museum Of Colonialization (MOC-II)
second iteration of the MOC, second microchallenge, 14. - 18. march 2023

**with marielle, carolina & stella**

our days are structured according to **[this plan](https://fablabbcn-projects.gitlab.io/learning/educational-docs/challenge/c_2/)**.

and in our part of the **[miro](https://miro.com/app/board/uXjVMeaB6bc=/)** we are trying to capture our thoughts.

next to the this repo, we are working also in a **[notion](https://hickory-polonium-fd1.notion.site/Marielle-Stella-Carolina-MDEF-22-23-34fdfc848ec44d93bae61fdf263d6c88)**


**what we ask**

maybe we could continue with our previouos idea of printing entry-tickets or receipts that a visitor gets once "visiting" the museum? **[printing device](https://www.google.com/search?q=bricogeek+impresora+termica&source=lmns&bih=712&biw=1312&client=firefox-b-d&hl=en&sa=X&ved=2ahUKEwip7Jynq9v9AhVwpycCHcn8B5EQ_AUoAHoECAEQAA)**

**what we do** 

*Description:* This is a guerilla stamp. When the user presses the button a speaker is activated, and the GPS location of the user is added to the MOC Map as you stamp a “thing”. The “thing” the user is stamping should be related to colonialism or ecological imperialism. The stamp is a QR code that allows the user to see the tagged locations of the different MOC spots.

<img src="../imagery/team.jpg" alt="drawing" width="800"/>

**what we provide** 


# how we get there - in theory

We combined the qualities we wanted our MOC Stamp to have and built upon the different ideas we wrote on post-its, mind-mapping and brain storming in 5min narrowed down our search for this machine’s second challenge.

**what needs to be done:**

device needs a battery and a whole to charge

determine location:
software - IP, a bit more complicated (@victor & oscar)
hardware - GPS

create button:
take the big button that exists (arcade style) and just print a "lid", nice cover

design stamp:
eva foam (block) - engrave really nice - really really nice to make stamps

programm speaker:
speaker;  sd-card holder / MP3 shield to store the sounds file


# how we get there - in practice

<img src="../imagery/team.jpg" alt="drawing" width="800"/>

### Cardboard prototype

The push button has to be pressed to stamp something and simultaneous to make the sound and call on the attention of others (to what is being stamped - QR code). So before we moved on to 3D softwares and 3D printing we built and iterated a cardboard prototype based on a “arcade style button” already at FabLab. During this time we also made sure we were already taking the necessary measurements and metrics to pass this ideation to a 3D software.

<img src="../imagery/cardboard.jpg" alt="drawing" width="800"/>

### 3D software - Rhino

Translating our cardboard prototype into Rhino to be 3D printed. This was a task we did the 3 of us. Marielle and I (Carolina) are still not as proficient as Stella and wanted to learn and iterate with her. It worked out, as we kept on giving feedback on assembling, practicality, function and measurements and combining small nocks of knowledge we had between the three.

<img src="../imagery/rhino.jpg" alt="drawing" width="200" alig="right"/>
<img src="../imagery/electronics.jpg" alt="drawing" width=600"/>

### electronics

We need to make a set-up that includes a ESP32, a speaker, a DFPlayer Mini (SD card with MP3 files), a GPS and a button.

We researched on some examples related to the DFPlayer Mini and Speaker. And, manged to start seing data related to the position of the GPS with the help of Edu.

<img src="../imagery/essentials.jpg" alt="drawing" width="800"/>

<img src="../imagery/3Dprinter.jpg" alt="drawing" width="800"/>

another useful **[youtube video](https://www.youtube.com/watch?v=kq2RLz65_w0)** we are inspired by. 

### GPS

OUR TALK WITH VICTOR:

what we need is to record the geolocation and the time (through a GPS in the device)

there needs to be featherboard in the device. on the featherbaord, we connect, record the GPS that will give us the data of the geolocation and time

then, the QR code (that will be stamped), will lead to a public webserver - meaning, we need a public webserver.

that is easy, but the question is, through which server / which computer will translate the data from the feather onto the digital platform (map...)

so we have to link the data and the webpage
this is possible through the mqtt (which works via publish and subscribe)

geo data logger vs. geo data tagger **[another helpful link?](https://www.instructables.com/Geo-Data-Logger-ArduinoGPSSDAccelerometer-to-l/)**

the link could be **[adafruit itself](https://learn.adafruit.com/welcome-to-adafruit-io/what-is-adafruit-io)**

this might be our hero this time... **[Todd Treece](https://cdn-learn.adafruit.com/downloads/pdf/adafruit-io-basics-gps.pdf)**



<img src="../imagery/GPSsuccessI.jpg" alt="drawing" width="800"/>

<img src="../imagery/GPSsuccessI.jpg" alt="drawing" width="800"/>

## References & Resources
