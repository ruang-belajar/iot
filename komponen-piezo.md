# Komponen: Piezo

Piezo speaker adalah speaker sederhana yang bisa digunakan untuk mengeluarkan suara dengan frekuensi tertentu.

Piezo memiliki 2 kaki:
1. Kaki + : untuk dihubungkan dengan pin OUTPUT
2. Kaki - : untuk dihubungkan ke GND

Contoh:
![](../res/piezo.png)

Tambahkan kode berikut dan coba pelajari:

```cpp
// pin output piezo
int pinPiezo = 8;

void setup() {
    pinMode(pinPiezo,OUTPUT);
}

void loop() {  	
    tone(pinPiezo,400);
    delay(1000);
    tone(pinPiezo,700);
    delay(1000);         
}
```