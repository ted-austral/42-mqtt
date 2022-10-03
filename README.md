# 42-mqtt

Presentacion IoT: ESP32 + MQTT + NodeRed

*   Realizada en Universidad Austral - Electrónica
*   dias 1 y 8 de Noviembre 2021
*   Presentador: Ing. Eduardo A. Martinez

Se incluyen los fuentes de ESP32 diagramados para cargar
y compilar en PlatformIO bajo Visual Studio Code

En el subdirectorio docs, se encuentra la documentación
adicional presentada, como diagramas, ppt y flujos de NodeRed

## Demostración básica

### Placas ESP32

  Se trata de dos placas de desarrollo de ESP32 que cada una de las cuales posee un sensor de temperatura y hunedad DHT22 y un LED  
  Cada placa está conectada a un broker MQTT con la cual esta relacionada con los siguientes topicos:  
    
  1. Publica temperatura y humedad  
  2. Suscribe a _toggle_ LED  
  3. Suscribe a _interval_ que cambia el periodo de adquisicion de temperatura y humedad  

### Servidores Node-Red

  Los otros dos clientes conectados al broker MQTT son dos servidores Node-Red, uno alojado en una maquina Linux y otro alojado en un smartphone; si bien por comodidad ambos están en la misma red local que el ESP32, podrían estar ubicados en cualquier sitio fuera de la red local, ya que su única vinculación es con el broker MQTT.  

  Ambos servidores Node-Red publican una página con un tablero (_dashboard_) con la información que se intercambia con el broker MQTT; he aqui los topicos que intercambian:  

  1. Publican _toggle_ LED mediante un botón en el _dashboard_  
  2. Publican _interval_ para cambiar el periodo de adquisición de temperatura y humedad  
  3. Suscriben a temperatura y humedad  

### Broker MQTT

  El broker MQTT por defecto no es local y está identificado en _platformio.ini_  
  Se puede elegir un broker local, que es _Mosquitto_ ubicado en una maquina Linux  


Ver README.md en el directorio docs



