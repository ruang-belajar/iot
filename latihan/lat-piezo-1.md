# Piezo

Buatlah rangkaian berikut:

![](../res/piezo.png)

Tambahkan kode berikut dan coba pelajari:

```cpp
// frekuensi awal
int frek = 100;

// penambahan frekuensi
int x = 10;

int pinPiezo = 8;

void setup() {
    pinMode(pinPiezo,OUTPUT);
    Serial.begin(9600);
}

void loop() {
  	
    tone(pinPiezo,frek);
    Serial.println(frek); // membantu programer mengencek frekuensi yang sedang aktif
    frek = frek + x;
  
    delay(100);
  
    // setiap frekuensi melewati angka 500 & 100, maka
    // x dikali -1. Sehingga ia akan berubah dari + jadi -
    // begitu juga sebaliknya
    // x positif berarti ini bagian dimana "nada naik"
    // x negatif berarti ini bagian dimana "nada turun"
    if(frek>500 || frek<100) {
      x*=-1;
    } 
    
         
}
```

Dari contoh diatas, coba kerjakan soal-soal berikut:

## Soal 1
Tambahkan _potentiometer_ ke dalam rangkaian. Ketika _potentimeter_ di putar, maka frekuensi yang dibunyikan berubah. Semakin diputar ke kiri, maka frekuensi akan semakin tinggi.
