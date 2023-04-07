# OverTheWire
    
## Los wargames de krypton se basan en una serie de retos de criptografía que van desde lo mas básico hasta cierto grado de dificultad pasando de criptografía obsoleta hasta criptogrfía mas moderna.


## Herramientas utilizadas: 

   ### Crypto corner

https://crypto.interactive-maths.com/
   
   ### Asecuritysite
  
  https://asecuritysite.com/coding/freq
   
   ### Boxentriq

https://www.boxentriq.com/
  
  
   ### Dcode
   
https://www.dcode.fr/
  
  
  
  
  
### Krypton 0-1

    El primer nivel se trata de descifrar el texto que nos dan en base64.

  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton0sol.png)



### Krypton 1-2
  
     El segundo nivel se trata de una encriptación en ROT13.
  
  ![](https://github.com/albertominan/WriteUps/blob/772b1204dcb0777f7f001955dd04ee1293eda07c/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton1.png)
    
  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton1sol.png)
  
  

### Krypton 2-3

    El tercer nivel se trata de un cifrado CAESAR.

![](https://github.com/albertominan/WriteUps/blob/772b1204dcb0777f7f001955dd04ee1293eda07c/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton2tit.png)

![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton2.png)

![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton2sol.png)



### Krypton 3-4
    
    El cuarto nivel se trata de cifrado de substitución 
    pero esta vez no nos proporcionan ningun mecanismo de cifrado como en el reto anterior.
  
  ![](https://github.com/albertominan/WriteUps/blob/772b1204dcb0777f7f001955dd04ee1293eda07c/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton3tit.png)
  
  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton3.png)
  
    Valiendome de la herramienta:  https://crypto.interactive-maths.com/frequency-analysis-breaking-the-code.html
    realizamos un análisis de frecuencia del texto.
  
  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton3sol1.png)

    Los ordenamos por TRIGRAPHS y vemos que los más comúnes son "THE" en el alfabeto inglés 
    y en nuestro texto "JDS" así que daremos por hecho que J es T, D es H y S es E.
    
  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton3sol2.png)
  
    Después de varias pruebas substituyendo los resultados de los trigraphs sin éxito me fuí a Jcryptool 
    y pude concluir substituyendo allí de nuevo los trigraphs que fuí sacando añadiendo letras al texto 
    y viendo que tenían sentido pude sacar finalmente la clave.
    
  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton3sol3.png)
  
    Ya solo nos queda usando el comando tr substituir la clave proporcionada con la clave conseguida.
  
  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton3sol4.png)

### Krypton 4-5
  
    El quinto nivel se trata de un cifrado VIGENERE.
  
  ![](https://github.com/albertominan/WriteUps/blob/772b1204dcb0777f7f001955dd04ee1293eda07c/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton4tit.png)
    
  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton4.png)

    Nos dicen que la longitud de la clave es 6.
     
  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton4sol1.png)
  
    Nos vamos a dcode e introducimos el primer texto con la clave conocida HCIKV RJOX 
    la cual nos da la clave que necesitamos para descrifrar el reto "FREKEY".
  
  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton4sol2.png)
    
    Utilizando esta clave sacamos la clave final que es "CLEARTEXT".
    
  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton4sol3.png)

### Krypton 5-6
  
    El sexto nivel se trata de lo mismo que el anterior pero desconocemos la longitud de la clave.
  
  ![](https://github.com/albertominan/WriteUps/blob/772b1204dcb0777f7f001955dd04ee1293eda07c/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton5tit.png)
    
  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton5.png)
  
    Volvemos a usar dcode e introducimos la clave del archivo krypton6 que es "BELOS Z"
    y descubrimos que la clave del texto es "KEYLENGTH".
  
  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton5sol1.png)
     
     Usamos esta clave para descifrar "BELOS Z" y sacamos la clave final "RANDOM".
     
  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton5sol2.png)



### Krypton 6-7
  
    El séptimo y último nivel se trata de un STREAM CIPHER.
  
  ![](https://github.com/albertominan/WriteUps/blob/772b1204dcb0777f7f001955dd04ee1293eda07c/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton6ti.png)
    
  ![](https://github.com/albertominan/WriteUps/blob/21a2eea56521c2b9de1e5792e67d8c4a8b23b23d/Criptograf%C3%ADa/OverTheWire/Krypton/Capturas/krypton1sol.png)



**Autor:** [AlbertoMiñan](https://github.com/albertominan)
