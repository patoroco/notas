#Cap 4. Container, Blocks and Iterators
- *Array* y *hashes* (arrays asociativos o diccionarios).
- Creación con `[…, …]` o `new Array`.
- los índices negativos indican el orden empezando desde el final, por ejemplo `a[-1]` es el elemento final.
- se puede pedir un rango con un par de números:
	
		a[<start>, <count>] = …
	
		a[1, 3] = [<2º elemento>, <3º elemento>, <4º elemento>]
		a[3, 1] = [<4º elemento>]
		
		
		#Rangos
		a = [1, 3, 5, 7, 9]
		
		a[1..3]		#=> [3, 5, 7]	(.. incluye el extremo)
		a[1...3]	#=> [3, 5]		(no incluye el extremo)
		
		#Con índices negativos
		a[-3..-1] = [5, 7, 9]
	
