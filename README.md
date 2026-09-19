# SQL Select Fundamentals — TechStore

## ¿Por qué es mala práctica usar SELECT * en producción?

Porque empeora el rendimiento de la consulta, ya que trae todas las columnas de la tabla, incluso las que no vas a usar. En una tabla con pocas filas como `sales` no se nota, pero en una tabla real con millones de registros y decenas de columnas, traer datos de más hace que la consulta sea más lenta y consuma más memoria innecesariamente.
Escribir el nombre de cada columna que necesitás deja en claro, para cualquiera que lea el código después, exactamente qué datos se están usando.

## ¿Por qué son importantes los alias para un stakeholder no técnico?

Porque el equipo de finanzas no tiene por qué conocer los nombres técnicos de las columnas de la base de datos, y esos nombres muchas veces no son intuitivos fuera del contexto técnico.
Por ejemplo, la columna `total_amount` le dice poco a alguien de finanzas a primera vista. Al escribir `total_amount AS monto_total`, el resultado de la consulta muestra directamente la columna llamada `monto_total`, en español y con un nombre que cualquier persona del área entiende sin tener que preguntar qué significa `total_amount`. Lo mismo pasa con `order_date AS fecha_pedido`: en vez de mostrar `order_date`, el reporte queda con una columna que dice `fecha_pedido`, lista para pegar en un informe sin necesidad de "traducir" nada después.
