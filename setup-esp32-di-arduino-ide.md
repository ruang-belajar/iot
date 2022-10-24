# Setup ESP32 di Arduino IDE

Jika Anda menggunakan perangkat ESP32, Anda bisa menggunakan Arduino IDE untuk upload program. Ikuti langkah-langkah berikuti supaya Arduino IDE bisa mengenali ESP32.

1. Buka Arduino IDE, kemudian klik Menu `File > Preferences`
   
   ![](res/setup-esp-1.png)

   Pada kolom _Additional, tambahkan link berikut:
   ```
   https://dl.espressif.com/dl/package_esp32_index.json
   ```

2. Klik menu `Tools > Board: > Boards Manager ...`

   ![](res/setup-esp-2.png)

3. Pada kolom pencarian tulis ESP32 kemudian install dan tunggu sampai selesai

   ![](res/setup-esp-3.png)

4. Install telah selesai. Kemudian kita test.
   
   Klik menu `Tools > Board: > ESP32 DEV Module`

   ![](res/setup-esp-4.png)

5. Pilih socket COM:

   ![](res/setup-esp-5.png)

6. Buka example dengan klik menu `File > Example > WiFi > WiFiScan`

   ![](res/setup-esp-6.png)

7. Setelah tampil, kemudian kita klik tombol upload (arah kanan). Tunggu hingga selesai compilenya. Jika sudah muncul tulisan "Conecting ... " pada keterangan dibawah, tekan dan tahan tombol "boot" pada hardware ESP32 yang berada pada sebelah kiri port usb.

   ![](res/setup-esp-7.png)

8. Hingga ada tulisan "Leaving..." maka tombol boot boleh dilepas.

   ![](res/setup-esp-8.png)

   Setelah itu maka akan ada pemberitahuan "Done Uploading"


9. Selesai Upload, kita buka Serial monitor yang ada disebelah kanan atas. Maka akan muncul tulisan seperti berikut:

   ![](res/setup-esp-9.png)

sumber:
https://www.robotikindonesia.com/2020/01/cara-menggunakan-esp32-di-arduino-ide.html