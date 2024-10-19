# PRIMER EJERCICIO

## PASOS

### Paso 1: Configuración del entorno en MongoDB Atlas

1. **Crear una cuenta en MongoDB Atlas:**
   - Si no tienes una cuenta, regístrate en [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. **Crear un Cluster:**

   - Una vez dentro del panel de MongoDB Atlas, selecciona la opción de crear un nuevo cluster (puedes usar la versión gratuita).
   - Configura el cluster con las opciones predeterminadas y espera a que se aprovisione (toma algunos minutos).

3. **Crear una base de datos y colección:**
   - En el menú del cluster, ve a la opción “Collections” y crea una nueva base de datos, por ejemplo: `BibliotecaDB`.
   - Dentro de esta base de datos, crea una nueva colección llamada `Libros`.

### Paso 2: Modelo de datos para los libros

Cada libro en la colección `Libros` tendrá la siguiente estructura:

```json
{
  "titulo": "Nombre del libro",
  "autor": "Nombre del autor",
  "categoria": "Categoría del libro",
  "anioPublicacion": 2024,
  "disponible": true
}
```

### Paso 3: Agregar 11 libros a la colección

Puedes usar el siguiente script para agregar 11 libros a la colección `Libros` desde el shell de MongoDB o desde MongoDB Compass:

```js
db.libros.insertMany([
  {
    titulo: "Cien años de soledad",
    autor: "Gabriel García Márquez",
    categoria: "Novela",
    anioPublicacion: 1967,
    disponible: true,
  },
  {
    titulo: "Don Quijote de la Mancha",
    autor: "Miguel de Cervantes",
    categoria: "Novela",
    anioPublicacion: 1605,
    disponible: true,
  },
  {
    titulo: "El amor en los tiempos del cólera",
    autor: "Gabriel García Márquez",
    categoria: "Novela",
    anioPublicacion: 1985,
    disponible: true,
  },
  {
    titulo: "1984",
    autor: "George Orwell",
    categoria: "Ciencia ficción",
    anioPublicacion: 1949,
    disponible: true,
  },
  {
    titulo: "Fahrenheit 451",
    autor: "Ray Bradbury",
    categoria: "Ciencia ficción",
    anioPublicacion: 1953,
    disponible: true,
  },
  {
    titulo: "Crónica de una muerte anunciada",
    autor: "Gabriel García Márquez",
    categoria: "Novela",
    anioPublicacion: 1981,
    disponible: true,
  },
  {
    titulo: "El Principito",
    autor: "Antoine de Saint-Exupéry",
    categoria: "Fábula",
    anioPublicacion: 1943,
    disponible: true,
  },
  {
    titulo: "Orgullo y prejuicio",
    autor: "Jane Austen",
    categoria: "Novela",
    anioPublicacion: 1813,
    disponible: true,
  },
  {
    titulo: "Matar a un ruiseñor",
    autor: "Harper Lee",
    categoria: "Novela",
    anioPublicacion: 1960,
    disponible: true,
  },
  {
    titulo: "El Hobbit",
    autor: "J.R.R. Tolkien",
    categoria: "Fantasía",
    anioPublicacion: 1937,
    disponible: true,
  },
  {
    titulo: "El señor de los anillos",
    autor: "J.R.R. Tolkien",
    categoria: "Fantasía",
    anioPublicacion: 1954,
    disponible: true,
  },
]);
```

### Paso 4: Eliminar un libro por título

Para eliminar un libro en particular, usa el método `deleteOne` con una query que filtre por el título del libro.

```js
db.libros.deleteOne({ titulo: "El Hobbit" });
```

Esto eliminará el libro titulado "El Hobbit" de la colección.

### Paso 5: Consulta por título

Puedes realizar una consulta para buscar libros por título utilizando el siguiente comando. Este buscará todos los libros cuyo título contenga una coincidencia:

```js
db.libros.find(
  { titulo: /Cien años de soledad/i },
  { titulo: 1, autor: 1, categoria: 1, _id: 0 }
);
```

Este comando busca libros cuyo título incluya "Cien años de soledad" (ignora mayúsculas y minúsculas) y muestra el título, autor y categoría de cada uno.

### Paso 6: Consulta por autor

Para buscar libros por autor, puedes usar el siguiente query. Esto buscará todos los libros de un autor específico:

```js
db.libros.find(
  { autor: "Gabriel García Márquez" },
  { titulo: 1, autor: 1, categoria: 1, _id: 0 }
);
```

Esta consulta devolverá los libros escritos por Gabriel García Márquez y mostrará solo los campos seleccionados (título, autor, categoría).

### Paso 7: Consulta por categoría

Para buscar libros según la categoría, realiza la siguiente consulta. Esto devolverá todos los libros dentro de una categoría específica, como "Ciencia ficción":

```js
db.libros.find(
  { categoria: "Ciencia ficción" },
  { titulo: 1, autor: 1, categoria: 1, _id: 0 }
);
```

Este comando devolverá todos los libros de la categoría de ciencia ficción y mostrará el título, autor y categoría de cada uno.

### Paso 8: Probar las consultas en MongoDB Atlas

Puedes ejecutar las consultas en MongoDB Atlas utilizando MongoDB Compass, el shell de MongoDB o directamente en la consola de MongoDB Atlas. MongoDB Atlas te permite ver tus colecciones, insertar y eliminar documentos, y ejecutar consultas de forma visual.

### Resumen:

1. **Agregar libros:** Utiliza `insertMany` para agregar varios libros a la colección.
2. **Eliminar un libro:** Utiliza `deleteOne` para eliminar un libro por su título.
3. **Buscar por título:** Utiliza `find` con un filtro para títulos.
4. **Buscar por autor:** Utiliza `find` con un filtro para autores.
5. **Buscar por categoría:** Utiliza `find` con un filtro para categorías.
