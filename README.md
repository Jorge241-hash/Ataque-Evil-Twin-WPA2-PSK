
<div align="center">

# ATAQUE EVIL TWIN CONTRA WPA2 PSK - HACKING ÉTICO - JORGE LÓPEZ ARCOS


<img width="1536" height="1024" alt="eviltwin" src="https://github.com/user-attachments/assets/67c579ae-33cb-4083-aec2-9e46ed426887" />


</div>
<br>
<br> 


## DESCRIPCIÓN DEL ATAQUE 

Este ataque llamado Evil Twin (Gemelos Malvados) es una técnica de hacking en la que un atacante suplanta un punto de acceso Wi-Fi con el mismo SSID que la red legal. Consiste en manipular a los usuarios para incitar a que se conecten a la red ilegal, con lo que el atacante puede interceptar su tráfico, robar contraseñas o realizar sniffing como el MITM. Es un ataque bastante común porque los usuarios suelen confiar en redes sin conocer su autenticidad.

<br>
<br> 

## CARACTERÍSTICAS DEL ATAQUE 

-  **Fácil de implementar**: Se puede implementar con herramientas accesibles como Airbase-ng, Wifiphisher o EvilAP.

-  **Difícil de detectar para usuarios sin conociemientos de redes**: La gran mayoría de dispositivos se conectan automáticamente a redes con nombres comunes.

-  **Se explotan más las redes públicas y corporativas**: Este ataque suele ser más común en aeropuertos, cafeterías y hoteles.

-  **Ataques MITM**: Permite a atacantes ponerse en mitad de la comunicación y capturar datos confidenciales como pueden ser credenciales o correos electrónicos.

-  **Suplantación de páginas web**: Con el fin de robar credenciales mediante ataques de ingeniería social (phishing, pretexting, etc...), algunos ataques de Evil Twin pueden redirigir a una página falsa de autenticación.  

<br>
<br> 


## HERRAMIENTAS UTILIZADAS PARA LA REALIZACIÓN DEL PROYECTO

Para la realización de este ataque van a ser necesarias las siguientes herramientas:

- Máquina Kali Linux: Esta máquina funcionará como atacante en la que suplantaremos el punto de acceso Wi-Fi.

- Alfa Network AWUS036ACH: Utilizaré esta tarjeta para poder obtener información acerca de las redes Wi-Fi y poder realizar el proyecto. 

- Airgeddon: Herramienta Open Source que se utiliza para realizar auditorías de seguridad y pentesting en redes inalámbricas Wi-Fi.


<br>
<br>


## DESARROLLO DEL PROYECTO

- Primero actualizo los repositorios y después instalo la herramienta Airgeddon.

 ```bash
# Actualizo los repositorios e instalo Airgeddon
 sudo apt update

 git clone https://github.com/v1s1t0r1sh3r3/airgeddon

 cd airgeddon

 sudo bash airgeddon.sh

```

<img width="700" height="332" alt="Captura1" src="https://github.com/user-attachments/assets/4c7e4f1b-d725-4295-a072-97244a001b0d" />

<br> 

<img width="700" height="332" alt="Captura2" src="https://github.com/user-attachments/assets/3e317519-43ba-45e0-92a6-06b0996b930f" />

<br>

<img width="400" height="200" alt="Captura4" src="https://github.com/user-attachments/assets/5e44bfba-7d22-42c0-97ab-e0aac0a736e7" />


<br>
<br>

- Ahora ponemos la tarjeta en modo monitor y matamos los procesos.

 ```bash
# Mato los procesos y pongo la tarjeta en modo monitor

 sudo airmon-ng check kill
 sudo airmon-ng start wlan0

```

<img width="800" height="350" alt="Captura3" src="https://github.com/user-attachments/assets/0c2db72e-3634-411f-bbb8-012358f68806" />

<br>
<br>

- Una vez hemos ejecutado el **sudo bash airgeddon.sh**, en el menú elegimos la interfaz que vamos a usar.

<br> 

<img width="900" height="416" alt="Captura5" src="https://github.com/user-attachments/assets/3bdfcc02-c305-418b-bf3c-f164f97081a1" />

<br>
<br>

- Después de elegir la interfaz, elegimos la opción 5 para capturar el Handshake.

<br>

<img width="664" height="416" alt="Captura6" src="https://github.com/user-attachments/assets/41899376-3455-4414-8b69-7011ad8488e6" />

<br>
<br>


- En esta captura muestro como indico la opción 6 para capturar el handshake.

<br>

<img width="664" height="416" alt="Captura7" src="https://github.com/user-attachments/assets/c974ab94-14b4-4a3e-b721-0c1c27cb0bf9" />

<br>
<br>

- Ahora seleccionamos la red que queremos atacar que en este caso es CETI

<br>

<img width="782" height="589" alt="Captura9" src="https://github.com/user-attachments/assets/a663aa57-82ae-4f91-a067-07b6f447111f" />

<br>
<br>

- A continuación, seleccionamos la opción 2 para forzar tráfico y desautenticar a los usuarios.

<br> 

<img width="878" height="406" alt="Captura10" src="https://github.com/user-attachments/assets/d5d37b13-a178-453b-8657-ef903e583fbe" />

<br>
<br>

- En esta captura muestro que puesto un límite de 100 segundos para generar el handshake y expulsar a los clientes de la red para forzarlos a reconectar.

<br>

<img width="1335" height="501" alt="Captura11" src="https://github.com/user-attachments/assets/d2cb4405-8161-4c7e-96cd-4517b010a600" />

<br>
<br>

