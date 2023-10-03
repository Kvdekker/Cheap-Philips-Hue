# Cheap-Philips-Hue
By Koen Dekker
Last updated 3 October 2023

## Introductie
Door gebruik te maken van deze manual, leer je zelf om een goedkope Philips Hue te maken. Je kan dan via een color picker zelf de kleur instellen die je ledstrip weergeeft. Hiermee maak je gebruik van maar vier onderdelen:
1. NodeMCU Arduino Board, ESP8266
2. LED strip
3. [Arduino IDE](https://www.arduino.cc/en/software)
4. Een Wifi connectie

Wij gaan er van uit dat u het Arduino Board correct hebt geinstalleerd. Als u alle onderdelen klaar heeft liggen, gaan we van start.

## Stap 1: Installeer de Arduino Libraries
Open de Arduino applicatie.
Klik onder File op _New Sketch_
![image](https://github.com/Kvdekker/Cheap-Philips-Hue/assets/96053886/19b4c07d-5949-49a2-bcb7-42761d7a19b8)

Klik vervolgens op Tools -> Manage Libraries
![image](https://github.com/Kvdekker/Cheap-Philips-Hue/assets/96053886/b8f28a1a-0c8f-47db-9369-2fc6ad5035f6)

Tik bovenin onder Library Manager _Adafruit IO Arduino_ in. Je krijgt dan een lijst te zien met verschillende libraries te zien. Zoek daar de gene die je hebt ingevoerd. 
![image](https://github.com/Kvdekker/Cheap-Philips-Hue/assets/96053886/6c32f5e3-aadf-4cf8-83af-eea4b7960101)

Klik vervolgens op _Install_ en daarna op _Install All_. Hiermee installeer je de juiste library die je kan gebruiken voor je zelf gemaakte Philips Hue!
![image](https://github.com/Kvdekker/Cheap-Philips-Hue/assets/96053886/86622f24-2ae8-471e-970b-18812bf5a92f)

Ga naar het notificatie icoon rechts onderin en klik erop. Als er _"Successfully installed library Adafruit IO Arduino:4.2.7"_ staat, dan is hij succesvol geinstalleerd.
