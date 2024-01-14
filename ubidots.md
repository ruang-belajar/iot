# Ubidots

Ubidots adalah salah satu platform yang memberikan layanan IoT untuk perangkat kita bisa berinteraksi lewat internet.

Berikut beberapa persiapan yang perlu dilakukan untuk menggunakan Ubidots. Pada halaman ini, contoh dan panduan diperuntukan untuk mikrokontroller NodeMCU. Jika Anda menggunakan perangkat lain, Anda bisa check panduan di situs Ubidots.

1. Membuat akun di ubidots
2. Download dan install [Ubidots Library](https://github.com/ubidots/ubidots-nodemcu/archive/master.zip).
3. Copy [Ubidots token](http://help.ubidots.com/ubidots-app/how-to-get-a-token-from-your-ubidots-account)

## Mengirim data
```cpp
/****************************************
* Include Libraries
****************************************/

#include "Ubidots.h"

/****************************************
* Define Instances and Constants
****************************************/   
 
const char* UBIDOTS_TOKEN = "...";  // Put here your Ubidots TOKEN
const char* WIFI_SSID = "...";      // Put here your Wi-Fi SSID
const char* WIFI_PASS = "...";      // Put here your Wi-Fi password 

Ubidots ubidots(UBIDOTS_TOKEN, UBI_HTTP);

/****************************************
* Auxiliar Functions
****************************************/

// Put here your auxiliar functions

/****************************************
* Main Functions
****************************************/  

void setup() {                       

  Serial.begin(115200);
  ubidots.wifiConnect(WIFI_SSID, WIFI_PASS);
  // ubidots.setDebug(true);  // Uncomment this line for printing debug  messages                     
}

void loop() {

  float value1 = random(0, 9) * 10;
  float value2 = random(0, 9) * 100;
  float value3 = random(0, 9) * 1000;
  ubidots.add("Variable_Name_One", value1);// Change for your variable name  
  ubidots.add("Variable_Name_Two", value2);
  ubidots.add("Variable_Name_Three", value3);
  
  bool bufferSent = false;
  bufferSent = ubidots.send(); // Will send data to a device label that matches the device Id

  if (bufferSent) {
  // Do something if values were sent properly
   Serial.println("Values sent by the device");
  }
  delay(5000);
}
```

## Membaca data
```cpp
/****************************************
 * Include Libraries
 ****************************************/

#include "Ubidots.h"

/****************************************
 * Define Constants
 ****************************************/

const char* UBIDOTS_TOKEN = "...";  // Put here your Ubidots TOKEN
const char* WIFI_SSID = "..."; // Put here your Wi-Fi SSID
const char* WIFI_PASS = "..."; // Put here your Wi-Fi password

Ubidots ubidots(UBIDOTS_TOKEN, UBI_HTTP);

/****************************************
 * Auxiliar Functions
 ****************************************/

// Put here your auxiliar functions

/****************************************
 * Main Functions
 ****************************************/

void setup() {

  Serial.begin(115200);
  ubidots.wifiConnect(WIFI_SSID, WIFI_PASS);
  // ubidots.setDebug(true); //Uncomment this line for printing debug messages
}

void loop() {
  /* Obtain last value from a variable as float using HTTP */
  float value = ubidots.get("a020a6133e21", "variable_name_one");

  // Evaluates the results obtained
  if (value != ERROR_VALUE) {
    Serial.print("Value:");
    Serial.println(value);
  }
  delay(5000);
}
```

**Referensi:**
- https://help.ubidots.com/en/articles/513312-connect-a-nodemcu-esp8266-to-ubidots-over-http