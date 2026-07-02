## Planificacion:
En este primer puerto (21), fui bastante directo, habia mucha informacion a la vista, tenia un puerto i una version exacta, asi que lo primero que hice fue pasarlo por la herramienta 'searchploit'.

<img width="853" height="141" alt="imagen" src="https://github.com/user-attachments/assets/6dc0c70f-c154-481f-a032-50a4c5857fdf" />

Esto me dejaba con dos exploits, que al buscar sobre ellos resultaron ser un backdoor muy conocido.
Como se ve en la imagen en el segundo, entre parentesis, pone Metasploit.

###Metasploit:
Metasploit es un framework de pentesting donde hay miles de exploits i payloads en un solo lugar.

Por lo tanto entre en este con 'msfconsole'. Dentro de este busque por exploits para vsftpd 2.3.4

<img width="870" height="294" alt="imagen" src="https://github.com/user-attachments/assets/cc65e7fa-0e1d-4ee6-b680-361e9ff607bf" />

Aqui encontre el exploit que habia que usar, i con el comando 'use' lo prepare, despues puse quien era el atacante i quien la victima con 'set LHOST' i 'set RHOST'.

<img width="861" height="416" alt="imagen" src="https://github.com/user-attachments/assets/99824448-d939-456c-9cca-86a6c78c9b0a" />

I por ultimo con el comando exploit se ejecuta i se abre una terminal Meterpeter, una terminal con herramientas de post explotación, en la maquina victima.

<img width="854" height="562" alt="imagen" src="https://github.com/user-attachments/assets/bdcf9938-9535-45aa-9828-e7a4661ce12f" />

A partir de aqui se pueden crear mas usuarios root, robar archivos, etc.
