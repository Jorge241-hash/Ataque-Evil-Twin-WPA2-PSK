
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

- Máquina víctima: Con la máquina anfitriona funcionará como víctima para que se se conecte a la red vulnerable.     

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

<img width="700" height="300" alt="Captura3" src="https://github.com/user-attachments/assets/0c2db72e-3634-411f-bbb8-012358f68806" />

<br>
<br>

- Una vez hemos ejecutado el **sudo bash airgeddon.sh**, en el menú elegimos la interfaz que vamos a usar.

<br> 

<img width="1002" height="315" alt="Captura5" src="https://github.com/user-attachments/assets/3bdfcc02-c305-418b-bf3c-f164f97081a1" />

<br>
<br>

- Después de elegir la interfaz, elegimos la opción 5 para capturar el Handshake.

<br>

<img width="1003" height="529" alt="Captura6" src="https://github.com/user-attachments/assets/41899376-3455-4414-8b69-7011ad8488e6" />

<br>
<br>


- Ahora seleccionamos la opción 6 para capturar el handshake.

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

-    






## CONCLUSIÓN





<br>
<br>


## BIBLIOGRAFÍA 

A continuación, muestro los siguientes enlaces a videos y tutoriales que me ha servido para realizar este proyecto:

- https://redtiseg.com/2025/03/09/evil-twin-attack-un-peligro-silencioso-en-redes-inalambricas/
  
- https://www.kaspersky.es/resource-center/preemptive-safety/evil-twin-attacks

-  



<br>
<br> 

