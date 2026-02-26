# SOLUCION CONSULTAS SQL

# CONSULTAS BASICAS

1) SELECT codigo_oficina, ciudad FROM oficina;
2) SELECT ciudad, telefono FROM oficina WHERE pais = 'españa';
3) SELECT nombre, CONCAT(apellido1, ' ', apellido2) AS apellidos, email FROM empleado WHERE codigo_jefe = 7;
4) SELECT puesto, nombre, CONCAT(apellido1, ' ',apellido2) AS Apellidos, email FROM empleado WHERE codigo_jefe IS NULL;
5) SELECT nombre, CONCAT(apellido1, ' ',apellido2) AS Apellidos, puesto FROM empleado WHERE NOT puesto = 'Representante Ventas';
6) SELECT nombre_cliente FROM cliente WHERE pais = 'Spain';
7) SELECT DISTINCT(estado) FROM pedido;
8) SELECT DISTINCT(codigo_cliente) FROM pago WHERE YEAR(fecha_pago) = 2008;
9) SELECT * FROM pedido WHERE YEAR(fecha_pedido) = 2009 AND estado = 'Rechazado';
10) SELECT * FROM pedido WHERE MONTH(fecha_entrega) = 01;
11) SELECT * FROM pago WHERE YEAR(fecha_pago) = 2008 AND forma_pago = 'PayPal' ORDER BY ASC;
12) SELECT DISTINCT(forma_pago) FROM pago;
13) SELECT * FROM producto WHERE gama = 'Ornamentales' AND cantidad_en_stock > 100 ORDER BY precio_venta DESC;
14) SELECT * FROM cliente WHERE ciudad = 'Madrid' AND codigo_empleado_rep_ventas IN (11, 30);

# CONSULTAS MULTITABLA JOIN

1) SELECT cl.nombre_cliente, em.nombre , em.apellido1 FROM cliente cl JOIN empleado em ON cl.codigo_empleado_rep_ventas = em.codigo_empleado;
2) SELECT c.nombre_cliente, p.total, e.nombre AS representante FROM cliente c JOIN pago p ON c.codigo_client = p.codigo_cliente JOIN empleado e ON c.codigo_empleado_rep_ventas = e.codigo_empleado;
3) SELECT c.nombre_cliente, e.nombre AS representante FROM cliente c JOIN empleado e ON c.codigo_empleado_rep_ventas = e.codigo_empleado LEFT JOIN pago p ON c.codigo_client = p.codigo_cliente WHERE p.codigo_cliente IS NULL;
4) SELECT c.nombre_cliente, p.total, e.nombre AS representante, o.ciudad FROM cliente c JOIN pago p ON c.codigo_client = p.codigo_cliente JOIN empleado e ON c.codigo_empleado_rep_ventas = e.codigo_empleado JOIN oficina o ON e.codigo_oficina = o.codigo_oficina;
5) SELECT DISTINCT o.linea_direccion1, o.linea_direccion2, c.nombre_cliente FROM oficina o JOIN empleado e ON o.codigo_oficina = e.codigo_oficina JOIN cliente c ON e.codigo_empleado = c.codigo_empleado_rep_ventas WHERE c.ciudad = 'Fuenlabrada';
6) SELECT e.nombre AS empleado, j1.nombre AS jefe FROM empleado e LEFT JOIN empleado j1 ON e.codigo_jefe = j1.codigo_empleado;
   SELECT e.nombre AS empleado, j1.nombre AS jefe, j2.nombre AS gran_jefe FROM empleado e LEFT JOIN empleado j1 ON e.codigo_jefe = j1.codigo_empleado LEFT JOIN empleado j2 ON j1.codigo_jefe = j2.codigo_empleado;
7) SELECT c.nombre_cliente, p.codigo_pedido, p.fecha_esperada, p.fecha_entrega FROM cliente c JOIN pedido p ON c.codigo_client = p.codigo_cliente WHERE p.fecha_entrega > p.fecha_esperada;
8) SELECT DISTINCT c.nombre_cliente, pr.gama FROM cliente c JOIN pedido p ON c.codigo_client = p.codigo_cliente JOIN detalle_pedido dp ON p.codigo_pedido = dp.codigo_pedido JOIN producto pr ON dp.codigo_producto = pr.codigo_producto;

# CONSULTAS DE CONJUNTOS SUBCONSULTAS Y OUTER JOINS

1) SELECT c.nombre_cliente FROM cliente c LEFT JOIN pago p ON c.codigo_cliente = p.codigo_cliente WHERE p.codigo_cliente IS NULL;
2) SELECT e.nombre, e.apellido1 FROM empleado e LEFT JOIN cliente c ON e.codigo_empleado = c.codigo_empleado_rep_ventas WHERE c.codigo_cliente IS NULL;
3) SELECT p.nombre, p.descripcion FROM producto p LEFT JOIN detalle_pedido dp ON p.codigo_producto = dp.codigo_producto WHERE dp.codigo_producto IS NULL;

# AGREGACION Y ESTADISTICAS

1) SELECT COUNT() AS total_empleados FROM empleado;
2) SELECT país, COUNT() AS total_clientes FROM cliente GROUP BY país;
3) SELECT AVG(total) AS promedio_pago FROM pago WHERE YEAR(fecha_pago) = 2009;
