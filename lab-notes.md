# Diseño de la ERD #
He creado las siguientes entidades (copiado de dbdiagram.io - hay un pantallazo adjunto en el repositorio)  
<pre>
Table CLIENTES {  
  ID_CLIENTE integer [primary key]  
  NOMBRE_CLIENTE varchar  
  CORREO_CLIENTE varchar  
  PAIS_CLIENTE varchar  
}  
  
Table PRODUCTOS {  
  ID_PRODUCTO integer [primary key]  
  NOMBRE_PRODUCTO varchar  
  CATEGORIA_PRODUCTO varchar  
  PRECIO_PRODUCTO decimal(10,2)  
}  
  
Table PEDIDOS {  
  ID_PEDIDO integer [primary key]  
  FECHA_PEDIDO date  
  ID_CLIENTE integer [ref: > CLIENTES.ID_CLIENTE]  
  ID_PRODUCTO integer [ref: > PRODUCTOS.ID_PRODUCTO]  
  CANTIDAD_PEDIDO integer  
</pre>
  # Decisiones PK y FK #
  Indicadas en el código proporcionado arriba  
  # Consultas y resultados # 
  <pre>
SELECT
  PEDIDOS.ID_PEDIDO,
  CLIENTES.NOMBRE_CLIENTE,
  PRODUCTOS.NOMBRE_PRODUCTO,
  PEDIDOS.CANTIDAD_PEDIDO,
  PRODUCTOS.PRECIO_PRODUCTO,
  (PEDIDOS.CANTIDAD_PEDIDO * PRODUCTOS.PRECIO_PRODUCTO) AS Total
FROM PEDIDOS
JOIN CLIENTES ON PEDIDOS.ID_CLIENTE = CLIENTES.ID_CLIENTE
JOIN PRODUCTOS ON PEDIDOS.ID_PRODUCTO = PRODUCTOS.ID_PRODUCTO
</pre>
<pre>
ID_PEDIDO	NOMBRE_CLIENTE	NOMBRE_PRODUCTO	CANTIDAD_PEDIDO	PRECIO_PRODUCTO	TOTAL
5001	Ana Gómez	Portátil Dell XPS 13	1	1200.00	1200.00
5002	Carlos Pérez	iPhone 13	2	999.99	1999.98
5003	Lucía Díaz	Auriculares Sony WH-1000XM4	1	349.90	349.90
5004	Ana Gómez	Auriculares Sony WH-1000XM4	2	349.90	699.80
</pre>
  # Consultas implementadas y resultados #
  
