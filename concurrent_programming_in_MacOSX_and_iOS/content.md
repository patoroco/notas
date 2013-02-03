##GCD (Grand Central Dispatch)
Todos los métodos de GCD empiezan con *dispatch_*

Diferentes *dispatch_queues*:

* **Main queue:** `dispatch_get_main_queue`
* **Concurrent queues:** `dispatch_get_global_queue`
* **Serial queues:** funcionan como FIFO.  
`dispatch_queue_create` (para crearla)  
`disptch_release` (para liberarla)

####Macros para llamar a las colas
* `DISPATCH_QUEUE_PRIORITY_LOW`
* `DISPATCH_QUEUE_PRIORITY_DEFAULT`
* `DISPATCH_QUEUE_PRIORITY_HIGH`

####Para "despacharlas":
* `dispatch_async` (para bloques)
* `dispatch_async_f` (para funciones de C)
* `dispatch_after` (debug en nanosegundos)
* `dispatch_once` se encarga de ejecutar un bloque únicamente una vez en toda la vida de la aplicación.  
Hay que pasarle un token de tipo *dispatch_once_t*.

####Agrupar tareas
* `dispatch_group_create`
* `dispatch_group_async`
* `dispatch_group_notify`
* `dispatch_release`

