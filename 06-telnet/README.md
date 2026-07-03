## Planificación
En este puerto no encontre una manera igual de directa para acceder asi que decidi simular un ataque de MITM (Man in the middle).

## Man in the middle

Como en el puerto 23 (Telnet) de Metasploitable2 acepta conexiones en texto plano, sin ningún tipo de cifrado.Significa que cualquier usuario y contraseña enviados durante el login viajan por la red "en claro", legibles por cualquiera que pueda interceptar el tráfico.
Por lo tanto simulamos un escenario en el que un tercer equipo (víctima del MITM) se conecta por Telnet a Metasploitable2, y la máquina atacante (Kali) se sitúa en medio de esa comunicación mediante **ARP Spoofing**, capturando las credenciales sin que ninguna de las dos partes lo note.
