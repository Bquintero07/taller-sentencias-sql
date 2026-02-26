# taller-sentencias-sql

1. Consultas sobre una tabla (Básicas)
Oficinas: Devuelve un listado con el código de oficina y la ciudad.
Oficinas en España: Devuelve la ciudad y el teléfono de las oficinas de España.
Empleados y Jefes: Nombre, apellidos y email de los empleados cuyo jefe tiene código 7.
El Gran Jefe: Nombre del puesto, nombre, apellidos y email del jefe de la empresa (sin jefe).
No Comerciales: Nombre, apellidos y puesto de empleados que no sean 'Representante Ventas'.
Clientes Nacionales: Nombre de todos los clientes españoles.
Estados de Pedido: Listado de los distintos estados de un pedido (sin repetir).
Pagos 2008: Código de cliente de aquellos que realizaron pagos en 2008 (sin repetidos).
Pedidos Rechazados: Listado de pedidos rechazados en 2009.
Entregas de Enero: Pedidos entregados en el mes de enero de cualquier año.
Paypal 2008: Pagos realizados en 2008 vía Paypal. Ordenar de mayor a menor.
Formas de Pago: Todas las formas de pago en la tabla pago (sin repetidos).
Stock Ornamental: Productos 'Ornamentales' con stock > 100. Ordenar por precio (desc).
Clientes Madrid: Clientes de Madrid cuyo representante tenga código 11 o 30.
2. Consultas Multitabla (JOINs)
Clientes y Representantes: Nombre de cliente y nombre/apellido de su representante.
Pagos realizados: Nombre de clientes con pagos y sus representantes.
Sin Pagos: Nombre de clientes sin pagos realizados y sus representantes.
Localización: Clientes con pagos, sus representantes y la ciudad de su oficina.
Oficinas en Fuenlabrada: Dirección de oficinas con clientes en Fuenlabrada.
Jerarquía:
Empleados junto al nombre de sus jefes.
Empleado, nombre de su jefe y nombre del jefe de su jefe.
Retrasos: Clientes con pedidos no entregados a tiempo (fecha_entrega > fecha_esperada).
Gamas por Cliente: Diferentes gamas de producto compradas por cada cliente.
3. Consultas de Conjuntos (Subconsultas y Outer Joins)
Clientes sin actividad:
Que no han realizado ningún pago.
Que no han realizado ningún pedido.
Que no han realizado ni pagos ni pedidos.
Empleados sin actividad:
Que no tienen una oficina asociada.
Que no tienen un cliente asociado.
Sin cliente asociado + datos de su oficina.
Productos olvidados:
Productos que nunca han aparecido en un pedido.
Mostrar nombre, descripción e imagen de dichos productos.
Casos Avanzados:
Oficinas sin representantes de ventas cuyos clientes compraron 'Frutales'.
Clientes con pedidos pero sin pagos realizados.
Empleados sin clientes y el nombre de su jefe.
4. Agregación y Estadísticas
Personal: ¿Cuántos empleados hay en la compañía?
Países: ¿Cuántos clientes tiene cada país?
Finanzas: ¿Cuál fue el pago medio en 2009?
