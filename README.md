# flow4
Repositorio con actividad de flow 4

Esta actividad es para entender MQTT junto Node-RED

Primero se se implementó el siguiente comando: mosquitto_sub -h localhost -p 1883 -q 0 -t codigoIot/G7/ejemplo

Donde: -h es host -p es puerto -q es caliddad del servicio -t tema

Posteriormente se abre otra terminal para ejecutar el siguiente comando: mosquitto_pub -h localhost -p 1883 -q 0 -t codigoIot/G7/ejemplo -m "Hola Teresa"

Ahora se elebora la conexión con el servidor publico mosquitto:

mosquitto_pub -h ip -p 1883 -q 0 -i teresa-44 -t codigoIot/g9/mosquitto/msg -m "Teresa Fiel"

-i es tu ID -m "mensaje que quieras escribir"

Este se muestra en la ventana de comando y de esta forma todos pudimos ver lo que escribieron los compañeros del salón.

Actividad: Ver la temperatura de mis compañeros mediante una gráfica en donde los valores son mandados constantemente

Abrimos Node-RED

En el cual implementamos los nodos:

-mqtt in (Server en el se esta manejando y Elegir la direccion en Topic de los temas)

-json (Always convert to JavaScript Object) -function (Agregar el siguiente codigo

msg.topic = msg.payload.id;

msg.payload = msg.payload.temp;

return msg; )

-msg -chart (Gráfica)

-inject (Este es para que pueda mandar la misma temperatura constantemente durante un intervalo de tiempo) -mqtt out

Listo
