# Latihan 11

Lengkapi program dibawah ini dengan memberikan nilai/perintah yang tepat pada bagian yang ditandai dengan `_____`

```cpp
int nyala=0;
int status;
int pinLED = __ ; // A
int pinButton = __;  // B

void setup()
{
  pinMode(______, OUTPUT); // C
  pinMode(______,INPUT);   // D
  _____.begin(9600);  // E
}

void _____ // F
{
  status = digitalRead(pinButton);
  Serial.println(status);
  
  if(status==HIGH) {
    if(nyala==HIGH) {
      nyala = LOW;
    } else {
      nyala = HIGH;
    }
  } 
  
  ______(pinLED, nyala); // G
  delay(100);
}
```