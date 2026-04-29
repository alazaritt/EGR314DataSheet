---
title: Reflection
---

## Review of Module's Sucess

Looking back at the module requirements, several key objectives were successfully accomplished. The ESP32-S3 microcontroller was properly integrated and configured on my custom PCB, powered correctly, and successfully programmed. The camera module was also able to initialize, capture single images, and transmit compressed image data packets, demonstrating that basic communication between the microcontroller and the camera was functional. Additionally, an I2C-based rotary encoder was successfully integrated and used to demonstrate reliable I2C communication, which was one of the intended functions of the camera interface.

However, some major requirements were not fully achieved. The OV2460 camera module did not perform as it should’ve when used with the ESP32-S3 on my PCB. While the camera worked correctly on the ESP32-S3 devkit in a breadboard setup, it was not able to stream video when connected to the ESP32-S3 on the PCB. Although the system could capture still images and transmit compressed byte data, it was not possible to reconstruct or meaningfully use the image data, or achieve continuous video streaming. The camera was, however, able to send status updates. It periodically transmitted key configuration data, including the camera state, frame width and height corresponding to the captured image resolution, and error codes (if any). This confirmed that internal camera control logic and communication pathways were functioning, even if full image utilization was limited. 

After extensive research when I was trying to debug the camera, I realized that the S3 model of the ESP32 did not support the same libraries that the devkit did for the camera. This incompatibility made it physically impossible to make the camera stream video as it was supposed to. Despite this limitation, partial camera functionality and successful I2C integration via the rotary encoder showed that several core system components were operational.


## Microcontroller/Module Startup Tip

* Carefully read the datasheets to make sure all connections are where they should be and all resistor/capacitor values are accurate
* Make the software/firmware is correctly flashed to the ESP32 
* Verify power connections and voltage levels on important points early to avoid damaging components
* Use test points or accessible pins to simplify debugging
* Start with simple programming before integrating the entire system at once to make sure individual components work as they should


## Lessons Learned

1. Read datasheets closely when picking components to make sure everything will function as intended. 
2. Read datasheets very carefully when designing PCBs, making sure that any "typical use” schematics that come directly from the datasheet are accurately followed.
3. Pay attention to the physical size of surface mount parts when ordering them to make sure the ones that are ordered aren’t super tiny and hard to work with.
4. Order more a a sufficient amount of extra parts in case some get lost or backups are needed. If parts need to be ordered right away, it can take a while for them to arrive and can delay work time.
5. Make sure there are plenty of test points and open connections on the PCB for debugging.
6. Make sure all part/PCB orders are placed early so that when everything arrives, PCB assembly can start right away to allow time for system debugging.
7. Do research correctly to make sure that parts will work on the specific ESP32 that will be used. Just because it is supported on the devkit does not necessarily mean ot will be supported on the S3 chip.
8. Design the PCB in a modular way. If there is a short on one subsystem, being able to isolate other parts can prevent components from being damaged.
9. Test continuity of surface mount parts as they are being soldered to remove any shorts and make sure that everything is making good contact.
10. Make sure that the GPIO pins that are being assigned have no interference and can accurately support what is being used by them.


## Recommendations for Future Students

1. Read your datasheets thoroughly to ensure informed component selection and proper circuit implementation.
2. Start putting together your PCB as soon as you get all of your parts! When you start running into issues, it will help to have time on your hands to figure things out.
3. Take advantage of office hours early! More and more people are needing help at the last minute and it may be harder/take longer to get more one-on-one help.
4. When soldering components, regularly test continuity to make sure nothing is shorted out before you keep putting new parts on your board.
5. Use a hot air station instead of a soldering iron! The surface mount parts are so insanely tiny that a soldering iron can make things more difficult and even slow down the process.
