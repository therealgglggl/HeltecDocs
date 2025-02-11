# Heltec ESP32+LoRa Series Quick Start
{ht_translation}`[简体中文]:[English]`

Before all operation, please confirm whether the `USB driver`, `Git` and `Arduino IDE` has been installed correctly. If not, please refer to this two articles [establish serial connection](https://docs.heltec.org/general/establish_serial_connection.html) and [Install Git and Arduino IDE](https://docs.heltec.org/general/how_to_install_git_and_arduino.html).

The Heltec ESP32 development environment already contains the basic code. For the special codes related to the Heltec ESP32 development board, please refer to: [https://github.com/Heltec-Aaron-Lee/WiFi_Kit_series/tree/master/esp32/libraries/Heltec-Example](https://github.com/Heltec-Aaron-Lee/WiFi_Kit_series/tree/master/esp32/libraries/Heltec-Example) .

![](img/quick_start/09.png)



**There are three methods to install the development framework, choose one of they:**

- [Via Arduino Board Manager](esp32-via-arduino-board-manager)
- [Via Git](esp32-via-git)
- [Via Local File](esp32-via-local-file)

```{Tip} When we updated the V3 series development environment, we integrated the sample code and added it to the development environment without additional downloading libraries. We have handled the compatibility of the sample code so that the code can be used for various versions of the ESP32 development board. When you use the new development environment, the old version of the library can no longer be used, such as ESP32_ LoRaWAN, Heltec_ ESP32. When you update the development environment, we recommend that you delete the old development environment, download the new development environment, and delete the old version of the library. For Git, it has been updated to the V3 series development environment on September 19, 2022. For  "Arduino Boards Manager", V0.0.7 is the V3 series development environment. If you modify a lot of code in the old development environment and use it in the project, we recommend that you still use the old development environment.

```

```{Tip} Due to the ESP32 chip was replaced in the V3 version of the ESP32 series product. If you install the old environment through Git and get updates through "git pull", you need to execute 'get.exe "under the" WiFi_Kit_series\esp32\tools "path again to download the latest compilation chain.

```

&nbsp;

(esp32-via-arduino-board-manager)=
## Via Arduino Board Manager

### Step1. Download Arduino-ESP32 Support

Open Arduino IDE, and click `File`->`Peferences`.

![](img/quick_start/01.png)

&nbsp;

![](img/quick_start/02.png)

**Input the last ESP32 package URL:** [https://github.com/Heltec-Aaron-Lee/WiFi_Kit_series/releases/download/1.0.0/package_heltec_esp32_index.json](https://github.com/Heltec-Aaron-Lee/WiFi_Kit_series/releases/download/1.0.0/package_heltec_esp32_index.json)

![](img/quick_start/03.png)

Click `Tools --> Board --> Boards Manager...`, search `Heltec ESP32` in the new pop-up dialog, then select the latest version and click `install`

![](img/quick_start/04.png)	

![](img/quick_start/05.png)

The source code of Heltec ESP series (ESP32 & ESP8266) framework available here: [https://github.com/Heltec-Aaron-Lee/WiFi_Kit_series](https://github.com/Heltec-Aaron-Lee/WiFi_Kit_series)

&nbsp;

(esp32-via-git)=
## Via Git

After obtaining updates through "**git pull**", please execute "**get. exe**" under the path of "**Arduino\hardware\WiFi_Kit_series\esp32\tools**" to obtain the latest compilation tool.

![](img/quick_start/21.png)

- For Windows: `https://github.com/Heltec-Aaron-Lee/WiFi_Kit_series/blob/master/InstallGuide/windows.md`
- For MacOS: `https://github.com/Heltec-Aaron-Lee/WiFi_Kit_series/blob/master/InstallGuide/mac.md`
- For Linux
  - Debian/Ubuntu: `https://github.com/Heltec-Aaron-Lee/WiFi_Kit_series/blob/master/InstallGuide/debian_ubuntu.md`
  - Fedora: `https://github.com/Heltec-Aaron-Lee/WiFi_Kit_series/blob/master/InstallGuide/fedora.md`
  - OpenSUSE: `https://github.com/Heltec-Aaron-Lee/WiFi_Kit_series/blob/master/InstallGuide/opensuse.md`

&nbsp;

(esp32-via-local-file)=
## Via Local File

Download the development environment. [https://resource.heltec.cn/download/tools/WiFi_Kit_series.zip](https://resource.heltec.cn/download/tools/WiFi_Kit_series.zip)

Open Arduino IDE, and click `File`->`Peferences`.

![](img/quick_start/01.png)

Go to the folder in the red box.

![](img/quick_start/16.png)

Create a new "hardware" folder in the Arduino folder. If there is already a "hardware" folder, you don't need to create a new one.

![](img/quick_start/17.png)

Go to the "hardware" folder and extract "WiFi_Kit_series" into this folder.

![](img/quick_start/18.png)

Go to the "WiFi_Kit_series" folder, refer to the figure below to confirm whether the path in the red box is correct.

![](img/quick_start/19.png)

Restart the Arduino IDE to confirm whether the development environment is installed successfully.

![](img/quick_start/20.png)

&nbsp;

## Example

This section for verifying whether you can program with Arduino or not. Now, The USB cable connects to Heltec ESP32 board, then select your serial port which is connected to Heltec ESP32 board.



Select a demo example, compile and upload.

### Execute an example

Correctly select a board and relevant options in the `Tools` menu:

![](img/quick_start/08.png)

Then select an example.

![](img/quick_start/09.png)

Compile & Upload

![](img/quick_start/10.png)

### New a Heltec ESP32 program

Open Arduino IDE, create a new  `.ino` file, then copy the below code.

```arduino
#include <heltec.h>

// the setup routine runs once when starts up
void setup(){

  // Initialize the Heltec ESP32 object
  Heltec.begin(true /*DisplayEnable Enable*/, true /*LoRa Disable*/, true /*Serial Enable*/, true /*PABOOST Enable*/, 470E6 /**/);
}

// the loop routine runs over and over again forever
void loop() {

}
```

compile it and upload, the  screen (if this board has a screen) will show and Arduino's serial monitor will print something, it means Heltec ESP32 board is running successfully!
