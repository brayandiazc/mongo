# SEGUNDO EJERCICIO

## PASOS

Esta colección llamada "productos" permite almacenar la información de los productos. Cada documento representa un producto individual y contiene campos como "nombre", "categoria", "precio" y "cantidad_disponible". El campo "\_id" se genera automáticamente por MongoDB y sirve como identificador único para cada documento.

### Paso 1: Crear la colección "productos" en MongoDB Atlas

1. **Conéctate a MongoDB Atlas:**

   - Si no tienes una cuenta en MongoDB Atlas, regístrate y crea un cluster gratuito en [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
   - Crea una nueva base de datos llamada `tienda` y una colección llamada `productos`.

2. **Insertar los 10 productos iniciales:**
   Utiliza el siguiente código para insertar 10 productos a tu colección `productos` en MongoDB. Puedes hacerlo desde MongoDB Compass, el shell de MongoDB, o utilizando una conexión con algún lenguaje de programación (ejemplo: Node.js).

```js
db.productos.insertMany([
  {
    nombre: "Camiseta",
    categoria: "Ropa",
    precio: 25.99,
    cantidad_disponible: 100,
  },
  {
    nombre: "Zapatos",
    categoria: "Calzado",
    precio: 59.99,
    cantidad_disponible: 50,
  },
  {
    nombre: "Pantalón",
    categoria: "Ropa",
    precio: 45.5,
    cantidad_disponible: 75,
  },
  {
    nombre: "Gorra",
    categoria: "Accesorios",
    precio: 15.99,
    cantidad_disponible: 30,
  },
  {
    nombre: "Bufanda",
    categoria: "Accesorios",
    precio: 12.5,
    cantidad_disponible: 40,
  },
  {
    nombre: "Reloj",
    categoria: "Joyería",
    precio: 150.0,
    cantidad_disponible: 20,
  },
  {
    nombre: "Sudadera",
    categoria: "Ropa",
    precio: 35.99,
    cantidad_disponible: 60,
  },
  {
    nombre: "Bolso",
    categoria: "Accesorios",
    precio: 89.99,
    cantidad_disponible: 25,
  },
  {
    nombre: "Correa",
    categoria: "Accesorios",
    precio: 29.99,
    cantidad_disponible: 100,
  },
  {
    nombre: "Anillo",
    categoria: "Joyería",
    precio: 199.99,
    cantidad_disponible: 15,
  },
]);
```

### Paso 2: Consultas para buscar productos por nombre, categoría y rango de precios

#### 1. **Buscar productos por nombre:**

```js
db.productos.find(
  { nombre: /Camiseta/i }, // Busca productos cuyo nombre contenga "Camiseta"
  { nombre: 1, categoria: 1, precio: 1, cantidad_disponible: 1, _id: 0 }
);
```

#### 2. **Buscar productos por categoría:**

```js
db.productos.find(
  { categoria: "Accesorios" }, // Busca productos que pertenecen a la categoría "Accesorios"
  { nombre: 1, categoria: 1, precio: 1, cantidad_disponible: 1, _id: 0 }
);
```

#### 3. **Buscar productos por un rango de precios:**

```js
db.productos.find(
  { precio: { $gte: 20, $lte: 50 } }, // Busca productos con un precio entre 20 y 50
  { nombre: 1, categoria: 1, precio: 1, cantidad_disponible: 1, _id: 0 }
);
```

### Paso 3: Consulta para mostrar productos ordenados por precio de forma descendente

```js
db.productos
  .find({}, { nombre: 1, categoria: 1, cantidad_disponible: 1, _id: 0 })
  .sort({ precio: -1 }); // Ordena por precio de mayor a menor
```

### Paso 4: Agregar 3 nuevos productos

Agrega estos tres nuevos productos a la colección:

```js
db.productos.insertMany([
  {
    nombre: "Pulsera",
    categoria: "Joyería",
    precio: 120.0,
    cantidad_disponible: 35,
  },
  {
    nombre: "Cinturón",
    categoria: "Accesorios",
    precio: 32.5,
    cantidad_disponible: 80,
  },
  {
    nombre: "Calcetines",
    categoria: "Ropa",
    precio: 8.99,
    cantidad_disponible: 200,
  },
]);
```

### Paso 5: Actualizar la información de un producto

Para actualizar la información de un producto, por ejemplo, la camiseta, utiliza el siguiente comando:

```js
db.productos.updateOne(
  { nombre: "Camiseta" }, // Busca el producto por su nombre
  {
    $set: { precio: 28.99, cantidad_disponible: 120 }, // Cambia el precio y la cantidad disponible
  }
);
```

### Paso 6: Mostrar productos con cantidad disponible menor a un valor dado

Si quieres mostrar productos que tienen una cantidad disponible menor a un valor dado (por ejemplo, 30 unidades), puedes ejecutar lo siguiente:

```js
db.productos.find(
  { cantidad_disponible: { $lt: 30 } }, // Busca productos con cantidad menor a 30
  { nombre: 1, cantidad_disponible: 1, _id: 0 }
);
```

### Resumen de los pasos:

1. **Agregar productos:** Utiliza `insertMany()` para insertar varios productos a la vez.
2. **Buscar productos por nombre, categoría y rango de precios:** Utiliza `find()` con los criterios correspondientes.
3. **Mostrar productos ordenados por precio:** Utiliza `sort()` para ordenar los productos por su precio de forma descendente.
4. **Agregar más productos:** Utiliza `insertMany()` para agregar más productos a la colección.
5. **Actualizar un producto:** Utiliza `updateOne()` para modificar los detalles de un producto.
6. **Consulta por cantidad disponible:** Utiliza `find()` para buscar productos con una cantidad disponible menor a un valor dado.
