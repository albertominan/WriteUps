# SanClemente-ForenseWindows
    
   Analisis forense de un equipo windows


### Caso #2

  ![hippo](https://ctfd.iessanclemente.net/files/b4676f992bf6e0e39b40fbcbedf1ce79/mafia_color.gif)
  
## Parte 1

El ex-piloto de carreras John Tanner es ahora un policía infiltrado en la Mafia de Nueva York. Su capo, el señor Castaldi, planea un golpe de forma inminente. Suponemos que el elegido para llevarlo a cabo es el implacable asesino a sueldo Jean Paul, alias “El Francés”, y que, como de costumbre, Tanner conducirá el coche de la huida. Sin embargo, aún no sabemos cuál es el objetivo.

Lo que sí sabemos es que Tanner estuvo manteniendo conversaciones con el Sr. Castaldi a través de una aplicación de chat. Por desgracia, dicha aplicación está cifrada con un mecanismo conocido como Double Ratchet, similar al que usan WhatsApp y sus competidores y, por tanto, no hemos podido intervenir dichas comunicaciones.

Ahora, Tanner está desaparecido y su ordenador está frito, lo cual no es de extrañar, pues medio FBI y parte de la policía metropolitana están sobornados. Por suerte, poco antes del golpe, uno de nuestros técnicos pasó a Tanner un USB con un programa para ejecutar. Dicho programa, llamado DumpIt, sirve para recoger una imagen de memoria del equipo. Cuando nuestros hombres llegaron, el USB estaba en el escondrijo acordado, así que quizás los agentes corruptos del FBI no lo hayan tocado. Como era de esperar, allí había una imagen de memoria con lo último que Tanner ejecutó en el ordenador antes de salir. Además, como habíamos quedado, en la recepción del hotel de enfrente de su apartamento nos dejó una nota en la cual estaba escrito el código hash de la imagen creada: a518111a8f288d94fb4fb0069e36a884e1483f72b51b876303b6c7cfcb945715

## Parte 2

Finalmente unos expertos en hardware han logrado rescatar una imagen del disco de Tanner. Con la nueva información adquirida, podemos sacar algunos datos más de su actividad en los últimos días. Los hashes del archivo son los siguientes:

MD5: 8712a3760e8fc801425309852ee1127a ExamenForense.img

SHA-1: eaa88659a5dd2453527ffee0ccb13447c7223184 ExamenForense.img

SHA-256: e4216bb636648b7a4188aacef3587c64aabfb05aade76b6070b3ce8d66d4568a ExamenForense.img

Evidencias aportadas:

Captura de memoria RAM (DRIVERGAME-20220212-133941.dmp - 2GB).
Imagen disco duro (ExamenForense.img.zip - 7.1GB --> descomprimido 32,0 GB)




# Solución



## 1.1 ¿Cuál es el nombre del equipo?
    
   ``Drivergame``
   
  Abriendo la imagen con autopsy podemos ver en Operating System Information el nombre del equipo.


![Imagen1](https://user-images.githubusercontent.com/117050752/220441200-6bb3ee05-0e32-4657-8efa-1820fa5870c1.png)


## 1.2 ¿Cuál es el hash de la contraseña del usuario Tanner?

   ``3ec585243c919f4217175e1918e07780``
    
   Nos vamos a la ram con volatility y con el comando
   
   ``python2.7 vol.py -f /home/beto/Downloads/DRIVERGAME-20220212-133941.dmp --profile=Win7SP1x64 hashdump`` 
   
   sacamos el hash del usuario Tanner
   
   
   ![Imagen2](https://user-images.githubusercontent.com/117050752/220443838-5bca3fd1-04a3-48bb-876d-e14ae56f822e.png)
   
   
## 1.3 ¿Cuál es la contraseña correspondiente a dicho hash?

  ``abc123.``
  
  Pasamos el hash de nuestro usuario por el crackstation...
  
   ![Imagen3](https://user-images.githubusercontent.com/117050752/220444715-156d4071-0417-4c65-b091-cd2e9c64b645.png)


## 1.4 ¿Según el plugin consoles, ¿en qué dirección de memoria se encuentra la frase en la que Tanner pregunta a quién van a asesinar?

   ``0x192050``
   
   Usamos el comando consoles de volatility y vemos haciendo scroll la pregunta que hace Tanner
   
   ``python2.7 vol.py -f /home/beto/Downloads/DRIVERGAME-20220212-133941.dmp --profile=Win7SP1x64 consoles``
   
   ![Imagen4](https://user-images.githubusercontent.com/117050752/220445726-45880544-0382-475a-aaeb-664d925ffd74.png)


## 1.5 ¿Cómo se llama el archivo de proceso por lotes en el que se lanza la aplicación de chat?

   ``ChatApp2.bat``
   
   En este caso usaremos el comando cmdscan y encontramos nuestra aplicación de chat
   
   ``python2.7 vol.py -f /home/beto/Downloads/DRIVERGAME-20220212-133941.dmp --profile=Win7SP1x64 cmdscan``
   
   ![Imagen5](https://user-images.githubusercontent.com/117050752/220446716-2f23fe45-6381-4091-83e5-2b4e3b9355a9.png)


## 1.6 ¿Cuál es el identificador del proceso que tiene como hijo a una aplicación Java?

   ``Cmd.exe 	2956	Java.exe	4276	2956``
   
   Listamos los procesos con pstree y encontramos nuestro proceso padre e hijo
   
   ``python2.7 vol.py -f /home/beto/Downloads/DRIVERGAME-20220212-133941.dmp --profile=Win7SP1x64 pstree``
   
   ![Imagen6](https://user-images.githubusercontent.com/117050752/220447460-a3cd8061-afa3-42a1-a453-fd5232f1be09.png)


## 1.7 ¿Cuál es el apellido que Castaldi menciona durante la conversación en la que se revela que van a matar al Presidente?

   ``Maddox``
   
   Hacemos un dumpeo del proceso 3412 y luego lo analizamos con el siguiente comando:
   
   ``strings /home/beto/Desktop/3412.dmp -e l | grep "Castaldi" -A 20 -B 20``
   
   ![Imagen7](https://user-images.githubusercontent.com/117050752/220447915-f3f72bf2-38af-48aa-bf09-2c995beff7af.png)


## 1.8 ¿Cuál es el nombre de archivo (incluida la extensión) con la imagen JPG que se abrió un rato antes de que Tanner tuviera que abandonar el equipo?

   ``driver_you_are_the_wheelman.jpg.ink``
   
   Volvemos a autopsy y vemos los Recent Documents asociados a nuestro usuario Tanner
   
   ![Imagen8](https://user-images.githubusercontent.com/117050752/220448568-465d8b5a-e953-4515-abcf-11d296bdc998.png)


## 1.9 ¿Cuál es el identificador de proceso con el que abrió dicha imagen?

   ``2612``
    
   Repasando los procesos con pstree encontramos un proceso derivado de services.exe
   
  ![Imagen9](https://user-images.githubusercontent.com/117050752/220448980-bda95e03-a4f4-4ea2-8afe-cc958c850e2b.png)


## 2.1 ¿Cuál es la versión del SO? (incluida la edición y el service pack si lo hubiera)
    
   ``Windows 7 Professional N Service Pack 1``
    
   Podríamos usar imageinfo de volatility en nuestra imagen pero desde autopsy ya nos dice la versión del sistema
   
   ![Imagen10](https://user-images.githubusercontent.com/117050752/220449790-db34ed1a-8d76-4536-90af-ce50ff9ec796.png)


## 2.3 ¿?
