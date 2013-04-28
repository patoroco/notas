#Cap 4. Container, Blocks and Iterators
- *Array* y *hashes* (arrays asociativos o diccionarios).
- Creación con `[…, …]` o `new Array`.
- los índices negativos indican el orden empezando desde el final, por ejemplo `a[-1]` es el elemento final.
- se puede obtener un rango con un par de números:
	
		a[<start>, <count>] = …
	
		a[1, 3] = [<2º elemento>, <3º elemento>, <4º elemento>]
		a[3, 1] = [<4º elemento>]
		
		
		#Rangos
		a = [1, 3, 5, 7, 9]
		
		a[1..3]		#=> [3, 5, 7]	(.. incluye el extremo)
		a[1...3]	#=> [3, 5]		(no incluye el extremo)
		
		#Con índices negativos
		a[-3..-1] = [5, 7, 9]
	
- para las asignaciones, `a[1] = 'bat'`.
- si se añade un índice que no existía, se rellenan los intermedios con `nil`.

		a = [1, 'bat', 'cat', [9, 8], 9]
		a[6] = 99
		a #=> [1, 'bat', 'cat', [9, 8], 9, nil, 99]

- más ejemplos de asignaciones
     
		a = [1, 3, 5, 7, 9]		#=> [1, 3, 5, 7, 9]
		
		a[<start>, <length>] = 'valor'
		
		a[2, 2] = 'cat'			#=> [1, 3, 'cat', 9]
									(se reemplaza todo el rango por 'cat').
		
		a[2,0] = 'dog'			#=> [1, 3, 'dog', 'cat', 9]
									(se inserta 'dog' antes de la posición inicial, sin eliminar ningún elemento).
		
		a[1,1] = [9, 8, 7]		#=> [1, 9, 8, 7, 'dog', 'cat', 9]
									(si en la parte derecha hay un array, éste sustituye la posición por los elementos).
	
		a[0..3] = []			#=> ['dog', 'cat', 9]
									(elimina de la primera a la cuarta posición)
		
		a[5..6] = [99, 98]		#=> ['dog', 'cat', 9, nil, nil, 99, 98]
									(se colocan los números, y coom antes había hueco, se pone nil)
									
<hr />

###Manejo del array:
- array como stack

		stack = []
		stack.push
		stack.pop

- array como FIFO

		queue = []
		queue.shift		#=> añade el elemento a la cima del array
		queue.unshift	#=> elimina el elemento de la cima
	
- primeros *n* elementos del array: `array.first(n)`
- últimos *n* elementos del array: `array.last(n)`