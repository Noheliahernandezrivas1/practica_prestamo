NOMBRE: Nohelia Patricia Hernandez Rivas
CUENTA: 0805200500402

 Préstamo de equipo en Odoo
 PREGUNTAS Y RESPUESTAS 

 PASO 1

 1 ¿Qué pasa con un equipo cuando se desmarca el campo Activo? ¿Por qué es mejor que borrarlo?

Cuando se desmarca el campo Activo, el equipo queda archivado y deja de mostrarse en las vistas normales, pero sigue guardado en la base de datos. Es mejor que borrarlo porque se conserva su información y su historial, y se puede volver a activar cuando sea necesario.

2 ¿Para qué sirve copy=False en el campo codigo?

Sirve para evitar que se copie automáticamente el código de inventario cuando se duplica un equipo. Así, el nuevo registro no conserva el mismo código del equipo original, evitando duplicados de identificación.

PASO 2

3 Este modelo usa _name y _inherit al mismo tiempo. ¿Qué hace cada uno aquí?

_name define un modelo nuevo llamado prestamo.prestamo, que sirve para gestionar los préstamos de equipos. _inherit hereda las funciones del modelo mail.thread de Odoo, permitiendo registrar mensajes y realizar el seguimiento de cambios.

4 ¿Qué hace tracking=True en el campo state?

Permite registrar los cambios que se realizan en el campo state (estado del préstamo) en el historial de seguimiento o chatter de Odoo. Así se puede observar cuándo cambia el estado de un préstamo.

PASO 3

5 En fields.One2many("prestamo.linea", "prestamo_id"), ¿qué indica cada parámetro?

El primer parámetro, "prestamo.linea", indica el modelo relacionado que contiene las líneas de los equipos del préstamo. El segundo, "prestamo_id", indica el campo que relaciona cada línea con su préstamo.

6 ¿Qué pasa con las líneas cuando se borra un préstamo? ¿Qué parte del código lo define?

Las líneas relacionadas se eliminan automáticamente cuando se borra el préstamo. Esto lo define ondelete="cascade" en el campo prestamo_id del modelo prestamo.linea.

PASO 4

7 Los botones ya se ocultan según el estado. ¿Por qué los métodos vuelven a validar el estado?

Porque ocultar los botones no impide que los métodos se ejecuten por otras vías. La validación protege los datos y evita realizar operaciones no permitidas.

8 ¿Qué hace prestamo.linea_ids.equipo_id.write(...)? ¿Por qué no hace falta un for para cada equipo?

Actualiza el estado de todos los equipos asociados al préstamo a “Prestado”. No hace falta un for porque Odoo permite modificar varios registros al mismo tiempo mediante write().

PASO 5

9 El campo equipo_id ya filtra los equipos disponibles. ¿Por qué hace falta el TODO 5?

Porque el filtro solo muestra los equipos disponibles al seleccionar uno en la interfaz. La validación del TODO 5 comprueba que el equipo siga disponible al momento de realizar el préstamo, evitando prestar un equipo que ya esté prestado.

10 ¿En qué momento se ejecuta un método con @api.constrains? ¿Y la validación de action_prestar?

Un método con @api.constrains se ejecuta cuando se crea o modifica un registro y cambian los campos indicados en el decorador. La validación de action_prestar se ejecuta cuando se llama a ese método, normalmente al presionar el botón Prestar.