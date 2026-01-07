# Modelo Biblioteca (Diseño conceptual)

## 1. Entidades y atributos

### Libros

- **codigo_libro** (PK)
- titulo
- anio_publicacion
- categoria

### Autores

- **id_autor** (PK)
- nombre
- apellido
- nacionalidad

### Usuarios

- **id_usuario** (PK)
- nombre
- apellido
- fecha_registro

### Prestamos (cabecera)

> Un préstamo pertenece a un único usuario, pero puede incluir varios libros.

- **id_prestamo** (PK)
- **id_usuario** (FK → usuarios.id_usuario)
- fecha_prestamo

### Prestamo_libro (detalle)

> Tabla intermedia préstamo-libro con atributo extra: fecha_devolucion.

- **id_prestamo** (FK → prestamos.id_prestamo)
- **codigo_libro** (FK → libros.codigo_libro)
- fecha_devolucion
- **PK compuesta:** (id_prestamo, codigo_libro)

### Libro_autor (intermedia N:M)

- **codigo_libro** (FK → libros.codigo_libro)
- **id_autor** (FK → autores.id_autor)
- **PK compuesta:** (codigo_libro, id_autor)

---

## 2. Relaciones y cardinalidades

- **Libros ↔ Autores**: N:M  
  Un libro puede tener varios autores y un autor puede tener varios libros → `libro_autor`

- **Usuarios → Prestamos**: 1:N  
  Un usuario puede realizar varios préstamos y cada préstamo pertenece a un único usuario → `prestamos.id_usuario`

- **Prestamos ↔ Libros**: N:M con atributos extra  
  Un préstamo puede incluir varios libros y un libro puede aparecer en múltiples préstamos, registrando fecha_devolucion → `prestamo_libro`

---

## 3. Claves primarias y foráneas

### Primary keys

- libros(codigo_libro)
- autores(id_autor)
- usuarios(id_usuario)
- prestamos(id_prestamo)
- libro_autor(codigo_libro, id_autor)
- prestamo_libro(id_prestamo, codigo_libro)

### Foreign keys

- prestamos.id_usuario → usuarios.id_usuario
- libro_autor.codigo_libro → libros.codigo_libro
- libro_autor.id_autor → autores.id_autor
- prestamo_libro.id_prestamo → prestamos.id_prestamo
- prestamo_libro.codigo_libro → libros.codigo_libro

---

## 4. Diagrama ER en Workbench

Archivos esperados:

- `biblioteca.mwb` (modelo de Workbench)
- `biblioteca_diagrama.png` (export del diagrama)
