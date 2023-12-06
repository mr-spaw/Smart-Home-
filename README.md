# Smart-Home-
Developing a smart home system using a NodeMCU and 5V relay module. Employ the Blynk IoT software, utilizing HTTP requests to control a light bulb's on/off functionality. NodeMCU acts as the system's brain, with the relay module functioning as a switch for the bulb. This setup enables easy remote control and monitoring through Blynk's interface.



#define BLYNK_TEMPLATE_ID "**********************"
#define BLYNK_TEMPLATE_NAME "home automation"
#define BLYNK_AUTH_TOKEN "*************************"

#define BLYNK_PRINT Serial
#include <ESP8266WiFi.h> 
 
#include <BlynkSimpleEsp8266.h>
 

char auth[] = BLYNK_AUTH_TOKEN;

char ssid[] = "*************";  // type your wifi name
char pass[] = "****************";  // type your wifi password

//used 1 relay but you can use multiple relay
int relaypin = D4;
void setup()
{     
  Serial.begin(115200);
  Blynk.begin(auth, ssid, pass);    
  pinMode(relaypin,OUTPUT);
 
  }

void loop()
{
  Blynk.run(); 
 }


 //the http link- https://blr1.blynk.cloud/external/api/update?token=give your token&givethepin=1or0
