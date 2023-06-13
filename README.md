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
<!--* Un utilitaire pour transferer les fichiers entre votre PC et la carte STM32 : rshell
```bash
python3 install pip
pip3 install rshell
```-->
* Un utilitaire pour communiquer sur la liaison série avec le microcontroleur (putty, minicom, terraterm, etc...)

### Installer micropython sur la carte Nucleo-L476RG
Micropython est un interpréteur python codé en C pour fonctionner sur micro-controleur ARM. Il faut installer micropython sur le micro-controleur avant de pouvoir éxécuter du code écriten micropython :
1. Télécharger le fichier [.hex](NUCLEO_L476RG-20230426-v1.20.0.hex)
2. Connecter le carte Nucleo sur votre ordinateur
3. Copier le fichier .hex dans le périphérique de masse

### Running 
1. Ecrire votre code en micropython dans votre IDE préféré
2. Ouvrir une liaison série avec votre carte Nucleo :
    * minicom -D /dev/ttyACM0 sous linux
    * putty port COMx, baudrate 115200 sous Windows
    * Remarque : Si rien ne s'affiche, appuyer sur ENTER, vous devriez avoir le prompt ">>>" annonçant que votre carte est bien flashée avec le firmware micropython
3. Placer la carte en "paste mode" avec le raccourci Ctrl+E
4. Copier votre code :
    * avec la souris
    * Ctrl+Shift+V si vous être sous minicom
5. Sortir du "paste mode" avec le raccourci Ctrl+D, votre code s'éxécute tout de suite.
6. Si votre code contient une boucle infinie, faîtes Ctrl+C pour arrêter votre programme

#### Blinking led
```python
led = pyb.LED(1)
while True:
    led.toggle()
    pyb.delay(1000)
```
