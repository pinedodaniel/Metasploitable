## Planificación
El priemer paso al ver que tenia una versión de este puerto fue mirar por searchsploit si habia algun exploit conocido de backdoor o algo por el estilo. I si en ese caso
estaba disponible en Metasploit.
Con un simple comando se puede comprovar que si es possible:

<img width="1165" height="207" alt="imagen" src="https://github.com/user-attachments/assets/485aadc3-8202-485b-b2b7-9d63a2a02b1b" />

## Metasploit

Ahora usando Metasploit simplemente hay que buscar con 'search' UnrealIRCd y el unico exploit, que es de backdoor, y usarlo con el comando 'use'.

Ahora para saber que opciones hay que completar para usar Metasploit usamos 'show options', y completamos 'set LHOST', 'set RHOST' y 'set PAYLOAD'.

<img width="938" height="233" alt="imagen" src="https://github.com/user-attachments/assets/9efe71af-9af7-4163-8dd2-695844e5958f" />

<img width="1218" height="525" alt="imagen" src="https://github.com/user-attachments/assets/08ac4905-2894-4a10-b8eb-560ee9b1c60a" />

Una vez todo configurado simplemente se ejecuta con exploit y eso abre una terminal root con la que se podrian crear mas usuarios root para mantener el control sobre la maquina
victima, se podrian robar/encriptar archivos y una infinidad de usos mas.

<img width="778" height="259" alt="imagen" src="https://github.com/user-attachments/assets/427e90fc-ecf9-49e4-8122-532e3e097671" />
