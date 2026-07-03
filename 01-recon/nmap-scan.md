# Reconocimiento
Antes de atacar cualquier cosa ha de haber un planificamiento previo, una parte de esa planificación es hacer un mapa de a donde vamos a intentar entrar. Ese mapeo es el primer paso en el ataque entre estas dos maquinas.
Este se hace con la herramienta Nmap i netdiscover.

## Netdiscover
Con netdiscover miramos que mas hay en nuestra red:

<img width="628" height="183" alt="imagen" src="https://github.com/user-attachments/assets/8278453c-9d8a-44ab-aa54-c4f4ed3f2d25" />

Aqui se puede ver que con la IP 192.168.100.10/24 (la nuestra) tenemos en nuestra red otra IP 192.168.100.20 que es a la que atacaremos.


## Nmap
Nmap es una herramienta ya incluida en los paquetes de Kali, con esta se pueden ver al usar ciertos parametros:
- **Los puertos**
- **El estado de los puertos (abierto/cerrado)**
- **El servicio que se esta hosteando en este puerto**
- **I la version de el servicio que se proporciona**

En nuestro caso usamos como parametro -sV.

No siempre se tiene acceso a todas estas opciones, un ejemplo es:
<img width="739" height="541" alt="imagen" src="https://github.com/user-attachments/assets/f8c5452c-3ffe-4d66-a3be-dabab62d52cd" />

En el puerto 6000 se puede ver que que en la version pone (acces denied).
Y en otras la version no se especifica del todo.
