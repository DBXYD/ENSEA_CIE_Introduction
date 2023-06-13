# ENSEA
# Challenge d'Introduction à l'ENSEA

## Quick install

### Installation outils nécessaires


### Flash Nucleo-L476RG
Télécharger le fichier [.hex](NUCLEO_L476RG-20230426-v1.20.0.hex)


### Running 


#### Blinking led
```python
led = pyb.LED(1)
while True:
    led.toggle()
    pyb.delay(1000)
```
