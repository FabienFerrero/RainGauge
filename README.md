# RainGauge
The device uses LoRaWAN to uplink temperature, humidity and precipitation sensor data through calculation.
Data will be sent every 6 minutes, if there is rain, the sending time will be 1 minute
Support sensors:
- [Digital humidity and temperature sensor - SHTC3](https://www.sensirion.com/products/catalog/SHTC3/)

## Getting Started

### Hardware

- USB to UART Converter
- RainGauge board

### Sortware

- Arduino IDE (version v1.8.13 or above is recommended)
- RUI3 lastest firmware for RAK3172: [RAK3172-E_latest_final.hex](https://downloads.rakwireless.com/RUI/RUI3/Image/RAK3172-E_latest_final.hex)
- (STM32CubeProgammer)[https://www.st.com/en/development-tools/stm32cubeprog.html]

### Additional Libraries

- Adafruit_SHTC3.h


## Installation

### Hardware connection:

![image](https://github.com/XuanMinh201/RainGauge/assets/75436464/43590e25-210d-4a73-9fea-75715c76654b)

On the RainGauge board

![image](https://github.com/XuanMinh201/RainGauge/assets/75436464/83794843-a9d2-4d8a-8205-b86d8a1eae8a)

### In STM32CubeProgammer:
  -  Hold the **B_RAK (boot)** button and press **R_RAK (reset)** button and release the **B_RAK (boot)** button to enter bootmode.
  -  Select UART, Baudrate 115200 and press Connect.
  -  Open RAK3172-E_latest_final.hex
  -  Select the address as in following image if needed
  -  Press Download to upload firmwave
  -  After download success, press **R_RAK (reset)** button to exit the bootmode
  -  
<!-- ![image](https://github.com/XuanMinh201/RF210/assets/75436464/55f5c5ab-d69a-4a25-94da-563d1e52a172) -->
<img src="https://github.com/XuanMinh201/RF210/assets/75436464/55f5c5ab-d69a-4a25-94da-563d1e52a172" height="450">

### In Arduino IDE:
  -  Add this JSON in Additional Boards Manager URLs [\(Show me how?\)](https://support.arduino.cc/hc/en-us/articles/360016466340-Add-third-party-platforms-to-the-Boards-Manager-in-Arduino-IDE):

```  
https://raw.githubusercontent.com/RAKWireless/RAKwireless-Arduino-BSP-Index/main/package_rakwireless.com_rui_index.json
```

  -  Go to **Tool -> Board -> Boards Manager**, search & install **RAKwireless RUI STM32 Boards**
  -  Open ```ATC_Command_RF210.ino``` sketch, seletc **WisDou RAK3172-T Board** from **Tool** menu
  -  Plug in your board and upload


<!-- ![image](https://github.com/XuanMinh201/RF210/assets/75436464/141710ed-1294-46ea-9951-63bea73622ed) -->
<img src="https://github.com/XuanMinh201/RF210/assets/75436464/141710ed-1294-46ea-9951-63bea73622ed" height="450">

  -  Select **Tool -> Board -> RAKwireless RUI STM32 Modules -> WisDuo RAK3172 Evaluation Board**
    
<!-- ![image](https://github.com/XuanMinh201/RF210/assets/75436464/146c570a-ec82-45bc-ada0-89544624b861) -->
<img src="https://github.com/XuanMinh201/RF210/assets/75436464/146c570a-ec82-45bc-ada0-89544624b861" height="450">


## The Things Network
- Depends on your country region and how you set up your gateway. Please create the correct application with it to be able to receive data
- In Danang, Vietnam we use the [**AS923_2**](https://ns.docs.everynet.io/channel_plans/AS920-923.html) band and [eu1.cloud.thethings.network](https://eu1.cloud.thethings.network/console/)
- You need to **create application** for RainGauge Board
  
![image](https://github.com/XuanMinh201/RainGauge/assets/75436464/6263f471-85bb-40d7-8175-f36b86bb3b63)

- Select **end device -> Register end device** to create your device
  
![image](https://github.com/XuanMinh201/RainGauge/assets/75436464/f2f3e594-0dc0-4156-b542-02ef4c0393e8)

![image](https://github.com/XuanMinh201/RainGauge/assets/75436464/ff61130b-e472-45ed-bed2-2af3d836196b)

- After creating the device, now you just need to copy **Device address, NwkSKey, AppSKey** and paste it into your code.
  
![image](https://github.com/XuanMinh201/RainGauge/assets/75436464/8cf5e5bc-677c-4cd7-925a-3b8f63af2f02)

- The data sent will be in the default format
  
![image](https://github.com/XuanMinh201/RainGauge/assets/75436464/e0ee5e85-7242-4a3e-989e-dfcfdc9c6fe4)

- You can change the format of the data to be able to observe changes
  
![image](https://github.com/XuanMinh201/RainGauge/assets/75436464/2781e16a-544a-484d-b850-0a4cea05c686)

![image](https://github.com/XuanMinh201/RainGauge/assets/75436464/8319f2fe-63a4-4159-a227-730c41d03d47)

![image](https://github.com/XuanMinh201/RainGauge/assets/75436464/bacd2547-f00b-4ce3-921c-7f5aad7f8b5a)

## Energy consumption
- The average energy consumption when the device is operating (sending data to the server) is **8.36mA** for **~15s**.
  
- ![image](https://github.com/XuanMinh201/RainGauge/assets/75436464/788eb731-e495-4512-936f-1b925529a2cb)

- When the device is inactive, it will be in sleep mode. Power consumption is **6.81 uA**
  
![image](https://github.com/XuanMinh201/RainGauge/assets/75436464/86c0f74d-2d5f-4a63-b74b-9b4ac87fee55)

### If you have any question or discussion points, please let me know via the [Issues](https://github.com/XuanMinh201/RainGauge/issues) & [Disscussions](https://github.com/XuanMinh201/RainGauge/discussions)





