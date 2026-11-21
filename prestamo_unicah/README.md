NOMBRE: Nohelia Patricia Hernandez Rivas
CUENTA: 0805200500402

 Préstamo de equipo en Odoo
 PREGUNTAS Y RESPUESTAS 

 1 ¿Qué pasa con un equipo cuando se desmarca el campo Activo? ¿Por qué es mejor que borrarlo?

Cuando se desmarca el campo Activo, el equipo queda archivado y deja de mostrarse en las vistas normales, pero sigue guardado en la base de datos. Es mejor que borrarlo porque se conserva su información y su historial, y se puede volver a activar cuando sea necesario.

2 ¿Para qué sirve copy=False en el campo codigo?

Sirve para evitar que se copie automáticamente el código de inventario cuando se duplica un equipo. Así, el nuevo registro no conserva el mismo código del equipo original, evitando duplicados de identificación.

3 Este modelo usa _name y _inherit al mismo tiempo. ¿Qué hace cada uno aquí?

_name define un modelo nuevo llamado prestamo.prestamo, que sirve para gestionar los préstamos de equipos. _inherit hereda las funciones del modelo mail.thread de Odoo, permitiendo registrar mensajes y realizar el seguimiento de cambios.

4 ¿Qué hace tracking=True en el campo state?

Permite registrar los cambios que se realizan en el campo state (estado del préstamo) en el historial de seguimiento o chatter de Odoo. Así se puede observar cuándo cambia el estado de un préstamo.
