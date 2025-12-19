# LogIoT

------------

### Proyecto LogIoT - Practica Profesionalizante 1

Como parte del TP numero 2, seleccionamos el proyecto comenzado por Luciano.
El mismos consta de un sistema de logistica via GPS para localizacion, automatizacion de recorridos, seguimiento y metrica de elementos moviles como AGV o vehiculos automatizables.

EL proyecto consta del dispositivo enbebido con su sistema de sensores y comunicacion. Backend para comunincacion con base de datos y sistemas de visualizacion como Grafana. Y aplicacion WEB para seguimiento, control y debug de los dispositivos desplegados.

-----------

**Profesor:** Violi, Dante

**Integrantes:**
 - Lisandro Juncos                   | https://github.com/Lisandro-05
 - Macarena Carballo [Scrum Master]  | https://github.com/MacarenaAC
 - Raul Jara                         | https://github.com/r-j28
 - Luciano Lujan [Prouduct Owner]    | https://github.com/lucianoilujan
 - Fernando Gimenez Coria            | https://github.com/FerCbr
 - Vittorio Durigutti                | https://github.com/vittoriodurigutti
 - Ares	Diego                        | https://github.com/diegote7

-----------

### Stack Tecnologico:

- Backend (docker)
    - Mosquitto: Broker MQTT local (puertos 1883, 9001)
    - Web App: Flask + SocketIO para dashboard web
    - InfluxDB: Base de datos de series temporales
    - Grafana: Dashboards y visualización
    - Telegraf: 2 instancias
    - telegraf: Broker local Mosquitto (comentado)
    - telegraf_aws: AWS IoT Core con certificados SSL
    - PostGIS: Base de datos geoespacial
    - Geoproc App: Procesamiento geoespacial
    - Publisher: Simulador de camiones
    - Node-RED: Flujo de datos
    - NPM: Proxy reverso
    - Cloudflare Tunnel: Acceso externo

- Dispositivo Embebido:
    - ESP32
    - MOdulo GPS
    - Modulo pantalla TFT
    - Modulo sensor de proximidad


-----------

### Flujos de Datos

**Producción (AWS IoT Core)**

ESP8266 → AWS IoT Core → Telegraf AWS → InfluxDB → Grafana
                    ↓
                Web App (app.py) → Dashboard Web

**Desarrollo/Testing (Mosquitto local)**

Publisher → Mosquitto → Telegraf (comentado) → InfluxDB
                    ↓
                Web App → Dashboard Web

-----------
-----------

### Arquitectura de red:
