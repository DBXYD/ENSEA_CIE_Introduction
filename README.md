# ENSEA
# Challenge d'Introduction à l'ENSEA

## Objectifs & cahier des charges
1. Réaliser un objet innovant en petit groupe (4 personnes environ), dans un temps imparti avec des capteurs et actionneurs imposés,
2. Découvrir l'école,
3. Rencontrer les étudiants et le personnel de l'école.

## Quick install

### Installation outils nécessaires
Pour travailler avec micropython sur une carte à micro-controlleur STM32 (Nucleo-L476RG), vous avez besoin de : 
* Un ordinateur
* Un IDE, de préférence avec la coloration syntaxique (PyCharm, Visuel Studio Code, Sublime Text, Notepad++, etc...)
* Un utilitaire pour transferer les fichiers entre votre PC et la carte STM32 : rshell
```bash
python3 install pip
pip3 install rshell
```
* Un utilitaire pour communiquer sur la liaison série avec le microcontroleur (putty, minicom, terraterm, etc...)

### Installer micropython sur la carte Nucleo-L476RG
Micropython est un interpréteur python codé en C pour fonctionner sur micro-controleur ARM. Il faut installer micropython sur le micro-controleur avant de pouvoir éxécuter du code écriten micropython :
1. Télécharger le fichier [.hex](NUCLEO_L476RG-20230426-v1.20.0.hex)
2. Connecter le carte Nucleo sur votre ordinateur
3. Copier le fichier .hex dans le périphérique de masse

### Running 


#### Blinking led
```python
led = pyb.LED(1)
while True:
    led.toggle()
    pyb.delay(1000)
```
