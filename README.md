# home-assistant_config

## My setup :

### Serveur :

 - Raspberry Pi 4 (v. 4 Go) avec une carte SD 64 Go
 - Raspberry Pi OS (anciennement Raspbian)
 - Configuration docker

My home assistant instance is not using Home Assistant OS but a docker container because my server is not only used for Home Assistant, so, I installed **Hass.io** as a docker container. This is quite a complex manipulation for a beginner but the work of @gcgarner makes it very easy with his **IOTstack** script.

*NB: if you are using a machine based on an ARM architecture such as a Raspberry, you don’t have access to certain features of Hass.io which only work on x86 architectures.*

### My UI:

You will find all the integrations I use in `configuration.yaml`. You should know that all the data collected by the sensors is stored in a time series **InfluxDB** database located on another docker container. The data is then formatted by **Grafana**.

### Sensors used :

`openhardwaremonitor` : collecte des informations sur les composants de mon ordinateur principal et les envois à Home Assistant via le port 8085

- `systemmonitor` : collects information about the components of my desktop and sends it to Home Assistant via port 8085
- `authenticated` : gets data relating to users' connections on Home Assistant (*eg : date of last connection, IP address, etc.*)
- `speedtestdotnet` : performs an internet connection speed test via the famous Speedtestdotnet platform and stores the results every 30 minutes
- `spotify` : Gets the activity of my Spotify account
- `notify.signal` : Notification service through the ultra-encrypted Signal platform, an automation sends me information about the server every evening at 8:00PM.
- `pi_hole` : Service allowing to manage Pi Hole (an network-wide ad blocker) which is in another container.
- `influxdb` : Send the Home Assistant data points to InfluxDB
- `Google` : google API used to get some data from my google calendar  



## Mon installation :

### Serveur :

 - Raspberry Pi 4 (v. 4 Go) avec une carte SD 64 Go
 - Raspberry Pi OS (anciennement Raspbian)
 - Configuration docker

Mon instance de home assistant n’utilise pas Home Assistant OS mais un conteneur docker car je n’utilise pas mon serveur uniquement pour Home Assistant. J’ai donc installé **Hass.io** en tant que conteneur docker. C’est une manipulation assez complexe pour un débutant mais le travail de @gcgarner le rend très facile avec son script **IOTstack**.

*NB : si vous utilisez une machine basée sur une architecture ARM comme un Raspberry, vous n’avez pas accès à certaines fonctionnalités de Hass.io qui ne fonctionnent que sur les architectures x86.*

### Mon interface :

Vous retrouverez toutes les intégrations que j’utilise dans `configuration.yaml`. Il faut savoir que toutes les données récoltées par les capteurs sont stockées dans une base de données time series **InfluxDB** situé sur un autre conteneur docker. Les donné sont ensuite mis en forme par **Grafana**.

### Capteurs utilisés :

`openhardwaremonitor` : collecte des informations sur les composants de mon ordinateur principal et les envois à Home Assistant via le port 8085

- `systemmonitor` : collecte les informations sur les composants du serveur (le Raspberry Pi)
- `authenticated` : Récupère les données relatives aux connections des utilisateurs sur Home Assistant (date de la dernière connexion, adresse IP, etc…)
- `speedtestdotnet` : effectue un teste de vitesse de connexion internet via la célèbre plateforme Speedtestdotnet et récupère les résultats toutes les 30 minutes
- `spotify` : Récupère l’activité de mon compte Spotify
- `notify.signal` : Service de notification au travers de la plateforme ultra crypté Signal, une automatisation m’envoi des informations sur le serveur tous les soirs à 20h00.
- `pi_hole` : Service permettant de gérer Pi Hole (un bloqueur de publicité s’appliquant à tous le resaux locale) qui se trouve dans un autre conteneur.
- `influxdb` : Permet d’envoyer les données de Home Assistant à InfluxDB
- `Google` : API google utilisé pour récupère les données de mon calendrier google


![Home Assistant interface](/chrome_teRx2BuXOw.png)
![Grafana interface](/chrome_WRt5YNnWen.png)
