## Planificación
En este caso atacamos el puerto 80 i el servicio es de tipo http asi que ya me plantee usar herramientas de com 'curl' i 'nikto'.
Al hacerlo encontre unas credenciales obvias que usaria para crear la shell post exploit.

<img width="872" height="519" alt="imagen" src="https://github.com/user-attachments/assets/e809660d-7d5e-4630-bff0-91cecbcd9d80" />

Tambien ejecute la herramienta Nikto para hacer un scan de la pagina web, aunque no encontro mucho descubri que el protocolo http usa la extension WebDAV.

## WebDAV
WebDAV es una extension del protocolo http que hace que pase de ser solo lectura a lectura i escritura, lo que permite subir archivos, y en caso de que este mal configurado se puedan subir scripts maliciosos.
Al saber que usa este tipo de extension quise probar si podia subir algun payload y para eso quise comprobar que tipo de acciones aceptaba, en especial si aceptaba el PUT.
Para esto use la herramienta 'davtest' con las credenciales que habia encontrado previamente.

<img width="704" height="378" alt="imagen" src="https://github.com/user-attachments/assets/60f91674-cb6e-42e0-948e-d08293152c23" />
<img width="715" height="523" alt="imagen" src="https://github.com/user-attachments/assets/f43f6763-0ffc-41b4-9bff-ab0977ad244c" />

Con esto no solo supe que se podian subir archivos sino que ademas los podia ejecutar.
Asi que decidi crear un payload que me diera acceso a shell.
I use la herramienta de Metasploit 'msfvenom' para crearlo como archivo '.php':

<img width="682" height="108" alt="imagen" src="https://github.com/user-attachments/assets/e1b0c27c-b8fe-487c-848d-0848c038983e" />

Este payload lo que hace es generar codigo en php que, al ejecutarse, abre una sesión Meterpreter que se contecte a 192.168.100.10:4444. Todo esto guardado en un archivo llamado shell.php.
