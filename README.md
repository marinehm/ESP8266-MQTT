# ESP8266-MQTT

Publish and Subcribe to mulitiple topics on an ESP8266
This was all created using Wemos D-1 mini's (ESP8266) with Arduino Pub-Sub Client libraries and a Raspberry Pi Zero W
running Mosquitto MQTT.

    This project was to create a polling station whereas, 
I press a button at the reception desk and 4 remote offices are notified that there are charts pending.
This is accomplished over wifi.  Either log on to an existing wifi, use the Wemos D-1 mini or Raspberry Pi Access Point to
for a stand-alone system.

    Originally, I used works LAN WiFi.  It was too unreliable, then I switched over to using the Wemos at the Reception
desk as an access point.  It worked pretty well.  Then I decided to add a button in each remote office.
Pressing a button on the remote station would result in an a single LED from row of of 4 LEDs corresponding to each remote office,
to light up at the reception desk.

    You could use it however you wish.  In my case, I press the button in the remote office to get help, but you could just as well
have the button indicate you are with a client and not to be bothered.


    When connecting each Wemos to MQTT, each Wemos/Client must have a unique name.
Streamlining the MQTT brokering I used the string comparison protocol.  But, In doing this I ran into a bit of trouble and
discovered the the topic comparison did not produce favorable results.  My topics were Chaperone/PSA, Chaperone/PSB,
Chaperone/PSC and Chaperone/PSD.  I could not get the LEDs to act independently.  But changing the tops to:
Chaperone/A, Chaperone/B, Chaperone/C and Chaperone/D.  Works!  

    So to recap:  Give each client a unique name, choose topic names wisely
    
    Special thanks to @PaulRB on the Arduino Forum, @DougieLawson on the Raspberry Pi forum and James Lewis from
    TheBaldEngineer.com   THANK YOU ALL FOR YOUR PATIENCE AND ASSISTANCE!
    
    My next goal is to turn the PiZero W's WiFi into an access pont.  Stay tuned...
