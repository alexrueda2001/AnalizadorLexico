En esta práctica se nos pedía construir un analizador léxico, para lo cual teníamos total libertad. Para
ello, decidí partir del siguiente supuesto, que he inventado para este trabajo.

“Una nueva Ley Orgánica ha prohibido el envío de publicidad a oficinas de la Administración Pública,
tanto por correo postal como por correo eléctronico. Nos piden crear un detector de SPAM capaz de
identificar publicidad leyendo el asunto del email, que sea capaz de extraer los datos de la empresa
anunciante contenidos en el mensaje para gestionar después las sanciones correspondientes.”

Para probar y mostrar el funcionamiento del analizador léxico, también generé el siguiente fichero de
entrada, donde podemos ver una serie de correos electrónicos (separados por guiones) recibidos por
parte de un trabajador de la oficina. Vemos como hay tanto emails publicitarios, como laborales y
personales: 'correos.txt'

Vemos como en los diferentes emails incluimos direcciones de correo electrónico, teléfonos y enlaces
web. El objetivo del analizador será extraer los datos de los emails publicitarios, pasando por alto los
personales y laborales.

En 'practica2' se puede ver el código del analizador léxico.

Defino expresiones para identificar los datos de una empresa, que serán emails, teléfonos (que pueden ser tanto móviles como fijos)
y enlaces web (que empezarán por el prefijo https:// o www. Además, definimos la expresión regular
SPAM, que es la encargada de identificar palabras clave como “descuentos”, “gratis”, “ofertas”...
También tendremos una expresión fin para identificar la separación entre emails.
A continuación, definimos el comportamiento del programa cuando encuentra alguna de esas expresio-
nes. Para ello utilizamos la variable publi, que pondremos a 1 cuando identifiquemos un correo SPAM.
Si esta variable tiene estado 1 y se identifican otras expresiones (que serán los datos de la empresa
anunciante), se mostrarán por pantalla. Cuando llegamos al final de un correo y leemos guiones, po-
nemos esa variable a 0 para buscar otro posible SPAM.
Por último, ya en el programa principal, vemos como se muestra un mensaje indicando el número de
emails marcados como SPAM recibidos.

En 'resultados' vemos que cumplimos nuestro objetivo.

Vemos como el analizador léxico es capaz de identificar los correos cuyo asunto indica un indicio
de publicidad, guardando los datos de contacto de la empresa anunciante para tramitar después la
correspondiente sanción. Podemos ver como no hace nada con los correos personales y laborales.

