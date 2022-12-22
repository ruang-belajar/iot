# Infrared Receiver

_Infrared Receiver_ adalah komponen yang digunakan untuk menangkap sinyal dari _infrared receiver_.

![](res/ir-receiver-pin.png)

Untuk mempermudah kita membaca data dari _infrared receiver_, kita memanfaatkan header _IRremote.h_. Install header ini lewat menu _Tools - Manage Libraries_ (cari "IRremote.h")

Untuk mencobanya, buatlah rangkaian sederhana microcontroller + _infrared receiver_ dengan program sebagai berikut:

```cpp
#include <IRremote.h>

void setup() {
  Serial.begin(9600);
  IrReceiver.begin(8); //8: nomor PIN untuk sinyal dari IR Receiver
}
void loop() {
  if (IrReceiver.decode()) {
    if(IrReceiver.decodedIRData.command>0) { // jika ada sinyal, tampilkan data
        Serial.println("================");
        
        // menampilkan data integer
        Serial.println(IrReceiver.decodedIRData.command);

        // menampilkan data dengan format HEXADESIMAL
        Serial.println(IrReceiver.decodedIRData.command,HEX);
        IrReceiver.resume();

        delay(1000);      
    }
    
  }
}
```

Upload dan lihat hasilnya pada Arduino. Untuk mencobanya, gunakan sembarang remote yang menggunakan infrared, arahkan pada _infrared receiver_ kemudian lihat hasilnya pada _Serial Monitor_ ketika Anda menekan tombol pada remote control.