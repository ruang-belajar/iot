# Latihan 12

![](res/potentiometer.png)

Program dibawah ini akan mengirimkan data yang dibaca dari potensiometer (yang tersambung ke pin `0` Arduino) ke platform Ubidots, dengan interval 10 detik.

Lengkapi program dibawah ini dengan memberikan nilai/perintah yang tepat pada bagian yang ditandai dengan `_____`

```cpp
#include "Ubidots.h"

const char* UBIDOTS_TOKEN = "...";  // Put here your Ubidots TOKEN
const char* WIFI_SSID = "...";      // Put here your Wi-Fi SSID
const char* WIFI_PASS = "...";      // Put here your Wi-Fi password 
int pinPotentio = 0;
int nilai = 0;

Ubidots ubidots(UBIDOTS_TOKEN, UBI_HTTP);

void setup() {                       
  Serial.begin(115200);
  ubidots.wifiConnect(WIFI_SSID, WIFI_PASS);
}

void loop() {

  ___________ // A
  ubidots.add("Potentio", ____ ); // B
  
  bool bufferSent = false;
  bufferSent = ubidots.send(); 

  if (bufferSent) {
   Serial.println("Data berhasil dikirim");
  }
  delay(____); //C
}
```