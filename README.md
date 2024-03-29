# Write-Ups

<p align="center">
  <img src="https://github.com/UchaCTF/WriteUps/blob/8cc7c994164c2aa4031ad6cb107eaf0284246896/Logo.v2.peque.jpg">
</p>

## Herramientas utilizadas:

# Criptografía

- [CyberChef](https://gchq.github.io/CyberChef/) - Herramienta de manipulación de datos para descifrar y codificar mensajes cifrados (página web).
- [Hashcat](https://hashcat.net/hashcat/) - Herramienta de cracking de contraseñas que admite una amplia variedad de algoritmos de hash (herramienta de línea de comandos).
Ejemplo de uso: `hashcat -m 0 -a 0 hash.txt rockyou.txt` donde `hash.txt` es el archivo que contiene los hashes a crackear y `rockyou.txt` es el archivo que contiene la lista de contraseñas.
- [John the Ripper](https://www.openwall.com/john/) - Herramienta de cracking de contraseñas que admite varios tipos de cifrado y formatos de archivo (herramienta de línea de comandos). Ejemplo de uso: `john hash.txt` donde `hash.txt` es el archivo que contiene los hashes a crackear.

    - **WriteUps de ejemplo**:    
        - ![TheSenderConundrum](https://github.com/UchaCTF/WriteUps/tree/main/Forense/2023Vishwactf/TheSenderConundrum) (*Zip Cifrado*)
        
- [CryptoCorner](https://crypto.interactive-maths.com/) - Herramientas criptográficas y de codificación para ayudar a cifrar y descifrar datos. Algunas de las herramientas que ofrece son generadores de claves criptográficas, cifradores y descifradores de mensajes, y herramientas para el análisis de criptogramas (página web).
- [AsecuritySite](https://asecuritysite.com/coding/freq) - Herramientas para el análisis y la protección de la información. Una de las herramientas que ofrece es el analizador de frecuencia, que permite analizar la frecuencia de aparición de caracteres en un mensaje cifrado para ayudar a descifrarlo. (página web).
- [Boxentriq](https://www.boxentriq.com/) - Plataforma en línea que ofrece diversas herramientas y desafíos para el aprendizaje y la práctica de habilidades en áreas como la criptografía, la esteganografía y la resolución de acertijos. Entre sus herramientas se incluyen generadores de claves criptográficas, cifradores y descifradores de mensajes, y herramientas de análisis de criptogramas. (página web).
- [Dcode](https://www.dcode.fr/) -  plataforma en línea tipo cyberchef que proporciona una amplia variedad de herramientas criptográficas y de codificación para ayudar a cifrar y descifrar datos de forma segura. También ofrece herramientas para la resolución de acertijos y problemas matemáticos, así como para el análisis de criptogramas y códigos. (página web).

    - **WriteUps de ejemplo**:    
        - ![OverTheWire](https://github.com/albertominan/WriteUps/tree/main/Criptograf%C3%ADa/OverTheWire/Krypton) (*Análisis de frecuencia*)
      

# Esteganografía

- [Steghide](http://steghide.sourceforge.net/) - Herramienta de esteganografía para ocultar datos en imágenes y archivos de audio (herramienta de línea de comandos).
Ejemplo de uso: `steghide extract -sf imagen.jpg` donde `imagen.jpg` es el archivo de imagen que contiene datos ocultos.
- [Exiftool](https://exiftool.org/) - Herramienta para leer y escribir metadatos en archivos de imagen, audio y video (herramienta de línea de comandos).
Ejemplo de uso: `exiftool archivo.jpg` donde `archivo.jpg` es el archivo de imagen del que deseas obtener información.

    - **WriteUps de ejemplo**:    
        - ![FindLocation](https://github.com/UchaCTF/WriteUps/tree/main/Esteganograf%C3%ADa/VU%20Cyberthon%202023)

- [Foremost](https://github.com/korczis/foremost) - Herramienta de recuperación de datos para extraer archivos de un sistema de archivos o una imagen de disco (herramienta de línea de comandos).
Ejemplo de uso: `foremost -t all -i imagen.dd` donde `imagen.dd` es la imagen de disco que deseas analizar.
- [Strings](https://linux.die.net/man/1/strings) - Utilidad de línea de comandos que puede buscar cadenas de texto en un archivo binario (herramienta de línea de comandos). Ejemplo de uso: `strings archivo.bin` donde `archivo.bin` es el archivo binario del que deseas extraer las cadenas de texto.
- [Audacity](https://www.audacityteam.org/) - Programa de edición y grabación de audio de código abierto y multiplataforma que permite modificar y analizar archivos de audio (aplicación de escritorio). 

    - **WriteUps de ejemplo**:    
        - ![CanYouSeeMe](https://github.com/UchaCTF/WriteUps/tree/main/Esteganograf%C3%ADa/2023Vishwactf/CanYouSeeMe) (*Análisis de espectro*)

- [Binwalk](https://github.com/ReFirmLabs/binwalk) - Herramienta de análisis y extracción de firmware que permite identificar y extraer archivos y sistemas de archivos incrustados en imágenes de firmware (herramienta de línea de comandos). Ejemplo de uso: `binwalk -e firmware.bin` donde `firmware.bin` es el archivo de firmware que contiene archivos o sistemas de archivos incrustados.

    - **WriteUps de ejemplo**:    
        - ![CanYouSeeMe](https://github.com/UchaCTF/WriteUps/tree/main/Esteganograf%C3%ADa/2023Vishwactf/CanYouSeeMe)

# Forense

### Suites forenses

- [Autopsy](https://www.sleuthkit.org/autopsy/) - Herramienta de análisis forense que puede analizar imágenes de discos y sistemas de archivos (herramienta gráfica).

    - **WriteUps de ejemplo**:    
        - ![Forense en Windows](https://github.com/UchaCTF/WriteUps/tree/main/Forense/Windows/San%20Clemente%20CASO%20%232)

- [Bulk Extractor](https://github.com/simsong/bulk_extractor) - Herramienta de análisis forense digital que extrae automáticamente información como correos electrónicos, números de tarjeta de crédito y URLs de archivos, imágenes de disco y volcados de memoria (herramienta de línea de comandos). Ejemplo de uso: `bulk_extractor -o salida carpeta_imagen.dd` donde `salida` es la carpeta de destino para los resultados del análisis y `carpeta_imagen.dd` es la imagen de disco o archivo que se va a analizar.

- [OS Forensics](https://www.osforensics.com/) (versión de prueba limitada a 30 días)

- [FTK Imager](https://accessdata.com/product-download/ftk-imager-version-4-5)

- [SDL Redline](https://www.mandiant.com/resources/download/redline)

### Análisis memoria RAM

- [Volatility](https://www.volatilityfoundation.org/) - Herramienta de análisis de memoria para extraer información de la memoria volátil de un sistema (herramienta de línea de comandos).
Ejemplo de uso: `volatility -f memoria.mem imageinfo` donde `memoria.mem` es el archivo de imagen de memoria volátil que deseas analizar.

    - **WriteUps de ejemplo**:    
        - ![Forense en Windows](https://github.com/UchaCTF/WriteUps/tree/main/Forense/Windows/San%20Clemente%20CASO%20%232)

### Montaje de imágenes

- [OSF Mount](https://www.osforensics.com/tools/mount-disk-images.html)

### Editor hexadecimal de disco

- [Active disk Editor](https://www.disk-editor.org/)

### Análisis de MFT

- [Mft2Csv](https://tzworks.net/prototype_page.php?proto_id=3)

### Análisis de LogFile y UsnJrnl

- [Log File Parser](https://github.com/jschicht/LogFileParser)
- [NTFS Log Tracker](https://github.com/jschicht/NTFS-Log-Tracker)

### Análisis del registro de Windows

- [RegRipper](https://github.com/keydet89/RegRipper3.0)
- [Windows Registry Recover](https://www.nirsoft.net/utils/windows_registry_recovery.html)
- [Registry Explorer](https://ericzimmerman.github.io/#!index.md)
- [RECmd](https://ericzimmerman.github.io/#!index.md)
- [USBDeview](https://www.nirsoft.net/utils/usb_devices_view.html) (análisis de dispositivos USB)
- [USB Detective](https://www.13cubed.com/products) (análisis de dispositivos USB)

### Análisis de los logs de windows (Event Log)

- [FullEventLogView](https://www.nirsoft.net/utils/full_event_log_view.html) de Nirsoft

### Análisis de Prefetch y Superfetch

- [WindowsPrefetchView](https://www.nirsoft.net/utils/win_prefetch_view.html) de Nirsoft
- [CrowdResponse](https://www.crowdstrike.com/resources/community-tools/crowdresponse/)

### Análisis del registro de actividad

- [Windows Timeline Parser](https://github.com/kacos2000/WindowsTimeline)
- [WxTCmd](https://github.com/EricZimmerman/WxTCmd)

### Análisis de la papelera de reciclaje

- [Rifiuti2](https://github.com/abelcheung/rifiuti2)
- [RBCmd](https://github.com/kacos2000/RecycleBin)

### Registros de seguimiento (Event Log Tracer, etl)

- [ETLParser](https://github.com/woanware/etlparser)

### Navegadores Web

- [SQLite Studio](https://sqlitestudio.pl/)
- [IE HistoryView](https://www.nirsoft.net/utils/iehv.html) de Nirsoft
- [ESEDatabaseView](https://www.nirsoft.net/utils/ese_database_view.html) de Nirsoft
- [BrowsingHistoryView](https://www.nirsoft.net/utils/browsing_history_view.html) de Nirsoft
- [IECookiesView](https://www.nirsoft.net/utils/iecookies.html) de Nirsoft
- [EdgeCookiesView](https://www.nirsoft.net/utils/edge_cookies_view.html) de Nirsoft
- [IECacheView](https://www.nirsoft.net/utils/ie_cache_viewer.html) de Nirsoft
- [MZCacheView](https://www.nirsoft.net/utils/mozilla_cache_viewer.html) de Nirsoft
- [ChromeHistoryView](https://www.nirsoft.net/utils/chrome_history_view.html) de Nirsoft
- [ChromeCookiesView](https://www.nirsoft.net/utils/chrome_cookies_view.html) de Nirsoft
- [ChromeCacheView](https://www.nirsoft.net/utils/chrome_cache_view.html) de Nirsoft

### Correo electrónico

- [PST Viewer](https://www.nucleustechnologies.com/pst-viewer.html)

# Hacking Web

- [Burp Suite](https://portswigger.net/burp) - Suite de herramientas de hacking web para probar y explotar vulnerabilidades en aplicaciones web (herramienta gráfica).
- [SQLMap](https://github.com/sqlmapproject/sqlmap) - Herramienta de automatización de inyección SQL para probar vulnerabilidades en bases de datos (herramienta de línea de comandos).
Ejemplo de uso: `sqlmap -u "http://example.com/?id=1" --dbms=mysql --dump` donde `http://example.com/?id=1` es la URL de la aplicación web vulnerable, `--dbms=mysql` indica el tipo de base de datos y `--dump` indica que deseas descargar toda la información de la base de datos.
- [OWASP ZAP](https://www.zaproxy.org/) - Proxy de seguridad web de código abierto que se puede utilizar para encontrar y explotar vulnerabilidades (herramienta gráfica).

# Misc



# OSINT

- [The Harvester](https://github.com/laramies/theHarvester) - Herramienta de recopilación de información que puede buscar correos electrónicos, nombres de usuario, hostnames, etc. en fuentes públicas (herramienta de línea de comandos).
Ejemplo de uso: `theharvester -d example.com -l 500 -b google` donde `example.com` es el dominio que deseas analizar, `-l 500` indica que deseas limitar la salida a 500 resultados y `-b google` indica que deseas usar la búsqueda de Google.
- [Maltego](https://www.maltego.com/) - Herramienta de investigación y análisis de enlaces para recopilar información y relaciones en línea (herramienta gráfica).

# Pwning

- [GDB](https://www.gnu.org/software/gdb/) - Depurador de código abierto que puede ser útil para analizar y explotar vulnerabilidades en binarios ejecutables (herramienta de línea de comandos).
- [IDA Pro](https://www.hex-rays.com/products/ida/) - Desensamblador y depurador que puede ser útil para analizar binarios ejecutables y encontrar vulnerabilidades (herramienta gráfica).
- [Pwntools](https://github.com/Gallopsled/pwntools) - Marco de explotación para binarios ejecutables que puede ser útil para crear exploits (herramienta de línea de comandos).
Ejemplo de uso: `python -c "from pwn import *; print(hexdump(asm(shellcraft.sh())))"` para crear un exploit simple que ejecute una shell en el objetivo.

# Reversing

- [Ghidra](https://ghidra-sre.org/) - Marco de ingeniería inversa de código abierto que puede ser útil para analizar binarios ejecutables (herramienta gráfica).
- [Radare2](https://github.com/radareorg/radare2) - Marco de ingeniería inversa de código abierto que puede ser útil para analizar binarios ejecutables (herramienta de línea de comandos).
Ejemplo de uso: `r2 archivo` donde `archivo` es el archivo binario que deseas analizar.
- [IDA Pro](https://www.hex-rays.com/products/ida/) - Desensamblador y depurador que puede ser útil para analizar binarios ejecutables y encontrar vulnerabilidades (herramienta gráfica).

# Tráfico de Red

- [Tcpdump](https://www.tcpdump.org/) - Herramienta de línea de comandos para capturar y analizar el tráfico de red en tiempo real (herramienta de línea de comandos).
Ejemplo de uso: `tcpdump -i eth0 tcp port 80` donde `eth0` es la interfaz de red y `tcp port 80` indica que deseas capturar el tráfico TCP en el puerto 80.
- [Scapy](https://scapy.net/) - Herramienta de manipulación de paquetes de red que puede ser útil para crear y enviar paquetes personalizados (herramienta de línea de comandos).
Ejemplo de uso: `sudo scapy` para iniciar Scapy en modo interactivo y luego `send(IP(dst="www.google.com")/ICMP())` para enviar un paquete ICMP a la dirección IP de Google.
- [Wireshark](https://www.wireshark.org/) - Analizador de tráfico de red que puede ser útil para encontrar y analizar paquetes específicos (herramienta gráfica).

    - **WriteUps de ejemplo**:    
        - ![Inj3ct0r](https://github.com/UchaCTF/WriteUps/tree/main/Tr%C3%A1fico%20de%20Red/2023Vishwactf/inj3ct0r) (*Teclado USB*)



