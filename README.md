# Museum Of Colonialization (MOC-II)
second iteration of the MOC, second microchallenge, 14. - 18. march 2023

**with marielle, carolina & stella**

our days are structured according to **[this plan](https://fablabbcn-projects.gitlab.io/learning/educational-docs/challenge/c_2/)**.

and in our part of the **[miro](https://miro.com/app/board/uXjVMeaB6bc=/)** we are trying to capture our thoughts.

next to the this repo, we are working also in a **[notion](https://hickory-polonium-fd1.notion.site/Marielle-Stella-Carolina-MDEF-22-23-34fdfc848ec44d93bae61fdf263d6c88)**



**what we ask**

maybe we could continue with our previouos idea of printing entry-tickets or receipts that a visitor gets once "visiting" the museum? **[printing device](https://www.google.com/search?q=bricogeek+impresora+termica&source=lmns&bih=712&biw=1312&client=firefox-b-d&hl=en&sa=X&ved=2ahUKEwip7Jynq9v9AhVwpycCHcn8B5EQ_AUoAHoECAEQAA)**

**what we do** 

**what we provide** 


# how we get there - in theory

NEED:

device needs a battery and a whole to charge

location:
software - IP, a bit more complicated (@victor & oscar)
hardware - GPS

button:
take the big button that exists (arcade style) and just print a "lid", nice cover

stamp:
eva foam (block) - engrave really nice - really really nice to make stamps

speaker:
speaker;  sd-card holder / MP3 shield to store the sounds file


TALK WITH VICTOR:

what we need is to record the geolocation and the time (through a GPS in the device)

there needs to be featherboard in the device. on the featherbaord, we connect, record the GPS that will give us the data of the geolocation and time

then, the QR code (that will be stamped), will lead to a public webserver - meaning, we need a public webserver.

that is easy, but the question is, through which server / which computer will translate the data from the feather onto the digital platform (map...)

so we have to link the data and the webpage
this is possible through the mqtt (which works via publish and subscribe)

geo data logger vs. geo data tagger **[another helpful link?](https://www.instructables.com/Geo-Data-Logger-ArduinoGPSSDAccelerometer-to-l/)**

the link could be **[adafruit itself](https://learn.adafruit.com/welcome-to-adafruit-io/what-is-adafruit-io)**

this might be our hero this time... **[Todd Treece](https://cdn-learn.adafruit.com/downloads/pdf/adafruit-io-basics-gps.pdf)**


# how we get there - in practice



## References & Resources
