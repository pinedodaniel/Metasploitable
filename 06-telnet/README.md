## Planificación
En este puerto no encontre una manera igual de directa para acceder asi que decidi simular un ataque de MITM (Man in the middle).

## Man in the middle

Como en el puerto 23 (Telnet) de Metasploitable2 acepta conexiones en texto plano, sin ningún tipo de cifrado.Significa que cualquier usuario y contraseña enviados durante el login viajan por la red "en claro", legibles por cualquiera que pueda interceptar el tráfico.
Por lo tanto simulamos un escenario en el que un tercer equipo (víctima del MITM) se conecta por Telnet a Metasploitable2, y la máquina atacante (Kali) se sitúa en medio de esa comunicación mediante **ARP Spoofing**, capturando las credenciales sin que ninguna de las dos partes lo note.

## Spoofing
El spoofing consiste en envenenar a ambas maquinas para que piensen que estan hablando entre ellas cuando en realidad estan comunicandose con una tercera (Kali).

Primero activamos el reenvio de paquetes IP:
sudo sysctl -w net.ipv4.ip_forward=1

I seguido de eso las envenenamos para que crean que siguen conectadas entre ellas:
sudo arpspoof -i eth0 -t 192.168.100.30 192.168.100.20
sudo arpspoof -i eth0 -t 192.168.100.20 192.168.100.30

## Wireshark
Ahora mediante la herramienta wireshark empezamos a capturar el trafico que circula por la red a la que esta conectada la maquina atacante. De esta entramos a eth0 que es por donde se estan conectando las dos maquinas victima y aplicamos un filtro para leer solo al puerto 23:
tcp.port == 23

<img width="1543" height="715" alt="imagen" src="https://github.com/user-attachments/assets/10fbf454-eafa-4d4b-b5b7-2eb8df245e70" />


Ahora desde nuestra nueva 3era maquina nos conectamos con telnet a la maquina Metasploitable con las credenciales que nos sabemos legitimamente.
I finalmente desde wireshark, haciendo click derecho en cualquier paquete de protocolo tcp, a la opción follow > TCP stream.
Nos encontraremos esto:

<img width="713" height="412" alt="imagen" src="https://github.com/user-attachments/assets/bb26c671-3f2b-4cb8-a230-f403dab70c49" />

Que aunque tenga un formato raro, debido a que telnet envia los paquetes de texto caracter por caracter, se puede ver que el usuario y contraseña son msfadmin y msfadmin.
Con esto ya se podria acceder a la maquina victima desde nuestro propio telnet o usar estas credenciales para otro tipo de ataques que nos den shells con mejores permisos.
