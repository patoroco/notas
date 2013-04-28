#Cap 2. Ruby.new
- Constructor standard, new: `song.new('Título')`.
- `puts` imprime una cadena por pantalla con salto de línea final.
- no hace falta poner `;` al final de las sentencias.
- no se definen las variables locales, se usan (similar a PHP).
- los comentarios se colocan con `#`.
- aconsejan utilizar identación de 2 caracteres.
- métodos definidos con `def <nombre> (<parametros>)`.
- no se usan las llaves para los métodos, simplemente se pone `end`.
- si se utilizan comillas dobles, se interpreta el contenido: `"cadena #{nombre}"`.
- el valor devuelto por un método es el de la última expresión evaluada, por lo que se puede evitar el `return` si se quiere.


##Convenciones en Ruby
El primer caracter de un nombre indica cómo es usado:

- **minúscula ó _**: variables locales, parámetros de los métodos y nombres de métodos.
- **$**: variables globales.
- **@**: variables de instancia.
- **@@**: variables de clase.
- **mayúscula**: nombres de clase, nombres de módulo y constantes.


##Array y Hashes

###Arrays
- Los arrays comienzan con el índice 0.

		a = [1, 'cats', 3.14]	==> creación
		a[2] = nil				==> se sustituye 3.14 por nil
		
- El método `inspect` de array devuelve los componentes.
- Para crear un array de palabras se utiliza:
		
		a = %w(ant bee cat dog elk)
		
	Aunque sería lo mismo que hacer:
	
		a = ['ant', 'bee', 'cat', 'dog', 'elk']
		
###Hashes
####Creación
		inst_section = {
			'cello'		=> 'string',
			'clarinete'	=> 'woodwind',
			…
		}
####Acceso
		inst_section['cello']



##Símbolos
Son nombres de constantes que no hay que predeclarar, y que garantizan el ser únicos. **Empiezan con :**.

		NORTH	= 1			=>	:nort
		EAST	= 2			=>	:east
		SOUTH	= 3			=>	:south
		WEST	= 4			=>	:west
		
Se pueden utilizar como claves en los hashes:

		inst_section{
			:cello		=> 'string',
			:clarinet	=> 'woodwind',
			…
		}
		
Y en Ruby 1.9 se puede hacer directamente:
		
		inst_section{
			:cello	:	'string',
			:clarinet:	'woodwind',
			…
		}
		

##Estructuras de control
No se utilizan llaves.

###If / else
		if …
			…
		elseif …
			…
		else
			…
		end

###While
		while …
			…
			…
		end
		
- nil es tratado como false en las condiciones.


###Modificadores de estamentos
	if radiation > 3000
		puts "Danger"
	end
Puede escribirse directamente `puts "Danger" if radiation > 3000`.

	square = 2
	while square < 1000
		square = square * square
	end
Puede escribirse directamente `square = square * square while square < 1000`.


###Expresiones regulares
Operador `=~` para devolver la posición donde se encontraron las coincidencias de expresiones regulares.

	if line =~/Perl | Python/
		puts "Scripting language mentioned: #{line}"
	end
	
###Bloques
Bloque de una línea

	{puts "Hello"}
	
Bloque de varias líneas

	do
		…
		…
	end
	()
	
###Iteradores
	animals = %w(ant bee cat dog)
	animals.each{|animal| puts animal}
	
O más fácil aún

	['cat', 'dog', 'horse'].each{|name| print name, " "}
	
###Reading and 'Riting'
	gets