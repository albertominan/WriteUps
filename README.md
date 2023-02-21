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


### Solución

1.1 ¿Cuál es el nombre del equipo?
    
   ``Drivergame``
   
  Abriendo la imagen con autopsy podemos ver en Operating System Information el nombre del equipo.


![Imagen1](https://user-images.githubusercontent.com/117050752/220441200-6bb3ee05-0e32-4657-8efa-1820fa5870c1.png)


1.2 ¿Cuál es el hash de la contraseña del usuario Tanner?

   ``3ec585243c919f4217175e1918e07780``
    
   Nos vamos a la ram con volatility y con el comando
   
   ``python2.7 vol.py -f /home/beto/Downloads/DRIVERGAME-20220212-133941.dmp --profile=Win7SP1x64 hashdump`` 
   
   sacamos el hash del usuario Tanner
   
   
   ![Imagen2](https://user-images.githubusercontent.com/117050752/220443838-5bca3fd1-04a3-48bb-876d-e14ae56f822e.png)
