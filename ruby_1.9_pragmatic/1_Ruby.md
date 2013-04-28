#Cap 1. Ruby

- habla de la instalación de Ruby desde el código fuente y desde los binarios.

- Asegurarnos de que al hacer un `ruby -v` en consola, devuelve la versión 1.9.

- `irb` (Interactive Ruby) es una shell de Ruby con histórico de comandos, edición de líneas y demás capacidades. Tiene su propio capítulo más adelante.

- Se pueden crear ejecutables como en PHP / bash / etc. poniendo en la primera línea del fichero script `#! /usr/local/bin/ruby -w`, o si el sistema lo permite: `#! /usr/bin/env ruby` busca directamente el PATH de Ruby. Por último habría que dar permisos de ejecución (+x) al fichero.

- la librería standard de Ruby tiene más de 9000 métodos. Utilizar [http://ruby-doc.org](http://ruby-doc.org) como referencia.
- en local, utilizar el comando `ri <Clase:Método>` para ver la documentación:
	
		ri GC:enable	#=> método de clase
		ri Array.assoc	#=> método de instancia
		
		Para que muestre las líneas:
		export RI="--format ansi --width 70"