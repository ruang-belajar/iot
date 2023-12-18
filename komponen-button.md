# Button

Button adalah salah alat input yang paling sederhana yang kita bisa coba. Perhatikan rangkaian berikut:

![](res/button-1.jpg)

```cpp
int status=0;

void setup()
{
  pinMode(13, OUTPUT);
  pinMode(7,INPUT);
  Serial.begin(9600);
}

void loop()
{
  status = digitalRead(7);

  Serial.println(status); // menampilkan nilai yang dibaca digitalRead()

  if(status==HIGH) {
    digitalWrite(13, HIGH);
  } else {    
    digitalWrite(13, LOW);
  }
}
```

Untuk membaca kondisi tombol, digunakan `digitalRead()`. Fungsi ini akan mengembalikan nilai `HIGH` pada saat tombol ditekan, `LOW` pada saat dilepas.

Dalam membuat rangkaian sirkuit menggunakan button, perhatikan skema berikut:

![](res/button-2.jpg)