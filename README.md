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

<img src="/imagery/electronics.jpg" alt="drawing" width="600"/>

The next morning they are ready, yet there is a lot of work to do...

The button exists mainly out of two parts. The top part and the down part. The top part is quit ok, the botton part we have to adjust. Because we don't know precicely the new measures which will depend on the electronics that need to fit, we create our Rhino model (which yesterday we easily did almost exclusively with the bollean-command) again - from scratch and with Grasshopper.

<img src="/imagery/grasshopper.png" alt="drawing" width="600"/>

furhermore, we adjust the walls, because we want that the speaker inside will be loud outside. So gaps are kind of essential. Ok, so far so good. Again, we export the stl-file (this time a bit more precise to have a smooth rounding) and upload the CURA-files onto the sd-cards and onto the printers to let them do their work over the night (sleep is fully overrated when being a electronic device).

<img src="/imagery/stl.png" alt="drawing" width="200"/>

<img src="/imagery/rhino-updated.png" alt="drawing" width="600"/>


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

**translating feather data to digital platform**

the part that was supposed to be the most easy part (translating the GPS data into a digital platform and into a simple data-sheet) turned out to take us a whole morning of searching in old codes, reading and watching tutorials and mixing it up to create our own code. Without Daphne and all her patience this would have never worked out. And then the end of course Victor who came for half an hour and brough some order into our chaos - and sieheda, the code works. One of our main **[manuals was this](https://cdn-learn.adafruit.com/downloads/pdf/mqtt-adafruit-io-and-you.pdf)**. 

<details> 
the code:

```

#include <SparkFun_I2C_GPS_Arduino_Library.h> //Use Library Manager or download here: https://github.com/sparkfun/SparkFun_I2C_GPS_Arduino_Library
I2CGPS myI2CGPS; //Hook object to the library

#include <TinyGPS++.h> //From: https://github.com/mikalhart/TinyGPSPlus
TinyGPSPlus gps; //Declare gps object

#include <Wire.h>
#include <WiFi.h>

#include "Adafruit_MQTT.h"
#include "Adafruit_MQTT_Client.h"

#define WLAN_SSID       "wifi"
#define WLAN_PASS       "wifi password"
#define AIO_SERVER      "io.adafruit.com"
#define AIO_SERVERPORT  1883
#define AIO_USERNAME    "IO username"
#define AIO_KEY         "IO key"

WiFiClient client;

const char MQTT_SERVER[] PROGMEM = AIO_SERVER;
const char MQTT_USERNAME[] PROGMEM = AIO_USERNAME;
const char MQTT_PASSWORD[] PROGMEM = AIO_KEY;

// Setup the MQTT client class by passing in the WiFi client and MQTT server and login details.
Adafruit_MQTT_Client mqtt(&client, AIO_SERVER, AIO_SERVERPORT, AIO_USERNAME, AIO_KEY);
//Adafruit_MQTT_Subscribe gpsdata = Adafruit_MQTT_Subscribe(&mqtt, AIO_USERNAME "/feeds/gpsdata");
Adafruit_MQTT_Publish latitude = Adafruit_MQTT_Publish(&mqtt, AIO_USERNAME "/feeds/latitude");
Adafruit_MQTT_Publish longitude = Adafruit_MQTT_Publish(&mqtt, AIO_USERNAME "/feeds/longitude");

int lastPost = 0;

#define BUTTON_PIN 4
bool butState = HIGH;

void setup()
{
  pinMode(BUTTON_PIN, INPUT_PULLUP);
  
  Serial.begin(115200);

  if (myI2CGPS.begin() == false) {
    Serial.println("GPS Module failed to respond. Please check wiring.");
    while (1);
  }
  
  Serial.println("GPS working!!");

  Serial.println(); 
  Serial.println();
  Serial.print("Connecting to ");
  Serial.println(WLAN_SSID);

   WiFi.begin(WLAN_SSID, WLAN_PASS);
   while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print("."); 
   }

  Serial.println();
  Serial.println("WiFi connected");
  Serial.println("IP address: "); Serial.println(WiFi.localIP());

  //mqtt.subscribe(&gpsdata);
}

void MQTT_connect(){
 
  int8_t ret;

   // Stop if already connected.
   if (mqtt.connected()) {
   return;
   }
   
   Serial.print("Connecting to MQTT... ");
  while ((ret = mqtt.connect()) != 0) { // connect will return 0 for connected
    Serial.println(mqtt.connectErrorString(ret));
    Serial.println("Retrying MQTT connection in 5 seconds...");
    mqtt.disconnect();
    delay(5000); // wait 5 seconds
   }
   Serial.println("MQTT Connected!");
}

//Display new GPS info
void displayInfo()
{
  //We have new GPS data to deal with!
  Serial.println();

  if (gps.time.isValid())
  {
    Serial.print(F("Date: "));
    Serial.print(gps.date.month());
    Serial.print(F("/"));
    Serial.print(gps.date.day());
    Serial.print(F("/"));
    Serial.print(gps.date.year());

    Serial.print((" Time: "));
    if (gps.time.hour() < 10) Serial.print(F("0"));
    Serial.print(gps.time.hour());
    Serial.print(F(":"));
    if (gps.time.minute() < 10) Serial.print(F("0"));
    Serial.print(gps.time.minute());
    Serial.print(F(":"));
    if (gps.time.second() < 10) Serial.print(F("0"));
    Serial.print(gps.time.second());

    Serial.println(); //Done printing time
  }
  else
  {
    Serial.println(F("Time not yet valid"));
  }

  if (gps.location.isValid()) {
    Serial.print("Location: ");
    Serial.print(gps.location.lat(), 6);
    Serial.print(F(", "));
    Serial.print(gps.location.lng(), 6);
    Serial.println();
  }
  else {
    Serial.println(F("Location not yet valid"));
  }
}

void loop() {
  MQTT_connect();
 
  while (myI2CGPS.available()) {//available() returns the number of new bytes available from the GPS module
    gps.encode(myI2CGPS.read()); //Feed the GPS parser
  }

//  if (gps.time.isUpdated()) { //Check to see if new GPS info is available
//    displayInfo(); 
//  }

  bool butNow = digitalRead(BUTTON_PIN);
  if (butNow != butState) {
    butState = butNow;

    if (butNow == LOW) {
      latitude.publish(gps.location.lat());
      longitude.publish(gps.location.lng());
      Serial.println(F("\nSending location "));
      Serial.println(gps.location.lat(), 6);
      Serial.println(gps.location.lng(), 6);
    }
  }
}


```
</details> 

What it does atm (explanation of unknown names and words are following): 

• it sets up a ***wifi*** (because we wont have a sim-card in our stamp but in order to load the data directly into the digital world, a wireless connection is needed) - thus there is the possibility of chosinng a mobile-hotspot or to add the credentials of a local wifi. 

• it links the ***feather (GPS) to the adafruit IO server AND a personal account*** (that is needed to later on work with the date in multiple ways). So for this we made our **[adarfuit IO account](https://io.adafruit.com/distel/wippersnapper)** and connect our feather ESP32. To test if there is a stable connection, we make the built in LED **[blink](https://learn.adafruit.com/quickstart-adafruit-io-wippersnapper/blink-a-led)** before we continue with our arduino code. 

• it ***sets up an MQTT*** that in our case equals our adafruit account. The MQTT in a network protocol, a language to enable the exchange of messages from remote locations and the digital (very important for **the Internet of Things**).

• furthermore we set up a ***button function*** to make sure that the GPS data is not being uploaded onto our digital platform constantly but only when we push. = bool butState part in the code. We make sure that the publishing function is being activated when the button is pushed and released. 

<img src="/imagery/IOaccount.png" alt="drawing" width="400" align="left"/>


next we research platforms that enable us to mapp our feather data in on online-and-real-time-updating map (to be an issue!). We try out various road. The **[adafruit IO WipperSnapper](https://io.adafruit.com/distel/wippersnapper)** offers a mapping fuction, yet it turns out that they use another GPS-sensor and when trying to work with their file, it does nto run because our GPS is not a **[FONA GPS](https://cdn-learn.adafruit.com/downloads/pdf/adafruit-io-basics-gps.pdf)**. To rewrite their code with our **[Qwiic GPS SparkFun](https://learn.sparkfun.com/tutorials/sparkfun-gps-breakout---xa1110-qwiic-hookup-guide?_ga=2.201024366.1763643038.1678813580-1396006468.1678813580#hardware-overview)** seems a bit overwhelming, after a few trials, we leave it to that and search for something else.

we anyway create a ***adafruit IO account*** with ***two feeds (one for longitude and one for latitude)*** and ***one dashboard (in which both are combined)***. We see the data longitude, latitude, date and time when we push the buttom that is linked to the feather appear in our feeds and dashbard. It turns out, no need for all of that. We are making our life more complex than it is. So we rewrite our code just a tiny bit and sent *latiude,longitude*-data as ***one line*** to our ***longitude feed***. 

The platform **[IFTTT](https://ifttt.com/)** offers multiple ways to link data to online services. One of them is the linkage of adafruit account to a googlsheet. And in google again, their googlemaps has a **[mymaps](https://www.google.com/maps/d/u/0/?hl=en)** function. In this, we can create a "private" map that be can publish but with which we can subscribe to a google spreadsheet that we make (from our drive). Problem: the map is not updated automatically, neither is the spreadsheet (yet) meaning we have to update the map manually in order to update the pins on the map. So what we need is a way, code, trick to automate the data-translation from GPS to google spreadsheet AND a real-life update from google spreadsheet to the map created in mymaps. 

A little research further we stumple upon a googlesheet add-on from **[theXS mapping](https://www.thexs.ca/xsmapping)** whose service offers us to mapp the data of our googlesheet in real-time in their maps - whose are linked to google maps (yet it somehow isnt mymaps anymore - however - XSmaps is fine by me). This seems to automate the process from spread-sheet to map - first moment of succcess = we see the coordinates on the map as little pins. Little downer, this automated process updates only hourly (if you dont pay for a pro-account) - not in real real time. But ok, es lo que hay. Somewhere we need to make compromises it seems.

<img src="/imagery/maptest1.png" alt="drawing" width="600"/>

In IFTTT we edit out **[applet] (https://ifttt.com/explore/Appletsin)** (which is just the name IFTTT gave to the linking-process). We edit and say if: there is new data in the adadfruit longitude feed, then add a new row into the latitude googlesheet in our drive (folder - location). Dont get confused with the names - its all a but messed up we know.

<img src="/imagery/IFTTT.png" alt="drawing" width="400" align="left"/>

summed up:

we have a button that, when pushed, sends a GPS location to an ***adafruit IO account*** with the ***feed longitude***. Via IFTTT, we send the data into a googlesheet which uses the XSmapping add-on to drop pins at the GPS data (updating it every hour). 


*combining speaker, GPS and button* 

a new code combines now also the audo-file

<details> 
the updated code:

```

```
</details> 


### thoughts on blackboxing and stupifying citizens

focussing on protocolls rather than on platforms might be sometimes a more time intense way but is is better. What all the platforms we encountered in the last few days are doing, is putting their brandmark onto simple and open-to-the-public funcions. Companies like googe, adafruit, IFTT are hiding these functions behind new names (e.g. renaming topic int feed or dashboard). 

if in the future we want to bypass making 4 different accounts on various websited and crearing complex detours that are slowing down the processing of our data from one place to another, we can do some deeper research towards protocolls. 

**how to post mqtt data digitally and accessibly? (in a sheet, a map, a webpage...)**

now we **[adafruit IO](https://learn.adafruit.com/welcome-to-adafruit-io/overview)** (***account 1***)that started as a platform to make information of these simple protocolls available to citizens. Yet, it seems they are as well developinig more and more patters that seerve to hide the simplicity and accessiibility of code-fuctions. We used **[IFTT](https://ifttt.com/explorehttps://ifttt.com/explore)** (***account 2***) to translate the data that our feather uploaded into adafruit IO into a **[googlesheet](https://docs.google.com/spreadsheets/)** (***account 3***). Then we used a googlesheet add-on from **[theXS mapping](https://www.thexs.ca/xsmapping)** whose service offers us to mapp the data of our googlesheet in real-time (well actually only every hour) in their mapps - whose are linked to google maps. 

### Button mechanics

### Stamp

## References & Resources

research:

**[against the white cube gallery](http://vibe-experience.com/)**

GPS:

geo data logger vs. geo data tagger **[another helpful link?](https://www.instructables.com/Geo-Data-Logger-ArduinoGPSSDAccelerometer-to-l/)**

the link could be **[adafruit itself](https://learn.adafruit.com/welcome-to-adafruit-io/what-is-adafruit-io)**

this might be our hero this time... **[Todd Treece](https://cdn-learn.adafruit.com/downloads/pdf/adafruit-io-basics-gps.pdf)**

a person doing something similar with **[temperature data](https://www.cytron.io/tutorial/send-sensors-data-to-adafruit-io-using-esp32)**

the ada fruit blink **[tutorial](https://learn.adafruit.com/quickstart-adafruit-io-wippersnapper/blink-a-led)**

ne of our main **[manuals from adafruit IO](https://cdn-learn.adafruit.com/downloads/pdf/mqtt-adafruit-io-and-you.pdf)**. 
