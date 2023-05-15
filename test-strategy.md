Primero definiríamos las funciones que necesitamos, que aparece, que no aparece y cuales serían las mas importantes para luego ir bajando de categoría las mismas. 

En este caso tenemos que la interfaz muestra 
* El nombre del juego
* Las instrucciones 
* Espacio para escribir el numero 
* El botón para ingresar el numero

------------------------------------------------------------------------------------------------------------------------------------------
Luego de esto vemos que es lo que no funciona de lo que sabemos que debe de aparecer
* No se muestra alerta de que el numero es un decimal
* No aparece el mensaje de El numero es mayor 
* No aparece el mensaje de El numero es menor 
* No aparece mensaje de felicitaciónes 

-----------------------------------------------------------------------------------------------------------------------------------------
Datos necesarios para proceder, Aquí vemos cuales son los no negociables para poder proceder con el script. 
* El numero random se genera correctamente 
* El boton hace el ingreso del numero 
* El script recibe el numero y puede hacer las comparaciónes 
-----------------------------------------------------------------------------------------------------------------------------------------
Descripción de pasos. 

1. Verificamos que el numero random se genere correctamente entre 1 y 100. Para esto revisamos la función. En este caso en Math.random, sin embargo buscando la función vemos que esta nos genera un numero aleatorio entre 0 y 1 por lo tanto tenemos que corregirla. Para esto podemos agregar una función con nombre getRandomIntInclusive, ya que esta nos va a permitir poner nuestros propios limites y no tener que cambiar algunos datos mas como lo haríamos utilizando math.floor. 

2. Al intentar verificar el ingreso del numero por medio del boton y hacer una comparación con el numero random dentro de la consola para observar si todo iba bien hasta el momento, nos encontramos con que tenemos un error en el addeventlistener por lo cual se corrigió. Este era llamado 2 veces en la linea 108 y en la linea 116
  - El error encontrado era que se escribió addeventListener() en lugar de addEventListener()

3. Al corregir este error ya podemos observar que nos sale el mensaje de "Incorrecto" en color verde y la label que nos da el valor de nuestro numero aleatorio anterior. Lo que no podemos ver es el mensaje de mayor o menor por lo cual nos vamos a buscar en donde se ejecuta la comparación y sus derivados, encontramos que en la linea 53 a la const lowOrHi le falta un . antes de low. Al hacer este cambio, ya sale "El numero es mayor" y "El numero es menor"

4. Al hacer la prueba ingresando diferentes numeros encontramos 2 errores mas, el primero es que aún acepta numeros no enteros, por ejemplo 0.2 y el segundo error es que independientemente del numero de intentos al llegar al limite, sale el mensaje de adivinaste el numero! aunque este no sea el correcto. Para arreglar estos errores entonces hacemos lo siguiente 
* Para no dejar que el usuario pueda ingresar un numero decimal, entonces hacemos otro if en donde usamos !Number.isInteger para hacer la verificación. 
* Al buscar el problema del mensaje, se observo que los mensajes estaban cambiados de lugar por lo que se realizo el cambio respectivo. 

5. Al seguir haciendo pruebas se observo que el mensaje Incorrecto! salía en donde deberían aparecer solamente perdistes o felicitaciones por lo que se eliminaron las lineas en donde estaba descrito el mismo y se agrego a las lineas de LoworHi

6. Se observo que el color de fondo del mensaje de felicitaciones era negro por lo cual se cambio a verde

7. Se utilizo parseInt en la linea 80 debido a que no ejecutaba la comparación de manera correcta al ingresar el numero correcto. 


Resumen de errores corregidos. 

1. Linea 47 se agrego getRandomIntInclusive(1, 100) para tener un numero entre 1 y 100 ya que no se estaba generando correctamente. 
2. linea 108 y 116 no se llamaba correctamente el addEventListener, se corrigió cambiando addeventListener por addEventListener. 
3. linea 53 faltaba un punto decimal antes de lowOrHi, se agrego el punto decimal ---> .lowOrHi
4. linea 70 se agrego un if para verificar que el numero fuera entero y no decimal o letra 
5. linea 82 El mensaje debería ser 'Felicitaciones! adivinaste el número!' pero estaba '!!!Pérdistes!!!', se hizo el cambio. 
6. linea 87 El mensaje debería ser '!!!Pérdistes!!!' pero estaba 'Felicitaciones! adivinaste el número!', se realizo el cambio. 
7. linea 83 El color del background era negro, se cambio a verde. 
8. Se elino la linea en donde estaba escrito Incorrecto! ya que usaba el mismo espacio que los 2 mensajes anteriores, se agrego en la linea 92 y 94 
9. Linea 80 se agrego parseInt para que fuera posible realizar la comparación
10. Linea 50 se cambiaron los ATTEMPS a 10. 

