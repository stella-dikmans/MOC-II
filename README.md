# Museum Of Colonialization (MOC-II)
second iteration of the MOC, second microchallenge, 14. - 18. march 2023

**with marielle, carolina & stella**

our days are structured according to **[this plan](https://fablabbcn-projects.gitlab.io/learning/educational-docs/challenge/c_2/)**.

and in our part of the **[miro](https://miro.com/app/board/uXjVMeaB6bc=/)** we are trying to capture our thoughts.

next to the this repo, we are working also in a **[notion](https://hickory-polonium-fd1.notion.site/Marielle-Stella-Carolina-MDEF-22-23-34fdfc848ec44d93bae61fdf263d6c88)**

**what we ask**

we want to continue with out MOC (museum of colonialization) idea that we had a few weeks ago during  **[the first micro challenge](https://github.com/stella-dikmans/MOC)**. REDEFINITION: everywhere on the world we encounter signs of colonial-pracices that increase iniequalities. This can be linked to past practices of european colonialism, or present practices of plastic pollution. We can see this in the stattues that populate city-streets but also in the plant-hybrids(ecological impreialism). Our goal is to make these signs more visible to all of us passing them everyday. how can we provoke attention? how can we question what we take for granted? 

ideas to go on with: 

• printing entry-tickets or receipts that a visitor gets once "visiting" the museum. **[printing device](https://www.google.com/search?q=bricogeek+impresora+termica&source=lmns&bih=712&biw=1312&client=firefox-b-d&hl=en&sa=X&ved=2ahUKEwip7Jynq9v9AhVwpycCHcn8B5EQ_AUoAHoECAEQAA)**

• sticker to sticker the streetscapes (and statues) of the city - guerilla like

We collected the qualities and the attributes we want our next iteration to have.

Qualities: playful learning; feeling seen; questioning the everyday / taken for granted 

attributes: portable; interactive; respectful; fun; triggering

**what we do** 

this time we come up with the idea of a (guerilla) stamp / attention-button a la **[that was easy](https://www.youtube.com/watch?v=NojiCsZQSr8)**. A person pushes our button that at the same time is a stamp. Thus pressing onto the button leaves a print on the surface the button is put upon. Through the push-mechanism, speaker is activated that says something (provoking) and the GPS location of the user is added to a *MOC Map*. The image the stamp stamps is a QR-code (and potentially a provocing sentence) that leads directlly to the map on which the user will encounter their location as a pin as well as all ther pins of prior users. 

<img src="/imagery/team.jpg" width="600" >

**what we provide** 

a portable guerilla tool that everyone can use to mark that they paid attention. That they recognize an entangled (hi)story that is not been paid enough attention to. 

# how we get there - in theory

we are designing a portable device that functions as a button and carries all the electronics that we need to excecute our codes. The device needs to be able to play a sound-file, determine its location and linking it to an online platform. At the same time, it needs to be able to be pressed against a surface and leave a trace with the image we want (stamp).

*software:* code for speaker, code for GPS (more detailed later on)

*hardware:* button-mechanism (take the big button that exists (arcade style) and just print a "lid", nice cover), stamp (eva foam block), ink, battery to charge, GPS, speaker, sd-card holder / MP3 shield, feather

# how we get there - in practice

### Cardboard prototype

The button has have a push-mechanism that when pressed, stamps a surface onto the surface the button is on. Simultaneously it will make a sound and by that call the attention. Before we move to 3D softwares and 3D printing (for the button) we design, built and iterated a cardboard prototype based on a “arcade style button" that be get from the fablab. we take measures and metrics to later pass this ideation to a 3D software.

<img src="/imagery/cardboard.jpg" alt="drawing" width="600"/>

### 3D software - Rhino

Now we are translating our cardboard prototype into Rhino to be 3D printed. We do this all together, giving feedback on assembling, practicality, function and measurements and combining small dots of knowledges we have between the three of us. We export it as an st-file and set up the CURA-file to print it in the 3D-printers over night. 

<img src="/imagery/rhino.jpg" alt="drawing" width="200" alig="right"/>

<img src="/imagery/electronics.jpg" alt="drawing" width=600"/>

The next morning they are ready, yet there is a lot of work to do...

The button exists mainly out of two parts. The top part and the down part. The top part is quit ok, the botton part we have to adjust. Because we don't know precicely the new measures which will depend on the electronics that need to fit, we create our Rhino model (which yesterday we easily did almost exclusively with the bollean-command) again - from scratch and with Grasshopper.

<img src="/imagery/grasshopper.png" alt="drawing" width=600"/>

furhermore, we adjust the walls, because we want that the speaker inside will be loud outside. So gaps are kind of essential. Ok, so far so good. Again, we export the stl-file (this time a bit more precise to have a smooth rounding) and upload the CURA-files onto the sd-cards and onto the printers to let them do their work over the night (sleep is fully overrated when being a electronic device).

<img src="/imagery/stl.png" alt="drawing" width=200"/>

<img src="/imagery/rhino-updated.png" alt="drawing" width=600"/>


### Electronics

*for the speaker:*

We need to make a set-up that includes a ESP32, a speaker, a DFPlayer Mini (SD card with MP3 files), a GPS and a button.

We researched on some examples related to the DFPlayer Mini and Speaker. And, manged to start seing data related to the position of the GPS with the help of Edu.

<img src="/imagery/essentials.jpg" alt="drawing" width="600"/>

<img src="/imagery/3Dprinter.jpg" alt="drawing" width="600"/>

another useful **[youtube video](https://www.youtube.com/watch?v=kq2RLz65_w0)** we are inspired by. 

*for the GPS:*

first things first, is it possible? we talk with Victor:

what we need is to record the geolocation and the time (through a GPS in the device). There needs to be featherboard in the device. On the featherbaord, we connect a GPS that will give us the data of the geolocation and time. Then, we have to link that data to a webpage or a existing map in order t create a QR code that can be translated into a stamp and will lead to that digital interfacec. This means, we meed to access a public webserver. The question is, through which server / which computer will we be able t translate the data from the feather onto the digital platform (map...)? could be a this is mqtt (which works via publish and subscribe) technique. 

ok, it seems possible. With the help of Edu, we compile the hardware needed to obtain a GPS signal. We use our adafruiit featherboard and a **[Qwiic GPS SparkFun](https://learn.sparkfun.com/tutorials/sparkfun-gps-breakout---xa1110-qwiic-hookup-guide?_ga=2.201024366.1763643038.1678813580-1396006468.1678813580#hardware-overview)**. We install some libraries linked to this specific GPS into our arduino app and run a few different example codes to see what we get. After few trials, it works (we have to leave the building though to get our location). So we have a GPS that gives us the date, time, longitute and altitude data. It's a start.

<img src="/imagery/GPSsuccessI.png" alt="drawing" width="600"/>

<img src="/imagery/GPSsuccessII.png" alt="drawing" width="600"/>

now it is time to see the mapping options for this data in public and real-time (turns out to be an issue!). We try out the **[adafruit IO WipperSnapper](https://io.adafruit.com/distel/wippersnapper)** to use their maps, yet it turns out that they use another GPS-sensor and when trying to work with their file, it does nto run because our GPS is not a **[FONA GPS](https://cdn-learn.adafruit.com/downloads/pdf/adafruit-io-basics-gps.pdf)**. Bueno, next try, it the **[itfff](https://ifttt.com/)** service that promises multiple ways to link data to online services. Another road we take is the googlemaps **[mymaps](https://www.google.com/maps/d/u/0/?hl=en)** function. Here, we can create a google spreadsheet (from our drive) to a private map (that we can publish later on). The only thing is, the map is not updated automatically, neither is the spreadsheet (yet). So what we need is a way, code, trick to automate the data-translation from GPS to google spreadsheet AND a real-life update from google spreadsheet to the map created in mymaps. Seems like google-drive, and google spreadsheets have some interesting **[add-ons](https://www.thexs.ca/posts/how-to-update-my-map-automatically-when-the-data-changes#h.ezgq3z1p20b4)** that could make our life easy (finally). Ok, it seems to automate the process from spread-sheet to map - first moment of succcess = we see the coordinates on the map as little pins. Little downer, this automated process updates only hourly - not in real real time. But ok, es lo que hay. Somewhere we need to make compromises it seems.

<img src="/imagery/maptest1.png" alt="drawing" width="600"/>


### Button mechanics

### Stamp

## References & Resources

research:

**[against the white cube gallery](http://vibe-experience.com/)**

GPS:

geo data logger vs. geo data tagger **[another helpful link?](https://www.instructables.com/Geo-Data-Logger-ArduinoGPSSDAccelerometer-to-l/)**

the link could be **[adafruit itself](https://learn.adafruit.com/welcome-to-adafruit-io/what-is-adafruit-io)**

this might be our hero this time... **[Todd Treece](https://cdn-learn.adafruit.com/downloads/pdf/adafruit-io-basics-gps.pdf)**