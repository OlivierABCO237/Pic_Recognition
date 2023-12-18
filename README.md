# Pic_Recognition
Classification of images of components by edge impulse and visualisation with Nodered

## Step 1: Data acquisition and classification

- We made a database, adding the database of the teacher with pictures taken ourselves with the phone.
- We made 6 labels: Capacitors, Resistors, Diodes, Integrated Circuit, Leds.
![WhatsApp Image 2023-12-17 at 12 21 35 (2)](https://github.com/OlivierABCO237/Pic_Recognition/assets/148442075/f6fdec90-154d-4c9a-a41d-01f12d605fc0)

- We created an impulse and saved up the model.
  

![DataAcqsui](https://github.com/OlivierABCO237/Pic_Recognition/assets/148442075/e77329a7-8ea8-4ba7-a484-bd0148fe8ce4)

- We saved parameters and processed features:
  

![features](https://github.com/OlivierABCO237/Pic_Recognition/assets/148442075/91c45914-b4d9-45c5-b009-9ab4e8f6ad46)

- First, we let images Height and Weight to 98.

![impulsedesign](https://github.com/OlivierABCO237/Pic_Recognition/assets/148442075/e561300b-e9c5-4c8b-a82a-f272c161229f)

- It gave a very good model with a verry good accuracy, but too heavy for our MCU and for our Camera. We were not able to test the model after generating libraries.

![training](https://github.com/OlivierABCO237/Pic_Recognition/assets/148442075/44599597-a112-4392-b2ae-cc028d789565)

The solution was to change the size of images, putting it to 28. The model was a bit less accurate, but verry good aswell.

![Train2](https://github.com/OlivierABCO237/Pic_Recognition/assets/148442075/9ede90e1-f8e9-429e-b175-a64db1f0d62b)

- We generated an arduino library to test the model, and it worked verry well, like the video bellow shows.

  ## STEP2: Connecting ARduino BLE Sense to Nodered

- La bibliothèque __ArduinoBLE__ permet de faciliter la connexion du MCU à d'autres périphériques fonctionnant en Bluetooth. 
Comme programme test, nous avons recupéré et modifié le programme **ButtonLED**.
- Nous avons créé un service pour chaque Objet à reconnaitre. L'idée est d'incrémenter une variable int chaque fois que l'objet est reconnu, et de l'envoyer en temps réel par bluetooth à l'interface Node-red. D'ou les variables LED1, Resistor1, ETC...
![Services](https://github.com/OlivierABCO237/Pic_Recognition/assets/148442075/87739fe7-4295-4cf0-864e-7572789c5438)








