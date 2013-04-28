#Cap 3. Clases, Objetos y Variables

- `p` imprime una representación del objeto.
- `puts` llama al método to_s, que codemos sobrescribir para tener una mejor representación.

##Accessors

###Getters
Se puede definir un método:

	def isbn
		@isbn	# => variable de instancia
	end
	
O también permite crear *attr_reader*

	class BookInStock
		attr_reader :isbn, :price
		def initialize (isbn, price)
			@isbn = isbn
			@price = Float(price)
		end
	end
	
###Setters
Método

	def price = (new_price)
		@price = new_price
	end

También podemos utilizar el *attr_accessor* dentro de la clase: `attr_accessor :price`.

###Atributos virtuales
Principio de acceso uniforme según Bertrand Meyer.

Métodos que devuelven algo:
	
	def precio_en_centimos
		Integer (price * 100 + 0.5)
	end

O que convierten algo para una variable de instancia
	
	def price_in_cents = (cents)
		@price = cents / 100.0
	end

Y luego se cambiaría con `book.price_in_cents = 3800`.

<hr />

- Para incluir librerías en Ruby:
	
		require 'cvs'
	Para otros ficheros nuestros:
	
		require relative 'book_in_stock'
		
- Para imprimir por la salida de errores:
		
		STDERR. puts <lo_que_sea>
		
###Control de acceso
- **métodos públicos** (`public`): por defecto, excepto initialize.
- **métodos protegidos** (`protected`): accesible por ellos mismos y subclases.
- **métodos privados** (`private`): conocidos como *propios*.

Se pone encima de la definición del método:

	protected
		def método
	end
	
También se puede escribir en la clase todo junto:

	class MyClass
		def metodo 1
			…
		end
		.
		.
		.
		public: metodo1, metodo3
		protected: metodo2
		private: metodo4
	end
	
###Variables
Información del objeto

	objecto.class
	objeto.object_id