- Volvemos al menú principal seleccionando la opción 0.

<br>

<img width="1265" height="512" alt="Captura12" src="https://github.com/user-attachments/assets/2960611b-be29-4cf9-923d-7f8ca74d5d4f" />
 
<br>
<br>


- Seleccionamos la opción 7 para elegir el ataque de Evil Twin. 

<br>

<img width="1350" height="509" alt="Captura13" src="https://github.com/user-attachments/assets/994d8cdb-95cc-4daa-b7ec-619f1388b123" />

<br>
<br>


- Una vez dentro, elegimos la última opción de portal cautivo. 

<br>

<img width="1184" height="477" alt="Captura14" src="https://github.com/user-attachments/assets/3970122b-fd52-4d03-86c9-b03dbdd9d983" />

<br>
<br>

- En esta captura se muestra como hago el escaneo de todas las redes WiFi cercanas. 

<br>

<img width="1349" height="427" alt="Captura15" src="https://github.com/user-attachments/assets/32afbabe-1443-44aa-b0e8-ff3a9ea4030d" />

<br>
<br>


- Seleccionamos el ataque deauth aireplay con el fin de desautenticar a los clientes y cuando se intenten conectar de nuevo generar el handshake.

<br>

<img width="1118" height="394" alt="Captura16" src="https://github.com/user-attachments/assets/9ab92e14-ab95-41e3-af09-be498f3dcf9e" />

<br>
<br>


- A continuación, seleccionamos la red de CETI con el objetivo de crear el portal cautivo y suplantarla.

<br>

<img width="1366" height="642" alt="Captura16ç" src="https://github.com/user-attachments/assets/defa2eea-d866-4df7-bcc2-f99dc8066e78" />

<br>
<br>

- En esta captura indico el fichero de handshake que quiero utilizar. 

<br>

<img width="1348" height="513" alt="Captura18" src="https://github.com/user-attachments/assets/c2555aa7-cfde-4438-a1e9-672aa8792d9f" />

<br>
<br>

- Seleccionamos el idioma en el que cliente verán el portal cautivo.

<br>

<img width="1304" height="577" alt="Captura19" src="https://github.com/user-attachments/assets/e9a5433c-1d73-4b05-9a24-1f245b308e7c" />

<br>
<br>

- Ahora aceptamos el portal cautivo.

<br>

<img width="1349" height="222" alt="Captura20" src="https://github.com/user-attachments/assets/730213d8-ade0-4706-be7b-770fa593d822" />

<br>
<br>

- Se muestra que el ataque está activo y su muestra varias ventanas del ataque como son el AP, DHCP, DNS y el control donde monitoriza y verifica la contraseña.

<br>

<img width="1356" height="603" alt="Captura21" src="https://github.com/user-attachments/assets/b63ce6a4-d097-40d1-8f03-91b93eb1bbce" />

<br>
<br>

- Si vemos la redes Wi-Fi disponibles, podemos ver que se ha suplantado la red original de CETI.  

<br>

<img width="683" height="733" alt="Captura22" src="https://github.com/user-attachments/assets/64ab864b-858c-45d6-b37e-6c4b60fa34de" />

<br>
<br>

- A continuación, introducimos la contraseña de la red Wi-Fi de CETI.

<br>

<img width="681" height="557" alt="Captura23" src="https://github.com/user-attachments/assets/4e05d0a2-016a-4db7-9343-7122d301aa08" />

<br>
<br>

- Por último, se muestra que se ha obtenido la contraseña de la red Wi-Fi y que el ataque se ha producido correctamente.

<br>

<img width="1361" height="363" alt="Captura24" src="https://github.com/user-attachments/assets/ac34edd2-5119-401c-a0ba-a167af50e366" />

<br>
<br>


## MITIGACIÓN

Para poder protegernos de los ataques de Evil Twin conviene realizar los siguientes aspectos: 

- Actualizar a WPA3: Ofrece una protección mucho mejor frente a los ataques de fuerza bruta y Evil Twin gracias al protocolo SAE.

- Cambiar contraseñas por defecto: Asignar una contraseña segura a tu router para dificultar a los atacantes.

- Usar VPN: El uso de una VPN permite encriptar el tráfico de la red lo que provoca que el atacante solo veo los datos cifrados.

- Desactivar la conexión automática: Evita conectarse de forma automática a todos los puntos de accesos Wi-Fi que te acerques.

- No iniciar sesión en cuentas personales: Es de principal importancia no iniciar sesión en tus cuentas personales. Además, es muy importante no introducir datos de pago ni acceder a servicios de pago, como la banca por Internet.


<br>
<br>


## CONCLUSIÓN

En conclusión, me ha parecido un ataque bastante interesante en el que se muestra el procedimiento que utilizan los atacantes para suplantar la red Wi-Fi original con el objetivo de analizar el tráfico de la red y obtener datos confidenciales como pueden ser la contraseña de la propia red o datos de cualquier usuario. Recomiendo a futuros alumnos a realizar este proyecto porque ayuda bastante a entender el funcionamiento de la red Wi-Fi.


<br>
<br>


## BIBLIOGRAFÍA 

A continuación, muestro los siguientes enlaces a vídeos y tutoriales que me han ayudado para realizar este proyecto:

- https://redtiseg.com/2025/03/09/evil-twin-attack-un-peligro-silencioso-en-redes-inalambricas/
  
- https://www.kaspersky.es/resource-center/preemptive-safety/evil-twin-attacks

- https://diegoaltf4.com/evil-twin/

- https://ciberseguridad.com/amenzas/ataque-evil-twin/


<br>
<br> 

