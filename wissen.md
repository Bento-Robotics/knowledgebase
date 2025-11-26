# allwissend
In diesem Dokument soll *alles* Bento dokumentiert bzw erklärt werden.
⚠️ Wenn etwas fehlen sollte, bitte ein Issue machen und wir besserns nach!

## Basics

---

## Elektronik

### Circuitpython

#### Libraries / pipkin

Circuitpython bzw auch Micropython Libraries werden mit dem Tool `pipkin` verwaltet.  
Thonny hat eine ältere Version von diesem Tool integriert, da es aber teilweise damit hapert nutzen wir es einfach direkt:  

##### Installation
```shell
sudo apt update && sudo apt install pipx
pipx install --preinstall setuptools pipkin
```

> [!TIP]
> Wir brauchen `pipx` weil normales `pip` mit dem `apt` package manager nicht zusammen funktioniert.


##### Nutzung
Nun kann jedes Package wie bei `pip` installiert werden:  
```shell
pipkin install <package name aus tutorial/github>
# pipkin install adafruit-circuitpython-matrixkeypad
```
Der Microcontroller wird automatisch erkannt.  

##### Häufige Fehler
Falls pipkin den Microcontroller nicht von selber findet: `ERROR: Could not auto-detect target`  
entweder du hast ein *Lade*kabel und kein *Daten*kabel,  
oder sonst was geht ab.  

Microcontroller sollten unter `/dev/ttyACM0` nummeriert auftauchen (oder manchmal `/dev/ttyUSBx`).  
Wenn du mehrere Serial-geräte angeschlossen hast (zb einen LiDAR) kann es auch zu Verwirrung kommen.  
Den port kann man `pipkin` vorschreiben:  
```shell
pipkin --port=<port> install <package name aus tutorial/github>
# pipkin --port=/dev/ttyACM1 install adafruit-circuitpython-matrixkeypad
```

---

## Software
