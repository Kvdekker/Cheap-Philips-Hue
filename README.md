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
![image](https://github.com/Kvdekker/Cheap-Philips-Hue/assets/96053886/1bf76cdd-60fd-4fbd-8a5b-dd2eb0243268)

## Stap 2: Adafruit account aanmaken
Voor het gebruik van de colorpicker heb je een Adafruit OI account nodig. Doe dit via https://io.adafruit.com
Heb je al een account? Ga dan via de Adafruit website naar dashboard.

Klik vervolgens op het gele sleutel icoon rechts boven op je scherm:
![image](https://github.com/Kvdekker/Cheap-Philips-Hue/assets/96053886/cdb4392b-9210-4ab1-8dc6-1fd9fe0e5f66)
Hier kom je op een scherm waar jij jou gebruikersnaam ziet en je persoonlijke sleutel. Deze gegevens houdt je alleen voor jezelf. Dit beschermt jouw data voor mensen die er misbruik van willen maken.

Kopieer de gehele code die binnen het _Arduino_ kopje staat. Er zou dan bijvoorbeeld moeten staan:
**#define IO_USERNAME "Jouwgebruikersnaam"**
**#define IO_KEY "Jouwsleutelcode"**
Zodra je deze code gekopieërd hebt, klik je dit weg en klik je vervolgens op _New Dashboard_.
![image](https://github.com/Kvdekker/Cheap-Philips-Hue/assets/96053886/49b00eb0-775d-47a0-824c-f93861326ed4)
Geef dit dashboard een naam naar jouw persoonlijke voorkeur, voeg een descriptie toe en klik op create.

Op het volgende scherm, klik je recht op het tandwiel icoon en klik je op _Create New Block_.
![image](https://github.com/Kvdekker/Cheap-Philips-Hue/assets/96053886/7e6e293e-df8f-4c6e-95de-2c0a45804968)
Klik vervolgens op Color picker.
![image](https://github.com/Kvdekker/Cheap-Philips-Hue/assets/96053886/4b7eb959-630a-41f9-a990-29d097d88282)

Nu zal je hoogswaarschijnlijk de vraag krijgen om een _Feed te connecten_. Dit kan je doen door in het lege vak een naam in te typen. _**LET OP** De naam die je hier intypt ga je moeten hertypen in de code_! Dit zorgt ervoor dat jij de kleur kan zenden naar jouw Arduino Kit. Vink daarna jouw gemaakte Feed aan en klik op next step. 
![image](https://github.com/Kvdekker/Cheap-Philips-Hue/assets/96053886/02fd3baf-e22a-4fd0-812a-080d988c9f24)

Geef hier jouw Color picker een Block Title (als je dat wilt). Klik daarna op create block.
![image](https://github.com/Kvdekker/Cheap-Philips-Hue/assets/96053886/2570b547-7649-40f3-9656-9b4c4c20188c)

Test nu de color picker door erop te klikken en de kleur aan te passen in de browser. Werkt dit? Dan ben je klaar met stap 2.

## Stap 3: Connect Arduino met Color Picker
Open je Arduino IDE file die je in stapt 1 geopend hebt. Klik op File -> Examples -> Adafruit IO Arduino (scroll even naar beneden, ik maakte die fout ook!) -> adafruitio_14_neopixel. Klik hierop en hij zal een nieuwe sketch openen. Zet deze op groot beeld.
![image](https://github.com/Kvdekker/Cheap-Philips-Hue/assets/96053886/0816838d-e9c1-4720-907f-d001650bd771)
Zie je hetzelfde als op de foto hierboven? Dan ben je goed bezig.

Met deze code gaan we jou LEDS connecten aan het dashboard die je zojuist aangemaakt hebt, waar jouw colorpicker klaar staat om gebruikt te worden.

Je moet nu Binnen Arduino IDE klikken op het tabje boven in, genaamd config.h . Hier ga jij je de gebruikersnaam en sleutel die je eerder gekopieerd hebt van jouw dashboard hierin plakken. Ik kon zelf eerder niet vinden waar ik dit moest plakken, omdat ik het tabje Config.h niet kon vinden. Vervang bovenin je code de tejst #define IO_USERNAME en #define IO_KEY met de gegevens die je gekopieerd hebt. Ga vervolgens naar beneden totdat je #define WIFI_SSID en #define WIFI_PASS tegenkomt. Hier vul jij jouw Wifi inlog en wachtwoord in. Vul dit in tussen de aanhalingstekens. 

Ga vervolgens terug naar het vorige tabje wat naast config.h staat.

Scroll totdat je #define PIXEL_PIN tegenkomt en vul de juiste waardes in. Ik heb mijn draad op D5 met 15 leds. Vul dit in.
![image](https://github.com/Kvdekker/Cheap-Philips-Hue/assets/96053886/1c988b03-e69b-4076-90f2-cf247ce4286e)

Vul ook jouw Feednaam in die jij gemaakt hebt:
![image](https://github.com/Kvdekker/Cheap-Philips-Hue/assets/96053886/5c7333ea-3e25-4f45-86e6-49d99e4eaadc)

Klik nu op verify om te controleren of jouw code klopt. Klik vervolgens op Upload. Verander nadat de code geupload is naar jouw Arduino de kleur via de Colorpicker in de webbrowser in. Veranderd jouw ledstrip? Gefeliciteerd! Jouw eigen goedkopen Philips Hue is af!
