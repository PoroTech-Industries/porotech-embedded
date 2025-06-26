# PoroCar Embedded

## Überblick

Firmware die auf einem Arduino Uno läuft.\
Arduino ist nur für das Auslegen der Sensoren und überträgt Daten per Serielle Schnittstelle an [PoroCar-Client](https://github.com/PoroTech-Industries/porotech-client)(Raspberry)

## Verwendete Hardware

| Bauteil     | Funktion                                                                       |
|-------------|--------------------------------------------------------------------------------|
| Arduino Uno | Zentrale Sensordatenerfassung                                                  |
| 4x F249     | Drehzahlsensoren                                                               |
| GY-2761     | Magnetometer zu Richtungsbestimmung                                            |
| MPU6050     | Gyroskop + Beschleunigungssensor                                               |
| 3x HC-SR04  | Ultraschallsensoren zur Hinderniserkennung (vorne links, vorne rechts, hinten) |
| DHT11       | Temperatur/Luftfeuchtigkeitssensor                                             |

## Status der Sensoren

| Sensor | Wichtigkeit | Status       | Begründung                             |
|-|-------------|--------------|----------------------------------------|
| F249 Encoder | Niedring    | Funktioniert | Nur für schöne visualisierung          |
| MPU6050 | Hoch        | Meh          | Kp ob richtig geht ohne Kompass eh emo |
| GY-2761 | Hoch        | Meh          | Yaw daten sind übel emo                |
| HC-SR04 | Mittel      | Funktioniert | Erkennt sachen                         |
| DHT11 | Niedrig     | Funktioniert | Gibt plausible Werte                   |

## Setup 

1. Klonen

```bash
git clone https://github.com/PoroTech-Industries/porotech-embedded.git
```

2. Verkabeln
    ![Fritzing Kabelung](https://github.com/PoroTech-Industries/porotech-documentation/blob/master/porotech-embedded/pinout.png)


3. Projekt öffnen
Öffne `porocar.ino` in Arduino IDE

4. Kompilieren und auf Uno Hochladen
- Schließe den Uno an dein Gerät per USB an
- Wähle das richtige Board aus
- Hochladen


## Datenübertragung

- Baudrate: 115200
- Format: `DATASTART|sensorerkennung: sensorwerte|...|DATAEND