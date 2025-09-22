# Diseño de la ERD #
He creado las siguientes entidades (copiado de dbdiagram.io - hay un pantallazo adjunto en el repositorio)
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

  # Decisiones PK y FK #
  Indicadas en el código proporcionado arriba  
  # Consultas implementadas y resultados #
  
