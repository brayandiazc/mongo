# Sistema de Gestión de Biblioteca, Productos y Pedidos

Este proyecto tiene como objetivo crear un sistema de gestión utilizando MongoDB Atlas. Incluye la gestión de libros en una biblioteca, productos en una tienda y un sistema de pedidos. Las funcionalidades incluyen agregar, buscar y eliminar registros, así como realizar consultas avanzadas.

## Descripción del proyecto

Este proyecto consiste en tres ejercicios que utilizan MongoDB Atlas para gestionar una biblioteca, productos en una tienda, y un sistema de clientes y pedidos. El propósito es construir una base de datos escalable y funcional, utilizando operaciones CRUD y consultas avanzadas. Este proyecto demuestra cómo interactuar con MongoDB utilizando consultas en `find()`, `insertMany()`, `updateOne()`, `deleteOne()`, y agregaciones.

## Capturas de Pantalla del Proyecto

Incluir capturas de pantalla o imágenes que muestren el proyecto en funcionamiento.

![Home](imagenes/home.png)
Vista de la colección en MongoDB Atlas.

## Prerrequisitos o Dependencias

Para ejecutar este proyecto, necesitarás las siguientes herramientas:

- **Sistema Operativo:** Windows 10 / Ubuntu 20.04
- **Lenguaje de programación:** Node.js (para interactuar con la base de datos si es necesario)
- **Base de Datos:** MongoDB Atlas
- **Herramientas:** MongoDB Compass, MongoDB Shell

## Instalación del Proyecto

Sigue estos pasos para configurar el entorno y el proyecto:

1. **Crear una cuenta en MongoDB Atlas:**
   Regístrate en [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. **Configurar el Cluster:**
   Crea un cluster gratuito y una base de datos con sus respectivas colecciones según las indicaciones de cada ejercicio.

3. **Insertar datos:**
   Utiliza los scripts proporcionados en los pasos de cada ejercicio para insertar los datos necesarios.

## Instrucciones para Ejecutar el Proyecto

1. Abre MongoDB Compass o MongoDB Shell para interactuar con la base de datos.
2. Inserta los datos proporcionados en las colecciones.
3. Ejecuta las consultas necesarias según los ejemplos de cada ejercicio.

## Instrucciones para Cargar los Datos Semilla a la Base de Datos

Cada uno de los ejercicios incluye datos de ejemplo que se pueden cargar utilizando el método `insertMany()`. Puedes copiar y pegar los scripts en MongoDB Compass o el shell de MongoDB para poblar las colecciones.

```bash
# ejemplo de comando para insertar múltiples documentos
db.productos.insertMany([...])
```

## Ejercicio 1: Sistema de Gestión de Biblioteca

### Funcionalidades implementadas:

1. **Agregar libros:** Inserta libros en la colección `Libros`.
2. **Eliminar libros:** Elimina libros por título.
3. **Buscar libros:** Búsquedas por título, autor o categoría.

### Instrucciones:

1. Configura MongoDB Atlas y crea una base de datos llamada `BibliotecaDB`.
2. Inserta libros en la colección `Libros`.
3. Ejecuta consultas para buscar libros por diferentes criterios y eliminar libros cuando sea necesario.

## Ejercicio 2: Sistema de Gestión de Productos

### Funcionalidades implementadas:

1. **Agregar productos:** Inserta productos en la colección `Productos`.
2. **Actualizar productos:** Actualiza información de productos.
3. **Buscar productos:** Consultas por nombre, categoría y rango de precios.
4. **Ordenar productos por precio:** Ordena los productos en función de su precio.

### Instrucciones:

1. Configura MongoDB Atlas y crea una base de datos llamada `Tienda`.
2. Inserta los productos usando `insertMany()`.
3. Realiza las consultas de productos y actualiza la información según sea necesario.

## Ejercicio 3: Sistema de Gestión de Clientes y Pedidos

### Funcionalidades implementadas:

1. **Colecciones:** `Productos`, `Clientes` y `Pedidos`.
2. **Insertar datos:** Registra productos, clientes y pedidos.
3. **Consultas:** Búsquedas de pedidos por cliente y por productos específicos.
4. **Optimización:** Creación de índices para mejorar el rendimiento.

### Instrucciones:

1. Configura MongoDB Atlas y crea las colecciones `Clientes`, `Productos` y `Pedidos`.
2. Inserta clientes, productos y pedidos.
3. Ejecuta consultas de agregación para buscar pedidos y productos asociados.

## Credenciales de Acceso

No se requieren credenciales para este proyecto. La base de datos es pública para fines de desarrollo.

## Autor

- [Brayan Diaz C](https://github.com/brayandiazc)

## Licencia

Este proyecto está bajo la Licencia MIT - ve el archivo [LICENSE.md](LICENSE) para más detalles.

---

⌨️ con ❤️ por [Brayan Diaz C](https://github.com/brayandiazc) 😊
